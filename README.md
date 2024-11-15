# API de Gestão de Consultório Médico

Esta é uma API RESTful desenvolvida com **Spring Boot** para gestão de um consultório médico. A API permite o cadastro de pacientes, médicos, agendamentos e outros recursos necessários para o gerenciamento de um consultório. A aplicação inclui recursos de **segurança** usando **Spring Security** para autenticação e controle de acesso.

A persistência dos dados é realizada utilizando **MySQL** como banco de dados.

## Funcionalidades

- **Gestão de Pacientes**:
  - Cadastro de novos pacientes.
  - Edição e exclusão de pacientes.
  - Listagem de pacientes cadastrados.

- **Gestão de Médicos**:
  - Cadastro de novos médicos.
  - Edição e exclusão de médicos.
  - Listagem de médicos cadastrados.

- **Agendamento de Consultas**:
  - Cadastro de consultas com médico, paciente, data e hora.
  - Listagem de consultas agendadas.
  - Cancelamento e alteração de consultas.

- **Segurança**:
  - Autenticação de usuários (médicos e administradores) com **Spring Security**.
  - Autorização baseada em roles (papéis de usuário como `ROLE_ADMIN`, `ROLE_MEDICO` e `ROLE_PACIENTE`).
  - Proteção de endpoints sensíveis com controle de acesso.

## Tecnologias Utilizadas

- **Java**: Linguagem de programação principal.
- **Spring Boot**: Framework para desenvolvimento rápido de APIs.
- **Spring Security**: Para autenticação e autorização de usuários.
- **Spring Data JPA**: Para persistência de dados no banco de dados.
- **MySQL**: Banco de dados para persistência de informações.
- **Maven**: Gerenciador de dependências e build do projeto.
- **JJWT (JSON Web Token)**: Para geração de tokens JWT para autenticação.

## Endpoints da API


## Segurança e Autenticação

A API utiliza **Spring Security** para proteger os endpoints. O acesso aos recursos é restrito com base no **role** do usuário, que pode ser um dos seguintes:

- **ROLE_ADMIN**: Permite o gerenciamento de pacientes, médicos e consultas.
- **ROLE_MEDICO**: Permite o gerenciamento de consultas (mas não pode acessar dados de outros médicos ou pacientes).
- **ROLE_PACIENTE**: Permite visualizar informações sobre o paciente, agendar consultas e ver suas consultas agendadas.

A autenticação é feita utilizando **JSON Web Tokens (JWT)**, que são enviados no cabeçalho `Authorization` de cada requisição após o login.
