# m-data-stack

Descrição do repositório:

O Objetivo desse repositório é criar um pipeline de dados em que pegamos dados públicos do Covid existentes no portal de dados abertos do google e fazer carga em um data warehouse (snowflake).
Utilizaremos o airbyte para fazer o processo de carga, o dbt para fazer as transformações e o metabase para criar um dashboard com as principais informações.


Transformação dos dados:

-> A transformação dos dados será feita através da ferramenta dbt
-> Criaremos uma tabela agregada com os dados que queremos utilizar para montar o dashboard/ fazer nossas análises
-> O dbt exige um repositório para ele, portanto, para encontrar os códigos do dbt devemos olhar no repositório dbt-data-stack
-> O que o dbt faz? Ele pega os dados que estão no banco e trabalhar modelos a partir dessas tabelas de origem (criar um modelo/dataset)
-> Modelo dbt: São as queries em que fazemos as agregações e cálculos que desejamos
-> Criamos um repositório só para o dbt (nome do repositório: dbt-data-stack). Esse repositório é privado por conta dos arquivos de comexão com o banco de dados


Criando rede dos containers:

É importante criar essa rede para que os containers se enxerguem e conversem entre si

docker network ls (criando rede de containers)
docker network create modern-data-stack (criando uma nova rede)
docker network inspect modern-data-stack(comando para verificar o que temos na rede)
docker network connect modern-data-stack airbyte-proxy (adicionando um container na rede modern-data-stack)
