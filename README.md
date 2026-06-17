# Trabalho-final-IAM : Bank Marketing
### Análise Exploratória de Dados
---

## Integrantes do Grupo
- **Gustavo Alexandre de Carvalho**  
- **Eduarda Machado Carreira**  
- **Cleorbeth Oliveira Santos**

---

## Problema Analisado

Este projeto aborda um problema de **classificação binária** utilizando Regressão Logística. O objetivo é prever se uma pessoa possui renda anual superior a 50 mil dólares (>50K) ou igual/inferior a 50 mil dólares (<=50K), com base em características socioeconômicas e demográficas.

A Regressão Logística é um modelo estatístico amplamente utilizado para problemas de classificação, que estima a probabilidade de uma observação pertencer a uma determinada classe através da função sigmoide.

---

## Dataset Utilizado

**Adult Income Dataset (Census Income)**

- **Fonte**: UCI Machine Learning Repository
- **Registros**: 32.561 observações
- **Atributos**: 15 variáveis (14 preditoras + 1 variável alvo)

---

## Resumo dos Principais Achados da EDA

### 1. Distribuição da Variável Alvo
- **Desbalanceamento de classes**: O dataset apresenta desbalanceamento significativo, com aproximadamente 75% das observações na classe "<=50K" e apenas 25% na classe ">50K".
- Este desbalanceamento pode impactar o desempenho do modelo, especialmente na classe minoritária.

### 2. Valores Ausentes
- Identificados valores ausentes representados por "?" em variáveis categóricas.
- As variáveis mais afetadas são: `workclass`, `occupation` e `native-country`.
- Tratamento: remoção das linhas com valores ausentes para garantir qualidade dos dados.

### 3. Características dos Dados
- **Idade**: Variação de 17 a 90 anos, com média em torno de 38 anos.
- **Horas trabalhadas**: Média de aproximadamente 40 horas semanais.
- **Escolaridade**: Distribuição variada, com concentração em High School e ensino superior.

### 4. Desempenho do Modelo
- **Acurácia**: O modelo alcança boa performance geral na classificação.
- **Matriz de Confusão**: Permite visualizar a distribuição de acertos e erros por classe.
- **Curva ROC e AUC**: Indicam a capacidade discriminativa do modelo entre as duas classes.

### 5. Insights Relevantes
- Variáveis como `education-num`, `hours-per-week`, `capital-gain` e `marital-status` tendem a ser importantes preditores de renda.
- O pré-processamento com One-Hot Encoding é essencial para lidar com as múltiplas variáveis categóricas do dataset.

---

### Variáveis do Dataset:

| Variável | Tipo | Descrição |
|----------|------|-----------|
| age | Numérico | Idade do indivíduo |
| workclass | Categórico | Tipo de empregador |
| fnlwgt | Numérico | Peso final (representatividade demográfica) |
| education | Categórico | Nível de escolaridade |
| education-num | Numérico | Escolaridade em anos |
| marital-status | Categórico | Estado civil |
| occupation | Categórico | Ocupação profissional |
| relationship | Categórico | Relacionamento familiar |
| race | Categórico | Raça/Etnia |
| sex | Categórico | Sexo |
| capital-gain | Numérico | Ganho de capital |
| capital-loss | Numérico | Perda de capital |
| hours-per-week | Numérico | Horas trabalhadas por semana |
| native-country | Categórico | País de origem |
| income | Categórico | **Variável alvo** (<=50K ou >50K) |

---

## Instruções para Execução do Notebook

### Pré-requisitos

Certifique-se de ter o Python 3.8+ instalado e as seguintes bibliotecas:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Estrutura do Projeto

```
projeto/
├── atividade3_regressao_logistica_adult_income.ipynb  # Notebook principal
├── README.md                                           # Este arquivo
└── adult.csv                                           # Dataset (baixar separadamente)
```

### Download do Dataset

O dataset pode ser obtido de uma das seguintes formas:

1. **UCI Repository**: https://archive.ics.uci.edu/ml/datasets/adult
2. **Kaggle**: https://www.kaggle.com/datasets/uciml/adult-census-income
3. **Diretamente no código**: O notebook carrega automaticamente via URL

### Execução

1. **Clone ou baixe o projeto**:
   ```bash
   # Se baixou o ZIP do v0, extraia os arquivos
   unzip projeto.zip
   cd projeto
   ```

2. **Abra o Jupyter Notebook**:
   ```bash
   jupyter notebook atividade3_regressao_logistica_adult_income.ipynb
   ```
   
   Ou usando JupyterLab:
   ```bash
   jupyter lab atividade3_regressao_logistica_adult_income.ipynb
   ```

3. **Execute as células em ordem**:
   - Utilize `Shift + Enter` para executar cada célula sequencialmente.
   - Ou selecione `Cell > Run All` para executar todo o notebook.

### Ambiente Virtual (Recomendado)

```bash
# Criar ambiente virtual
python -m venv venv

# Ativar ambiente (Windows)
venv\Scripts\activate

# Ativar ambiente (Linux/Mac)
source venv/bin/activate

# Instalar dependências
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Possíveis Problemas e Soluções

| Problema | Solução |
|----------|---------|
| `ModuleNotFoundError` | Execute `pip install <nome_do_modulo>` |
| Erro ao carregar CSV | Verifique se o arquivo `adult.csv` está no diretório correto ou use a URL direta |
| Kernel não inicia | Reinstale o Jupyter: `pip install --upgrade jupyter` |

---

## Metodologia

O notebook segue a seguinte estrutura metodológica:

1. **Conhecendo os Dados** - Carregamento e exploração inicial
2. **Análise do Atributo Alvo** - Distribuição e visualização
3. **Pré-processamento** - Tratamento de dados e encoding
4. **Divisão dos Dados** - Separação em treino e teste
5. **Treinamento** - Ajuste do modelo de Regressão Logística
6. **Avaliação** - Métricas de desempenho e matriz de confusão
7. **Curva ROC** - Análise da capacidade discriminativa
8. **Reflexão Final** - Interpretação e conclusões

---

## Referências

- Dua, D. and Graff, C. (2019). UCI Machine Learning Repository. Irvine, CA: University of California, School of Information and Computer Science.
- Scikit-learn Documentation: https://scikit-learn.org/stable/
- Pandas Documentation: https://pandas.pydata.org/docs/



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


