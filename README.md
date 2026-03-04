# 🛒 Sistema de Banco de Dados – Supermercado Online
📌 Sobre o Projeto

---
Este projeto foi desenvolvido para a disciplina de Banco de Dados, com o objetivo de aplicar conceitos de:

Modelagem de Dados (MER/DER)

Estruturação Relacional

Integridade Referencial

Implementação de Scripts DDL em SQL

O sistema representa um Supermercado Online (E-commerce), permitindo o gerenciamento de clientes, produtos, categorias, pedidos e pagamentos.

# 👨‍💻 Integrantes

João Victor Seki

Henry Youji

Cauã Bolani

Nicolas Emanuel

---

#🗄️ Estrutura do Banco de Dados

O banco de dados é composto pelas seguintes entidades:

Cliente

Categoria

Produto

Pedido

Item_Pedido

Pagamento

O modelo foi desenvolvido seguindo a 3ª Forma Normal (3FN), garantindo:

✔ Redução de redundância
✔ Integridade referencial
✔ Organização estrutural
✔ Separação adequada de responsabilidades

🔗 Relacionamentos Principais

Um Cliente pode realizar vários Pedidos (1:N)

Um Pedido pode conter vários Produtos (N:N via Item_Pedido)

Um Produto pertence a uma Categoria (N:1)

Um Pedido possui um Pagamento (1:1)
---

#📊 Modelagem

O projeto inclui:

📘 Dicionário de Dados

📈 Diagrama Entidade-Relacionamento (DER)

📄 Script SQL de criação (DDL)

🛠️ Tecnologias Utilizadas

MySQL

MySQL Workbench

SQL (DDL)

Git & GitHub
---

# ▶️ Como Executar o Projeto

Abrir o MySQL Workbench

Criar uma nova conexão (caso necessário)

Executar o arquivo:

script.sql

O banco supermercado será criado automaticamente com todas as tabelas e relacionamentos.
