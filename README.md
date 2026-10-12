# FarmTech Solutions — Fase 6 — Grupo 21

Projeto acadêmico da FIAP para reconhecer **bananas e garrafas PET em imagens** e comparar três abordagens de visão computacional: YOLO customizada, YOLO padrão e CNN treinada do zero.

**Prazo informado pelo grupo: 13/10/2026.** A contribuição da YOLO customizada está executada e disponível neste repositório. A entrega completa depende da integração das demais contribuições e do vídeo.

## Acesso às contribuições

| Material | Acesso | Situação neste repositório |
| --- | --- | --- |
| YOLO customizada — Lucas | [Notebook executado](notebooks/LucasCarvalhoCordeiro_rm570388_pbl_fase6.ipynb) · [Abrir no Colab](https://colab.research.google.com/github/lucas-crvlh/fase6-cap1-farmtech/blob/main/notebooks/LucasCarvalhoCordeiro_rm570388_pbl_fase6.ipynb) | Dois experimentos, teste, imagens processadas e conclusões disponíveis |
| Dados e pesos | [Google Drive do grupo](https://drive.google.com/drive/folders/1T-mHMYGu8Nj33VuK808TOb8hT5D6Q5OT) | Base usada na YOLO customizada e resultados preservados |
| Resumo da YOLO para comparação | [Resultados da Frente 1](docs/RESULTADOS_FRENTE1.md) | Métricas, durações, protocolo e caminhos disponíveis |
| YOLO padrão e comparação — Elton | Contribuição ainda não integrada | A incorporar ao notebook consolidado |
| CNN do zero — Matheus | Contribuição ainda não integrada | A incorporar ao notebook consolidado |
| Vídeo demonstrativo | Link ainda não informado | Publicar como não listado no YouTube, com até cinco minutos |

O notebook disponível reúne a **Entrega 1**. O notebook consolidado deverá acrescentar a **Entrega 2**, comparando as três abordagens em qualidade, facilidade de integração, treinamento/customização e inferência. A descrição completa da YOLO customizada está no notebook.

## Equipe

| Integrante | RM | Frente | Responsabilidade |
| --- | --- | --- | --- |
| Lucas Carvalho Cordeiro | 570388 | 1 | YOLO customizada e integração do notebook final |
| Larissa | A confirmar na integração | 2 | Organização das imagens, marcações e README |
| Elton | A confirmar na integração | 3 | YOLO padrão e comparação das abordagens |
| Matheus | A confirmar na integração | 4 | CNN do zero e montagem do vídeo |

A identificação do notebook consolidado deve incluir o nome completo e o RM dos quatro integrantes.

## Base de imagens

As marcações foram preparadas pelo grupo no Make Sense IA. A base conferida antes dos treinamentos contém **80 fotos** e seus arquivos de marcação, identificados no [manifesto](data/manifesto.csv).

| Classe | ID | Treino | Validação | Teste | Total |
| --- | ---: | ---: | ---: | ---: | ---: |
| Banana | 0 | 32 | 4 | 4 | 40 |
| Garrafa PET | 1 | 32 | 4 | 4 | 40 |
| **Total** | | **64** | **8** | **8** | **80** |

As três abordagens devem usar essas mesmas imagens em cada conjunto. YOLO detecta e localiza objetos; a CNN classifica a foto inteira. O notebook explica o critério de classificação por foto usado para apoiar a comparação, mantendo as métricas de detecção separadas.

A configuração dos caminhos está em [data/dataset.yaml](data/dataset.yaml). Fotos originais e pesos permanecem no Drive. Para executar no Colab, adicione a pasta compartilhada a **Meu Drive** e siga a introdução do notebook.

## Organização e integração

- [Notebooks](notebooks/README.md): contribuição publicada e orientações para reunir as demais seções.
- [Resultados da Frente 1](docs/RESULTADOS_FRENTE1.md): resumo para Elton e Matheus usarem na comparação.
- [Figuras da YOLO](docs/figuras/frente1_yolo/): curvas, referências, previsões e matriz de confusão.
- [Arquivos de resultados](docs/resultados/frente1_yolo/): CSVs, JSONs, configurações e registro de inferência.
- [Planejamento inicial](PLANEJAMENTO.md): histórico da divisão de responsabilidades e critérios de revisão.

Cada responsável deve fornecer sua contribuição com código executado, saídas, explicações e os arquivos necessários. Lucas integra o notebook final; Larissa revisa a documentação; Elton reúne a comparação; Matheus monta o vídeo.

Antes da submissão, conferir o notebook consolidado, os nomes e RMs, o acesso aos dados e o conteúdo dos links. O vídeo deve demonstrar a solução funcionando. Após a submissão, manter a versão entregue sem novos commits, conforme o enunciado.
