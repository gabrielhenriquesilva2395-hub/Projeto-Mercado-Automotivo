# 📊 Relatório Executivo: Inteligência de Mercado & Precificação Automotiva

**Autor:** Gabriel Henrique  
**Área de Aplicação:** Business Intelligence, Pricing & Analytics  
**Base Analisada:** +550.000 transações de veículos seminovos e usados  

---

## 🎯 1. Sumário Executivo

Este projeto teve como objetivo analisar a dinâmica de precificação no mercado de veículos seminovos e desenvolver uma solução automatizada para apoiar a tomada de decisão comercial na entrada e saída de estoque.

A partir do tratamento de dados transacionais, identificamos padrões de desvalorização, fatores multiplicadores de margem e construímos um modelo preditivo capaz de estimar o valor justo de mercado de um veículo em tempo real.

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

## 🤖 4. Solução Preditiva (Machine Learning)

Para eliminar o tempo excessivo gasto com consultas manuais de mercado, desenvolvemos um modelo de **Regressão Linear** com as seguintes características:

- **Variáveis Consideradas:** Ano de Fabricação, Marca, Tipo de Carroceria, Nota de Conservação e Quilometragem.
- **Capacidade Explicativa ($R^2$):** **`65.39%`** de toda a variação de preços explicada com apenas 5 atributos essenciais.
- **Erro Médio Absoluto ($MAE$):** **`$ 3.564,90`**, com altíssima aderência na faixa central do mercado ($ 10.000 a $ 25.000).
- **Entregável Operacional:** **Simulador Interativo em Tempo Real** integrado ao fluxo de avaliação de veículos.

---

## 🚀 5. Próximos Passos & Evoluções Recomendadas

1. Integrar variáveis de localização geográfica (estado/região) para capturar variações tributárias e de frete.
2. Desenvolver interface web amigável (via Streamlit ou Power BI) para uso direto pelos avaliadores de concessionárias.
3. Testar modelos ensemble (Random Forest e XGBoost) para ganho adicional de acurácia em segmentos premium e de luxo.
