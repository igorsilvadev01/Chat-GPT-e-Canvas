# Porsche Sales Intelligence — Dashboard Interativo

Dashboard de vendas em HTML, CSS e JavaScript, desenvolvido para o desafio da DIO **Criando Agentes de Criação de Dashboards com Excel e Claude Code**.

## Acessar a dashboard

[Abrir Porsche Sales Intelligence](https://igorsilvadev01.github.io/Chat-GPT-e-Canvas/).

## Perguntas de negócio

1. **Quais modelos geram mais receita?** A receita por modelo evidencia quais linhas do portfólio concentram o faturamento.
2. **Como os clientes pagam?** A distribuição das modalidades de pagamento esclarece o perfil das transações.
3. **Onde se concentram as vendas?** O ranking de estados identifica mercados geográficos relevantes.

## Indicadores e funcionalidades

- Vendas registradas, receita em USD, ticket médio e veículos entregues;
- Filtros combináveis por modelo, estado, cidade, ano do veículo e método de pagamento;
- Gráficos e KPIs calculados novamente a cada filtro;
- Busca nos registros e exportação CSV da seleção atual;
- Interface responsiva e HTML único com dados embutidos (não requer servidor ou dependências JavaScript externas).

## Tratamento de dados

Origem: planilha Porsche disponibilizada pela DIO, com 100 registros e campos originais e sanitizados. Somente os campos sanitizados foram incorporados ao HTML: `SaleDateSanitized`, `PorscheModelSanitized`, `ModelYearSanitized`, `SalesPriceSanitized`, `VehicleMileageSanitized`, `PayMethodSanitized`, `CitySanitized`, `StateSanitized` e `DeliveryStatusSanitized`, além do identificador `sale_id`.

Valores de ano, preço e quilometragem foram convertidos para números; datas com `INVALID` foram transformadas em valor nulo e exibidas como “Não informada”, sem imputações. Dados pessoais, como nome do cliente, foram excluídos. A receita é a soma dos preços de venda disponíveis, independentemente do status logístico da entrega.

## Prompt inicial utilizado

> Gere uma dashboard responsiva em um único arquivo `index.html`, utilizando somente dados sanitizados de uma planilha de 100 vendas da Porsche. Apresente total de vendas, receita, ticket médio e entregas. Responda, com gráficos interativos, quais modelos geram mais receita, como os clientes pagam e quais estados concentram mais vendas. Adicione filtros combináveis por modelo, estado, cidade, ano e pagamento. Use identidade visual premium escura com detalhes vermelhos e dourados. O HTML deve funcionar no GitHub Pages sem build.

## Refinamentos feitos

- Acrescentada exportação CSV dos registros filtrados e tabela com busca;
- Tratamento explícito de datas marcadas como inválidas;
- Evitado carregar bibliotecas de gráficos externas: barras e gráfico de rosca são gerados com HTML/CSS/JavaScript;
- Incluída adaptação para telas pequenas e prevenção de inserção de HTML nos valores textuais.

## Ferramentas

ChatGPT para análise e geração do projeto (alternativa ao antigo Canvas); Python e `artifact_tool` para extrair campos sanitizados; HTML/CSS/JavaScript para a dashboard. Não foi usado Claude Code nem um agente autônomo com skill. Esse segundo fluxo pode ser adicionado posteriormente para comparação.

## Publicação

O GitHub Actions publica automaticamente `index.html` no GitHub Pages a cada atualização da branch `main`. O dashboard funciona totalmente no navegador, com dados sanitizados incorporados, filtros, busca e exportação CSV.

## Observação

Projeto educacional, sem afiliação à Porsche AG. Valores monetários estão em USD conforme a planilha original.
