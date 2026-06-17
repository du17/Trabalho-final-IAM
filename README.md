# Trabalho-final-IAM : Bank Marketing (Análise e Modelagem Preditiva)
---

## Integrantes do Grupo
- **Gustavo Alexandre de Carvalho**
- **Eduarda Machado Carreira**
- **Cleorbeth Oliveira Santos**

---

## Problema Analisado
Este projeto aborda um problema de **classificação binária**. O objetivo preditivo é antecipar se um cliente do banco irá ou não assinar um depósito a prazo (variável-alvo `y`). Como a taxa natural de conversão dessas campanhas é baixa (em torno de 11,69%), ligar para toda a base gera um custo operacional insustentável. A aplicação de Machine Learning visa focar os esforços do telemarketing estritamente nos clientes com maior propensão de aceite.

---

## Dataset Utilizado
**Bank Marketing Dataset**
- **Fonte**: UCI Machine Learning Repository (ID: 222)
- **Atributos Principais**: Características demográficas (idade, profissão, saldo) e características da campanha (duração da chamada, mês do contato).

---

## Resumo dos Principais Achados da EDA (Parte 1)
1. **Desbalanceamento de classes**: O dataset apresenta quase 88% das observações na classe "não" e apenas 12% na classe "sim".
2. **Impacto da Duração**: A "duração da chamada" provou ser a variável mais importante; chamadas longas convertem mais.
3. **Sazonalidade**: Março, setembro, outubro e dezembro são estatisticamente os melhores meses para campanhas.

---

## Metodologia de Modelagem e Machine Learning (Parte 2)
Na segunda fase, o projeto focou em criar e avaliar motores preditivos:
1. **Prevenção de Data Leakage**: Utilizamos `Pipelines` com `ColumnTransformer` para aplicar o `StandardScaler` e o `OneHotEncoder` apenas na base de treino, isolando a base de teste de forma cega.
2. **Tratamento do Desbalanceamento**: Ativação nativa do hiperparâmetro `class_weight='balanced'`.
3. **Otimização**: Uso de `GridSearchCV` (cv=5) para descobrir a profundidade ideal da Árvore de Decisão sem gerar *overfitting*.
4. **Algoritmos Treinados**: Regressão Logística (Baseline), Árvore de Decisão, Random Forest e LightGBM.

---

## Resultados Finais e Conclusão
Devido ao desequilíbrio da base, a "Acurácia" foi descartada como métrica principal, dando lugar ao **F1-Score** e à curva **ROC-AUC**.

- **O Falso Vencedor**: O Random Forest alcançou a maior acurácia (~89,3%), mas falhou em encontrar os clientes interessados (Recall de apenas 20%).
- **O Campeão Real**: O **LightGBM** obteve o melhor desempenho na separação das classes, com um **AUC-ROC de 0,802**. 
- **A Decisão de Negócio**: O LightGBM foi configurado para errar de forma segura. Ele gerou 1.198 falsos positivos (ligações baratas perdidas) estritamente para manter os falsos negativos (clientes lucrativos perdidos) no mínimo possível (386 casos).

---

## Instruções para Execução do Projeto

### Pré-requisitos
```bash
# Instale as bibliotecas necessárias incluindo a API da UCI e o LightGBM
pip install pandas numpy matplotlib seaborn scikit-learn lightgbm ucimlrepo

### Execução

Clone ou baixe o repositório.

Abra os Jupyter Notebooks na sequência de desenvolvimento:

projeto_final_parte1.ipynb (Análise Exploratória)

projeto_final_parte_2.ipynb (Modelagem ML)

Execute as células em ordem: Os dados serão importados automaticamente da nuvem pelo módulo ucimlrepo.

