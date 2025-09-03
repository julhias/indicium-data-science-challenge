# Análise Estratégica e Modelo Preditivo para a Indústria Cinematográfica

> Projeto de Ciência de Dados desenvolvido como solução para o desafio do processo seletivo da **Indicium**.

## 📝 Descrição do Projeto

Este projeto realiza uma análise do dataset "IMDB Top 1000 Movies" com o objetivo de fornecer recomendações estratégicas para um estúdio de Hollywood fictício, a **PProductions**. A análise vai além dos dados fornecidos, utilizando uma abordagem de **enriquecimento de dados** através da API do The Movie Database (TMDb) para incluir informações financeiras cruciais como Orçamento (`Budget`) e Faturamento (`Revenue`).

Os dois pilares do projeto são:
1.  **Análise de Negócio:** Extrair insights sobre os fatores que impulsionam o sucesso financeiro (medido pelo Retorno sobre Investimento - ROI) e o sucesso de crítica/público (medido pela nota IMDB).
2.  **Modelagem Preditiva:** Construir e treinar um modelo de Machine Learning (usando XGBoost) para prever a nota IMDB de um filme com base em suas características.

## 🚀 Principais Insights de Negócio

A análise dos dados, combinando informações do IMDB e do TMDb, revelou conclusões estratégicas para a PProductions:

* **1. Sucesso Financeiro (ROI) ≠ Sucesso de Crítica (Nota IMDB):** A descoberta mais importante é que os fatores que levam à alta lucratividade não são os mesmos que levam à aclamação. O modelo preditivo confirmou isso ao atribuir baixa importância a features financeiras na previsão da nota.

* **2. A Fórmula da Lucratividade:** A maior lucratividade (ROI) não está nos blockbusters de maior faturamento, mas sim em gêneros de **orçamento controlado e alto apelo de público**, como **Terror** e **Família/Animação**.

* **3. A Fórmula da Aclamação:** O fator mais importante para prever uma alta nota de avaliação é o **"Star Power"**. A reputação prévia do **ator principal** e do **diretor** são os indicadores mais fortes de que um filme será bem recebido.

* **4. O Papel das Franquias:** Franquias e sequências não garantem, em média, uma avaliação superior à de filmes originais. Sua força reside na **mitigação de risco financeiro** ao capitalizar sobre uma base de fãs já existente.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3
* **Bibliotecas Principais:**
    * `Pandas` e `NumPy` para manipulação e limpeza de dados.
    * `Scikit-learn` para pré-processamento e engenharia de features.
    * `XGBoost` para a construção do modelo de regressão.
    * `Matplotlib` e `Seaborn` для создания визуализаций.
    * `Requests` para consumo da API do TMDb.
    * `Tqdm` para barras de progresso.
* **Ambiente:** Google Colab.

## 📁 Estrutura do Repositório

```
├── LH_CD_JuliaPedro.pkl    # Modelo treinado e componentes (scaler, encoders, etc.).
├── README.md              # Documentação do projeto (este arquivo).
├── analise_filmes.ipynb   # Notebook Jupyter com todo o código e a análise.
└── requirements.txt       # Lista de dependências para reprodução do ambiente.
```

## ⚙️ Como Executar o Projeto

1.  **Clone o Repositório**
    ```bash
    git clone [https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git](https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git)
    cd SEU-REPOSITORIO
    ```

2.  **Configure a Chave de API**
    * Para executar a etapa de enriquecimento de dados, é necessária uma chave de API do [The Movie Database (TMDb)](https://www.themoviedb.org/settings/api).
    * No notebook `analise_filmes.ipynb`, insira a chave na célula designada. O código está preparado para usar o gerenciador de "Secrets" do Google Colab para maior segurança.

3.  **Execute o Notebook**
    * Abra o arquivo `analise_filmes.ipynb` em um ambiente Jupyter (como o Google Colab) e execute as células em ordem.
    * O notebook possui uma **lógica de cache**: na primeira execução, ele buscará os dados na API (processo demorado) e salvará um arquivo `imdb_enriquecido.csv`. Nas execuções seguintes, ele carregará este arquivo diretamente, pulando a etapa da API.

## 📊 Performance do Modelo

O objetivo do modelo final era prever a nota do IMDB. A performance foi:
* **RMSE (Root Mean Squared Error):** ~0.23
* **R² (R-squared):** ~0.19

O R² relativamente baixo reforça o principal insight do projeto: métricas financeiras e de produção têm baixo poder explicativo sobre a aclamação final de um filme, que é um fenômeno altamente subjetivo e mais dependente de fatores de reputação (elenco e diretor).

## 👨‍💻 Autor
Julia Pedro Silva
* **[Seu Nome Completo]**
* **LinkedIn:** https://pt.linkedin.com/
* **GitHub:** https://www.youtube.com/watch?v=TsaLQAetPLU
