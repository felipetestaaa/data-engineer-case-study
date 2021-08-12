# Desafio de Engenharia de Dados
## Considerações sobre o desafio
* O prazo padrão para entrega da solução é de 7 dias corridos, contados a partir da data de recebimento do desafio. Caso você precise de mais tempo, entre em contato conosco e fechamos uma nova data para a entrega. Não se preocupe, somos super flexíveis ;)
- Não se preocupe em responder todos os pontos do desafio. Queremos ver até que ponto você consegue se aprofundar :)
 
## Case Study
### Contexto Geral
Nós, da empresa **TupiCrypto**, temos um projeto onde iremos construir uma plataforma para comercializar fotos e cartões postais dos principais pontos turísticos brasileiros como Non-fungible tokens (NFTs). Um NFT é um ativo digital que representa objetos do mundo real, como arte, música, fotos, itens de jogos e vídeos. Eles são comprados e vendidos online, frequentemente com criptomoedas, e são baseados na tecnologia de Blockchain, como Ethereum. Para maiores informações podem visitar esse [link](https://www.forbes.com/advisor/investing/nft-non-fungible-token/). A comercialização dos NFTs está crescendo muito nos ultimos anos e um exemplo de sucesso são os [CryptoPunks](https://www.moneytimes.com.br/o-que-sao-cryptopunks-e-por-que-estao-bombando-no-mundo-artistico-dos-tokens-nfts/), onde um NFT foi vendido por 650 ETH (equivalente a US$ 1,24 milhões de dólares). E nós da TupiCrypto queremos surfar essa onda junto no mercado aqui pelas terras tupiniquins.
 
Você foi convocado pelo líder do time de Analytics para ajudar a coletar algumas informações para a construção de um relatório solicitado pelo CEO da **TupiCrypto**. Nesse relatório será necessário a cotação de duas criptomoedas em específico (Ethereum e Bitcoin) em Doláres (USD), Reais (BRL) e Euro (EUR).
 
Como a empresa ainda é nova, não existe nenhum padrão de conjunto de tecnologias que a empresa utiliza para suas aplicações e projetos (Tech Stack), como um data warehouse, uma ferramenta de ETL etc. Em um papo com o líder de tecnologia você também propôs que juntamente com o projeto da análise Ad-Hoc solicitado pelo squad de Analytics você irá sugerir um stack de dados para a empresa **TupiCryto**.
 
## Desafio
### Parte 1 - Mão na Massa - Relatório do time de Analytics
Devido a urgência do relatório para uma tomada de decisão importante o CEO da **TupiCrypto** solicitou para começar pelo projeto com o squad de Analytics. Para isso, você montou algumas perguntas para que possa conseguir a desenvolver o pipeline de dados:
 
#### Qual o formato da entrega (csv, banco de dados, planilha etc)?
Como é uma análise sazonal, vamos precisar acompanhar essas atualizações diariamente. E a sugestão é que os dados sejam armazenados no BigQuery e que sejam atualizados diariamente às 7h da manhã, horário de brasília (GMT-3). O banco de dados no BigQuery deverá conter informações somente a partir do dia **01-01-2021**.
 
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
 
**ATENÇÃO**
Os dados deverão ser salvos no BigQuery em um projeto que criamos para você, no caso [data-case-study-322621](https://console.cloud.google.com/bigquery?project=data-case-study-322621). Você poderá criar a tabela *crypto_currency* dentro do dataset com seu respectivo nome e sobrenome. 
Iremos criar um usuário para você realizar consultas e verificar o que está sendo salvo no BigQuery via interface, esse usuário será criado com o email fornecido por você. Para realizar as operações de inserção no banco você deverá usar uma [Service Account](https://cloud.google.com/iam/docs/understanding-service-accounts), nós iremos compartilhar com você também por email. Por favor, não inclua qualquer credencial, service account ou password no seu repositório.


#### Qual tecnologia usar para realizar o ETL?
Como a **TupiCrypto** ainda não possui nenhuma estrutura definida do stack de dados e devido a urgência da necessidade do relatório você sugeriu que esse pipeline de dados seja feito usando o [Airflow](https://airflow.apache.org/). O Airflow é uma ferramenta de orquestração e monitoramento de workflows, porém na comunidade é usado também como uma ferramenta completa de ETL (orquestração, monitoramento e execução do ETL). Neste [post](https://towardsdatascience.com/getting-started-with-airflow-using-docker-cd8b44dbff98) o autor explora como iniciar com o Airflow e os passos para criar sua primeira DAG, caso seja seu primeiro contato com o Airflow aqui você pode tirar algumas dicas de proximos passos.
 
#### O que deve ser entregue nesta primeira etapa?
O objetivo desta etapa é que você desenvolva uma DAG para executar, scheduling e monitoramento do pipeline de dados. No final, o arquivo contendo o código deverá ser compartilhado no repositório em algum provedor Git de sua escolha como (GitHub, BitBucket etc).
 
1) Desenvolver uma DAG no Airflow para extrair os dados da API, transformar no formato requerido e inserir as informações no banco de dados no BigQuery. Além disso, essa DAG deve-se conter um Crontime para que rode todo dia na hora requisitada. Não se esqueça dos requisitos da tabela explicados acima.
2) Compartilhar o arquivo ou arquivos auxiliares da DAG desenvolvida através de um repositório público em algum provedor Git de sua escolha como (GitHub, BitBucket etc). 

Obs: Sabemos que é relativamente simples e possui N maneiras de realiza-lo, mas não se esqueça que é um momento para você demonstrar as suas skills!
 
**ATENÇÃO - Não compartilhe Credenciais e/ou Service Accounts no repositório.**
 
### Parte 2 - Teórica
Nesta segunda etapa você deve propor um desenho arquitetural descritivo (tech stack), você terá que apresentar a sua solução proposta bem como as respostas das perguntas e não necessariamente necessita estar no repositorio da Parte 1, poderá ser feito em Slides, Excel, Cartolina o que se sentir mais confortável.

A proposta deve-se contemplar os seguintes cenários:
 
1) Deve ser flexível para coletar dados de diferentes fontes de dados como databases, web applications, arquivos e APIs.
2) Deve-se conter um data warehouse cloud-based (GCP, AWS, Azure) para armazenar as informações.
3) Ferramenta de Transformação usada para limpar dados e aplicar regras de negócio.
4) Ferramenta de visualização para criar reportes e coletar insights.
 
Segue um **exemplo** de uma imagem de um desenho arquitetural descritivo (tech stack). Segue uma imagem exemplo encontrado no [link](https://blog.indicium.tech/aproximando-os-dados-dos-analistas-etl-elt/):

![Exemplo de stack](https://blog.indicium.tech/content/images/2021/05/indicium-blog-exemplo-de-pipeline-de-dados-usando-elt.png)
 
Após a apresentação da solução você deverá responder algumas perguntas:
 
### Perguntas principais
Para a seção de perguntas, lembrando, não se preocupe em responder todos os pontos. Queremos ver até que ponto você consegue se aprofundar :)
 
1) Um Cientista de Dados solicitou uma base no qual quer saber se existe relação entre o preço da Ethereum e Bitcoin. Ele prefere que seja um arquivo csv com 100 amostras aleatoriamente. Como você faria essa operação na arquitetura proposta?
2) No final do ano, um outro Cientista de Dados solicitou melhorar o modelo de machine learning para prever a quantidade de transações (vendas), lembrando que pedidos podem ser cancelados depois de 90 dias, e precisa exatamente o mesmo dataset disponibilizado para a primeira versão. Como na arquitetura proposta isso poderá ocorrer?
3) Uma das regras de negócio foi alterada e pediram para alterar os dados do data warehouse. Como isso poderia ser feito?
4) Os líderes perceberam uma oportunidade no Canadá e pediram para adicionar a cotação do dólar canadense (CAD) no ETL construido na primeira parte. Quais alterações seriam necessárias nos scripts/códigos/conectores e nos bancos de dados?
 
### Perguntas Bônus - Opcionais (valem pontos extras)
1) O excesso de requisições a infraestrutura está perdendo desempenho gradativamente, aumentando o tempo de resposta. Como você propõe analisar o desempenho? Existe alguma estratégia para escalar?
2) Um requisito primordial é a integridade de todas as informações salvas no data lake. Como você trabalharia com backup e redundância?
3) Temos um apreço muito grande pela qualidade e disponibilidade. Para isso, contamos com algumas métricas para ajudar a nos prevenir e/ou nos alertar sobre problemas. Como metrificar e monitorar as atividades na Arquitetura Proposta?
4) Fomos questionados, por uma ação judicial, sobre dados que foram vazados. Como na sua arquitetura vamos proteger a confidencialidade de dados?
5) A empresa **TupiCrypto** está crescendo exponencialmente e com isso diversos times de BI e Analista de dados estão explorando o seu tech stack de dados. Como você facilitaria a descoberta de dados e a documentação?
 
### Exemplos de Respostas da Parte 2: Teórica
* *cenário:*  “Um Cientista de Dados solicitou uma base no qual quer saber se existe relação entre o preço da Ethereum e Bitcoin. Ele prefere que seja um arquivo csv com 100 amostras aleatoriamente. Como você faria essa operação na arquitetura proposta?”
   * *R:* No modelo proposto com o *Z* esse dataset seria persistido de maneira XYZ e uma aplicação externa poderia se conectar a essa base para executar uma query extraindo a amostra de 100 itens e salva-lo em CSV...
 
* *cenário:* “No final do ano, um outro Cientista de Dados solicitou melhorar o modelo de machine learning para prever a quantidade de transações (vendas), lembrando que pedidos podem ser cancelados depois de 90 dias, e precisa exatamente o mesmo dataset disponibilizado para a primeira versão. Como na arquitetura proposta isso poderá ocorrer?”
  *  *R:* No modelo proposto com o *Z* o dado bruto ficaria disponível de forma XPTO de forma permanente e incremental, sendo assim possibilita a criação de novos modelos aproveitando...