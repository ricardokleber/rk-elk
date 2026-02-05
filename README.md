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

