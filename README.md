# Análise de Correlação de Dados da NFL

## Visão Geral

Este projeto realiza uma análise exploratória de dados de estatísticas da National Football League (NFL) para identificar correlações entre diferentes variáveis estatísticas. O objetivo é entender como as diversas estatísticas de jogo se relacionam entre si.

## Metodologia

1.  **Importação de Bibliotecas:**
    
    * Foram importadas as bibliotecas `pandas` para manipulação de dados, `numpy` para operações numéricas, `matplotlib.pyplot` e `seaborn` para visualização de dados, e módulos do `sklearn` para modelagem (embora não utilizados neste código).
    
2.  **Carregamento de Dados:**
    
    * Três arquivos CSV contendo estatísticas da NFL foram carregados em DataFrames do pandas:
        * `nfl_estatisticas_passes.csv`
        * `nfl_estatisticas_pontos.csv`
        * `nfl_estatisticas_recepcoes.csv`
        
3.  **Exploração Inicial dos Dados:**
    
    * As primeiras linhas de cada DataFrame foram exibidas usando `head()` para verificar a estrutura dos dados.
    * Informações gerais sobre os DataFrames (nomes das colunas, tipos de dados, etc.) foram mostradas com `info()`.
    * Estatísticas descritivas (média, desvio padrão, mínimo, máximo, etc.) foram calculadas para as colunas numéricas usando `describe()`.
    
4.  **Limpeza de Dados:**
    
    * Valores nulos (ausentes) em cada DataFrame foram verificados com `isnull().sum()`.
    * Quaisquer linhas contendo valores nulos foram removidas dos DataFrames usando `dropna()` (observação: no código fornecido, não foram encontrados valores nulos).
    
5.  **Mesclagem de Dados:**
    
    * Os três DataFrames foram mesclados em um único DataFrame (`merged_df`) usando a função `merge()` do pandas.
    * A mesclagem foi realizada nas colunas em comum: `Nome_Jogador`, `TEAM`, `Ano` e `Tipo_Temporada`.
    * Sufixos foram adicionados aos nomes das colunas para diferenciar as origens (`_rec`, `_pts`, `_pass`).
    
6.  **Análise de Correlação:**
    
    * Apenas as colunas numéricas do DataFrame mesclado foram selecionadas para a análise de correlação.
    * A matriz de correlação foi calculada usando o método `corr()` do pandas.
    * Um mapa de calor da matriz de correlação foi gerado usando `seaborn.heatmap()` para visualizar as correlações entre as variáveis.
    * A visualização foi personalizada com anotações, esquema de cores e título, e salva em um arquivo PNG.
    
## Resultados
A matriz de correlação (visualizada no mapa de calor) mostra as relações lineares entre as diversas estatísticas da NFL. Os valores de correlação variam de -1 a 1, onde:

* 1 indica uma correlação positiva perfeita,
* \-1 indica uma correlação negativa perfeita,
* 0 indica ausência de correlação linear.

## Conclusão
Este projeto forneceu uma análise inicial das correlações entre as estatísticas da NFL. Os resultados podem ser usados para entender quais estatísticas estão mais fortemente relacionadas, o que pode ser útil para análises mais aprofundadas ou modelagem preditiva.
