
# Sistema de Avaliação Imobiliária com Regressão Linear

Este projeto tem como objetivo desenvolver um sistema de avaliação de imóveis no município do Rio de Janeiro utilizando técnicas de **regressão linear**. A ideia é prever o valor dos imóveis com base em variáveis como área, distância da praia e distância da farmácia mais próxima.

## 📌 Contexto

O mercado imobiliário brasileiro tem enfrentado desafios econômicos, o que aumenta a necessidade de estudos de precificação com base em dados reais. Com isso, aplicamos a metodologia de **Machine Learning supervisionado**, utilizando **regressão linear múltipla**.

---

## 📊 Dados

Utilizamos uma amostra aleatória de **5.000 imóveis** disponíveis para venda no município do Rio de Janeiro.

📁 Dataset disponível em:
[dataset.csv](https://raw.githubusercontent.com/TheGabrielVieira/regressao-linear-tecnicas-avan-adas/refs/heads/main/Dados/dataset.csv)

### Variáveis do conjunto de dados:

- `Valor`: Valor do imóvel (R$)
- `Area`: Área do imóvel (m²)
- `Dist_Praia`: Distância do imóvel até a praia (km)
- `Dist_Farmacia`: Distância até a farmácia mais próxima (km)

---

## 🧪 Tecnologias e Bibliotecas Utilizadas

- [Python 3.10+](https://www.python.org/)
- [Pandas](https://pandas.pydata.org/)
- [NumPy](https://numpy.org/)
- [Seaborn](https://seaborn.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [Scikit-learn](https://scikit-learn.org/)
- [Statsmodels](https://www.statsmodels.org/)

---

## ⚙️ Como Executar o Projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/TheGabrielVieira/regressao-linear-tecnicas-avan-adas.git
cd regressao-linear-tecnicas-avan-adas
```

### 2. Criar ambiente virtual (opcional, mas recomendado)

```bash
python -m venv venv
source venv/bin/activate    # Linux/macOS
venv\Scripts\activate     # Windows
```

### 3. Instalar as dependências

```bash
pip install -r requirements.txt
```

> Se ainda não tiver o arquivo `requirements.txt`, você pode gerar com:
```bash
pip freeze > requirements.txt
```

### 4. Executar o notebook Jupyter

```bash
jupyter notebook
```

Abra o notebook `.ipynb` do projeto e siga as células na ordem.

---

## 🔍 Etapas do Projeto

### 1. **Carregamento e inspeção dos dados**
- Visualização inicial
- Estatísticas descritivas
- Correlação entre variáveis

### 2. **Visualizações**
- Boxplot e histograma do valor dos imóveis
- Gráficos de dispersão simples e com linhas de regressão

### 3. **Transformações**
- Aplicação de transformação logarítmica para reduzir assimetria

### 4. **Divisão dos dados**
- Separação em dados de treino e teste (80/20)

### 5. **Estimação do modelo**
- Com todas as variáveis transformadas
- Remoção de variáveis irrelevantes (como `log_Dist_Farmacia`)
- Reestimação do modelo simplificado

### 6. **Avaliação do modelo**
- Coeficiente de determinação (R²)
- Interpretação dos coeficientes
- Previsões pontuais
- Reversão da escala logarítmica para reais (R$)
- Análise dos resíduos com histogramas e dispersão

---

## 📈 Exemplo de Previsão

```python
Area = 150
Dist_Praia = 1
entrada = [[np.log(Area), np.log(Dist_Praia + 1)]]

previsao = np.exp(modelo.predict(entrada)[0])
print(f'Valor estimado do imóvel: R$ {previsao:.2f}')
```

---

## 📌 Observações

- O modelo ainda pode ser melhorado com novas variáveis (ex: número de quartos, localização por bairro, tipo do imóvel, etc.).
- O logaritmo foi usado para tornar a distribuição mais simétrica e melhorar o ajuste do modelo.
- O projeto foi realizado e testado em ambiente Jupyter Notebook.

---

## 👨‍💻 Autor

Gabriel Vieira  
[github.com/TheGabrielVieira](https://github.com/TheGabrielVieira)

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.
