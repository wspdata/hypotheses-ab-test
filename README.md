# Loja Online — Priorização de Hipóteses e Análise de Teste A/B

## Descrição do Projeto
Projeto de análise de dados aplicado a uma grande loja online. O objetivo foi priorizar hipóteses de negócio que podem aumentar a receita, lançar um teste A/B e analisar seus resultados para apoiar a tomada de decisão sobre qual variante adotar.

---

## Metodologia

1. **Priorização de Hipóteses**
   - Aplicação dos frameworks **ICE** (Impact, Confidence, Effort) e **RICE** (Reach, Impact, Confidence, Effort) para ranquear hipóteses em ordem de prioridade.
   - Comparação entre os rankings e análise das diferenças entre os dois frameworks.

2. **Pré-processamento dos dados**
   - Conversão de colunas de data para o tipo `datetime`.
   - Identificação e remoção de usuários que apareceram em mais de um grupo do teste.

3. **Análise Exploratória do Teste A/B**
   - Receita acumulada por grupo ao longo do tempo.
   - Tamanho médio acumulado do pedido (ticket médio) por grupo.
   - Diferença relativa no ticket médio acumulado entre grupos.
   - Taxa de conversão diária e cumulativa por grupo.
   - Análise de anomalias: quantidade de pedidos por usuário e preços dos pedidos.

4. **Tratamento de Outliers**
   - Identificação via percentis 95 e 99 de pedidos por usuário e de valor por pedido.
   - Usuários com 3 ou mais pedidos e pedidos acima de $830 foram classificados como anomalias e removidos para análises filtradas.

5. **Testes de Significância Estatística**
   - Aplicação do teste **Mann-Whitney U** para comparar conversão e ticket médio entre os grupos A e B, tanto nos dados brutos quanto nos dados filtrados.

---

## Principais Resultados

- **Priorização:** O top 5 de hipóteses é o mesmo em ambos os frameworks (ICE e RICE), mas com ordenações distintas — RICE valoriza hipóteses de maior alcance, enquanto ICE pondera apenas impacto e confiança.

- **Receita e Ticket Médio:** O grupo B apresentou crescimento expressivo a partir da segunda semana do teste, influenciado por outliers (pedidos de alto valor). Após a filtragem, a diferença no ticket médio **não** se mostrou estatisticamente significativa em nenhum dos cenários.

- **Taxa de Conversão:** O grupo B demonstrou conversão cumulativa consistentemente superior ao grupo A a partir do 5º dia do teste. A diferença foi **estatisticamente significativa** tanto nos dados brutos quanto nos filtrados (p-value < 0,05 no teste de Mann-Whitney U).

- **Conclusão:** Com base nos resultados, recomenda-se **encerrar o teste e declarar o Grupo B como vencedor** — não há diferença significativa no ticket médio, mas há melhora real e estatisticamente comprovada na taxa de conversão.

---

## 📂 Conteúdo do Repositório

- **Notebook (.ipynb):** análise completa, incluindo priorização de hipóteses, EDA, análise de outliers, testes estatísticos e conclusão
- **hypotheses_us (.csv):** hipóteses de negócio utilizadas na etapa de priorização
- **costs_us (.csv):** dados de pedidos do teste A/B
- **visits_us (.csv):** dados de visitas por grupo ao longo do período
- **README (.md):** este arquivo

---

## Tecnologias e Bibliotecas

- Linguagem: **Python**
- Bibliotecas: **pandas**, **numpy**, **matplotlib**, **seaborn**, **scipy**
- Notebook: **Jupyter Notebook**

---

## Contato

Willian De Souza Pereira — ws13292@gmail.com

LinkedIn: https://linkedin.com/in/willian-de-souza-pereira-b69109202

---

## Licença

Este repositório está disponível para estudo e demonstração. Sinta-se à vontade para clonar, adaptar e abrir *issues* com dúvidas ou sugestões.
