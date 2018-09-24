# Appmoove: Teste prático para front-end developer 

## Pré requisitos

- HTML5
- CSS3
- Java Script
- Git


## Desafio

O desafio é realizar o desenvolvimento front-end de uma SPA (Single Page Aplication) de um site fictício, o site exibe informações do valor acionário de cinco empresas de tecnologia, são elas: Apple, Google, Microsoft, Facebook e IBM. O desenvolvimento deve seguir o esboço de [layout](layout.jpg). Os dados necessários para preencher as tiles e os gráficos devem ser requisitados desta [API](#api).


## Instruções

1. Faça o clone deste repositório.
2. Implemente o desafio.
3. Após término envie seu projeto <nome_candidato>.zip no e-mail contato@appmoove.com.br.

    **Atenção: Remova a pasta `node_modules` antes de zipar o projeto.**


### Design 

Quanto ao espaçamento, cores, tipografia, ficará a seu critério, use sua imaginação e proficiência para construir um design agradável, moderno, responsivo e usual.


### Topo

- No topo da página deve estar o título e o menu, ao rolar a página o menu deve ser mantido e apenas o conteúdo do body sofrer rolagem.
- O menu deve conter as três opções e o submenu como no layout.


### Slide

- O slideshow deve funcionar com as cinco imagens contidas [aqui](slide/)


### Tiles

- As tiles devem conter o valor atual de uma ação das cinco empresas de tecnologia.


### Gráfico

- O gráfico deve conter botões na lateral esquerda com o nome das empresas, estes botões alteram os dados do gráfico.
- O gráfico de linhas indicam a oscilação do valor acionário no mercado.
- Na parte superior há um filtro que possibilita escolher por [Today, Last 5 days, This Month], os dados do gráfico devem se adequar de acordo com o filtro.
- Você pode utilizar a biblioteca que quiser para construção dos gráficos (recomendamos a [ECharts](https://ecomfe.github.io/echarts-doc/public/en/index.html)).


### Rodapé 

- O rodapé possui um formulário simples, não é necessário que nenhuma ação ocorra.


## Especificações técnicas

1. A aplicação deve ser construída de forma **responsiva**, utilizando os **breakpoints** abaixo:

    Nome do breakpoint | Largura mínima | Largura mínima
    --- | --- | ---
    phone	| 320px	| Breakpoint para smartphones
    tablet | 768px	 | Breakpoint para tablets
    desktop	 | 1024px	|Breakpoints para desktops
    monitor	| 1280px	 | Breakpoints para desktops grandes

2. Suporte para IE10+, Chrome, Safari, Firefox
3. Utilizar os componentes do Bootstrap para montagem das telas.
4. Não utilizar templates/frameworks (React, Angular ou Vue). Nosso objetivo é testar suas habilidades com HTML/CSS/JS.


## Avaliação

### O que nós esperamos no seu teste 

- HTML5 escrito da maneira mais semântica possível.
- Layout responsivo.
- Utilização adequada do bootstrap.


### O que nós ficaríamos felizes de ver em seu teste

- Utilização de conceitos de UI design e UX design.
- Alguma metodologia para definição e organização do seu código.


### O que nos impressionaria

- Testes unitários.
- Aplicação de animações em css quando possível.


### O que nós não gostaríamos

- Descobrir que não foi você quem fez seu teste.
- Ver commits gigantes, sem mensagens ou com `-m` sem pé nem cabeça.


## O que avaliaremos de seu teste

- Componentização dos componentes Javascript.
- Históricos de commits do git.
- Organização, semântica, estrutura, legibilidade, manutenibilidade, escalabilidade do seu código e suas tomadas de decisões.
- Alcance dos objetivos propostos.


## API

Esta api fornece dados de valores do mercado de ações.
Para o desafio será consultado os valores de cinco empresas de tecnologias: Apple (AAPL), Google(GOGL), Microsoft(MSFT), Facebook(FB), IMB(IBM).

Documentação da API: https://www.alphavantage.co/documentation

- Query
    - function
        - GLOBAL_QUOTE = Dados brutos
        - TIME_SERIES_INTRADAY = Dados do dia
        - TIME_SERIES_DAILY - Dados diários
    - symbol
        - AAPL = Para Apple
        - GOGL = Para google
        - MSFT = Para Microsoft
        - FB = Para Facebook
        - IBM = Para IBM

Para consultar o valor de uma ação de cada empresa: 
- Obter o valor **price** do JSON e exibir na tile.
```
GET https://www.alphavantage.co/query?function=GLOBAL_QUOTE&symbol=AAPL&apikey=UL8W9UXLVG1QZRXW
```

Para consultar o histórico de valores de ações de uma empresa específica no dia de hoje:
```
GET https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=AAPL&interval=5min&apikey=UL8W9UXLVG1QZRXW
```

Para consultar o histórico de valores de ações de uma empresa específica nos últimos 5 dias:
```
GET https://www.alphavantage.co/query?function=TIME_SERIES_DAILY&symbol=AAPL&interval=5min&apikey=UL8W9UXLVG1QZRXW
```
