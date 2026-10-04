# 🏎️ Porsche Sales Analytics Dashboard

Dashboard interativo desenvolvido para responder a perguntas estratégicas de negócio sobre as vendas da Porsche, utilizando um único arquivo HTML com **Tailwind CSS** e **Chart.js**.

📍 **Dashboard On-line:** [Acesse a Dashboard publicada no GitHub Pages](https://dasilvaamos56-tech.github.io/porsche-sales-analytics)

---

## 📌 Perguntas de Negócio Escolhidas

1. **Quais são os modelos mais vendidos da Porsche? (Visão de Produto)**
   * **Por quê:** Identificar quais veículos possuem a maior demanda no mercado brasileiro para orientar decisões de estoque, importação e priorização de showroom.
   * **Visual:** Gráfico de Barras Horizontais.

2. **Como a receita total se distribui por Estado? (Visão Geográfica)**
   * **Por quê:** Mapear a concentração de faturamento regional para direcionar campanhas de marketing localizadas e otimizar a distribuição de concessionárias.
   * **Visual:** Gráfico de Rosca (*Donut Chart*).

3. **Qual é a preferência de método de pagamento do cliente Porsche? (Visão Financeira)**
   * **Por quê:** Entender a proporção transacional entre PIX, Financiamento e Transferência para renegociar taxas de intermediação financeira e otimizar o fluxo de caixa.
   * **Visual:** Gráfico de Pizza (*Pie Chart*).

---

## 🧹 Tratamento e Higienização dos Dados

A base crua passou pelo seguinte fluxo de sanitização antes de ser embarcada na dashboard:
1. **Limpeza de Fórmulas:** Remoção de vínculos dinâmicos e colunas brutas para evitar erros de renderização.
2. **Normalização dos Preços:** Conversão de valores em moeda (`R$`) com pontos e vírgulas para números decimais puros.
3. **Validação das Variáveis:** Padronização dos nomes dos modelos e siglas dos estados (UF).
4. **Embutimento:** Os 100 registros higienizados foram convertidos em uma estrutura de array de objetos JSON no arquivo JavaScript único (`index.html`).

---

## 🤖 Engenharia de Prompt e Processo de Construção

### Abordagem Utilizada:
Desenvolvimento direto via prompt estruturado com lógica em JavaScript puro, Tailwind CSS via CDN e Chart.js.

### Prompt Utilizado:
> "Atue como Desenvolvedor Front-end e Analista de Dados Sênior. Crie uma dashboard interativa em um único arquivo HTML (Single File) com estilo Dark Mode minimalista inspirado na Porsche (tons de preto `#0E0E11` e vermelho `#D5001C`). A página deve conter 3 cards de KPI no topo (Receita Total, Unidades Vendidas, Ticket Médio), 4 filtros dinâmicos (Modelo, Estado, Método de Pagamento e Ano) e 3 gráficos interativos em Chart.js respondendo às perguntas de negócio. Crie a lógica JS para atualizar KPIs e gráficos sem sobrepor instâncias."

### Evolução e Ajustes do Prompt:
- **Ajuste 1:** Adicionada a instrução `chartInstance.destroy()` no script JS para corrigir o bug de sobreposição de gráficos ao alterar os filtros.
- **Ajuste 2:** Inclusão de formatação monetária padrão BRL (`Intl.NumberFormat`) nos cards e tooltips.

