# Viabilidade de filmes

Grandes estúdios internacionais, como Warnes Bros, já apostam em startups que utilizam de **machine learning e inteligência artificial** para ajudar na **tomada de decisão na produção de filmes** prevendo seu possível **sucesso de lançamento**, mas esse tipo de previsibilidade ainda permanece uma ideia a ser desenvolvida no Brasil.

Um dos motivos que **ainda não há** este tipo de ferramenta **aplicada no Brasil** é a falta de pesquisadores no ramo e também temos pouco acesso a esses dados ligados a films produções e suas características que auxiliam no desenvolvimento de um modelo preciso e de possível utilização.

Ao nosso grupo acompanhar o mercado exterior de filmes e essa deficit do mercado brasileiro decidimos por usar da variabilidade nas previsões de aprendizado de máquina como um substituto para o risco podendo ajudar os executivos e produtores do estúdio a **decidir se devem ou não dar a autorização a um projeto de filme**.

Já de cara depois de decidirmos o tema notamos que prever o desempenho de um filme nas bilheterias, se seria uma produção viável ou não, é difícil porque há **muitos fatores envolvidos no sucesso**. Com isso em mente e em busca dos nossos dados, utilizamos de alguns artigos para que pudéssemos entender a **complexidade dos dados**.

Percebemos pela nossa pesquisa que seria essencial no processo termos cuidado ao fazer a **seleção, filtragem, limpeza e junção dos dados**, ja que tínhamos diferentes fontes de dados, e as informações nem sempre concordavam entre elas,o que cria **complexidade na estrutura** e necessita de mais atenção.

Sendo assim pegamos dados do **IMDb, The Numbers**, além de aplicarmos **funções** para criação de novas colunas. A base final que utilizamos em nosso estudo teve a seguinte estrutura:

<table align="left">
    <tr>
        <td><b>Nome da coluna:</b></td>
        <td><b>Significado:</b></td>
    </tr>
    <tr>
        <td>Titulo_ID</td>
        <td>Título do Filme</td>
    </tr>
    <tr>
        <td>Titulo_Tamanho</td>
        <td>Número de caracteres do Título</td>
    </tr>
    <tr>
        <td>TempoDuracao(min)</td>
        <td>Duração do Filme em minutos</td>
    </tr>
    <tr>
        <td>Inicio_Ano</td>
        <td>Ano em que se iniciou a produção do filme</td>
    </tr>
    <tr>
        <td>Inicio_Mes</td>
        <td>Mês em que se iniciou a produção do filme</td>
    </tr>
    <tr>
        <td>GrauInfluencia_Diretor</td>
        <td>Grau de Influência do Diretor</td>
    </tr>
    <tr>
        <td>GrauInfluencia_Ator </td>
        <td>Grau de Influência do Ator</td>
    </tr>
    <tr>
        <td>RestritoParaAdultos</td>
        <td>Se o filme é restrito para adultos</td>
    </tr>
    <tr>
        <td>Genero_Exclusividade</td>
        <td>Quão Exclusivo é o combo de gêneros daquele filme</td>
    </tr>
    <tr>
        <td>Genero_*</td>
        <td>Se o filme faz parte ou não daquele Gênero</td>
    </tr>
    <tr>
        <td>Producao_Orcamento($)</td>
        <td>Qual valor investido na produção do filme</td>
    </tr>
    <tr>
        <td>Bilheteria_Nacional($)</td>
        <td> O valor obtido na bilheteria Nacional</td>
    </tr>
    <tr>
        <td>Bilheteria_Mundial($)</td>
        <td>O valor obtido na bilheteria Mundial, ou seja, Nacional+Internacional</td>
    </tr>
    <tr>
        <td>ROI_Nacional</td>
        <td>O Retorno sobre Investimento Contando apenas a bilheteria Nacional</td>
    </tr>
    <tr>
        <td>ROI_Mundial</td>
        <td>O Retorno sobre Investimento Contando a bilheteria Mundial (total)</td>
    </tr>
    <tr>
        <td>BilheteriaNacional_Importancia(%)</td>
        <td>Quanto a bilheteria nacional representa da bilheteria total</td>
    </tr>
    <tr>
        <td>Producao_Viavel</td>
        <td>Se a produção do filme é viável, ou seja, se o retorno obtido é maior ou igual ao investimento</td>
    </tr>
</table>

Por fim, como já mencionamos antes o objetivo do nosso trabalho é **ajudar os executivos e produtores de estúdio a tomarem a decisão da produção viável ou não** de um filme baseada em **dados concretos e modelos treinados**, queremos proporcionar a essas empresas **maiores lucros, filmes de sucesso e até visão correta do mercado** (melhor gênero, público, período, duração e muito mais) que se inserem, conforme formos ajustando nossas bases e modelos com o tempo. Conforme, criamos em nosso projeto **5 modelos** para que pudéssemos estudar as performance e usabilidade, pensando em modelos baseados em árvore que em teoria performariam melhor com base mais complexas, iremos utilizar a **Árvore de decisão, Floresta aleatória e XGBoost** de regressão para prevermos o número de **ROI do filme**, que é o retorno sobre o investimento em cimado filme, já para os nossos outros modelos não baseados em árvore, teremos **Naive Bayes e SVC** de classificação, prevendo a nossa coluna criada **"Producao_Viavel"** qual a variável binária foi classificada pelo ROI negativo, quando ouve gasto maior que o retorno e a *produção não é viável*, e pelo ROI positivo, que temos algum lucro tornando a *produção viável*.
