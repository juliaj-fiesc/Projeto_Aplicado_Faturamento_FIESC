**Projeto Aplicado – Projeção de Faturamento**

Pós-Graduação em Ciência de Dados e Inteligência Artificial – SENAI/SC.

Turma: PGCD 2025/1.

Professor: Willian Daniel de Matos.

Alunos: Adriano Maluf Teixeira, Cristina Aurich, Eliane Nunes da Silva, Eliane Nunes da Silva, Julia de Souza Jorge.


**Sobre o Projeto**

Este repositório reúne o material desenvolvido no Projeto Aplicado do curso de Ciência de Dados e Inteligência Artificial.
O objetivo principal é analisar dados históricos de faturamento do Sistema FIESC e desenvolver duas soluções:

- Função em Python para distribuição mensal de faturamento, baseada no comportamento real dos anos anteriores.
- Modelo preditivo de faturamento utilizando Deep Learning (LSTM), considerando a natureza temporal e sazonal dos dados.

**Objetivos do Trabalho**

Analisar o comportamento histórico do faturamento por regional, negócio e período;

Construir uma ferramenta analítica para projetar metas mensais;

Desenvolver um modelo preditivo capaz de estimar valores futuros de faturamento;

Auxiliar o planejamento estratégico e a tomada de decisão dos gestores.

**Estrutura do Repositório**
/
├── Projeto_Aplicado.ipynb     # Notebook principal com análises, função e modelo LSTM
├── dados_faturamento.xlsx     # Dataset utilizado no projeto
├── Municipios_por_regionalVP.xlsx
├── geojs-42-mun.json          # Base geográfica para mapas
├── Relatório Final Projeto Aplicado.pdf
└── README.md                  # Este arquivo

**Metodologia Utilizada**
1. Entendimento dos Dados

Foram utilizados dados de faturamento do SESI, SENAI e IEL (2022–2025), incluindo:

Regionais administrativas,

Grupos de negócio,

Categorias,

Filiais,

Datas e valores financeiros.

Realizaram-se:

Tratamento de tipos,

Verificação de nulos e duplicados,

Criação de colunas derivadas (mês/ano),

Análises gráficas exploratórias.

2. Função para Distribuição Mensal do Faturamento

A função:

Calcula o peso percentual de cada mês com base nos anos anteriores;

Distribui a meta anual proporcionalmente;

Gera tabela consolidada + gráfico dinâmico;

Permite filtros por regional, grupo de negócio e negócio.

Essa função substitui métodos manuais realizados em planilhas, trazendo mais agilidade, confiabilidade e padronização.

3. Modelo Preditivo (LSTM)

Por que LSTM?
Por ser um modelo adequado para séries temporais, capturando tendências, dependências e sazonalidades.

Principais etapas:

Agrupamento e interpolação de valores faltantes,

Normalização com RobustScaler,

Criação de janelas temporais (TimeSplitter),

Arquitetura com 3 camadas LSTM + camadas densas,

Treinamento por 900 épocas e validação cruzada,

Avaliação com MAE, MAPE e R².

Resultados:

MAE: ~39 mil

MAPE: 9,25% (excelente para previsão financeira)

R²: 0,9979 (alto poder explicativo)

O modelo conseguiu capturar picos sazonais (fev/jul) e gerar previsões consistentes.

Tecnologias Utilizadas

Python 3.x

Pandas

NumPy

Matplotlib

Scikit-learn

TensorFlow / Keras

Google Colab

Widgets interativos (ipywidgets)

Possíveis Melhorias Futuras

Treinamento com séries mais longas (pré-2022);

Inclusão de variáveis externas (macro, investimentos, eventos);

Teste de modelos ARIMA e regressão;

Deploy em aplicação web (Streamlit/Flask);

Automação da ingestão de dados.
