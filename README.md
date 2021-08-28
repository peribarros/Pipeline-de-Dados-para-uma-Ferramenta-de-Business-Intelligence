# Pipeline-de-dados-para-uma-ferramenta-de-Business-Intelligency
Extração de dados de dois bancos de dados, sendo um no formato .csv e o outros em postgres, e salvos no disco local na data atual. Criação de um novo arquivo de dados a partir daquelas fontes e enviado para um banco de dados Postgres na nuvem. Após isso, integrar este novo arquivo com um dashboard no Google Data Studio.

![image psd (3)](https://user-images.githubusercontent.com/71424123/131224466-40a087c9-b5b2-4d4a-ae0b-cab64cf95866.png)

# Fontes de Dados
O arquivo northwind.sql está no localhost e o arquivo order_details.csv no google sheets (link da planilha: https://cutt.ly/DWpS1Vs).
Esquema do banco de dados dados northwind.sql:

![image psd (6)](https://user-images.githubusercontent.com/71424123/131224442-28f30a5c-56ce-4f89-a694-57725ae48c62.png)


# Pastas e Subpastas
pipeline/data/postgres/{tabela}/2021-01-01/arquivo.sql <br>
pipeline/data/postgres/{tabela}/2021-01-02/arquivo.sql <br>
pipeline/data/csv/2021-01-02/arquivo.csv

# Etapa 2
A consulta com a orders.sql (pedidos) e order_details.csv (detalhes adicionais dos pedidos) está como backup local na pasta
pipeline/data/consulta_final.csv e no ElephantSQL: https://www.elephantsql.com.

# Banco de Dados Final

![image psd (1)](https://user-images.githubusercontent.com/71424123/131223028-a215afb4-1b17-43b9-b03e-b51f48243e90.png)

# ElephantSQL > Google Data Studio

![image psd (2)](https://user-images.githubusercontent.com/71424123/131223132-9e79c216-1eaf-4766-80f9-fa5ec6d1f0e3.png)

O arquivo ‘consulta_final.csv’ no ElephantSQL está extraído para o Google Data Studio. Link do dashboard: https://datastudio.google.com/reporting/e7e95d31-9fd9-44f6-b9c8-b1353ce720b5/page/J01YC

# Como conectar Postgres ao Google Data Studio:
Faça login no Data Studio.
No canto superior esquerdo, clique em Criar e selecione Fonte de dados.
Selecione o conector PostgreSQL.
Configure o acesso ao seu banco de dados por meio de uma das opções de conexão (veja abaixo).
Clique em AUTENTICAR.
Você verá uma lista das tabelas nesse banco de dados.
Selecione uma tabela.
Clique em CONECTAR.
Agora você pode acessar todas as colunas da tabela como campos nos seus relatórios.
https://support.google.com/datastudio/answer/7288010?hl=pt-BR#zippy=%2Cneste-artigo

# Para reprocessar e salvar os arquivos em uma outra data nas subpastas 
basta inserir a data desejada em:

ano = '2021' <br>
mes = '09' <br>
dia = '01' <br>
data_hoje = outra_data <br>
outra_data = '{}-{}-{}'.format(ano, mes, dia)


