# Atividade Sudoku

# Sudoku 4x4 com Rede Neural Artificial Multicamadas

## Visão Geral

Este projeto implementa uma Rede Neural Artificial (RNA) Multicamadas capaz de aprender e resolver tabuleiros Sudoku 4x4 parcialmente preenchidos.

A solução utiliza aprendizado supervisionado, onde a rede é treinada com exemplos de tabuleiros incompletos e suas respectivas soluções corretas.

---

## Arquitetura da Solução

### Geração dos Dados
- Criação automática de tabuleiros Sudoku 4x4 válidos.
- Remoção aleatória de células para formar os problemas de entrada.
- Separação em conjuntos de treinamento e teste.

### Pré-processamento
- Conversão dos tabuleiros para representação One-Hot Encoding.
- Preparação dos dados para entrada na rede neural.

### Rede Neural Multicamadas

Arquitetura implementada:

```text
Entrada (16 células × 4 possibilidades)
        ↓
Flatten
        ↓
Dense(128) + ReLU
        ↓
Dense(128) + ReLU
        ↓
Dense(64) + ReLU
        ↓
Dense(64)
        ↓
Reshape(16 × 4)
        ↓
Softmax
```

### Validação
Após a predição, o tabuleiro gerado é validado para verificar:

- Linhas sem repetição
- Colunas sem repetição
- Blocos 2x2 válidos

---

## Tecnologias Utilizadas

- Python
- NumPy
- TensorFlow / Keras

---

## Execução

Instale as dependências:

```bash
pip install numpy tensorflow
```

Execute:

```bash
python sudoku_rna.py
```

---

## Generalização para NxN

A implementação foi desenvolvida para Sudoku 4x4, porém pode ser adaptada para Sudoku NxN mediante alterações em:

- Dimensão da grade
- Tamanho dos blocos
- Quantidade de entradas da RNA
- Quantidade de saídas da RNA
- Conjunto de treinamento

As principais dificuldades são o aumento da dimensionalidade, do custo computacional e da necessidade de mais exemplos para treinamento.

---

Projeto acadêmico desenvolvido para estudo de Redes Neurais Artificiais e Inteligência Artificial.
