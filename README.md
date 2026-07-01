# login-system

Projeto full stack criado para estudar autenticação, autorização e arquitetura moderna de aplicações web, construindo um sistema de login e cadastro com foco em aprendizado prático e evolução gradual do portfólio.

## Objetivo

Este repositório tem como objetivo ensinar, na prática, como funciona um fluxo real de autenticação em uma aplicação completa, envolvendo back-end, front-end, banco de dados e containers.

O projeto foi pensado com foco em aprendizado, então a evolução será feita em etapas pequenas, compreensíveis e bem documentadas.

## Stack escolhida

As tecnologias definidas para este projeto são:

- Back-end: Spring Boot
- Linguagem do back-end: Kotlin
- Build tool: Gradle
- Front-end: Angular
- Banco de dados: PostgreSQL
- Containers: Docker

## Escopo inicial (MVP)

A primeira versão do projeto deve incluir:

- cadastro de usuário
- login
- logout
- rota protegida
- persistência de dados no PostgreSQL
- interface simples em Angular
- autenticação com JWT
- fluxo com refresh token
- sessões persistidas
- autorização baseada em roles

## Modelo de autenticação

O projeto seguirá uma abordagem próxima da utilizada no mercado, combinando autenticação stateless e controle stateful de sessão:

- `access token` para autenticar requisições à API
- `refresh token` para renovar a autenticação sem exigir novo login imediato
- sessões persistidas para controlar logins ativos, logout, revogação e expiração
- `roles` armazenadas de forma relacional no banco para regras de autorização

Essa abordagem foi escolhida para permitir o estudo de conceitos modernos de segurança e arquitetura.

## Objetivos de aprendizado

Este projeto foi planejado para ajudar no estudo de:

- fundamentos do Spring Boot
- desenvolvimento back-end com Kotlin
- organização de projetos com Gradle
- estrutura de aplicações Angular
- modelagem relacional com PostgreSQL
- uso de Docker no ambiente de desenvolvimento
- diferença entre autenticação e autorização
- ciclo de vida de tokens JWT
- fluxo com refresh token
- persistência e revogação de sessões
- controle de acesso baseado em roles
- validação de dados
- hash de senha
- boas práticas de segurança em APIs

## Evolução sugerida do projeto

Uma ordem recomendada de implementação é:

1. Configurar o ambiente com Docker, PostgreSQL, back-end e front-end.
2. Criar a estrutura inicial do back-end com Spring Boot, Kotlin e Gradle.
3. Modelar usuários, roles e sessões no banco de dados.
4. Implementar cadastro com validação e hash de senha.
5. Implementar login com access token e refresh token.
6. Persistir sessões e permitir logout e revogação.
7. Proteger rotas no back-end e aplicar autorização por roles.
8. Integrar o Angular com os fluxos de autenticação.
9. Adicionar testes e refinar as decisões de segurança.

## Conceitos de domínio planejados

As principais entidades previstas para o projeto são:

- `User`
- `Role`
- `UserRole`
- `Session`

O modelo inicial de usuário pode incluir:

- `id`
- `name`
- `email`
- `passwordHash`
- `createdAt`

O modelo de sessão pode evoluir para incluir:

- `id`
- `userId`
- identificador ou hash do token
- `expiresAt`
- `revokedAt`
- `createdAt`

## Segurança

Alguns cuidados de segurança planejados para o projeto:

- hash de senha com algoritmo confiável
- validação de dados no front-end e no back-end
- restrição de e-mail único
- mensagens de erro genéricas em autenticação
- expiração de tokens
- revogação de sessões
- separação entre autenticação e autorização
- uso de variáveis de ambiente para configurações sensíveis

## Estrutura do repositório

Conforme o projeto crescer, a estrutura sugerida é:

- `backend/` para API, regras de negócio, autenticação, autorização, persistência e configurações do servidor
- `frontend/` para páginas, componentes, serviços, guards e estilos do Angular
- `tests/` para testes compartilhados de integração e ponta a ponta
- `docs/` para anotações de arquitetura, decisões de segurança, contratos de API e material de estudo

## Forma de desenvolvimento

Este projeto será desenvolvido com foco em aprendizado progressivo.

A ideia é:

- entender os conceitos antes de implementar
- avançar em etapas pequenas
- documentar decisões importantes
- revisar o código ao longo do processo
- evoluir o projeto de forma que ele também sirva como portfólio

## Status atual

O projeto está atualmente na fase de definição de escopo e preparação inicial do ambiente.
