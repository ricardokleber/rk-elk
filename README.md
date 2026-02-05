<img width="500" height="160" src="https://github.com/user-attachments/assets/6e275aa5-c639-40f6-9953-85b9382063bf" />

***
### 1. Para agilizar baixe (faça o 'pull') das 3 imagens que vamos utilizar:

```
docker pull ricardokleber/rk-elasticsearch:latest
```
```
docker pull ricardokleber/rk-kibana:latest
```
```
docker pull ricardokleber/rk-logstash:latest
```

### 2. Crie um diretório para o projeto:

```
mkdir rk-elk
```
```
cd rk-elk
```

### 3. Baixe o docker-compose pronto usando 'git clone':

```
git clone https://github.com/ricardokleber/rk-elk.git
```

### 4. Crie/instale os Dockers:

```
docker compose up -d
```

### 5. O contêiner que mais demora para ficar pronto (e que todos os demais dependem dele) é o Elasticsearch. Verifique se os logs param de ser gerados para que você possa seguir nas próximas configurações:

```
docker compose logs -f elasticsearch
```

### 6. Solicite agora que o Elasticsearch crie uma senha randômica para o usuário administrativo 'elastic':

```
docker exec -it elasticsearch /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic
```
## O Resultado será algo como:

`Password for the [elastic] user successfully reset.`

`New value: sqyTGEXI=CpgcWGDEyNY`

## A senha do usuário será esse valor indicado em 'New value' (copie e guarde para acessar o sistema).

### 7. Usando um navegador acesse o Elasticsearch usando a URL:
```
http://localhost:9200
```

### Forneça como credenciais o login 'elastic' e a senha gerada no tópico anterior:
<img width="394" height="201" src="https://github.com/user-attachments/assets/27b6114f-2017-4440-bb8b-9ab2074eb9c7" />

## O Resultado será algo como:
<img width="394" height="247" src="https://github.com/user-attachments/assets/1f41d19a-798f-4b93-a3bd-6e5cc2aaea55" />
