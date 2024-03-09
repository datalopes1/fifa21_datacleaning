
# 🧹 Limpeza e Manipulação de Dados com Dataset FIFA 21

Neste projeto foi feito o processo de limpeza e manipulação a partir do dataset FIFA 21 messy, raw dataset for cleaning/ exploring, que pode ser encontrado no [Kaggle](https://www.kaggle.com/datasets/yagunnersya/fifa-21-messy-raw-dataset-for-cleaning-exploring?select=fifa21+raw+data+v2.csv), com licensa CC0: Public Domain e enviado por [Rachit Toshniwal](https://www.kaggle.com/yagunnersya).

### 🛠️ Ferramentas utilizadas
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## 1.1. Os dados, o problema e os objetivos

O dataset utilizado é resultado de um process de webscrapping, e naturalmente os dados não estão limpos. Os dados foram extraídos do site sofifa.com na época de lançamento do FIFA 21 lançado em 2020.

Portando o objetivo é explorar os dados e fazer todos os processos de limpeza necessários.

## 1.2. Importação das bibliotecas e carregamento dos dados

Foram feitas as importações do pandas, numpy, datetime e os. 

# 🔍 2. Entendendo os dados
## 2.1. Observando com métodos 

Com os métodos shape, head(), tail() e info() - busquei entender quais seriam os objetivos do processo de limpeza.

## 2.2. Breves conclusões e identificação dos objetivos concretos do projeto
Após analisar com os métodos, cheguei a conclusão que os objetivos seriam:

- As colunas 'LongName', 'photoUrl', 'playerUrl', podem ser removidas.
- A coluna 'Club' pode ser limpa para remover os caracteres \n\n\n\n de seus nomes.
- A coluna 'Contract' está em um formato que pode ser melhorado, com a criação de uma coluna 'Contract_start_year' e 'Contract_end_year' e sua alteração para três status de contrato: 'Active', 'Free' e 'On Loan'.
- As colunas 'Height' e 'Weight' estão com dtype object, e alguns registros estão fora do - Sistema Internacional de Unidades, o que deve ser corrigido.
- A coluna 'Joined' pode ser convertido para datetime, e a coluna 'Loan Date End' pode ser transformada em base para preencher o 'Contract_end_year' dos jogadores On Loan.
- As colunas que envolvem valores monetários, devem ser convertidas para o dtype float e ter removidos os símbolos de Euro e multiplicar valores terminados em K por 1.000 e em M por 1.000.000.
- As colunas 'W/F', 'SM' e 'IR' possuem uma estrela que deve ser removida, e os valores transformados no dtype int.
- A coluna Hits tem um problema parecido com o das colunas de valores com um K equivalendo a 1000, com o adendo de um problema com os tipos dos dados.

# 🏗️ 3. Limpeza a manipulação dos dados
Neste ponto foi realizado todo o processo de limpeza e manipulação dos dados afim de atingir os objetivos traçados, e ao fim foi criado um novo dataset limpo. 

