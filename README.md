# 📱 Classificação de Faixa de Preço de Celulares — KNN

Trabalho interdisciplinar desenvolvido para as disciplinas de **Matemática para Computação**, **Inteligência Artificial e suas Aplicações**, **Fundamentos de Programação** e **Fundamentos de Lógica** — UniEduK / UniFAJ.

O objetivo do projeto é implementar e analisar o algoritmo **K-Nearest Neighbors (KNN)** aplicado à classificação de celulares em faixas de preço, com base em suas especificações técnicas.

---

## 👥 Integrantes do Grupo

| Nome | RA |
|------|----|
| Felipe Panini da Silva | 12631337 |
| Paulo Vitor Sando | 10722709 |
| David Fernando de Moraes Leitão | 12631713 |
| Manuela Caceres do Nascimento | 12632100 |
| Patrícia Andrade da Silva | 11513882 |

---

## 📂 Estrutura do Repositório

```
📦 Trabalho-Interdisciplinar---Mobile-Price
├── 📊 Dados
│   ├── mobile_price_dataset.xlsx          ← Dado bruto original
│   ├── mobile_price_dataset_silver.csv    ← Dado com tratamento intermediário
│   └── mobile_price_dataset_golden.csv    ← Dado final utilizado no modelo
│
├── 📓 Notebooks
│   ├── Celulares_Price.ipynb              ← Análise exploratória e pré-processamento
│   ├── KNN_Manual.ipynb                   ← Implementação manual do KNN (sem biblioteca)
│   └── KNN_Biblioteca.ipynb               ← Implementação do KNN com scikit-learn
│
└── 📄 Relatório
    └── Relatorio_Final.pdf                ← Relatório completo do trabalho
```

---

## 📁 Descrição dos Arquivos

### Dados

| Arquivo | Descrição |
|---------|-----------|
| `mobile_price_dataset.xlsx` | Dataset bruto com 2.000 registros e 21 atributos de especificações técnicas de celulares. Fonte original sem qualquer modificação. |
| `mobile_price_dataset_silver.csv` | Versão intermediária do dataset com renomeação de colunas (ex.: `blue` → `bluetooth`, `fc` → `front_camera`) para melhor legibilidade. |
| `mobile_price_dataset_golden.csv` | Versão final utilizada no treinamento do modelo. Contém apenas os 4 atributos selecionados: `battery_power`, `clock_speed`, `n_cores` e `ram`, além da variável alvo `price_range`. |

### Notebooks

#### `Celulares_Price.ipynb` — Análise Exploratória e Pré-processamento
Notebook inicial com a análise exploratória do dataset. Contém:
- Carregamento e visualização dos dados brutos
- Verificação de formato, tipos e quantidade de registros
- Normalização Min-Max dos atributos selecionados
- Divisão dos dados em treino (80%) e teste (20%)

#### `KNN_Manual.ipynb` — KNN Implementado do Zero
Implementação completa do algoritmo KNN **sem o uso de bibliotecas prontas**. Contém:
- Função de **Distância Euclidiana** implementada manualmente
- Função principal do KNN com identificação dos K vizinhos mais próximos e votação por maioria
- Testes com diferentes valores de K (1, 5, 10, 15, 20, 30, 50, 60, 65, 70, 250)
- Análise e interpretação dos resultados por valor de K
- **Melhor resultado:** K = 60 → Acurácia de **82,25%**

#### `KNN_Biblioteca.ipynb` — KNN com scikit-learn
Implementação do mesmo algoritmo utilizando a biblioteca **scikit-learn**. Contém:
- Uso do `KNeighborsClassifier` da biblioteca sklearn
- Divisão estratificada dos dados com `train_test_split`
- Normalização com `MinMaxScaler`
- Testes com diferentes valores de K (1, 5, 15, 25, 50, 100, 150)
- Matriz de confusão e relatório de classificação completo
- **Melhor resultado:** K = 50 → Acurácia de **80,00%**

---

## 🎯 Sobre o Dataset

O dataset contém especificações técnicas de 2.000 modelos de smartphones. A variável alvo é `price_range`, que classifica os aparelhos em 4 categorias:

| Valor | Categoria |
|-------|-----------|
| 0 | Baixo custo |
| 1 | Custo médio |
| 2 | Alto custo |
| 3 | Custo muito alto |

### Atributos selecionados para o modelo

Após análise exploratória, foram escolhidos 4 atributos com maior correlação com a faixa de preço:

| Atributo | Descrição |
|----------|-----------|
| `battery_power` | Capacidade da bateria em mAh |
| `clock_speed` | Velocidade do processador em GHz |
| `n_cores` | Número de núcleos do processador |
| `ram` | Memória RAM em MB |

---

## ▶️ Como Executar

### Pré-requisitos

```bash
pip install pandas numpy scikit-learn
```

### Ordem de execução recomendada

1. Abra e execute `Celulares_Price.ipynb` para entender o pré-processamento dos dados
2. Execute `KNN_Manual.ipynb` para ver a implementação manual do KNN
3. Execute `KNN_Biblioteca.ipynb` para ver a implementação com scikit-learn e a comparação de resultados

> **Observação:** os notebooks carregam o dataset diretamente do Google Drive via URL pública, portanto é necessária conexão com a internet.

---

## 📊 Resultados

| Implementação | Melhor K | Acurácia |
|---------------|----------|----------|
| KNN Manual | 60 | 82,25% |
| KNN com scikit-learn | 50 | 80,00% |

Para a análise completa e comparação detalhada entre as duas abordagens, consulte o relatório final (`Relatorio_Final.pdf`).
