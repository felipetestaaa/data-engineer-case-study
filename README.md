# Desafio de Engenharia de Dados
## Considerações sobre o desafio
* O prazo padrão para entrega da solução é de 7 dias corridos, contados a partir da data de recebimento do desafio. Caso você precise de mais tempo, entre em contato conosco e fechamos uma nova data para a entrega. Não se preocupe, somos super flexíveis ;)
- Não se preocupe em responder todos os pontos do desafio. Queremos ver até que ponto você consegue se aprofundar :)

## Case Study
### Overview
Nós, da empresa **TupiCrypto**, temos um projeto onde iremos construir uma plataforma para comercializar fotos e cartões postais dos principais pontos turísticos brasileiros como Non-fungible tokens (NFTs). Um NFT é um ativo digital que representa objetos do mundo real, como arte, música, fotos, itens de jogos e vídeos. Eles são comprados e vendidos online, frequentemente com criptomoeda, e são baseados na tecnologia de Blockchain, como Etherium. Para maiores informações podem visitar esse [link](https://www.forbes.com/advisor/investing/nft-non-fungible-token/). A comercialização dos NFTs está crescendo muito nos ultimos anos e um exemplo de sucesso são os [CryptoPunks](https://www.moneytimes.com.br/o-que-sao-cryptopunks-e-por-que-estao-bombando-no-mundo-artistico-dos-tokens-nfts/), onde um NFT foi vendido por 650 ETH (equivalente a US$ 1,24 milhões de dólares). E nós da TupiCrypto queremos surfar essa onda junto no mercado aqui pelas terras tupiniquins.

## Desafio

### Parte 1 - Mão na massa
Nesta etapa, você participará de um projeto juntamente com o squad de Analytics a desenvoler uma análise Ad-Hoc para um relatorio solicitado pelo CEO da **TupiCrypto**. Esse relatório que será gerado pelo squad de Analytics necessitará da cotação de duas criptomoedas em especifico (Ethereum e Bitcoin) em Doláres (USD), Reais (BRL) e Euro (EUR). Para isso, foi sugerida a captura dos dados a partir de uma API Gratuita chamada [Coingecko](https://www.coingecko.com/en/api#explore-api). 

Para te ajudar, segue os requirements para este projeto.

- No final deve-se compartilhar um .CSV contendo exatamente a schema solicitada pelo time de Analytics.
- Esse arquivo deverá conter informações somente a partir do dia **01-01-2021**.
- Segue abaixo a schema solicitada pelo time de Analytics.

#### *Arquivo .CSV a ser construído*
    - id
    - symbol
    - name
    - date
    - current_price_usd
    - current_price_eur
    - current_price_brl

#### O que você deve entregar nesta primeira etapa?
1) Um repositorio público em qualquer provedor Git, como GitHub, BitBucket etc. Contendo o código necessário para executar a tarefa e salvar o arquivo solicitado.

### Parte 2 - Teórica

Desenhar um tech stach de dados completo para receber informações de dados das seguintes schemas e com os seguintes requirements:

Desenho do Stack completo proposto por você que você deverá mostrar a sua solução para o problema proposto. Segue uma imagem exemplo encontrado no [link](https://blog.indicium.tech/aproximando-os-dados-dos-analistas-etl-elt/):
![Exemplo de stack](https://blog.indicium.tech/content/images/2021/05/indicium-blog-exemplo-de-pipeline-de-dados-usando-elt.png)


### Perguntas principais
1) Um Cientista de Dados solicitou uma base no qual quer saber se existe relação entre o preço de um vinho e país. Ele prefere que seja um arquivo csv com 100 amostras aleatoriamente. Como você faria essa operação na arquitetura proposta?
2) No final do ano, um outro Cientista de Dados solicitou melhorar o modelo que foi gerado entre preço e pais, e precisa exatamente o mesmo dataset disponibilizado para a primeira versão. Como na arquitetura proposta isso poderá ocorrer?
3) Um Cientista de Dados solicitou uma forma de verificar se existe a característica de "doçura" (sweetness) do vinho. Como a sua arquitetura disponibiliza a busca de existência e significado de cada informação?
4) Novas APIs complementares foram desenvolvidas para fornecer dados de outras empresas que fornecem NFTs: ano da safra, tipo de uva e nossos Crawlers já estão prontos para concatenar essas informações para os novos itens à coletar, porém os antigos precisam desta informação também. Como você propõe a adição destes dados na Arquitetura Proposta?
5) O excesso de requisições ao data lake está perdendo desempenho gradativamente, aumentando o tempo de resposta. Como você propõe analisar o desempenho? Existe alguma estratégia para escalar?
6) Um requisito primordial é a integridade de todas as informações salvas no data lake. Como você trabalharia com backup e redundância?
7) Temos um apreço muito grande pela qualidade e disponibilidade. Para isso, contamos com algumas métricas para ajudar a nos prevenir e/ou nos alertar sobre problemas. Como metrificar e monitorar as atividades na Arquitetura Proposta?
8) Temos um limite financeiro para investir mensalmente. Considerando Clouds Públicas e utilizando a arquitetura proposta, como poderíamos explorar este cenário financeiramente?
9) Fomos questionados, por uma ação judicial, sobre dados que foram vazados. Como na sua arquitetura vamos proteger a confidencialidade de dados?

### Perguntas Bônus (valem pontos extras)


.....

### Exemplos de Respostas da Parte 2: Teórica


* *cenário:*  “Um Cientista de Dados solicitou uma base no qual quer saber se existe relação entre o preço da Ethereum e Bitcoin. Ele prefere que seja um arquivo csv com 100 amostras aleatoriamente. Como você faria essa operação na arquitetura proposta?”
    * *R:* No modelo proposto com o *Z* esse dataset seria persistido de maneira XYZ e uma aplicação externa poderia se conectar a essa base para executar uma query extraindo a amostra de 100 itens e salva-lo em CSV...

* *cenário:* “No final do ano, um outro Cientista de Dados solicitou melhorar o modelo que foi gerado entre preço e pais, e precisa exatamente o mesmo dataset disponibilizado para a primeira versão. Como na arquitetura proposta isso poderá ocorrer?”
   *  *R:* No modelo proposto com o *Z* o dado bruto ficaria disponível de forma XPTO de forma permanente e incremental, sendo assim possibilita a criação de novos modelos aproveitando...




