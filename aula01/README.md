# Bootcamp dbt Core

Projeto do bootcamp de dbt Core da [Jornada de Dados](www.suajornadadedados.com.br)

## O que é dbt?

O dbt é um workflow de transformação focado em SQL que permite que equipes implementem código analítico de forma rápida e colaborativa, seguindo as melhores práticas de engenharia de software, como modularidade, portabilidade, CI/CD e documentação. Agora, qualquer pessoa da equipe de dados pode contribuir com segurança para pipelines de dados de nível de produção.

[documentação](https://www.getdbt.com/product/what-is-dbt)

## Arquitetura moderna

Esse projeto tem como objetivo apresentar de forma prática uma solução completa de dados aproveitando os principais módulos e funcionalidades do dbt-core.

## Introdução

A ferramenta dbt (data build tool) é uma solução inovadora no campo da engenharia de dados, projetada para conectar-se a repositórios de dados centralizados como Data Warehouses e Data Lakes. Ela habilita usuários de negócios, analistas e engenheiros a gerar transformações de dados, regras de negócios e insights valiosos de forma autônoma e eficiente.

## Objetivo do Projeto

O objetivo deste projeto é implementar uma solução de dados que foi inicialmente desenvolvida utilizando um processo padrão no PostgreSQL (criação de tabelas, views, procedures, etc.), mas agora utilizando dbt-core. A proposta é comparar as duas abordagens para evidenciar as vantagens e simplificações que o dbt-core pode oferecer em termos de manutenção, colaboração e escalabilidade das transformações de dados.

## Pré-requisitos

Antes de começar, certifique-se de ter os seguintes softwares instalados em seu sistema:

- [Git](https://git-scm.com/downloads): Para clonar o repositório.
- [Docker](https://www.docker.com/products/docker-desktop): Para executar os contêineres do PostgreSQL, pgAdmin e dbt.
- [Python](https://www.python.org/downloads/): Para rodar scripts auxiliares.
- [Poetry](https://python-poetry.org/docs/): Para gerenciar o ambiente do projeto.

## Hello World

### 1. Clonar o Repositório

Primeiro, clone este repositório para o seu ambiente local usando Git. Abra um terminal e execute o seguinte comando:

```sh
git clone https://github.com/Rafasansouza/bootcamp-dbt-core.git
cd bootcamp-dbt-core/dbt-northwind
```

### 2. Executar os Contêineres Docker

Com o Docker instalado, execute o seguinte comando para iniciar os contêineres:

```sh
docker-compose up --build
```

Isso iniciará os contêineres necessários: PostgreSQL e pgAdmin.

### 3. Acessar o pgAdmin para visualizar o seu banco

Para acessar o pgAdmin e visualizar os dados, abra seu navegador e vá para:

- URL: `http://localhost:5050/browser/`

Use as seguintes credenciais para se conectar ao banco de dados:

- **Host**: `db`
- **Porta**: `55432`
- **Nome do Banco**: `northwind`
- **Usuário**: `postgres`
- **Senha**: `postgres`

Vamos trabalhar nesse projeto com a base northwind

O dbt é uma ferramenta focada na transformação de dados dentro de um pipeline de ETL/ELT, onde ETL significa Extrair, Transformar e Carregar. Ele se concentra especificamente no aspecto de Transformação (T), permitindo a criação de fluxos de trabalho de transformação de dados usando SQL.

### 3. O diretório `bootcamp-dbt-core/dbt-northwind/dbt_project` é o projeto dbt. Caso queira iniciar do zero essa parte, exclua este diretório e execute:

```bash
# Na pasta dbt-northwind
poetry install
poetry run dbt init
```

Faça a respectiva configuração do seu projeto dbt. Escolha o nome do seu projeto, que será o nome do diretório que excluiu e escolha o conector postgres e coloque as credenciais de conexão com o db postgres que subiu no docker compose.

Por fim, garanta que o projeto está corretamente iniciado:

```bash
# Entre no seu projeto dbt
cd <Nome_do_seu_projeto> # Se for o mesmo do meu: cd dbt_project
poetry run dbt debug
```

No fim da execução a mensagem que deve aparecer é: "All checks passed!"