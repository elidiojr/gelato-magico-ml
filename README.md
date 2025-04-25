# 🍦 Prevendo Vendas de Sorvete com Azure Machine Learning

Este projeto demonstra como usar o **Azure Machine Learning** para prever as vendas diárias de sorvete da sorveteria Gelato Mágico com base na temperatura do dia. O objetivo é otimizar a produção, reduzir desperdícios e aumentar os lucros, utilizando recursos de Machine Learning em nuvem.

---

## 📁 Estrutura do Projeto

gelato-magico-azureml/

├ ── inputs/

│ └── temperaturas_vendas.csv

├ ── notebooks/

│ └── treinamento_azureml.ipynb

├ ── README.md

---

## 📊 Dados de Entrada

O arquivo `inputs/temperaturas_vendas.csv` contém dados históricos de temperatura e vendas:

temperatura,vendas

25,150

28,180

30,210

18,90

22,120


---

## 🚀 Como Executar no Azure ML

### 1. Suba os Dados

- Acesse o [Azure ML Studio](https://ml.azure.com/).
- Crie um novo Dataset e faça upload do arquivo `temperaturas_vendas.csv`.

### 2. Treine o Modelo

#### Opção 1: **Automated ML (sem código)**
- Crie um novo experimento de *Automated ML*.
- Selecione o dataset enviado.
- Defina a tarefa como **Regressão**.
- Escolha `vendas` como variável alvo e `temperatura` como preditora.
- Execute o experimento e aguarde o Azure ML testar diferentes modelos.

#### Opção 2: **Notebook (com código)**
- Importe o notebook em `notebooks/treinamento_azureml.ipynb` no Azure ML Studio.
- Execute as células para treinar, registrar e implantar o modelo usando o SDK do Azure ML.

### 3. Avalie e Registre o Modelo

- Analise as métricas (R², MSE) apresentadas pelo Azure ML.
- O melhor modelo será registrado automaticamente no seu workspace.

### 4. Deploy do Modelo

- No Azure ML Studio, selecione o modelo registrado e clique em **Implantar** para criar um serviço web (API REST).
- O Azure provisiona automaticamente um endpoint para consumo.

### 5. Faça Previsões

- Envie um JSON para o endpoint do modelo com a temperatura desejada.
- Exemplo de requisição:
    ```
    {
      "data": [
        {"temperatura": 29}
      ]
    }
    ```
- O serviço retorna a previsão de vendas para a temperatura informada.

---

## 📈 Resultados e Insights

- **Correlação forte** entre temperatura e vendas.
- O modelo de regressão linear obteve R² ≈ 0.92 nos testes.
- O Azure ML facilita o gerenciamento, registro e deploy do modelo com poucos cliques.

---

## 💡 Possibilidades Futuras

- Adicionar mais variáveis (dia da semana, feriados, chuva).
- Testar outros algoritmos (Random Forest, XGBoost).
- Automatizar o pipeline de dados e re-treinamento.

---

## ✨ O que aprendi

- Como usar o Azure ML para treinar, registrar e implantar modelos de machine learning.
- A importância do versionamento e reprodutibilidade de experimentos.
- Como criar APIs de previsão em nuvem de forma simples e escalável.


