# Plano de trabalho — FarmTech Solutions, Fase 6

> Plano inicial de organização. A situação atual das contribuições está no [README](README.md). Em 12/10/2026, a YOLO customizada foi executada e organizada no repositório; os prazos intermediários abaixo permanecem como registro do planejamento original.

Elaborado em **02/10/2026**. Prazo informado pelo grupo: **13/10/2026**. Meta interna: entregar em **12/10**, após a revisão final. Confirmar no portal o horário oficial; não foi informado no pedido.

Equipe: você, Larissa, Elton e Matheus. Divisão confirmada pelo grupo em **03/10/2026**: você assume a Frente 1; Larissa, a Frente 2; Elton, a Frente 3; Matheus, a Frente 4. O objetivo é cumprir integralmente as duas entregas obrigatórias, com evidências e revisão, buscando a nota máxima; a nota depende da avaliação da FIAP.

## 1. O que aprendemos com a fase 5

**Nota informada e confirmada na imagem: 25,65/27, equivalente a 95%.**

O professor elogiou o notebook executado, a análise exploratória, a clusterização, a investigação de outliers, a comparação dos cinco regressores com validação aninhada e a interpretação honesta da dificuldade de generalização do dendê. Também elogiou a comparação AWS e a distinção entre menor custo e escolha adequada ao cenário.

Dois problemas foram apontados explicitamente:

| Feedback | Medida para a fase 6 | Responsável | Verificação independente |
| --- | --- | --- | --- |
| Links dos vídeos trocados no README | Abrir cada link a partir do README final e verificar o conteúdo, título, duração e identificação da entrega | Frente 2 | Frente 3 |
| Avisos de pendência mantidos após a conclusão, inclusive em `docs/aws` | Revisar README, notebooks e documentos de apoio; atualizar o estado de cada item com base nas evidências | Frente 2 | Frente 1 |

Não foi fornecida uma decomposição do desconto por critério; portanto, não atribuímos os 1,35 pontos perdidos a um item específico.

**Limite da análise do repositório anterior:** a cópia local consultada contém 79 células de notebook, 45 de código, todas com execução registrada e sem saídas de erro salvas. Porém, nela o teste final ainda está desativado e há pendências de publicação. A revisão local de 08/09 também é anterior ao fechamento. O feedback do professor confirma que a versão entregue evoluiu. Esses arquivos ajudam a entender o método de trabalho; não representam integralmente a entrega corrigida. O notebook anterior não foi reexecutado nesta análise.

**Preservar:** separação entre desenvolvimento e teste, comparações justificadas, código executado, conclusões ligadas aos resultados e limitações honestas. **Melhorar:** reservar tempo e responsáveis para conferir a entrega já integrada.

## 2. Escopo que vale nota

Embora a abertura do enunciado seja resumida, o corpo do documento e o barema identificam **as Entregas 1 e 2 como obrigatórias**.

| Entrega | Conteúdo obrigatório |
| --- | --- |
| 1 — YOLO customizada | Duas classes distintas; pelo menos 40 imagens por classe; separação 32/4/4 por classe; Google Drive; rotulação no Make Sense IA; Colab conectado ao Drive; treino, validação e teste explicados; duas experiências com épocas diferentes; comparação e imagens processadas |
| 2 — Comparação de abordagens | Mesma base; YOLO tradicional do capítulo 3; CNN treinada do zero; comparação com a YOLO customizada quanto a facilidade de uso/integração, precisão, tempo de treinamento/customização e tempo de inferência |
| Entrega e apresentação | Novo repositório público do grupo; notebook executado, identificado e acessível; README introdutório com links; vídeo não listado de até cinco minutos; submissão no portal no prazo |

**Proposta:** um notebook final reunindo as duas entregas e um vídeo de até cinco minutos demonstrando ambas. O enunciado não exige explicitamente um segundo vídeo para a Entrega 2, ao contrário do que fazia na fase 5. Conferir eventual orientação complementar do portal.

O arquivo final deve seguir **`NomeCompleto_rmXXXXX_pbl_fase6.ipynb`**. Registrar os quatro nomes completos e RMs no notebook e no README. Confirmar quem será identificado no nome do arquivo consolidado.

**“Ir Além” não vale nota.** Não reservar uma das quatro frentes exclusivamente a extras. Só iniciar um extra se as duas entregas obrigatórias já estiverem executadas, integradas e revisadas até 09/10. Para um eventual extra, a opção com webcam é expressamente admitida nesta fase; a opção de transfer learning também exige fine tuning e a segunda abordagem com segmentação automática, não apenas carregar um modelo pré-treinado.

## 3. Divisão das quatro frentes

### Frente 1 — YOLO customizada e integração técnica

**Responsável: você.**

**Objetivo:** entregar a Entrega 1 funcionando e consolidar as quatro contribuições.

Tarefas:

- Em 02/10, fechar com a Frente 3 a implementação de YOLO usada nos capítulos e o protocolo comum de avaliação. O enunciado cita YOLOv5; confirmar o material antes de fixar a versão.
- Criar o esqueleto do notebook final: identificação, problema, ambiente, dados, treino, validação, teste, comparação e conclusões.
- Preparar Colab com montagem do Drive, instalação das versões testadas e caminhos configuráveis.
- Treinar dois experimentos independentes, por exemplo, **30 e 60 épocas**, partindo dos mesmos pesos iniciais e mantendo as demais configurações iguais. Não fazer o experimento de 60 épocas continuar a partir do de 30.
- Registrar épocas efetivamente executadas; controlar a parada antecipada para que os dois experimentos não acabem idênticos.
- Guardar configuração, curvas de perdas, métricas, tempo, pesos e imagens previstas de cada experimento em pastas identificadas.
- Escolher a configuração pela validação, antes de consultar o teste. Comparar os dois experimentos no teste apenas como avaliação final previamente prevista, sem reajustar o modelo a partir disso.
- Redigir interpretação dos resultados e limites da YOLO customizada; integrar as seções entregues pelos colegas.

**Entregas:** seção executada da YOLO customizada, pesos dos dois experimentos, tabela 30 × 60, previsões e conclusões. Primeira execução funcional até **05/10**; experimentos completos até **07/10**; integração até **09/10**.

**Critério de pronto:** outra pessoa consegue executar a seção com o dataset congelado; as duas experiências são identificáveis e têm saídas; a escolha é justificada pela validação; o teste final está executado, sem trava de desenvolvimento esquecida.

**Revisão:** a Frente 3 confere configurações, comparação e evidências. A Frente 1 coordena a integração; o grupo escolhe quem fará a submissão. Cada integrante entrega sua própria interpretação e evidências.

### Frente 2 — Dataset, rotulação e consistência documental

**Responsável: Larissa.**

**Objetivo:** garantir uma base comum confiável e uma entrega cuja documentação corresponda ao que foi realizado.

Tarefas:

- Coordenar a escolha das duas classes e um guia curto de inclusão de imagens e marcação das caixas.
- Dividir a coleta/rotulação: **cada integrante contribui com 10 imagens de A e 10 de B**, totalizando 80. Revisar qualidade antes de aceitar a contagem; substituir duplicatas ou imagens inadequadas.
- Registrar origem, identificação, classe e sessão/fonte de cada imagem; priorizar imagens próprias ou com condições de uso compatíveis. Não copiar imagens de benchmark conhecidas para o teste da YOLO pré-treinada.
- Separar por classe **32 treino, 4 validação e 4 teste**; manter fotos quase idênticas da mesma sessão no mesmo conjunto.
- Organizar Drive, exportações do Make Sense IA, rótulos e manifesto de divisão. Além do treino exigido no texto, rotular validação e teste para permitir avaliação quantitativa da detecção.
- Verificar imagem/rótulo correspondente, nomes de classes, caixas corretas e ausência de duplicatas entre conjuntos.
- Redigir a seção de dados: aquisição, exemplos, contagens, divisão, qualidade e limitações.
- Manter README introdutório com links corretos para notebook, dados necessários e vídeo; preencher equipe e conferir o nome do notebook.
- Em 11 e 12/10, auditar estados antigos, links e consistência entre documentos e vídeo.

**Entregas:** dataset e manifesto congelados, rótulos, seção de dados, README e checklist documental. Amostra para testar o fluxo até **03/10**; base final até **04/10**; README inicial até **05/10**; revisão final em **11–12/10**.

**Critério de pronto:** 64 imagens de treino, 8 de validação e 8 de teste, com 32/4/4 de cada classe; arquivos conferidos; Drive acessível pela rota documentada; README sem estados incorretos ou links trocados.

**Revisão:** a Frente 4 confere a base e a equivalência dos conjuntos da CNN; a Frente 3 verifica os links finais. A produção das 80 anotações é coletiva, com coordenação da Frente 2.

### Frente 3 — YOLO padrão e comparação das abordagens

**Responsável: Elton.**

**Objetivo:** entregar a referência da Entrega 2 e uma comparação tecnicamente justa.

Tarefas:

- Conferir com a Frente 1 o significado de “YOLO tradicional” no capítulo 3. **Hipótese de planejamento:** detector pré-treinado usado sem customização na base do grupo. Ajustar essa hipótese se o material da disciplina prescrever outra implementação.
- Confirmar, antes da coleta definitiva, que as duas classes escolhidas estão no vocabulário dos pesos dessa referência.
- Implementar inferência e avaliação da YOLO padrão nas mesmas imagens e com mapeamento explícito de classes.
- Definir antes do teste a conversão das detecções em uma classificação por imagem para comparação com a CNN.
- Criar o formato comum de resultados; receber métricas e previsões das outras frentes e gerar as tabelas automaticamente.
- Medir inferência em condições comparáveis e relatar hardware, resolução, lote, repetições e o que entra no tempo.
- Redigir a comparação das quatro dimensões do enunciado, incluindo facilidade de instalação, dependências, dados exigidos e integração.
- Fazer uma execução do notebook final em ambiente limpo e conferir os links do vídeo a partir do README publicado.

**Entregas:** seção executada da YOLO padrão, previsões, tabela comparativa, medições e análise crítica. Protocolo até **03/10**; referência funcional até **05/10**; comparação completa até **08/10**; revisão de execução em **10/10**.

**Critério de pronto:** resultados reproduzíveis para as mesmas imagens; classes corretamente mapeadas; tempos comparáveis; nenhum valor ausente disfarçado de zero; conclusão sustentada pelos números.

**Revisão:** a Frente 1 verifica o protocolo; a Frente 4 confere a comparação com a CNN.

### Frente 4 — CNN do zero e montagem da demonstração

**Responsável: Matheus.**

**Objetivo:** implementar a terceira abordagem obrigatória e demonstrar o funcionamento da solução.

Tarefas:

- Usar o manifesto da Frente 2 para organizar a base de classificação sem gerar uma nova divisão.
- Construir uma CNN pequena com pesos inicializados aleatoriamente, sem backbone pré-treinado. Justificar arquitetura, tamanho de entrada, função de perda e hiperparâmetros.
- Aplicar normalização e aumento de dados apenas onde apropriado; transformações aleatórias ficam no treino. Não multiplicar imagens antes da divisão.
- Treinar, acompanhar treino/validação e selecionar o checkpoint pela validação.
- Exportar curvas, matriz de confusão, métricas por classe, pesos e previsões individuais. Documentar sobreajuste e erros sem esconder resultados ruins.
- Medir tempo de treinamento e fornecer o modelo à rotina comum de inferência definida pela Frente 3.
- Redigir a seção da CNN e ajudar a interpretar as diferenças entre classificação e detecção.
- Montar o vídeo a partir das demonstrações de cada responsável. A Frente 2 organiza roteiro e links; a Frente 1 demonstra YOLO; a Frente 3 explica a comparação; a Frente 4 demonstra CNN e edita.

**Entregas:** seção executada da CNN, pesos, curvas, previsões e conclusões; vídeo final. CNN funcional até **05/10**; resultados até **07/10**; roteiro até **09/10**; gravação em **10/10** e publicação até **11/10**.

**Critério de pronto:** treinamento efetivamente do zero; mesmas imagens nas três abordagens; modelo e resultados salvos; vídeo de até cinco minutos mostrando execução e resultados reais.

**Revisão:** a Frente 1 confere a CNN; a Frente 2 confere roteiro e apresentação; a Frente 3 confere o link e o conteúdo publicado.

## 4. Decisões comuns para não bloquear a equipe

### Cenário e classes

**Escolha confirmada pelo grupo em 04/10/2026: banana e garrafa PET.** A demonstração reconhecerá esses dois tipos de objetos em imagens. As categorias `banana` e `bottle` constam no vocabulário COCO do YOLOv5, o que facilita comparar a rede padrão com a customizada. Na YOLO padrão, a classe `bottle` corresponde a garrafa de forma geral: ela não certifica o material PET. A base própria deve conter garrafas PET; o trabalho avalia o reconhecimento visual dos objetos dessa base. A correspondência deve ser conferida nos pesos realmente usados no capítulo. [Fonte oficial: classes COCO do YOLOv5](https://raw.githubusercontent.com/ultralytics/yolov5/master/data/coco.yaml).

Coletar no mínimo **40 imagens de banana e 40 de garrafa PET**. Cada integrante contribui com 10 imagens de cada objeto, seguindo o padrão coordenado por Larissa. Usar diferentes exemplares, fundos, iluminações, distâncias e ângulos em ambas as classes. Preservar as fotos originais: os retângulos feitos no Make Sense IA devem ser exportados como arquivos de anotação separados, sem desenhá-los permanentemente nas imagens usadas pelo modelo. Congelar e revisar a base antes dos experimentos oficiais. O trabalho é uma demonstração acadêmica.

Usar imagens com **uma única classe de interesse por imagem**, mesmo que haja outros objetos no fundo. Anotar todas as instâncias da classe alvo visíveis conforme a regra de rotulação. Variar fundo, iluminação, distância e ângulo em ambas as classes para reduzir atalhos visuais. Não selecionar apenas exemplos fáceis de teste.

### Contrato de dados e avaliação

| Item | Acordo proposto |
| --- | --- |
| Classes próprias | ID `0`: `banana`; ID `1`: `garrafa_pet`. Na YOLOv5 padrão treinada em COCO, correspondem a `banana` (ID 46) e `bottle` (ID 39); conferir a correspondência no modelo efetivamente usado |
| Manifesto | `image_id`, arquivo, classe, split, origem, grupo de sessão/fonte e hash; um único manifesto para todas as abordagens |
| Divisão | 40 imagens por classe: 32 treino, 4 validação, 4 teste; total 64/8/8 |
| Alterações | Corrigir problemas da base antes do congelamento; se uma correção posterior mudar a base, versionar e refazer as experiências afetadas |
| Seleção | Arquiteturas, épocas, checkpoints e limiares definidos usando treino/validação; teste reservado à avaliação final |
| Reexecução | Reexecutar o protocolo fechado para conferir funcionamento é permitido; usar o resultado de teste para escolher outro modelo compromete a avaliação |
| Artefatos | Identificar versão da base, modelo, seed, configuração, ambiente, pesos e diretório de cada execução |

Oito imagens de teste são poucas: **um erro altera a acurácia global em 12,5 pontos percentuais**, e um erro entre quatro imagens de uma classe altera seu recall em 25 pontos percentuais. Mostrar contagens de acertos/total e tratar conclusões como preliminares, mesmo se houver 100% de acerto. Métricas de detecção não seguem necessariamente esses incrementos, pois dependem das caixas e limiares.

### Como comparar sem misturar tarefas

YOLO localiza e classifica objetos; a CNN aqui classifica a imagem inteira. Portanto, produzir duas leituras:

1. **Detecção — YOLO customizada × padrão:** precision, recall, mAP@0.5 e mAP@0.5:0.95, por classe e no conjunto, com avaliação correta das caixas. As perdas de treino/validação ajudam a interpretar o aprendizado da customizada. [Referência oficial de métricas](https://docs.ultralytics.com/guides/yolo-performance-metrics/).
2. **Classificação por imagem — as três abordagens:** acurácia, taxa de erro, precision/recall/F1 por classe e matriz de confusão. Na YOLO, filtrar para as duas classes e usar a detecção de maior confiança acima de um limiar predefinido; se não houver detecção, registrar “sem detecção” e contar como erro. Não descartar essas imagens do denominador. Registrar empates ou ambiguidades pela regra definida antes do teste.

Não comparar numericamente mAP da YOLO com acurácia da CNN como se fossem a mesma métrica. Não confundir confiança de uma caixa com acurácia. Não comparar valores absolutos das funções de perda de arquiteturas diferentes como prova de superioridade.

Para a referência pré-treinada, reportar tempo de treinamento **“não realizado neste projeto”**; o pré-treinamento externo existiu. Registrar separadamente instalação/carregamento e inferência. Na comparação de inferência, usar o mesmo dispositivo, lote 1, aquecimento e repetições; sincronizar GPU se necessário e informar inclusão de pré/pós-processamento. Se cada arquitetura usar resolução diferente, explicitar essa diferença.

### Arquivos e integração

Proposta de estrutura final, a criar durante o desenvolvimento:

```text
README.md
notebooks/NomeCompleto_rmXXXXX_pbl_fase6.ipynb
data/manifesto.csv
data/dataset.yaml
docs/resultados/             # tabelas e previsões exportadas
docs/figuras/                # curvas, matrizes e testes processados
docs/COMO_REPRODUZIR.md      # somente se não couber no notebook
requirements.txt           # ambiente efetivamente testado
```

Drive: `images/train`, `images/val`, `images/test` e pastas correspondentes em `labels`, além de pesos e resultados preservados. O notebook deve explicar como acessar ou copiar a base para o Drive do avaliador; montar o Drive pessoal de quem corrige não disponibiliza automaticamente os arquivos do grupo.

Para YOLOv5, usar pares imagem/arquivo de caixas, coordenadas normalizadas e configuração das classes. Resultados de treinamento ficam em `runs/train`; as imagens anotadas por inferência são outro artefato, geralmente em `runs/detect`. Guardar ambos e documentar os caminhos reais da versão utilizada. [Guia oficial de treinamento customizado](https://docs.ultralytics.com/yolov5/tutorials/train-custom-data).

Durante o desenvolvimento, cada responsável trabalha em seu notebook de seção, com a mesma configuração de entrada e contrato de saída. A Frente 1 integra o notebook final; evitar que os quatro editem o mesmo `.ipynb` simultaneamente. Cada contribuição precisa chegar com código executado, saídas, explicação, arquivos necessários e instruções de execução.

## 5. Cronograma até 13/10

| Data | Trabalho e marco de conclusão |
| --- | --- |
| **02/10** | Assumir frentes; obter nomes/RMs; conferir capítulo 3, classes e horário do prazo; preparar Drive, repositório e estrutura do notebook |
| **03/10** | Testar fluxo completo com uma amostra; fechar contrato de dados/métricas; coleta e anotações em paralelo |
| **04/10** | Congelar base 64/8/8 e rótulos revisados; todos passam a usar o mesmo manifesto |
| **05/10** | Primeira execução funcional de YOLO customizada, YOLO padrão e CNN; README inicial e acesso ao Drive testado |
| **06–07/10** | Finalizar 30/60 épocas e CNN; validar, fechar escolhas e limiares; executar teste final; exportar resultados |
| **08/10** | Completar comparação das três abordagens, análise de erros, imagens e limitações |
| **09/10** | Integrar notebook; executar candidato completo; revisar conclusões; fechar roteiro do vídeo; decidir se sobra capacidade para algum extra |
| **10/10** | Frente 3 executa em ambiente limpo; Frente 4 revisa base/conjuntos; corrigir problemas e gravar demonstração |
| **11/10** | Publicar vídeo não listado; Frentes 2 e 3 verificam links, conteúdo e duração; Frentes 2 e 1 revisam estados documentais |
| **12/10** | Revisar versão final, acesso público, nome/RM, saídas e artefatos; realizar último commit antes da submissão; submeter e guardar comprovante |
| **13/10** | Margem de contingência se ainda não submetido, respeitando o horário oficial. Se já entregue, conferir comprovante e manter a versão congelada |

Após a submissão, adotar a regra conservadora de **não realizar novos commits** no repositório entregue. O enunciado alerta contra commits após a data de entrega.

Check-in diário curto: cada pessoa informa o que concluiu, fornece o link do artefato e registra bloqueios. Impedimentos com dataset ou acesso à GPU precisam ser comunicados no mesmo dia. Se houver atraso, preservar as duas entregas obrigatórias e retirar extras do caminho crítico.

## 6. Roteiro do vídeo obrigatório

Meta de duração: **4min40s**, deixando margem até cinco minutos.

| Tempo | Conteúdo | Participação sugerida |
| --- | --- | --- |
| 0:00–0:25 | Problema, duas classes e objetivo da demonstração | Frente 2 |
| 0:25–0:55 | Dataset, rotulação e divisão 32/4/4 por classe | Frente 2 |
| 0:55–2:10 | YOLO customizada: executar inferência, mostrar imagens e comparar 30/60 épocas | Frente 1 |
| 2:10–2:50 | YOLO padrão e funcionamento da referência | Frente 3 |
| 2:50–3:30 | CNN do zero, predição e matriz de confusão | Frente 4 |
| 3:30–4:20 | Comparação, erros e limitações | Frente 3, com resultados fornecidos pelas demais |
| 4:20–4:40 | Onde acessar notebook e como reproduzir | Frente 2 |

Mostrar inferência funcionando e resultados reais; não tentar gravar o treinamento completo. Todos fornecem sua demonstração; a montagem fica com a Frente 4. A participação de todos é uma sugestão de organização, não uma exigência explícita do enunciado.

## 7. Checklist para buscar a nota máxima

Os pesos abaixo foram transcritos do barema da fase 6 e somam 10. Não são a escala de 27 pontos mostrada na avaliação da fase 5.

| Critério | Peso | Evidência de conclusão | Responsável principal |
| --- | ---: | --- | --- |
| Repositório | 1,5 | Público, no prazo, notebook no nome exigido e versão congelada | Frente 1 |
| Notebook | 3,0 | Duas entregas completas, código executado, comparações, achados e limitações em Markdown | Todos; integração pela Frente 1 |
| README | 2,0 | Introdução clara, links funcionais de notebook e vídeo, sem duplicar o relatório | Frente 2 |
| Vídeo | 2,0 | Até cinco minutos, não listado, demonstração funcional e link correto | Frente 4; auditoria da Frente 3 |
| Organização | 1,5 | Arquivos identificáveis, leitura clara, estados consistentes e acesso reproduzível | Frente 2; revisão cruzada |

- [ ] Duas classes distintas e divisão exigida comprovadas pelo manifesto.
- [ ] Make Sense IA e Google Drive documentados; rótulos de treino, validação e teste conferidos.
- [ ] YOLO customizada com duas quantidades de épocas e resultados de ambas preservados.
- [ ] YOLO tradicional coerente com o capítulo 3 e comparação com a customizada.
- [ ] CNN treinada do zero, com curvas e avaliação.
- [ ] Comparação de facilidade, precisão, treinamento/customização e inferência.
- [ ] Separação clara entre métricas de detecção e classificação; ausência de detecção contabilizada.
- [ ] Teste final executado, com acertos e erros mostrados e limitações da amostra discutidas.
- [ ] Notebook final executa do início ao fim em ambiente limpo, sem depender de estado oculto.
- [ ] Células de código comentadas, saídas preservadas e interpretações atualizadas.
- [ ] Dataset, pesos e demais arquivos acessíveis pela rota de reprodução documentada.
- [ ] Nome completo/RM no nome do notebook e os quatro integrantes identificados.
- [ ] README, notebook, vídeo e documentos de apoio concordam sobre o que foi concluído.
- [ ] Termos como “pendente”, “não iniciado”, “TODO” e links provisórios foram revisados; limitações reais continuam declaradas.
- [ ] Cada link foi aberto a partir da versão final; vídeo correto, não listado e com duração conferida.
- [ ] Repositório e notebook verificáveis por outra pessoa; dados compartilhados sem depender da conta do autor.
- [ ] Último commit anterior à submissão; comprovante do portal guardado.

## 8. Bases desta proposta

- Enunciados completos das fases 5 e 6 fornecidos pelo grupo.
- Feedback do professor, datado de 18/09/2026 na imagem, e nota 25,65/27; texto também confirmado pelo usuário.
- Cópia local da fase 5: README, planejamento, notebook e registros de revisão/continuidade. Documentos históricos foram usados como evidência do trabalho, não como novas instruções para esta fase.
- Documentação oficial do YOLOv5 e referência de métricas citadas nos pontos técnicos. A definição específica de “YOLO tradicional” ainda depende do capítulo 3, que não foi fornecido.

Este documento é um plano de execução. Não afirma que modelos, dataset, vídeos ou repositório público da fase 6 já tenham sido implementados ou publicados.
