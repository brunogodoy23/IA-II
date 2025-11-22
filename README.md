# 🌽 Previsão de Produtividade Agrícola com IA Híbrida

> Projeto final da disciplina de **Inteligência Artificial II**.
> Uma abordagem que integra **Séries Temporais (ARIMA)** e **Machine Learning (Random Forest)** para estimar safras futuras baseadas em dados climáticos.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Data Science](https://img.shields.io/badge/Data_Science-Pandas_%7C_ScikitLearn-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Concluído-green?style=for-the-badge)

---

## 📋 Sobre o Projeto

A agricultura moderna depende de previsões precisas para mitigar riscos. Este projeto desenvolve um sistema preditivo que correlaciona variáveis climáticas históricas (temperatura, precipitação, umidade) com a produtividade agrícola total de uma região.

**O diferencial desta solução** é a sua arquitetura híbrida:
1.  **ARIMA (AutoRegressive Integrated Moving Average):** Utilizado para projetar o cenário climático de anos futuros (ex: 2025, 2026), onde não existem dados reais.
2.  **Random Forest Regressor:** Utiliza esses dados climáticos (reais ou projetados) para inferir a produtividade da safra em toneladas.

## ⚙️ Funcionalidades

- [x] **ETL Automatizado:** Tratamento de dados brutos do INMET (Clima) e IBGE/SIDRA (Produção).
- [x] **Validação Histórica:** Teste de acurácia com dados passados (Train/Test Split).
- [x] **Previsão Futura:** Geração de estimativas para anos subsequentes ao dataset.
- [x] **Visualização:** Gráficos comparativos entre *Real vs. Previsto*.

## 📊 Resultados e Discussão

O modelo foi avaliado utilizando métricas de regressão padrão. Os desafios encontrados refletem a complexidade de modelar sistemas biológicos apenas com variáveis climáticas.

### Métricas de Desempenho (Conjunto de Teste)

| Métrica | Valor Obtido | Interpretação |
| :--- | :---: | :--- |
| **R² (R-Squared)** | `-0.7168` | Indica dificuldade de generalização frente à média histórica. |
| **MAE** | `400.663 t` | Erro Médio Absoluto. |
| **RMSE** | `872.884 t` | Indica penalização por erros em picos de safra atípicos. |


**Principais Achados:**
1.  **Estabilidade vs. Volatilidade:** Devido à janela histórica curta (2018-2024) e estável, o modelo aprendeu um padrão conservador. As previsões para 2025/2026 tendem a replicar a média histórica.
2.  **Multifatorialidade:** O estudo concluiu que o clima, isoladamente, não explica a totalidade da variância produtiva. Fatores como solo e tecnologia são indispensáveis para aumentar a acurácia.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python
* **Manipulação de Dados:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Random Forest), Statsmodels (ARIMA)
* **Visualização:** Matplotlib

## 🚀 Como Executar

### Pré-requisitos

Certifique-se de ter o Python instalado. Instale as dependências com:

```bash
pip install pandas numpy scikit-learn statsmodels matplotlib
