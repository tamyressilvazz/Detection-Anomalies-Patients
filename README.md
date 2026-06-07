# 🫀 Detecção de Anomalias em Pacientes com Statlog Heart Dataset usando Isolation Forest

## 📖 Sobre o Projeto

Este projeto aplica técnicas de **Detecção de Anomalias (Anomaly Detection)** utilizando o algoritmo **Isolation Forest (iForest)** no dataset **Statlog Heart Disease**.

O objetivo é identificar pacientes que apresentam padrões clínicos incomuns quando comparados aos demais indivíduos da base de dados.

A identificação desses casos pode auxiliar em:

* Descoberta de registros atípicos;
* Identificação de possíveis erros de medição;
* Detecção de pacientes com características raras;
* Análise exploratória de dados médicos.

---

## 🎯 Objetivos

* Explorar estatisticamente os dados clínicos;
* Identificar possíveis outliers;
* Aplicar o algoritmo Isolation Forest;
* Visualizar distribuições e dispersões das variáveis;
* Analisar pacientes com características incomuns.

---

## 📊 Dataset

O projeto utiliza o **Statlog (Heart) Dataset**, um conjunto de dados amplamente utilizado em estudos de aprendizado de máquina voltados para diagnóstico de doenças cardíacas.

### Informações Gerais

* 270 pacientes
* 13 atributos clínicos
* Problema originalmente utilizado para classificação cardíaca
* Aplicado neste projeto para detecção de anomalias

### Variáveis Analisadas

O estudo concentrou-se principalmente nas seguintes variáveis:

| Variável    | Descrição         |
| ----------- | ----------------- |
| age         | Idade             |
| cholestoral | Colesterol sérico |
| pressure    | Pressão arterial  |

Esses atributos foram utilizados para identificar observações incomuns através do Isolation Forest.

---

## 🛠 Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* PyOD
* Isolation Forest

---

## 📈 Etapa 1 – Análise Exploratória

Inicialmente foram calculadas medidas estatísticas dos atributos, incluindo a mediana de cada variável.

### Estatísticas Utilizadas

* Mediana
* Distribuição dos dados
* Frequência dos valores

---

## 📊 Etapa 2 – Histogramas

Foram gerados histogramas para analisar a distribuição das variáveis:

* Idade (`age`)
* Colesterol (`cholestoral`)
* Pressão arterial (`pressure`)

### Objetivo

Identificar:

* Assimetrias;
* Concentração dos valores;
* Possíveis regiões extremas da distribuição.

---

## 📦 Etapa 3 – Boxplots

Foram construídos boxplots para cada variável analisada.

### Benefícios

Os boxplots permitem visualizar:

* Mediana;
* Quartis;
* Valores extremos;
* Possíveis outliers univariados.

---

## 🌲 Etapa 4 – Detecção de Outliers com Isolation Forest

Foi utilizado o algoritmo:

```python
IForest(contamination=0.05)
```

### Configuração

| Parâmetro     | Valor |
| ------------- | ----- |
| Contamination | 5%    |

A taxa de contaminação indica que aproximadamente 5% dos registros são considerados potenciais anomalias.

### Funcionamento

O Isolation Forest detecta anomalias isolando observações por meio de divisões aleatórias dos dados.

Observações raras ou extremas tendem a ser isoladas mais rapidamente, sendo classificadas como outliers.

---

## 🔍 Variáveis Utilizadas na Detecção

```python
variaveis = [
    'age',
    'cholestoral',
    'pressure'
]
```

Essas características clínicas foram utilizadas para treinar o modelo de detecção de anomalias.

---

## 📉 Visualização dos Outliers

Após o treinamento do modelo, foram produzidos gráficos de dispersão para visualizar os pacientes classificados como anômalos.

### Relações Avaliadas

#### Idade × Colesterol

Permite identificar pacientes com combinações incomuns entre idade e níveis de colesterol.

#### Idade × Pressão Arterial

Permite observar indivíduos que apresentam pressão arterial fora do padrão esperado para determinada faixa etária.

#### Colesterol × Pressão Arterial

Auxilia na identificação de perfis clínicos extremos relacionados ao risco cardiovascular.

---

## 🚨 Identificação dos Outliers

Após a classificação realizada pelo Isolation Forest, os registros identificados como anômalos são extraídos para análise detalhada.

```python
outliers_detectados = df[df['outlier'] == 1]
```

Esses pacientes representam observações que diferem significativamente do comportamento predominante na base de dados.

---

## 🚀 Como Executar

### Instalar Dependências

```bash
pip install pandas numpy matplotlib pyod
```

### Executar o Projeto

```bash
python exercicio_detecção_de_anomalias_v2_iforest.py
```

---

## 📂 Estrutura do Projeto

```text
.
├── statlog-heart-dataset.csv
├── exercicio_detecção_de_anomalias_v2_iforest.py
└── README.md
```

---

## 📚 Conceitos Aplicados

* Data Analysis
* Anomaly Detection
* Outlier Detection
* Isolation Forest
* Estatística Descritiva
* Visualização de Dados
* Aprendizado Não Supervisionado
* Análise Exploratória de Dados

---

## 📈 Principais Conclusões

* O Isolation Forest permitiu identificar automaticamente pacientes com características clínicas incomuns.
* Histogramas e boxplots auxiliaram na compreensão da distribuição das variáveis.
* As combinações entre idade, colesterol e pressão arterial evidenciaram regiões com maior concentração de anomalias.
* A técnica mostrou-se eficaz para análise exploratória e identificação de observações atípicas em dados médicos.

---

## 👨‍💻 Autor

**Tamyres Silva**

Projeto desenvolvido para fins acadêmicos na disciplina de Aprendizado de Máquina, explorando técnicas de detecção de anomalias em dados clínicos utilizando Isolation Forest.
