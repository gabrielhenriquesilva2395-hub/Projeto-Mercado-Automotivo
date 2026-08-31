# 📊 Relatório Executivo: Inteligência de Mercado & Precificação Automotiva

**Autor:** Gabriel Henrique  
**Área de Aplicação:** Business Intelligence, Pricing & Analytics  
**Base Analisada:** +550.000 transações de veículos seminovos e usados  

---

## 🎯 1. Sumário Executivo

Este projeto teve como objetivo analisar a dinâmica de precificação no mercado de veículos seminovos e desenvolver uma solução automatizada para apoiar a tomada de decisão comercial na entrada e saída de estoque.

A partir do tratamento de dados transacionais, identificamos padrões de desvalorização, fatores multiplicadores de margem e construímos modelos preditivos capazes de estimar o valor justo de mercado de um veículo em tempo real.

---

## 📈 2. Principais Indicadores do Negócio (KPIs)

- **Volume Transacionado Analisado:** `$ 7.430.270.930,00` (+7,4 Bilhões de dólares).
- **Ticket Médio por Veículo:** `$ 13.845,22`.
- **Quilometragem Média:** `66.454 milhas` (~107.000 km).
- **Nota Média de Conservação Física:** `30.8 / 50` (Padrão Regular/Bom).
- **Aderência à Tabela de Mercado (MMR):** `-0.73%` (Desconto médio controlado praticado nas negociações).

---

## 🔍 3. Principais Descobertas Estratégicas (Insights de Negócio)

### 1. O Fator Multiplicador da Conservação Física
- Veículos com notas de conservação no topo da escala (acima de 40/50) apresentam uma **valorização mediana superior a 35%** frente a veículos de conservação média.
- **Recomendação Estratégica:** Implementar um checklist operacional de preparação estética (polimento, higienização e pequenos reparos) antes da exposição do veículo, maximizando a margem líquida na revenda.

### 2. Curva de Depreciação e Giro de Estoque
- Veículos com 2 a 4 anos de fabricação sofrem a maior pressão de preço decorrente da entrada em massa de frotas desmobilizadas de locadoras.
- **Recomendação Estratégica:** Estabelecer limites rígidos de tempo de pátio (SLA de giro de 45 a 60 dias) para modelos de grande volume (Ford, Chevrolet e Nissan) para mitigar perdas por depreciação acumulada.

---

## 🤖 4. Solução Preditiva & Benchmark de Machine Learning

Para eliminar a subjetividade e o tempo excessivo gasto com consultas manuais de mercado, comparamos dois modelos preditivos:

| Modelo | R² (Capacidade Explicativa) | MAE (Erro Médio Absoluto) | RMSE ($) | Tempo | Papel Estratégico no Negócio |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Regressão Linear (Baseline)** | `65.39%` | `$ 3.564,90` | `$ 5.280,40` | `6.47s` | Explicabilidade rápida e sensibilidade de preço |
| **Random Forest Regressor (Ensemble)** | `71.72%` | `$ 2.971,04` | `$ 4.772,73` | `70.99s` | **Modelo Vencedor** (redução de erro de ~$593/carro) |

### 🚗 Entregável Operacional
- **Simulador Comercial em Tempo Real:** Ferramenta interativa onde o avaliador insere os dados do carro e recebe a precificação estimada, além de uma **Faixa Segura de Oferta (com margem garantida de 10% a 15%)**.

---

## 🚀 5. Roadmap e Recomendações de Implantação para a Operação

Para transformar o modelo preditivo em uma ferramenta corporativa de uso contínuo pelas equipes de compras e vendas, recomendo as seguintes fases de implantação:

1. **Camada de Geolocalização:** Incorporar variáveis de estado e região às cotações, precificando diferenças de alíquotas fiscais (IPVA) e custos logísticos de frete interestadual.
2. **Interface Operacional na Ponta:** Desenvolver uma aplicação web leve (Streamlit ou Dashboard corporativo) para que os avaliadores de pátio e concessionárias insiram os dados do veículo pelo celular e recebam a recomendação de oferta em tempo real.
3. **Governança de Dados & MLOps:** Estabelecer uma rotina de retreinamento mensal do modelo com os dados consolidados dos fechamentos de leilões e histórico de vendas do mês anterior, prevenindo desvios decorrentes de flutuações sazonais do mercado.
