# 📊 Análise Exploratória (EDA): Campanha de Telemarketing Bancário

## 📌 Sobre o Projeto
Este projeto faz parte do meu portfólio de estudos aplicados em dados, criado com o objetivo de simular demandas reais do dia a dia de um Analista de Dados. 

Para este cenário, utilizei uma base de dados pública do **Kaggle** contendo mais de 45 mil registros de uma campanha de marketing bancário (oferta de depósitos a prazo). Através de **Inteligência Artificial**, simulei a atuação de um "Líder Técnico" para gerar demandas corporativas com foco em **Análise Exploratória de Dados (EDA)** e **Visualização de Dados (Data Visualization)**, a fim de extrair insights para a "Diretoria de Marketing".

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Manipulação de Dados:** `pandas`
* **Visualização Gráfica:** `matplotlib`, `seaborn`
* **Ambiente de Desenvolvimento:** Jupyter Notebook
* **Fonte dos Dados:** Kaggle

## 🗂️ Estrutura da Análise (Fases do Projeto)

### 1. Extração (Extract)
* Leitura do arquivo `.csv` bruto contendo 45.211 linhas.
* Adaptação da leitura para o padrão europeu de arquivos CSV, que utiliza o ponto e vírgula (`sep=';'`) como delimitador, garantindo a separação correta das 17 colunas.

### 2. Transformação e Engenharia de Features (Transform)
Para viabilizar a criação de gráficos e cálculos estatísticos, os dados passaram por transformações lógicas:
* **Conversão de Variável Alvo:** Transformação da coluna `Target` (que continha textos `"yes"` e `"no"`) para a variável numérica `Target_Int` (`1` e `0`), possibilitando o cálculo matemático da Taxa de Conversão.
* **Categorização de Idades:** Criação da coluna `age_group`, agrupando a idade exata dos clientes nas categorias *Jovem* (menor de 30), *Adulto* (30 a 50) e *Sênior* (maior que 50) para análises demográficas.

### 3. Visualização de Dados (Data Visualization)
Com os dados limpos, foram geradas visualizações analíticas em alta qualidade utilizando a biblioteca `seaborn`:
* **Perfil de Clientes (Gráfico de Barras Horizontais):** Mapeamento e ordenação das profissões (`job`) mais frequentes contatadas pelo banco.
* **Distribuição de Renda (Histograma):** Análise do saldo bancário (`balance`) dos clientes. Foi aplicado um filtro (limite entre 0 e 20.000) no eixo X para remover *outliers* milionários e focar na distribuição da massa principal de clientes.
* **Taxa de Conversão (Gráfico de Barras com Média):** Cruzamento do estado civil (`marital`) com o `Target_Int`, gerando automaticamente a média matemática que revelou qual perfil de relacionamento tem maior propensão a aceitar a oferta do banco.

### 4. Carga e Exportação (Load)
* Geração do dataset final limpo (`banco_tratado.csv`).
* Exportação dos gráficos gerados como imagens `.png` (utilizando `plt.savefig()` com ajuste `bbox_inches='tight'`) para apresentação executiva.

