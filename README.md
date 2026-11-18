# Análise Global de Culinárias, Complexidade Culinária e Perfis Nutricionais

Projeto da disciplina de Data Analytics, Sistemas de Informação, 6º período (PUCPR).

*Integrantes:* Enzo Leitão, Giovani Simões, Luan Lucho e Sarah Maneira

## Sobre o projeto

Análise das receitas publicadas no Food.com entre 1999 e 2018 para comparar culinárias e restrições alimentares quanto a tempo de preparo, complexidade e perfil nutricional.

## Dados

- *Fonte:* [Food.com Recipes and Interactions](https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions) (Kaggle), a partir de Majumder et al. (2019).
- *Arquivo usado:* RAW_recipes.csv, com 231.637 receitas (231.630 após a limpeza).
- Os dados não ficam no repositório: o notebook baixa o arquivo automaticamente com kagglehub.

## Estrutura do notebook

| Etapa | Seções | Conteúdo |
|---|---|---|
| RA1 | 1 a 7 | Ingestão, diagnóstico de qualidade (Q1 a Q15), limpeza (D1 a D6) e geração da base final data/recipes_ra1.parquet |
| RA2 | 8 a 12 | Processamento em streaming simulado com Spark Structured Streaming e janelas temporais |
| RA3 | 3.1 a 3.5 | Estatística descritiva, visualizações, representatividade dos dados, Machine Learning (árvore de decisão) e conclusões |

## Como executar

1. Abra o notebook data_analytics_ra.ipynb no Google Colab.
2. Use *Ambiente de execução → Executar tudo*. O download dos dados é automático, sem conta ou chave de acesso.
3. Para rodar de novo, use *Ambiente de execução → Reiniciar sessão* antes de executar tudo, porque o streaming do RA2 não pode ser iniciado duas vezes na mesma sessão.

*Bibliotecas:* pandas, numpy, pyarrow, kagglehub, pyspark, matplotlib e scikit-learn, todas já disponíveis no Colab.

## Como verificar os resultados

- No RA1, um assert confere se a base limpa tem 231.630 linhas e 19 colunas.
- No RA3, as tabelas, os gráficos e as métricas aparecem nas saídas das células.
- A divisão treino/teste e o modelo usam random_state=42, então a acurácia (86,8%) se repete a cada execução.