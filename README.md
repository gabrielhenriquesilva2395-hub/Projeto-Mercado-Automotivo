# 🚗 Análise de mercado automotivo e estimativa de preços

Projeto de portfólio em análise de dados e machine learning aplicado a vendas de veículos usados e seminovos. O trabalho reúne indicadores comerciais, análise exploratória e modelos preditivos para apoiar a avaliação de preços.

## 🔗 Acesso rápido

* 📊 **[Notebook 01: Análise Exploratória, KPIs & Storytelling de Negócios](01_analise_exploratoria_e_negocios.ipynb)**
* 🤖 **[Notebook 02: Modelagem Preditiva & Benchmark (Regressão Linear vs. Random Forest)](02_modelo_preditivo_precificacao.ipynb)**
* 📑 **[Relatório Executivo para Decisores & Diretoria Comercial](relatorio_executivo.md)**

## 📌 Problema de negócio

Como avaliar se os preços praticados estão próximos da referência de mercado e quais características dos veículos estão associadas ao preço de venda? O projeto explora essas perguntas e compara dois modelos para estimar o preço de venda de um veículo a partir de seus atributos.

O *Manheim Market Report* (MMR) é usado como **referência de preço**, não como medida de margem. A base não contém custos de aquisição, comissões e demais despesas necessárias para calcular a margem financeira efetiva.

## 📊 Análises e indicadores

- **Preço praticado versus MMR:** diferença absoluta e percentual entre o preço de venda e a referência de mercado.
- **Perfil das transações:** volume de vendas por fabricante, ticket médio e características dos veículos analisados.
- **Ano, quilometragem e conservação:** relação dessas variáveis com o preço de venda observado.
- **Recomendações operacionais:** propostas de acompanhamento de preços e estoque apresentadas no relatório executivo. A base de vendas não mede o tempo de permanência de cada veículo em estoque.

## 🤖 Modelagem preditiva

O segundo notebook usa ano, fabricante, tipo de carroceria, estado de conservação e quilometragem para prever o preço de venda. Os modelos foram avaliados com divisão de 80% dos registros para treino e 20% para teste.

| Modelo | R² no teste | Erro médio absoluto (MAE) | RMSE |
| :--- | ---: | ---: | ---: |
| Regressão Linear | 65,39% | US$ 3.564,90 | US$ 5.280,40 |
| Random Forest Regressor | 71,72% | US$ 2.971,04 | US$ 4.772,73 |

Os valores acima são os resultados registrados no notebook. O Random Forest apresentou menor erro médio nesse teste. O notebook também contém uma função de **simulação** que recebe as características de um veículo e mostra as estimativas dos dois modelos.

## 🗂️ Arquivos publicados

```text
Projeto-Mercado-Automotivo/
├── 01_analise_exploratoria_e_negocios.ipynb
├── 02_modelo_preditivo_precificacao.ipynb
├── relatorio_executivo.md
├── requirements.txt
├── .gitignore
└── README.md
```

## 🛠️ Tecnologias

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn e Jupyter Notebook.

## 🚀 Como executar localmente

**Fonte dos dados:** [Vehicle Sales Data, publicado por Syed Anwar Afridi no Kaggle](https://www.kaggle.com/datasets/syedanwarafridi/vehicle-sales-data). A cópia utilizada contém 558.837 registros e 16 colunas. Consulte a página da fonte para as condições de uso.

Os notebooks leem `data/car_prices.csv`. **A base não está incluída neste repositório**. Para executar o projeto, baixe `car_prices.csv` da fonte acima e coloque o arquivo em uma pasta `data` na raiz do projeto. Não é necessário publicar a base no GitHub.

Depois de preparar a base, instale as dependências e abra os notebooks na ordem indicada:

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

- 📊 **[Abrir Notebook 01 — Análise Exploratória e Negócios](01_analise_exploratoria_e_negocios.ipynb)**
- 🤖 **[Abrir Notebook 02 — Modelo Preditivo & Benchmark de ML](02_modelo_preditivo_precificacao.ipynb)**
- 📑 **[Abrir Relatório Executivo](relatorio_executivo.md)**

Os notebooks contêm resultados de uma execução com a base indicada. Para reproduzir os resultados no seu ambiente, execute as células após disponibilizar a base de dados. Os tempos de treinamento podem variar conforme o computador.
