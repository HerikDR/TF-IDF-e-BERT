# Universidade Estadual de Londrina

**Curso:** Ciência de Dados e Inteligenda Artificial

**Disciplina:** 2COP019 - Aprendizado de Máquina Supervisionado

**Docente:** Bruno Squizato Faical

**Alunos:** Herik Daurizio Ricardo, Julia Yokoyama Massaki, Sofia Gutschow Casal

---

## Classificac̦ão de Sentimentos e Ańalise Comparativa: TF-IDF vs BERT

---

## 1. Fonte dos Dados

### Dataset de Avaliac̦ões do Mercado Livre

Este projeto utiliza dois arquivos JSON contendo avaliac̦ões de produtos do Mercado Livre (mercadolivre.com.br), em português do Brasil:

- **reviews_mercadolivre_com_br_1.json**: 103.476 registros
- **reviews_mercadolivre_com_br_2.json**: 103.476 registros

**Total combinado:** 206.952 registros

**Acesso ao dataset:** [Clique aqui](https://github.com/octaprice/ecommerce-product-dataset/tree/main/data/mercadolivre_com_br)

**Referência:** Octaprice. *E-commerce Product Dataset*. GitHub.

---

## 2. Modelo BERTimbau

Para a implementação baseada em transformers, utilizamos o modelo BERTimbau (BERT para português do Brasil), desenvolvido pela Neuralmind:

**Modelo:** bert-base-portuguese-cased

**Acesso:** [Clique aqui](https://huggingface.co/neuralmind/bert-base-portuguese-cased)

**Referência:** Neuralmind. *BERT-base-portuguese-cased*. Hugging Face.

---

## 3. Visão Geral da Implementac̦ão

Este notebook implementa uma soluc̦ão para triagem de avaliac̦ões de produtos do Mercado Livre em PT/BR. O fluxo de implementação foi organizado em tres etapas principais:

### 3.1 Dados e Baseline TF-IDF

Carregamento dos dados JSON, extração, limpeza e tratamento dos dados, definic̦ão do esquema bińario para classificac̦ão de sentimentos, balanceamento da distribuic̦ão das classes, divisão estrita em conjuntos de treino/validac̦ão/teste, e treinamento do método baseline utilizando TF-IDF (Term Frequency-Inverse Document Frequency) com classificador supervisionado.

### 3.2 Fine-tuning com BERTimbau

Preparac̦ão textual adequada para modelos Transformers, incluindo tokenizac̦ão especializada para portugûes, aplicac̦ão de fine-tuning no modelo BERTimbau, treinamento utilizando a mesma divișao estrita do baseline, e avaliac̦ão do desempenho do modelo.

### 3.3 Análise Comparativa

Comparac̦ão quantitativa das métricas de desempenho (acurácia, precisão, F1-score) no mesmo conjunto de teste entre os dois modelos, e investigac̦ão qualitativa dos erros de classificac̦ão, incluindo análise das características dos exemplos mal classificados por cada abordagem.

---

## 4. Tutorial de Implementac̦ão

### 4.1 Preparac̦ão do Dataset

1. Baixar os arquivos JSON do dataset:
   - [reviews_mercadolivre_com_br_1.json](https://github.com/octaprice/ecommerce-product-dataset/tree/main/data/mercadolivre_com_br)
   - [reviews_mercadolivre_com_br_2.json](https://github.com/octaprice/ecommerce-product-dataset/tree/main/data/mercadolivre_com_br)

2. Criar uma pasta chamada `dataset` dentro da pasta do projeto

3. Mover os arquivos JSON baixados para a pasta `dataset/`

### 4.2 Instalação das Dependencias

1. Garantir que Python 3.14 está instalado no sistema

2. Executar o comando no console para instalar as bibliotecas necessárias:

```bash
pip install -r requirements.txt
```

### 4.3 Execução do Notebook

1. Abrir o notebook `triagem_avaliacoes.ipynb` utilizando Jupyter Notebook, JupyterLab, ou outro ambiente compatível

2. Executar todas as células do notebook sequencialmente

3. Analisar os resultados das métricas de desempenho e a análise comparativa entre TF-IDF e BERTimbau

---

## 5. Referências Teóricas

Este trabalho baseia-se nos seguintes artigos científicos:

### 5.1 BERTimbau para Classificac̦ão de Emoc̦ões

**Hammes, Luiz; Freitas, Larissa.** *Utilizando BERTimbau para a Classificac̦ão de Emoc̦ões em Português.* Proceedings of the 13th Brazilian Symposium in Information and Human Language Technology, p. 56-63, 2021.

Este artigo apresenta a aplicac̦ão do modelo BERTimbau para classificac̦ão de emoc̦ões em texto em português, fornecendo a base téorica para o uso de transformers em tarefas de NLP em língua portuguesa.

### 5.2 TF-IDF para Minerac̦ão de Texto

**Qaiser, Shahzad; Ali, Ramsha.** *Text mining: use of TF-IDF to examine the relevance of words to documents.* International Journal of Computer Applications, v. 181, n. 1, p. 25-29, 2018.

Este trabalho discute o uso da métrica TF-IDF (Term Frequency-Inverse Document Frequency) para avaliar a relevância de palavras em documentos, estabelecendo a base metodológica para o modelo baseline utilizado neste projeto.

---

## 6. Estrutura do Projeto

```
projeto-aprendizado-maquina/
├── triagem_avaliacoes.ipynb    # Notebook principal da implementac̦ão
├── requirements.txt            # Dependencias do Python
├── dataset/                    # Pasta contendo os arquivos JSON
│   ├── reviews_mercadolivre_com_br_1.json
│   └── reviews_mercadolivre_com_br_2.json
├── README.md                   # Este arquivo
```
