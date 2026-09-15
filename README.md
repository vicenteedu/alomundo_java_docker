

# ☕ Java com Docker

Projeto simples desenvolvido em **Java** com o objetivo de praticar a criação, compilação e execução de uma aplicação Java utilizando também **Docker** para criar um ambiente isolado e reproduzível.

O programa executa uma classe Java e exibe uma mensagem no terminal.

---

## 📋 Sobre o projeto

Este projeto utiliza uma aplicação Java simples para demonstrar conceitos básicos como:

* Estrutura de uma aplicação Java;
* Método `main`;
* Compilação e execução pelo terminal;
* Criação de uma imagem Docker;
* Execução da aplicação dentro de um container;
* Uso de comandos básicos do Docker.

Ao executar o programa, será exibido:

```text
Hello World!
```

---

## 🛠️ Tecnologias utilizadas

* **Java**
* **JDK**
* **Docker**
* **Docker Desktop**
* **Git**
* **GitHub**

---

## 📂 Estrutura do projeto

```text
projeto/
│
├── Principal.java
├── Dockerfile
└── README.md
```

### `Principal.java`

Arquivo principal da aplicação contendo o método `main`.

### `Dockerfile`

Arquivo responsável pelas instruções utilizadas pelo Docker para criar a imagem da aplicação.

### `README.md`

Documentação do projeto.

---

## ✅ Pré-requisitos

Para executar o projeto localmente, é necessário possuir o Java instalado.

Verifique utilizando:

```bash
java -version
```

Para verificar o compilador Java:

```bash
javac -version
```

Para executar utilizando Docker, é necessário instalar o **Docker Desktop**.

### 🐳 Docker Desktop

Download oficial:

https://www.docker.com/products/docker-desktop/

Documentação oficial:

https://docs.docker.com/

Após instalar, verifique se o Docker está funcionando:

```bash
docker --version
```

Também é possível testar utilizando:

```bash
docker run hello-world
```

---

# ▶️ Executando sem Docker

Primeiro, clone o repositório:

```bash
git clone URL_DO_REPOSITORIO
```

Entre na pasta do projeto:

```bash
cd nome-do-projeto
```

Compile o programa:

```bash
javac Principal.java
```

Após a compilação, será criado o arquivo:

```text
Principal.class
```

Execute o programa:

```bash
java Principal
```

Resultado esperado:

```text
Hello World!
```

---

# 🐳 Executando com Docker

Antes de executar os comandos, certifique-se de que o **Docker Desktop esteja aberto e em execução**.

## 1. Criar o Dockerfile

Na raiz do projeto, crie um arquivo chamado:

```text
Dockerfile
```

Exemplo:

```dockerfile
FROM eclipse-temurin:21-jdk

WORKDIR /app

COPY Principal.java .

RUN javac Principal.java

CMD ["java", "Principal"]
```

O Dockerfile utiliza uma imagem Java baseada no **Eclipse Temurin JDK 21**.

---

## 2. Criar a imagem Docker

Dentro da pasta onde está o `Dockerfile`, execute:

```bash
docker build -t java-docker .
```

Onde:

* `docker build` cria uma nova imagem;
* `-t` define um nome para a imagem;
* `java-docker` é o nome escolhido para a imagem;
* `.` indica que o Dockerfile está no diretório atual.

Para verificar se a imagem foi criada:

```bash
docker images
```

---

## 3. Executar o container

Execute:

```bash
docker run java-docker
```

Resultado esperado:

```text
Hello World!
```

---

## 📦 Executando o container de forma interativa

Caso queira acessar um terminal dentro de um container, pode utilizar:

```bash
docker run -it java-docker /bin/bash
```

O parâmetro `-it` permite utilizar o terminal de forma interativa.

---

## 📋 Comandos Docker úteis

Listar imagens disponíveis:

```bash
docker images
```

Listar containers em execução:

```bash
docker ps
```

Listar todos os containers:

```bash
docker ps -a
```

Executar uma imagem:

```bash
docker run java-docker
```

Remover um container:

```bash
docker rm ID_DO_CONTAINER
```

Remover uma imagem:

```bash
docker rmi java-docker
```

Parar um container:

```bash
docker stop ID_DO_CONTAINER
```

---

## 🔄 Fluxo do projeto

O funcionamento utilizando Docker pode ser resumido da seguinte maneira:

```text
Código Java
    ↓
Principal.java
    ↓
Dockerfile
    ↓
docker build
    ↓
Imagem Docker
    ↓
docker run
    ↓
Container
    ↓
Aplicação Java executada
```

---

## 🧠 Conceitos praticados

Durante o desenvolvimento deste projeto foram utilizados conceitos de:

### Java

* Classes;
* Método `main`;
* Compilação com `javac`;
* Execução através da JVM;
* Saída de dados pelo console.

### Docker

* Imagens;
* Containers;
* Dockerfile;
* `docker build`;
* `docker run`;
* `docker ps`;
* `docker images`;
* Ambientes isolados.

---

## 🐳 O que é Docker?

Docker é uma plataforma que permite empacotar uma aplicação junto com o ambiente necessário para sua execução.

Dessa forma, ao invés de depender diretamente da configuração da máquina onde o projeto será executado, podemos criar uma **imagem Docker** contendo o Java e a aplicação.

Essa imagem pode então ser utilizada para criar **containers**, garantindo maior consistência entre diferentes ambientes.

---

## 📚 Links úteis

* [Docker](https://www.docker.com/)
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)
* [Documentação Docker](https://docs.docker.com/)
* [Docker Hub](https://hub.docker.com/)
* [Eclipse Temurin](https://adoptium.net/)
* [Documentação Java](https://docs.oracle.com/en/java/)

---

## 🎯 Objetivo

Este projeto foi desenvolvido com finalidade acadêmica e de aprendizado, buscando colocar em prática conceitos fundamentais de **Java** e introduzir o uso de **Docker** para criação e execução de aplicações em containers.

---

## 👨‍💻 Autor

**Vicente Eduardo**

Estudante de Ciência da Computação

GitHub: [vicenteedu](https://github.com/vicenteedu)

---

## 📄 Licença

Projeto desenvolvido para fins de estudo e aprendizado.
