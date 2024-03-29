# Computação UFCG

## Instale e configure o PostgreSQL
```
sudo apt-get install -y postgresql-12
sudo su postgres

export computacao_ufcg_user=computacao_ufcg_user
export computacao_ufcg_password=computacao_ufcg_password
export computacao_ufcg_db_name=computacao_ufcg_db_name

psql -c "CREATE USER computacao_ufcg_user WITH PASSWORD 'computacao_ufcg_password';"
psql -c "CREATE DATABASE computacao_ufcg_db_name OWNER computacao_ufcg_user;"
psql -c "GRANT ALL PRIVILEGES ON DATABASE computacao_ufcg_db_name TO computacao_ufcg_user;"
exit
```

## Teste se o BD foi criado com
```
PGPASSWORD=computacao_ufcg_password psql -h localhost computacao_ufcg_db_name computacao_ufcg_user
```

## Clone o repositório
```
git clone https://github.com/cilasmarques/ufcg-comp-app-api
cd ufcg-comp-app-api
```

## Crie um ambiente virtual e instale as dependencia
* Instale o python
  ```
  sudo apt-get install python3.8
  ```

* Crie o ambiente virtual
  ```
  sudo apt install python3.8-venv
  python3 -m venv computacaoUFCG
  ```

* Inicie o ambiente e instale as dependencias
  ```
  source computacaoUFCG/bin/activate
  pip install -r requirements.txt
  ```

## Inicie o projeto
  ```
  bash bin/start.sh
  ```
