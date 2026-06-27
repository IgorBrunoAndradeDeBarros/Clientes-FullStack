#  Sistema de Gestão de Clientes e Serviços (Full-Stack)

Bem-vindo ao repositório do **Clientes-FullStack**! Este é um sistema web completo (Front-End e Back-End) desenvolvido para facilitar o gerenciamento de clientes e o controle de serviços prestados a eles.

O objetivo do sistema é fornecer uma interface intuitiva para cadastrar clientes, registrar serviços vinculados a esses clientes, definir valores e pesquisar o histórico de serviços por filtros específicos (nome e mês).

---

##  Funcionalidades

- **Gestão de Clientes:** Cadastro, listagem, edição e exclusão de clientes (CRUD completo).
- **Registro de Serviços:** Lançamento de serviços prestados, vinculando ao cliente, com descrição, valor e data.
- **Filtros e Buscas:** Consulta de serviços prestados filtrando por nome do cliente e mês de realização.
- **Autenticação:** Cadastro e login de usuários com JWT.
- **Validações:** O sistema conta com validações robustas tanto no Front-End quanto no Back-End (ex: CPF válido, campos obrigatórios).

---

##  Tecnologias Utilizadas

###  Front-End (SPA)
- **Angular:** 9.1.1
- **Node.js:** 16.20.2
- **HTML5 / CSS3 / TypeScript**
- **Bootstrap**

### ️ Back-End (API REST)
- **Java:** JDK 21
- **Spring Boot:** 3.3.3
- **Spring Data JPA**
- **Banco de Dados:** H2 Database (em memória)
- **SpringDoc OpenAPI (Swagger)**
- **Lombok**
- **Maven**

###  Infraestrutura
- **Docker & Docker Compose**
- **Nginx** (reverse proxy + servir o front-end)

---

##  Como Executar com Docker (Recomendado)

### Pré-requisitos
- [Docker](https://www.docker.com/) instalado
- [Docker Compose](https://docs.docker.com/compose/) instalado

### Passo a Passo

1. Clone o repositório:
```bash
git clone https://github.com/IgorBrunoAndradeDeBarros/Clientes-FullStack.git
cd Clientes-FullStack
```

2. Suba os containers:
```bash
docker compose up --build -d
```

3. Acesse a aplicação no navegador:
```
http://localhost
```

> A API estará disponível em `http://localhost/api` e a documentação Swagger em `http://localhost:8080/swagger-ui/index.html` (acesso direto ao backend).

### Parar os containers
```bash
docker compose down
```

### Ver logs
```bash
docker compose logs -f
```

---

##  Como Executar Manualmente (sem Docker)

### Pré-requisitos

1. **Java JDK 21**
2. **Maven 3.8+**
3. **Node.js 16.20.2**
4. **Angular CLI 9.1.1**
```bash
npm install -g @angular/cli@9.1.1
```

### Passo 1: Clonar o Repositório

```bash
git clone https://github.com/IgorBrunoAndradeDeBarros/Clientes-FullStack.git
cd Clientes-FullStack
```

### Passo 2: Rodando o Back-End

```bash
cd clientes
mvn clean install
mvn spring-boot:run
```

A API estará em: **http://localhost:8080**  
Swagger: **http://localhost:8080/swagger-ui/index.html**

### Passo 3: Rodando o Front-End

Em um novo terminal:

```bash
cd clientes-app
npm install
npm run start
```

A aplicação estará em: **http://localhost:4200**

---

##  Estrutura do Repositório

```text
/Clientes-FullStack
├── clientes/                 # Back-End (Spring Boot / Java)
│   ├── src/main/java/        # Controllers, Entidades, Repositórios, Configurações
│   ├── src/main/resources/   # application.properties
│   └── pom.xml
│
├── clientes-app/             # Front-End (Angular / TypeScript)
│   ├── src/app/              # Componentes, Serviços, Módulos
│   ├── nginx.conf            # Configuração do Nginx (proxy reverso)
│   ├── Dockerfile
│   ├── package.json
│   └── angular.json
│
└── docker-compose.yml        # Orquestração dos containers
```
