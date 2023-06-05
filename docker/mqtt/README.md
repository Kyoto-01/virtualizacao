# TUTORIAL: Configuração do broker MQTT Mosquitto em um container Docker

## 1. Preparando o ambiente

### 1.1. Verifique as seguintes dependências:

* docker

### 1.2. Baixe o repositório com o dockerfile e os arquivos de configuração do Mosquitto.

```sh
git clone https://github.com/Kyoto-01/virtualizacao.git
```

```sh
cd virtualizacao/docker/mqtt
```

### 1.3. Construa a imagem a partir do dockerfile contido em `virtualizacao/docker/mqtt`.

```sh
sudo docker build -t meu-broker-mqtt:1.0 .
```

## 2. Subindo o container

### 2.1. Veja o endereço do broker.

```sh
ip a
```

### 2.2. Suba o container.

```sh
sudo docker run -p 1883:1883 --rm meu-broker-mqtt:1.0
```

## 3. Teste do broker

### 3.1 Abra um novo terminal e digite:

```sh
mosquitto_sub -h endereço_do_broker -t test
```

### 3.2 Abra mais um terminal e digite:

```sh
mosquitto_pub -h endereço_do_broker -t test -m "hello world!"
```

Agora verifique o terminal do passo 3.1, a mensagem publicada deve estar impressa na tela.



