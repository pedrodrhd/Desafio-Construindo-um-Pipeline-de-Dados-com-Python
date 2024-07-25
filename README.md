Desafio Construindo um Pipeline de Dados com Python
Este repositório contém a implementação de um pipeline de dados utilizando Apache Airflow. O objetivo deste projeto é demonstrar a criação e organização de um pipeline de dados completo com camadas distintas de armazenamento e processamento de dados, facilitando a análise e a geração de insights valiosos.

Estrutura do Projeto
O projeto está estruturado da seguinte forma:

desafio-construindo-um-pipeline-de-dados-com-python/
├── dags/
│   └── data_pipeline.py
├── data/
│   ├── bronze/
│   ├── gold/
│   ├── postgres/
│   ├── silver/
│   └── raw_data.csv
├── logs/
│   ├── scheduler/
│   └── webserver/
├── plugins/
├── docker-compose.yaml
└── Dockerfile

Camadas de Armazenamento
Bronze: Armazena os dados brutos carregados no pipeline.
Prata: Contém os dados processados, onde são realizadas operações de limpeza e transformação.
Ouro: Armazena os dados transformados e agregados, prontos para análises avançadas.
Como Executar
Para executar este projeto localmente, siga as instruções abaixo:

Pré-requisitos
Docker
Docker Compose
Passos para Executar
Clone o repositório: git clone https://github.com/seuusuario/desafio-construindo-um-pipeline-de-dados-com-python.git

Navegue até o diretório do projeto: cd desafio-construindo-um-pipeline-de-dados-com-python

Inicie os containers do Docker: docker-compose up -d

Acesse o Airflow no navegador: http://localhost:8080

Ative e execute o DAG data_pipeline:

Na interface do Airflow, ative o DAG data_pipeline.
Inicie a execução manualmente clicando no ícone de "Play".
Funções do Pipeline
upload_raw_data_to_bronze
Carrega os dados brutos para a camada Bronze, preservando a integridade dos dados.

process_bronze_to_silver
Realiza a limpeza dos dados na camada Prata:

Remove registros com campos nulos.
Corrige e-mails inválidos.
Calcula a idade dos usuários.
process_silver_to_gold
Transforma os dados para a camada Ouro:

Agrega os dados por faixa etária e status.
Prepara os dados para análises avançadas.
Estrutura do DAG
O DAG data_pipeline é composto pelas seguintes tarefas:

upload_raw_data_to_bronze: Carrega os dados brutos para a camada Bronze.
process_bronze_to_silver: Limpa e transforma os dados na camada Prata.
process_silver_to_gold: Agrega e prepara os dados na camada Ouro.

Considerações Finais
Este projeto exemplifica a utilização do Apache Airflow para orquestrar pipelines de dados complexos, com múltiplas camadas de processamento e armazenamento. A configuração é feita utilizando Docker para garantir um ambiente consistente e replicável.


