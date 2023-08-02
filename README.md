# NBA Data Crawler - Airflow
Somente linux!<br>
Autor: [@caiocolares](https://www.github.com/caiocolares)

## Configurando o projeto

1. Clone o projeto:
```bash
  git clone https://github.com/thiagosegato/nba-crawler-airflow.git
```

2. Acesse a pasta:
```bash
  cd nba-crawler-airflow
```

2.1. (Passo Opcional) A partir daqui você poderá optar a utilizar o Vscode. Caso prefira esse passo execute o comando abaixo para abrir a IDE:
```
code .
```
* Dica: Você pode iniciar um terminal dentro do próprio Vscode para continuar a configurar o projeto!

3. Crie um ambiente virtual python:
```
python3 -m venv .venv
source .venv/bin/activate
```

4. Instale o Airflow e as bibliotecas necessárias:
```
AIRFLOW_VERSION=2.6.2
PYTHON_VERSION="$(python3 --version | cut -d " " -f 2 | cut -d "." -f 1-2)"
CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"
pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}" \
  beautifulsoup4 lxml pandas
```

## Rodando o projeto

1. Ative o ambiente virtual python caso não esteja:
```
source .venv/bin/activate
```

2. Inicie o Airflow com 2 variáveis de ambiente:
```
export AIRFLOW_HOME=$(pwd)
export AIRFLOW__CORE__LOAD_EXAMPLES=False
airflow standalone
```

## Acessando a ferramenta
Acesse [http://localhost:8080](http://localhost:8080)<br>
Usuário: admin<br>
Senha: Copie a senha no arquivo `standalone_admin_password.txt`

#### Gráfico
![image](https://github.com/caiocolares/nba-crawler-airflow/assets/26276218/e50628a5-d4f7-4259-9754-1c5b2c5d9593)

#### Dag rodando
![image](https://github.com/caiocolares/nba-crawler-airflow/assets/26276218/6bdf4a65-c794-4735-9727-442d90a08ebd)

#### Testando o Operador diretamento do vscode
![image](https://github.com/caiocolares/nba-crawler-airflow/assets/26276218/b8bd4a52-6541-4cd1-ada0-e8eac02d8c86)

### Bibliotecas utilizadas
- [Airflow](https://airflow.apache.org/)
- [Pandas](https://pandas.pydata.org/)
- [BeautifulSoup4](https://pypi.org/project/beautifulsoup4/)
