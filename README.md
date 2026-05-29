# 🛒 Super Duper Mart

Sistema desktop de gerenciamento de mercado desenvolvido em Java com JavaFX, seguindo o padrão de arquitetura MVC e integração com banco de dados MySQL.

> Projeto acadêmico desenvolvido para a disciplina de Tópicos Avançados em Programação (TAP) — UFAM.

---

## 📋 Funcionalidades

- **Autenticação** — login de administrador com controle de acesso
- **Gestão de produtos** — cadastro, edição e controle de estoque com vínculo a marcas
- **Compras** — registro de entradas de estoque com atualização automática de quantidade
- **Vendas** — registro de saídas com cálculo de troco, valor total e forma de pagamento
- **Relatórios** — geração e armazenamento de relatórios operacionais
- **Marcas** — cadastro de marcas associadas aos produtos

---

## 🏗️ Arquitetura

O projeto segue o padrão **MVC (Model-View-Controller)** com camada DAO para acesso a dados:

```
src/
├── config/         # Configuração de conexão com o banco de dados
├── controllers/    # Lógica de negócio e controle das telas (FXML)
├── dao/            # Data Access Objects — queries e operações no MySQL
├── model/          # Entidades do sistema (Produto, Venda, Compra, etc.)
├── view/           # App.java (entry point JavaFX) e arquivos FXML/CSS
├── css/            # Estilização das telas
├── mysql/          # Scripts SQL de criação do banco
└── utils/          # Utilitários gerais
```

---

## 🗄️ Banco de Dados

O sistema utiliza **MySQL** com o seguinte modelo relacional:

| Tabela       | Descrição                                              |
|--------------|--------------------------------------------------------|
| `admin`      | Credenciais de acesso ao sistema                       |
| `marcas`     | Marcas dos produtos (chave primária: nome)             |
| `produtos`   | Catálogo de produtos com preços e estoque atual        |
| `compras`    | Registro de entradas de estoque                        |
| `vendas`     | Registro de vendas com forma de pagamento e troco      |
| `relatorios` | Histórico de relatórios gerados                        |

---

## 🚀 Como executar

### Pré-requisitos

- Java 11+
- MySQL 8+
- VS Code com extensão [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack) ou IntelliJ IDEA

### 1. Configurar o banco de dados

Execute o script SQL localizado em `mysql/` no seu cliente MySQL:

```sql
-- Cria e popula o banco de dados
source caminho/para/o/script.sql;
```

Ou copie e execute o conteúdo diretamente no MySQL Workbench / DBeaver.

### 2. Configurar a conexão

Edite o arquivo em `src/config/` com suas credenciais MySQL:

```java
// Exemplo esperado
String URL  = "jdbc:mysql://localhost:3306/superdupermart";
String USER = "seu_usuario";
String PASS = "sua_senha";
```

### 3. Executar a aplicação

Abra o projeto no VS Code ou IntelliJ e execute a classe `src/view/App.java` como ponto de entrada.

---

## 🛠️ Tecnologias utilizadas

| Tecnologia | Uso |
|---|---|
| Java | Linguagem principal |
| JavaFX | Interface gráfica desktop (FXML + CSS) |
| MySQL | Banco de dados relacional |
| JDBC | Conexão Java ↔ MySQL |
| Padrão DAO | Separação entre lógica e acesso a dados |
| Padrão MVC | Organização da arquitetura da aplicação |

---

## 👨‍💻 Autor

**Samuel Davi** — [github.com/Samuel-Davi](https://github.com/Samuel-Davi) | [linkedin.com/in/samchagas](https://linkedin.com/in/samchagas)
