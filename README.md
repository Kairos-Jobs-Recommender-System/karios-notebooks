# Kairos

Este repositório reúne materiais e experimentos de um projeto de recomendação de oportunidades de emprego. Esse diretório aborda o pré-processamento, as métricas e trabalhos futuros com redes neurais em grafos (GNNs) e dados sintéticos.

O conteúdo está organizado principalmente em notebooks Jupyter, acompanhados por bases de dados, resultados de experimentos e documentos de apoio. Não há uma aplicação única com um comando de execução geral: cada notebook tem seu próprio contexto, entradas e dependências.

## Estrutura do repositório

- [`preprocessing/`](preprocessing/) — notebooks de análise e preparação de dados:
  - [`analise-dataset-esco.ipynb`](preprocessing/analise-dataset-esco.ipynb) explora o vocabulário oficial da ESCO, com atenção às competências (*skills*), ocupações e seus relacionamentos.
  - [`preprocessamento-base-oportunidades.ipynb`](preprocessing/preprocessamento-base-oportunidades.ipynb) investiga e transforma dados de vagas do conjunto JobHunAI, incluindo a preparação de registros para associação com a ESCO.
  - [`esco-dataset/`](preprocessing/esco-dataset/) contém arquivos CSV da ESCO em português, como ocupações, competências, hierarquias e relações entre elas.
- [`metrics/`](metrics/) — notebooks de avaliação. [`avaliacao-bootstrap.ipynb`](metrics/avaliacao-bootstrap.ipynb) aplica bootstrap às avaliações e métricas dos motores BM25 e Jaccard para estimar intervalos de confiança e comparar resultados.
- [`future-work/`](future-work/) — experimentos de geração de dados sintéticos e treinamento de GNNs:
  - [`geracao-dados-sinteticos.ipynb`](future-work/geracao-dados-sinteticos.ipynb) explora Copula Gaussiana, redes Bayesianas, CTGAN e TVAE e compara a qualidade dos dados gerados por métricas.
  - [`treinar-gnn.ipynb`](future-work/treinar-gnn.ipynb) integra dados de um grafo no Neo4j com PyTorch Geometric e experimenta GNNs relacionais RGCN e RGAT para gerar representações e previsões.
  - Inclui também arquivos CSV e JSON com dados e métricas associados aos experimentos.
- [`knowledge/`](knowledge/) — textos de referência sobre geração de dados tabulares sintéticos e GNNs, além de um diagrama de explicabilidade.
- [`LICENSE`](LICENSE) — licença do repositório.

## Dados e dependências externas

Os notebooks não são totalmente autocontidos e podem depender de serviços ou arquivos externos:

- Os notebooks de avaliação e geração de dados sintéticos consultam coleções em um MongoDB. O endereço e o banco usados podem variar conforme a configuração presente em cada notebook.
- O treinamento das GNNs depende de um grafo acessível no Neo4j e de bibliotecas como PyTorch Geometric; o notebook descreve as etapas de integração.
- O notebook de pré-processamento de oportunidades espera o arquivo `SDE-Nov21.csv`: [Clique aqui para acessar os dados](https://github.com/coral-lab-asu/job-hunt-AI/tree/main/jobs)
- As células iniciais de cada notebook indicam bibliotecas adicionais e instruções específicas para aquele experimento.

Antes de executar um notebook, confira suas primeiras células, caminhos de entrada e configurações de conexão. Os resultados podem variar conforme os dados e o ambiente utilizados.
