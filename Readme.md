

## Projeto 5 - Biopark


### Setup de Ambiente DEV

> Requisitos: Python V3


#### Passo 1 - Criando virtual env (raiz do projeto clonado)
```bash
python3 -m venv .venv
```
Ativando o virtual env

```
.venv\Script\activate
```

#### Passo 2 - Instalando Requisitos

```
pip install -r requirements.txt
```


#### Passo 3 - Carregando Fixtures

```
python manage.py loaddata projeto5_website\fixtures\initial_data.json
```

#### Passo 4 - Criando superusuário

```
python manage.py createsuperuser
```


#### Passo 5 - Rodando Server

```
python manage.py runserver
```

Aponte seu navegador para [Link](http://localhost:8000/)




## Rotinas de manutenção de código
---

### Salvando banco de dados


Esse comando colocará o conteúdo do banco para a aplicação em um arquivo json. Preencha a *aplicação*  de acordo com a sua, o caminho de saída é onde o arquivo será armazenado.

```
python manage.py dumdata --indent 4 *aplicação* > path_arquivo_saída.json
```

### Criando lista de dependências

O pip freeze gerará uma lista de pacotes python instalados no .venv. Sempre que usar um novo pacote lembre de deixar o mesmo no arquivo de requirements para que os próximos programadores possam subir o django sem problemas.

### Migrações

As migrações podem ser regeradas sempre que necessário. Através do comando **"manage.py makemigrations"** o banco é comparado com os arquivos dentro do migrations. 

Se quiser gerar arquivos de migrations zerados, basta apagar todos os migrations, apagar o banco de dados e rodar o makemigrations.

***Atenção, caso faça muitas alterações os fixtures deixarão de funcionar***