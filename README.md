# FarmTech Solutions — Fase 6

Projeto acadêmico da FIAP, desenvolvido pelo **Grupo 21**, para reconhecer **bananas e garrafas PET em imagens** e comparar três abordagens de visão computacional: YOLO customizada, YOLO padrão e uma CNN treinada do zero.

**Prazo informado pelo grupo: 13/10/2026.** Este repositório reúne a estrutura inicial do trabalho. Os notebooks executados, resultados e vídeo serão adicionados durante a integração das contribuições.

## Equipe e divisão do trabalho

| Integrante | Frente | Responsabilidade |
| --- | --- | --- |
| Lucas Carvalho Cordeiro | 1 | YOLO customizada e integração do notebook final |
| Larissa | 2 | Organização das imagens, marcações e README |
| Elton | 3 | YOLO padrão e comparação das abordagens |
| Matheus | 4 | CNN do zero e montagem do vídeo |

Os nomes completos e RMs dos quatro integrantes serão registrados na identificação do notebook final.

## O que será entregue

- **Entrega 1:** treinamento da YOLO customizada com duas quantidades diferentes de épocas, comparação dos resultados e exemplos de detecção nas imagens de teste.
- **Entrega 2:** execução da YOLO padrão e treinamento da CNN do zero, com comparação de qualidade, facilidade de integração, tempo de treinamento e tempo de inferência.
- **Apresentação:** notebook executado, explicações dos resultados e vídeo não listado no YouTube, com duração máxima de cinco minutos.

A YOLO identifica o objeto e sua posição na imagem. A CNN classifica a imagem. O notebook final explicará essa diferença ao comparar os resultados.

## Imagens e marcações

A base compartilhada está no [Google Drive do grupo](https://drive.google.com/drive/folders/1T-mHMYGu8Nj33VuK808TOb8hT5D6Q5OT). Larissa coordena sua organização e a marcação dos objetos no Make Sense IA. O acesso aos arquivos deve ser conferido por outra pessoa antes da entrega.

As classes próprias são **`0: banana`** e **`1: garrafa_pet`**. A divisão exigida para a base de 80 imagens é:

| Classe | Treino | Validação | Teste | Total |
| --- | ---: | ---: | ---: | ---: |
| Banana | 32 | 4 | 4 | 40 |
| Garrafa PET | 32 | 4 | 4 | 40 |
| **Total** | **64** | **8** | **8** | **80** |

Essa tabela apresenta a divisão prevista. A conferência da versão final utilizada nos experimentos será registrada no notebook. Todas as abordagens devem usar as mesmas imagens em cada conjunto.

A configuração inicial dos caminhos e classes está em [data/dataset.yaml](data/dataset.yaml). As imagens e os pesos dos modelos ficam no Drive.

## Organização do repositório

```text
README.md                 Apresentação e links da entrega
PLANEJAMENTO.md           Plano de trabalho e critérios de revisão
data/dataset.yaml         Caminhos e classes para a YOLO
notebooks/                Contribuições e notebook final executado
docs/figuras/             Gráficos e exemplos de previsões
docs/resultados/          Tabelas e resultados da comparação
```

O [planejamento do grupo](PLANEJAMENTO.md) detalha as quatro frentes. O [guia de notebooks](notebooks/README.md) explica como organizar as contribuições para a integração.

## Como contribuir

1. Use a base final compartilhada por Larissa e preserve a divisão entre treino, validação e teste.
2. Trabalhe no arquivo da sua frente, preservando as saídas da execução e explicando os resultados.
3. Envie a contribuição para este repositório ou para Lucas integrar. Para editar diretamente no GitHub, é necessário ser adicionado como colaborador.
4. Confira os links e a execução completa após a integração.

Para obter uma cópia local:

```bash
git clone https://github.com/lucas-crvlh/fase6-cap1-farmtech.git
```

## Acesso à entrega final

- **Notebook:** será publicado em [notebooks/](notebooks/), com o nome `NomeCompleto_rmXXXXX_pbl_fase6.ipynb`, substituindo nome e RM pela identificação correta.
- **Dados:** [Google Drive do grupo](https://drive.google.com/drive/folders/1T-mHMYGu8Nj33VuK808TOb8hT5D6Q5OT).
- **Vídeo:** o link direto do vídeo não listado será incluído após a publicação.

Antes de enviar no portal, o grupo deve conferir o notebook executado, os nomes e RMs, o acesso aos dados e o conteúdo de cada link. Após a submissão, a versão entregue deve permanecer sem novos commits, conforme o enunciado.
