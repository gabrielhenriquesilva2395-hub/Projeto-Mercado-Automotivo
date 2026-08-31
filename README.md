# 🚗 Análise Estratégica & Modelo Preditivo de Precificação Automotiva

Projeto de análise de dados e machine learning desenvolvido para simular um cenário real de inteligência de negócios no setor automotivo e de varejo de veículos seminovos.

---

## 📌 1. Visão Geral do Projeto & Problema de Negócio

No mercado automotivo, a precificação correta de veículos usados é crítica para:
1. **Evitar dinheiro parado em estoque** (precificação acima do mercado).
2. **Evitar queima de margem e prejuízo** (venda abaixo do valor ótimo).

Este projeto responde a perguntas estratégicas de diretoria e implementa um modelo preditivo automatizado para recomendar o preço ideal de venda de um veículo no momento de sua avaliação.

---

## 🗂️ Estrutura do Projeto

```text
projeto-mercado-automotivo/
├── data/
│   └── car_prices.csv                          # Base com +550.000 transações
├── 01_analise_exploratoria_e_negocios.ipynb     # Análise de Negócios, KPIs e Storytelling
├── 02_modelo_preditivo_precificacao.ipynb        # Modelo de Machine Learning (Regressão)
├── README.md                                   # Apresentação do Portfólio
└── .venv/                                      # Ambiente virtual Python
```

---

## 📊 2. Principais Perguntas de Negócio Respondidas

- **Eficiência Comercial:** Comparação entre o Preço Praticado e a Tabela de Mercado (*Manheim Market Report - MMR*).
- **Curva de Depreciação:** Relação entre idade do veículo, quilometragem acumulada e valor residual.
- **Fator Conservação:** Impacto financeiro do estado físico do veículo no valor de revenda.
- **Ranking de Marcas:** Identificação de fabricantes com maior liquidez e retenção de valor.

---

## 🤖 3. Modelo Preditivo (Machine Learning)

- **Algoritmo:** Regressão Linear & Random Forest Regressor.
- **Variáveis de Entrada (Features):** Ano, Fabricante, Tipo de Carroceria, Condição Física e Quilometragem.
- **Variável Alvo (Target):** Preço de Venda (`sellingprice`).
- **Métricas de Sucesso:** $R^2$ (Capacidade explicativa) e $MAE$ (Erro Médio em dólares).

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python 3.12+
- **Manipulação de Dados:** `pandas`, `numpy`
- **Visualização & Storytelling:** `matplotlib`, `seaborn`
- **Machine Learning:** `scikit-learn`
- **Ambiente:** Jupyter Notebooks & Antigravity IDE

---

## 🚀 Como Executar Localmente

1. Ative o ambiente virtual:
   ```bash
   .\.venv\Scripts\activate
   ```
2. Abra os notebooks:
   - [01_analise_exploratoria_e_negocios.ipynb](01_analise_exploratoria_e_negocios.ipynb)
   - [02_modelo_preditivo_precificacao.ipynb](02_modelo_preditivo_precificacao.ipynb)
