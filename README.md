# projeto-semantix-dataengineer

Projeto Final Curso Data Engineer Semantix - COVID

### Ambiente de desenvolvimento

<b>Instalar as Ferramentas</b>
[Docker]('https://docs.docker.com/engine/install)</br>
[docker-compose](https://docs.docker.com/compose/install/)</br>

<b>Base de dados - Covid </b></br>
[Dados](https://mobileapps.saude.gov.br/esus-vepi/files/unAFkcaNDeXajurGB7LChj8SgQYS2ptm/04bd3419b22b9cc5c6efac2c6528100d_HIST_PAINEL_COVIDBR_06jul2021.rar)

### Como utilizar o Projeto

##### 1. Clonar o repositório em sua máquina

##### 2. Subir o Ambiente Big Data através do <i>docker-compose</i>

<i>Dentro da pasta docker execute um dos comandos abaixo:</i>

Ambiente Parcial:
`docker-compose -f docker-compose-parcial.yml up -d`

Ambiente Completo:
`docker-compose -f docker-compose-completo.yml up -d`

##### 3. Copiar o arquivo parquet-hadoop-bundle-1.6.0.rar para o diretório /opt/spark/jars do container

`docker cp parquet-hadoop-bundle-1.6.0.jar jupyter-spark:/opt/spark/jars`

<b>OBS:</b> Arquivo está na pasta <b>docker</b>

##### 4. Copiar a base de dados 4 arquivos csv para dentro do HDFS container namenode ou fazer download diretamento no container atraves do [curl ou wget]

`docker cp [path/arquivo.csv] namenode:/`

<b>OBS:</b> base de dados está dentro da pasta <b>base_dados</b>

- Criar o diretorio do projeto no HDFS
  `hdfs dfs -mkdir -p /user/user/projeto/data/csv`
- Enviar a base de dados para o diretorio do projeto
  `hdfs dfs -put *.csv /user/user/projeto/data/csv/`

##### 5. Executar o Jupyter Notebook

Acessar o localhost:8889
<b>OBS:</b> Arquivo Projeto.ipynb
