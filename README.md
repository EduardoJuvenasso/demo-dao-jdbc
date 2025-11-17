# 💻 Projeto: Implementação do Padrão DAO com JDBC

## 🌟 Visão Geral

Este projeto acadêmico demonstra a implementação do **Padrão de Projeto Data Access Object (DAO)** utilizando **Java** e **JDBC (Java Database Connectivity)**. O objetivo principal é criar uma camada de abstração robusta e desacoplada para o acesso a dados, garantindo que a lógica de negócios permaneça isolada dos detalhes de persistência.

A aplicação simula um sistema de gerenciamento simples, focado na manipulação de dados de entidades como `Department` (Departamento) e `Seller` (Vendedor), interagindo com um banco de dados relacional.

## 🎯 Destaques Técnicos e Aprendizados

Este projeto é uma prova da minha capacidade de aplicar conceitos fundamentais de desenvolvimento de software e boas práticas de engenharia:

*   **Padrão DAO:** Implementação completa do padrão DAO para as entidades `Department` e `Seller`, incluindo operações CRUD (Create, Read, Update, Delete) e consultas personalizadas.
*   **JDBC:** Utilização direta da API JDBC para conexão, execução de *statements* e gerenciamento de transações com o banco de dados.
*   **Gerenciamento de Conexões:** Implementação de uma classe utilitária (`DB`) para gerenciar o ciclo de vida das conexões com o banco de dados, garantindo o fechamento correto de recursos (`Connection`, `Statement`, `ResultSet`) e prevenindo *resource leaks*.
*   **Tratamento de Exceções:** Uso de exceções personalizadas (`DbException`, `DbIntegrityException`) para lidar com erros de banco de dados de forma clara e informativa, separando as preocupações de persistência.
*   **Modelagem de Dados:** Criação de classes de modelo (`entities`) para representar as tabelas do banco de dados, seguindo o princípio de POJO (Plain Old Java Object).
*   **SQL:** Criação e execução de *queries* SQL para a definição do esquema (`database.sql`) e para as operações de manipulação de dados.

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia | Descrição |
| :--- | :--- | :--- |
| **Linguagem** | Java | Linguagem principal de desenvolvimento. |
| **Acesso a Dados** | JDBC (Java Database Connectivity) | API para conexão e execução de comandos no banco de dados. |
| **Banco de Dados** | MySQL / H2 (Simulação) | Banco de dados relacional utilizado para persistência. |
| **IDE** | Eclipse | Ambiente de Desenvolvimento Integrado (IDE) utilizado. |

## ⚙️ Estrutura do Projeto

O projeto segue uma estrutura modular e organizada, refletindo a separação de responsabilidades:

```
.
├── src/
│   ├── application/      # Ponto de entrada e testes manuais da aplicação
│   ├── model/
│   │   ├── entities/     # Classes de modelo (POJOs)
│   │   └── dao/          # Interfaces do Padrão DAO
│   │       └── impl/     # Implementações concretas do DAO (com JDBC)
│   └── db/               # Classes utilitárias para conexão e exceções
├── database.sql          # Script de criação do esquema e tabelas do banco de dados
└── db.properties         # Arquivo de configuração para as credenciais do banco de dados
```

## 🚀 Como Executar o Projeto

Para rodar este projeto localmente, siga os passos abaixo:

### Pré-requisitos

*   Java Development Kit (JDK) instalado (versão 8 ou superior).
*   Um ambiente de banco de dados relacional (ex: MySQL) ou a utilização do H2 em memória.

### Configuração do Banco de Dados

1.  **Crie o Esquema:** Execute o script `database.sql` no seu SGBD para criar as tabelas necessárias (`Department` e `Seller`).
2.  **Configure a Conexão:** Edite o arquivo `db.properties` com suas credenciais de banco de dados:

    ```properties
    dburl=jdbc:mysql://localhost:3306/cursojava?useSSL=false&serverTimezone=UTC
    dbuser=seu_usuario
    dbpassword=sua_senha
    ```

### Execução

1.  Importe o projeto para sua IDE (ex: Eclipse).
2.  Execute a classe principal localizada em `src/application/Program.java` (ou similar) para ver os testes de CRUD em ação.

## 💡 Lições Aprendidas e Próximos Passos

A implementação deste projeto reforçou a importância de:

*   **Desacoplamento:** O padrão DAO isola a lógica de acesso a dados, facilitando a manutenção e a troca de tecnologia de persistência (ex: migrar de JDBC puro para JPA/Hibernate) sem impactar a lógica de negócios.
*   **Reutilização de Código:** As interfaces DAO promovem um contrato claro, permitindo que diferentes implementações sejam criadas e testadas.

**Melhorias Futuras:**

*   Migrar a implementação de JDBC puro para um *framework* ORM como **JPA/Hibernate** para reduzir o código *boilerplate*.
*   Implementar testes unitários para as classes DAO.
*   Adicionar uma camada de serviço (`Service Layer`) para encapsular a lógica de negócios.

---

*Desenvolvido por Eduardo Juvenasso como parte de um curso acadêmico.*
