# Analise-de-Dados-Datatran2026-PRF
Análise de dados dos acidentes que ocorreram nas rodovias federais em 2026 até setembro

## 1. Visão Geral do Projeto
### Objetivo:
Analisar o perfil, a distribuição espacial/temporal e as principais causas e consequências dos acidentes de trânsito registrados nas rodovias federais brasileiras nos meses de janeiro a setembro, utilizando Python e bibliotecas de manipulação e visualização de dados.

### Fonte dos Dados:
Base oficial de dados abertos da Polícia Rodoviária Federal (datatran2026.csv).

### Volume Analisado:
54.895 ocorrências de acidentes rodoviários, contemplando 30 variáveis descritivas por registro.

## 2. Arquitetura e Metodologia (CRISP-DM)
O projeto seguiu rigorosamente as etapas do framework padrão de mercado de análise e ciência de dados CRISP-DM (Cross-Industry Standard Process for Data Mining):
* Entendimento do negócio
* Entendimento dos dados
* Preparação dos dados
* Modelagem/Análise
* Avaliação
* Implantação

## 3. Entendimento do Negócio
Contexto Institucional: A Polícia Rodoviária Federal (PRF) atua na segurança viária, prevenção e repressão qualificada ao crime em mais de 75 mil quilômetros de rodovias e estradas federais em todo o território nacional.

### Missão, Visão e Valores:
1. Proteger a vida e os direitos humanos.
2. Proteger o meio ambiente.
3. Garantir a segurança pública e a cidadania nas rodovias.
4. Atuar com integridade e transparência.

### Perguntas de Negócio norteadoras:
As perguntas que nortearam essa análise de dados foram:
1. Quais são os estados com maior número de acidentes?
2. Quais são as principais causas e tipos de acidentes?
3. Em quais dias da semana e horários a incidência é maior?
4. De que forma a condição meteorológica influencia as ocorrências?
5. Quais são as consequências humanas (número de mortos e feridos) associadas aos incidentes?

## 4. Entendimento e Preparação dos Dados

### Dicionário de Dados:
Cruzamento com os metadados oficiais disponibilizados pela PRF para tipagem correta das variáveis.

### Análise de Valores Nulos e Faltantes:
O dataset demonstrou altíssima integridade estrutural, apresentando uma quantidade residual e irrelevante de valores nulos concentrada estritamente em colunas descritivas secundárias (como delegacias e UOPs), sem impacto para as análises centrais.

### Tratamento de Outliers:
Optou-se por não realizar a remoção de valores discrepantes (outliers), visto que eventos extremos (como acidentes com múltiplos veículos, elevado número de feridos ou óbitos) representam fatos reais críticos para a compreensão estatística da severidade dos acidentes nas rodovias.


## 5. Análise Descritiva e Exploratória

### Análise Unidimensional (Estatística Descritiva)
Aplicação de métricas estatísticas descritivas nas variáveis numéricas e categóricas através de funções em Python (.describe() e extração de metadados):
* Volume Total: 54.895 registros analisados.
* Média de pessoas envolvidas: ~2,62 pessoas por acidente.
* Média de veículos envolvidos: ~2,0 veículos por ocorrência.
* Severidade média: Aproximadamente 1,147 feridos por acidente, com média de 0,08 óbitos e 0,27 feridos graves por ocorrência.
* Os valores máximos registraram eventos de alta gravidade: até 23 óbitos, 48 feridos ou 19 veículos em ocorrências isoladas de grande proporção.

### Análise Bidimensional e Visualizações
Geração de gráficos automatizados (como Box Plots para variáveis numéricas e gráficos de barras para variáveis categóricas) para identificar padrões e correlações:
* Distribuição Temporal: Concentração de ocorrências nos finais de semana, com destaque para o domingo (8.740 registros).
* Distribuição Geográfica: O estado de Minas Gerais (MG) lidera o ranking absoluto de ocorrências com 7.132 registros, reflexo da extensividade de sua malha rodoviária federal.
* Causas Principais: A causa primária mais recorrente foi a "Ausência de reação do condutor" (8.778 ocorrências).
* Tipologia de Acidentes: O tipo predominante foi a "Colisão traseira" (11.073 registros).
* Condições de Contorno: Predominância de ocorrências sob condições de "Pleno dia" (30.124 casos), em trechos de "Reta" (30.219 casos) e sob condições meteorológicas de "Céu Claro" (34.368 casos), indicando que fatores comportamentais e desatenção superam fatores climáticos adversos na amostragem geral.

## 6. Respondendo às Perguntas de Negócio
### 1. Quais são os estados com maior número de acidentes?
<img src="./imagens datatran2026/1_acidentes_por_estado.png" alt="acidentes por estado" width="300">

Os Top 4 estados com maior número de acidentes são:
* 1º Lugar: MG
* 2º Lugar: SC
* 3º Lugar: PR
* 4º Lugar: RJ

### 2. Quais são as principais causas e tipos de acidentes?
<p align="left">
  <img src="./imagens datatran2026/2_acidentes_por_causa.png" alt="acidentes por causa" width="300">
  <img src="./imagens datatran2026/2_acidentes_por_causa_comparação.png" alt="comparação top10 vs outras" width="300">
</p>

As 10 principais causas de acidentes são:
* 1ª Ausência de reação do condutor
* 2ª Reação tardia ou ineficiente do condutor
* 3ª Acessar a via sem observar a presença de outros veículos
* 4ª Condutor deixou de manter distância do veículo da frente
* 5ª Manobra de mudança de faixa
* 6ª Velocidade incompatível
* 7ª Ingestão de álcool pelo condutor
* 8ª Demais falhas mecânicas ou elétricas
* 9ª Transitarna contramão
* 10ª Condutor dormindo

Além disso:
* Essas 10 principais causas de acidentes são responsáveis por 73,50% de todos os acidentes (40.347)
* Enquanto as Outras Causas representam 26,50% (um total de 14.548 acidentes)

### 3. Em quais dias da semana e horários a incidência é maior?
<p align="left">
  <img src="./imagens datatran2026/3_acidentes_por_dia_semana.png" alt="acidentes por dia da semana" width="300">
  <img src="./imagens datatran2026/3_acidentes_horarios.png" alt="acidentes por horário" width="300">
</p>

Os Top 3 dias da semana em que mais ocorrem acidentes são:
* Domingo
* Sábado
* Sexta-feira

Além disso, os horários em que mais ocorrem acidentes, em cada um desses Top 3, são:
* Das 17:00 às 20:00 no Domingo (um intervalo de 3 horas de pico no número de acidentes)
* Das 16:00 às 21:00 no Sábado (5 horas)
* Das 17:00 às 19:00 na Sexta-feira (2 horas)

### 4. De que forma a condição meteorológica influencia as ocorrências?
<img src="./imagens datatran2026/4_acidentes_por_clima.png" alt="acidentes por condições climáticas" width="300">

Aqui, vemos que as condições climáticas adversas não inlfuenciam no número de acidentes. Pois a maior parte dos acidentes acontece sob **condições de Céu Claro**.

### 5. Quais são as consequências humanas (número de mortos e feridos) associadas aos incidentes?
<p align="left">
  <img src="./imagens datatran2026/5_acidentes_por_tipo.png" alt="acidentes por tipo" width="300">
  <img src="./imagens datatran2026/5_acidentes_por_severidade.png" alt="severidade" width="300">
</p>

Os tipos de acidentes e suas consequências:
* Os Top 5 tipos de acidentes que mais acontecem nas rodovias são: Colisão traseira, Saída do leito carroçável, Colisção transversal, Colisão lateral mesmo sentido e Tombamento.
* O mais letal tipo de acidente, porém, é a Colisão frontal, que deixou 1.481 mortes
* O tipo que é mais grave, porém sem óbitos, é a Colisão Traseira, que deixou 2.688 feridos graves

## 7. Principais Conclusões e Insights


## 8. Tecnologias Utilizadas
* Linguagem: Python
* Manipulação de Dados: Pandas, NumPy
* Visualização de Dados: Matplotlib, Seaborn
