# Desafio de Engenharia de Dados
## Considerações sobre o desafio
* O prazo padrão para entrega da solução é de 7 dias corridos, contados a partir da data de recebimento do desafio. Caso você precise de mais tempo, entre em contato conosco e fechamos uma nova data para a entrega. Não se preocupe, somos super flexíveis ;)
- Não se preocupe em responder todos os pontos do desafio. Queremos ver até que ponto você consegue se aprofundar :)
 
## Case Study
### Contexto Geral
Nós, da empresa **TupiCrypto**, temos um projeto onde iremos construir uma plataforma para comercializar fotos e cartões postais dos principais pontos turísticos brasileiros como Non-fungible tokens (NFTs). Um NFT é um ativo digital que representa objetos do mundo real, como arte, música, fotos, itens de jogos e vídeos. Eles são comprados e vendidos online, frequentemente com criptomoedas, e são baseados na tecnologia de Blockchain, como Ethereum. Para maiores informações podem visitar esse [link](https://www.forbes.com/advisor/investing/nft-non-fungible-token/). A comercialização dos NFTs está crescendo muito nos ultimos anos e um exemplo de sucesso são os [CryptoPunks](https://www.moneytimes.com.br/o-que-sao-cryptopunks-e-por-que-estao-bombando-no-mundo-artistico-dos-tokens-nfts/), onde um NFT foi vendido por 650 ETH (equivalente a US$ 1,24 milhões de dólares). E nós da TupiCrypto queremos surfar essa onda junto no mercado aqui pelas terras tupiniquins.
 
Você foi convocado pelo líder do time de Analytics para ajudar a coletar algumas informações para a construção de um relatório solicitado pelo CEO da **TupiCrypto**. Nesse relatório será necessário a cotação de duas criptomoedas em específico (Ethereum e Bitcoin) em Doláres (USD), Reais (BRL) e Euro (EUR).
 
## Desafio
### Parte 1 - Relatório do time de Analytics
Devido a urgência do relatório para uma tomada de decisão importante o CEO da **TupiCrypto** solicitou para começar pelo projeto com o squad de Analytics. Para isso, você montou algumas perguntas para que possa conseguir a desenvolver o pipeline de dados:
 
#### Qual o formato da entrega (csv, banco de dados, planilha etc)?
Como é uma análise sazonal, vamos precisar acompanhar essas atualizações diariamente. E a sugestão é que os dados sejam armazenados no BigQuery e que sejam atualizados diariamente às 7h da manhã, horário de brasília (GMT-3). O banco de dados no BigQuery deverá conter informações somente a partir do dia **01-01-2021** até o dia atual.
 
Conforme solicitado pelo squad de Analytics você precisará coletar as informações da cotação de duas criptomoedas em específico (Ethereum e Bitcoin) em Dólares (USD), Reais (BRL) e Euro (EUR). Deve-se coletar os dados através de uma API Gratuita chamada [Coingecko](https://www.coingecko.com/en/api#explore-api).
 
Segue o exemplo da tabela solicitada, o arquivo deve conter exatamente essas colunas oriundas da API.
##### *crypto_currency*
   - id
   - symbol
   - name
   - snapshot_date
   - current_price_usd
   - current_price_eur
   - current_price_brl
   - market_cap_usd
   - market_cap_eur
   - market_cap_brl
 
**ATENÇÃO**
Os dados deverão ser salvos no BigQuery em um projeto que criamos para você, no caso [data-case-study-322621](https://console.cloud.google.com/bigquery?project=data-case-study-322621). Você poderá criar a tabela *crypto_currency* dentro do dataset *analytics_engineer_case*. 
Iremos criar um usuário para você realizar consultas e verificar o que está sendo salvo no BigQuery via interface, esse usuário será criado com o email fornecido por você. Para realizar as operações de inserção no banco você deverá usar uma [Service Account](https://cloud.google.com/iam/docs/understanding-service-accounts), nós iremos compartilhar com você também por email. Por favor, não inclua qualquer credencial, service account ou password no seu repositório.

#### Qual tecnologia usar para realizar o ETL?
Como a **TupiCrypto** ainda não possui nenhuma estrutura definida do stack de dados e devido a urgência da necessidade do relatório você sugeriu que esse pipeline de dados seja feito usando o [Airflow](https://airflow.apache.org/). O Airflow é uma ferramenta de orquestração e monitoramento de workflows, porém na comunidade é usado também como uma ferramenta completa de ETL (orquestração, monitoramento e execução do ETL). Neste [post](https://towardsdatascience.com/getting-started-with-airflow-using-docker-cd8b44dbff98) o autor explora como iniciar com o Airflow e os passos para criar sua primeira DAG, caso seja seu primeiro contato com o Airflow aqui você pode tirar algumas dicas de proximos passos.
 
#### O que deve ser entregue nesta primeira etapa?
O objetivo desta etapa é que você desenvolva uma DAG para executar, scheduling e monitoramento do pipeline de dados. No final, o arquivo contendo o código deverá ser compartilhado no repositório em algum provedor Git de sua escolha como (GitHub, BitBucket etc).
 
1) Desenvolver uma DAG no Airflow para extrair os dados da API, transformar no formato requerido e inserir as informações no banco de dados no BigQuery. Além disso, essa DAG deve-se conter um Crontime para que rode todo dia na hora requisitada. Não se esqueça dos requisitos da tabela explicados acima.
2) Compartilhar o arquivo ou arquivos auxiliares da DAG desenvolvida através de um repositório público em algum provedor Git de sua escolha como (GitHub, BitBucket etc). 

Obs: Sabemos que é relativamente simples e possui N maneiras de realiza-lo, mas não se esqueça que é um momento para você demonstrar as suas skills!
 
**ATENÇÃO - Não compartilhe Credenciais e/ou Service Accounts no repositório.**

### Parte 2 - Análise dos dados
Nesta etapa você irá analisar os dados e criar uma query para que o CEO consiga extrair as informações necessárias para o seu dia a dia. 

Segue o exemplo da tabela solicitada, o arquivo .sql deve gerar exatamente essas colunas.
##### *pricing_analysis*
   - id
   - symbol
   - name
   - snapshot_date
   - current_price_usd
   - price_delta_current_vs_7d
   - price_delta_current_vs_14d
   - market_cap_usd
   - market_cap_delta_current_vs_7d
   - market_cap_current_vs_14d

#### O que deve ser entregue nesta segunda etapa?
O objetivo desta etapa é que você desenvolva um arquivo SQL para consultar os dados que você populou no BigQuery e gerar o resultado solicitado pelo CEO. No final, o arquivo contendo o código deverá ser compartilhado no repositório junto com o código da etapa anterior.