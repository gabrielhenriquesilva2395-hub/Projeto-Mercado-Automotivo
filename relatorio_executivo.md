# 📊 Relatório executivo: análise de preços de veículos usados

**Autor:** Gabriel Henrique

**Área de aplicação:** Business Intelligence e análise de dados

**Fonte:** [Vehicle Sales Data, publicado por Syed Anwar Afridi no Kaggle](https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data)
**Base:** 558.837 registros originais; 536.667 registros após os filtros do notebook de análise exploratória

## 🎯 Objetivo

Analisar preços de venda de veículos usados e seminovos, compará-los à referência de mercado MMR e avaliar modelos que estimam o preço de venda a partir das características de cada veículo. O projeto é uma análise de portfólio; a função de simulação está disponível no notebook de modelagem.

O MMR é uma **referência de preço**, não uma medida de margem. A base não contém custos de aquisição, comissões ou demais despesas necessárias para calcular lucratividade.

## 📈 Indicadores da análise exploratória

| Indicador | Resultado |
| :--- | ---: |
| Soma dos preços de venda dos registros analisados | US$ 7.430.270.930 |
| Preço médio de venda por veículo | US$ 13.845,22 |
| Quilometragem média | 66.454 milhas |
| Nota média de conservação | 30,8 em escala até 50 |
| Desvio percentual médio do preço de venda em relação ao MMR | -0,73% |

Esses valores foram recalculados ao executar o [notebook de análise exploratória](01_analise_exploratoria_e_negocios.ipynb) com a base indicada. O desvio em relação ao MMR não permite concluir se as vendas tiveram lucro ou prejuízo.

## 🔍 Leituras para decisão

1. **Conservação e preço:** O gráfico por faixas de conservação mostra como os preços de venda variam entre grupos. A relação observada não demonstra quanto uma preparação estética aumentaria o preço; um checklist de conservação pode ser testado como proposta operacional.
2. **Ano do veículo:** O preço mediano varia entre anos de fabricação na base. Essa comparação não mede, sozinha, a depreciação de um mesmo veículo ao longo do tempo.
3. **Volume por fabricante:** O ranking identifica as marcas com mais transações registradas. Para medir giro de estoque, seriam necessários dados de entradas, saídas e tempo de permanência dos veículos.

## 🤖 Comparação dos modelos

O [notebook de modelagem](02_modelo_preditivo_precificacao.ipynb) usa ano, fabricante, tipo de carroceria, conservação e quilometragem para estimar o preço de venda. A avaliação foi feita com divisão aleatória de 80% dos registros para treino e 20% para teste.

| Modelo | R² no teste | MAE | RMSE |
| :--- | ---: | ---: | ---: |
| Regressão Linear | 65,39% | US$ 3.564,90 | US$ 5.280,40 |
| Random Forest Regressor | 71,72% | US$ 2.971,04 | US$ 4.772,73 |

O Random Forest apresentou menor erro médio absoluto nesse teste, uma diferença de cerca de **US$ 594 por veículo** em relação à Regressão Linear. O notebook inclui uma função que mostra estimativas dos dois modelos para veículos informados pelo usuário. Ela não calcula uma margem de compra segura nem foi avaliada em uma operação real.

## 🚀 Próximos passos para uso operacional

- Validar o modelo em transações posteriores às usadas no treinamento, para avaliar seu desempenho em outro período.
- Incorporar custos de aquisição e despesas caso a decisão exija análise de margem ou limite de oferta.
- Registrar entradas e saídas de estoque para medir tempo de permanência e giro.
- Testar a função com avaliadores e medir tempo de cotação e qualidade das decisões antes de afirmar ganhos operacionais.
