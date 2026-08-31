# 🚗 Análise Estratégica & Modelo Preditivo de Precificação Automotiva

Projeto de inteligência de negócios, ciência de dados e machine learning desenvolvido para simular um cenário real de estratégia comercial e precificação no setor automotivo e de seminovos.

---

## 🔗 Acesso Rápido aos Arquivos do Projeto

* 📊 **[Notebook 01: Análise Exploratória, KPIs & Storytelling de Negócios](01_analise_exploratoria_e_negocios.ipynb)**
* 🤖 **[Notebook 02: Modelagem Preditiva & Benchmark (Regressão Linear vs. Random Forest)](02_modelo_preditivo_precificacao.ipynb)**
* 📑 **[Relatório Executivo para Decisores & Diretoria Comercial](relatorio_executivo.md)**

---

## 📌 1. Visão Geral do Projeto & Problema de Negócio

No mercado automotivo, a precificação correta de veículos usados é crítica para:
1. **Evitar dinheiro parado em estoque** (veículos com preço acima do mercado perdem giro e depreciam).
2. **Evitar queima desnecessária de margem** (venda abaixo do valor justo de mercado).

Este projeto responde a perguntas estratégicas de diretoria comercial e implementa um sistema de inteligência preditiva com **benchmark de dois modelos de Machine Learning (Regressão Linear vs. Random Forest Regressor)** para recomendar o preço ideal de revenda no momento da avaliação de entrada.

---

## 🗂️ Estrutura do Repositório

```text
projeto-mercado-automotivo/
├── data/
│   └── car_prices.csv                          # Base histórica com +550.000 transações
├── 01_analise_exploratoria_e_negocios.ipynb     # Análise de Negócios, KPIs e Storytelling
├── 02_modelo_preditivo_precificacao.ipynb        # Modelagem Preditiva (Linear vs Random Forest)
├── relatorio_executivo.md                       # Relatório para Diretoria / Decisores
├── README.md                                   # Apresentação do Projeto
└── .venv/                                      # Ambiente virtual Python
```

---

## 📊 2. Principais Perguntas de Negócio Respondidas

- **Eficiência Comercial:** Comparação entre o Preço Praticado e a Tabela de Mercado (*Manheim Market Report - MMR*).
- **Curva de Depreciação:** Impacto conjunto da idade do veículo e quilometragem acumulada.
- **Fator Conservação:** Impacto financeiro do estado físico do veículo (notas de conservação) no valor de revenda.
- **Liquidez por Marca:** Identificação dos fabricantes com maior volume e retenção de valor residual.

---

## 🤖 3. Modelagem Preditiva & Benchmark de Machine Learning

Comparamos duas abordagens para avaliar o equilíbrio entre interpretabilidade e precisão:

| Modelo | Tipo | R² (Capacidade Explicativa) | MAE (Erro Médio em $) | RMSE ($) | Tempo de Treino | Papel Estratégico |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| **Regressão Linear** | *Baseline Paramétrico* | **`65.39%`** | **`$ 3.564,90`** | `$ 5.280,40` | `6.47s` | Linha de base rápida e explicabilidade direta |
| **Random Forest Regressor** | *Ensemble Não-Linear* | **`71.72%`** | **`$ 2.971,04`** | `$ 4.772,73` | `70.99s` | **Modelo Vencedor** (redução de erro de ~$593/carro) |

### 🔍 Principais Drivers de Precificação (*Feature Importance*):
1. **Quilometragem Acumulada (`odometer`):** Responde por mais de **50% do peso preditivo**.
2. **Ano de Fabricação (`year`):** Segundo maior impacto (~**11%**).
3. **Prêmios de Segmento & Marcas de Luxo (`make_Mercedes-Benz`, `make_Lexus`):** Valorização não-linear por prestígio de marca.
4. **Estado de Conservação Física (`condition`):** Fator multiplicador de margem líquida.

---

## 🛠️ Tecnologias & Ferramentas

- **Linguagem:** Python 3.12+
- **Manipulação de Dados:** `pandas`, `numpy`
- **Visualização & Storytelling:** `matplotlib`, `seaborn`
- **Machine Learning:** `scikit-learn` (`LinearRegression`, `RandomForestRegressor`, `metrics`)
- **Ambiente:** Jupyter Notebooks

---

## 🚀 Como Executar Localmente

1. Clone o repositório e ative o ambiente virtual:
   ```bash
   cd projeto-mercado-automotivo
   .\.venv\Scripts\activate
   ```
2. Acesse diretamente os notebooks navegáveis:
   - 📊 **[Abrir Notebook 01 — Análise Exploratória e Negócios](01_analise_exploratoria_e_negocios.ipynb)**
   - 🤖 **[Abrir Notebook 02 — Modelo Preditivo & Benchmark de ML](02_modelo_preditivo_precificacao.ipynb)**
   - 📑 **[Abrir Relatório Executivo](relatorio_executivo.md)**
