# Sistema de Pagamento em Java
🚀 Projeto pessoal desenvolvido em Java/Spring Boot para simular transações financeiras seguras, incluindo processamento, estornos e conciliação.

## 📌 Visão Geral
Este sistema é uma API RESTful que simula um gateway de pagamentos, com:
✅ Processamento de transações (cartão, PIX, boleto)
✅ Estornos e reembolsos
✅ Autenticação JWT e autorização por roles
✅ Integração com serviços externos (simulados)
✅ Armazenamento em banco de dados e filas assíncronas

## 🛠️ Tecnologias
- Backend: Java 17 + Spring Boot 3

- Banco de Dados: PostgreSQL

- Filas: RabbitMQ (para processamento assíncrono)

- Segurança: JWT, Spring Security, Criptografia AES

- Documentação: Swagger (OpenAPI 3.0)

- Testes: JUnit 5, Mockito, Testcontainers

- Deploy: Docker + Docker Compose

## ⚙️ Funcionalidades
1. Módulo de Pagamento
Processamento de transações com diferentes métodos (cartão, PIX, boleto)

Validação de dados e regras antifraude (simuladas)

Confirmação assíncrona via fila (RabbitMQ)

2. Módulo de Estorno
Reembolsos totais/parciais

Rastreamento de status

3. Módulo de Autenticação
Registro e login de usuários (clientes e lojistas)

Roles (USER, ADMIN) e permissões

4. Módulo de Notificação
Envio de e-mails (simulado) para confirmações e falhas

## 🏗️ Arquitetura
📁 payment-system  
├── 📂 core/           # Lógica de negócio  
├── 📂 api/            # Controllers REST  
├── 📂 infra/          # Banco, filas, segurança  
├── 📂 external/       # Integrações com gateways  
└── 📂 docs/           # Swagger e esquemas  
Padrões utilizados:

- Clean Architecture (camadas isoladas)

- Strategy (para diferentes gateways de pagamento)

- Observer (notificações)

- CQRS (separação entre leitura/escrita)

## 🚀 Como Executar
Pré-requisitos
### Java 17+

### Docker e Docker Compose

Passos:
- Clone o repositório:

bash
git clone [URL_DO_PROJETO]  
Suba os containers:

bash
docker-compose up -d  
Acesse a API:

Swagger UI: http://localhost:8080/swagger-ui.html

Endpoint base: http://localhost:8080/api/v1/payments

### 📊 Testes
bash
# Executar testes unitários  
./mvnw test  

# Executar testes de integração (com Testcontainers)  
./mvnw verify  
🔒 Segurança
Dados sensíveis (como números de cartão) são criptografados (AES-256)

Validação PCI-DSS simulada (não use em produção!)

Rate limiting básico (Spring Security)

