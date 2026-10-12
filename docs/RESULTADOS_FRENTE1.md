# Resultados da Frente 1 — YOLO customizada

**Autor:** Lucas Carvalho Cordeiro — RM 570388. **Grupo:** 21. **Execução:** 12/10/2026, Google Colab com GPU Tesla T4.

A contribuição está no [notebook executado](../notebooks/LucasCarvalhoCordeiro_rm570388_pbl_fase6.ipynb). Este resumo fornece os dados necessários para integrar a comparação com a YOLO padrão e a CNN. Os resultados completos e as conclusões estão no notebook.

## Modelo e protocolo

- YOLOv5s ajustada para `0: banana` e `1: garrafa_pet`, a partir dos pesos iniciais pré-treinados `yolov5s.pt`.
- Dois treinamentos independentes de 30 e 60 épocas, com o mesmo conjunto e os mesmos parâmetros explícitos: tamanho configurado 640, lote 16, seed 42, cache em RAM, workers 2, GPU e parada antecipada desativada.
- Base comum: 64 fotos de treino, 8 de validação e 8 de teste; 32/4/4 por classe, conforme o [manifesto](../data/manifesto.csv).
- Escolha pelo maior mAP@50–95 na validação, usando o `best.pt` de cada experimento. O escolhido foi o do treinamento de 60 épocas. O teste foi aplicado ao escolhido após essa decisão.
- Os CSVs de treinamento confirmam 30 linhas com épocas de 0 a 29 e 60 linhas de 0 a 59. `best.pt` pode representar uma época anterior à última.

## Validação dos dois experimentos

| Épocas | Precisão (%) | Recall (%) | mAP@50 (%) | mAP@50–95 (%) | Duração da execução (min) |
| ---: | ---: | ---: | ---: | ---: | ---: |
| 30 | 72,11 | 86,14 | 81,29 | 41,23 | 1,85 |
| 60 | 91,95 | 86,84 | 90,00 | 66,17 | 2,69 |

A duração de execução foi de **111,075986 s** e **161,160705 s**, respectivamente. Inclui o processo de treinamento, validações e gravação dos resultados; exclui o download inicial dos pesos. Não equivale apenas ao tempo de cálculo de treinamento na GPU.

Fontes: [comparação CSV](resultados/frente1_yolo/comparacao_validacao_yolo.csv), [registros de 30 épocas](resultados/frente1_yolo/exp_30_epocas_20261012_194929/) e [registros de 60 épocas](resultados/frente1_yolo/exp_60_epocas_20261012_200853/).

## Teste do modelo escolhido

| Modelo | Precisão (%) | Recall (%) | mAP@50 (%) | mAP@50–95 (%) |
| --- | ---: | ---: | ---: | ---: |
| YOLOv5s — treinamento de 60 épocas, `best.pt` | 90,87 | 72,92 | 83,74 | 55,63 |

Fonte: [CSV do teste](resultados/frente1_yolo/resultado_teste_yolo.csv).

Para a comparação com a CNN, a regra foi: **filtrar as duas classes, escolher a detecção de maior confiança a partir de 0,25 e contar ausência de detecção como erro**. O resultado foi **7/8 fotos corretas = 87,50%**, com **12,50% de erro**. Banana: 4/4; garrafa PET: 3/4. O erro foi `IMG-20261005-WA0044.jpg`, sem detecção.

Fonte: [previsões por foto](resultados/frente1_yolo/exp_60_epocas_20261012_200853/predicoes_por_foto_20261012_210135/acertos_por_foto.csv).

Essa medida avalia a classe da foto; algumas bananas ficaram sem detecção mesmo nas fotos cuja classe foi acertada. Não comparar mAP de detecção com acurácia da CNN como se fossem o mesmo indicador. A CNN deve usar as mesmas oito fotos de teste. A YOLO padrão deve mapear seus IDs reais para as classes correspondentes.

## Tempo de inferência

| Etapa medida por `detect.py` | Média por foto |
| --- | ---: |
| Preparação do tensor | 0,50 ms |
| Cálculo do modelo | 17,30 ms |
| Filtragem de caixas — NMS | 21,40 ms |

**Condições:** Tesla T4, lote 1, FP32 (`half=False`), `imgsz=640`, confiança mínima 0,25, IoU de NMS 0,60, máximo de 300 caixas e classes 0/1. As entradas reais registradas são de 640×480 ou 640×384. A média corresponde a uma execução das oito fotos após o aquecimento interno da rotina.

Os tempos não incluem todo o processo de leitura/redimensionamento, carregamento do modelo e gravação das imagens. A soma das etapas medidas é 39,20 ms, mas não é o tempo completo da aplicação. Para comparar, registrar hardware, resolução, lote e etapas incluídas de cada abordagem. Se houver outro protocolo de medição, apresentá-lo separadamente e explicitar a diferença.

Fontes: [tempos JSON](resultados/frente1_yolo/exp_60_epocas_20261012_200853/predicoes_por_foto_20261012_210135/tempos_inferencia.json) e [registro original](resultados/frente1_yolo/exp_60_epocas_20261012_200853/predicoes_por_foto_20261012_210135/log_inferencia.txt).

## Arquivos no Drive

[Pasta de resultados](https://drive.google.com/drive/folders/1EVA4QXNJNF10vW1OiszZ1bTl0X2RtXU6).

| Material | Link |
| --- | --- |
| Experimento de 30 épocas | [Pasta](https://drive.google.com/drive/folders/1R50y4zJWgg3gn74tfwMUIaH8oE5Wvyd_) |
| Experimento de 60 épocas | [Pasta](https://drive.google.com/drive/folders/1Op-7eRXBngeqHyPpuFWDbvGdGWMSsz-x) |
| Modelo escolhido | [best.pt de 60 épocas](https://drive.google.com/file/d/1cYQePSUJ_-xP7tWWdlYahTBRPNZKhWwc/view) |
| Teste e gráficos | [Pasta](https://drive.google.com/drive/folders/1ANo-hY_xPMw871ta3uPtwawT_aQF7Wbk) |
| Previsões individuais | [Pasta](https://drive.google.com/drive/folders/1HSx6pCi_C-JvG8XUBJrhHJGklT40YTsM) |

Caminho do modelo no Colab:

```text
/content/drive/MyDrive/FIAP_fase6_grupo21/resultados_yolo/exp_60_epocas_20261012_200853/weights/best.pt
```

## Ambiente e limites da revisão

O notebook registra o commit YOLOv5 `f9578796b8a64889aa9e66dc06914d19f40d338e`. O log registra Python `3.13.15` e PyTorch `2.11.0+cu130`. As versões completas das dependências não foram congeladas. Para repetir com o mesmo código, fixar o commit antes da instalação, conforme a orientação no notebook.

A revisão verificou a estrutura do notebook, a sintaxe das 13 células e do script de avaliação, os contadores de execução, a ausência de saídas de erro, as imagens incorporadas e a correspondência entre métricas, CSVs, configurações e tempos no Drive. O código e as saídas originais foram preservados. O treinamento não foi reexecutado localmente.

Os arquivos copiados têm origem e SHA-256 registrados em [origem_dos_arquivos.json](resultados/frente1_yolo/origem_dos_arquivos.json). O manifesto identifica a base conferida antes dos treinamentos; ele não detecta fotos apenas semelhantes nem comprova revisão visual integral das caixas.

A YOLO padrão, a CNN, a comparação completa e o vídeo ainda precisam ser incorporados à entrega do grupo. Também faltam os nomes completos e RMs dos demais integrantes na identificação consolidada.
