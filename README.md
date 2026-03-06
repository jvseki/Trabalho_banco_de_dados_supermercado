# 🛒 Sistema de Banco de Dados – Supermercado Online
---

# 📌 Descrição do Projeto


Este projeto consiste na modelagem e implementação de um Banco de Dados Relacional para um Sistema de Supermercado Online.

O objetivo é estruturar e organizar os dados de um sistema de e-commerce de supermercado, permitindo o gerenciamento de:

Clientes

Produtos

Categorias

Pedidos

Itens de pedidos

Pagamentos

O banco foi desenvolvido utilizando MySQL, aplicando conceitos de Modelagem Entidade-Relacionamento (MER), normalização de dados e integridade referencial.

# 👨‍💻 Integrantes do Projeto


João Victor Seki

Henry Youji

Cauã Bolani

Nicolas Emanuel

---

# 🧱 Estrutura do Banco de Dados


O sistema é composto por 6 tabelas principais, que representam as entidades do sistema.

📦 Tabelas do Banco
👤 Cliente

Armazena os dados dos usuários cadastrados no sistema.


Campos:

id_cliente – Identificador único do cliente (PK)

nome – Nome do cliente

email – Email do cliente (único)

senha – Senha de acesso

telefone – Telefone para contato

data_cadastro – Data de cadastro do cliente
---

# 🏷️ Categoria

Responsável por organizar os produtos por tipo.

Campos:

id_categoria – Identificador da categoria (PK)

nome – Nome da categoria

descricao – Descrição da categoria

Exemplos de categorias:

Alimentos

Bebidas

Limpeza

Higiene
---
# 📦 Produto

Armazena os produtos disponíveis no supermercado.

Campos:

id_produto – Identificador do produto (PK)

nome – Nome do produto

descricao – Descrição do produto

preco – Preço do produto

estoque – Quantidade disponível em estoque

id_categoria – Categoria do produto (FK)

imagem_url – URL da imagem do produto

# 🧾 Pedido

Representa as compras realizadas pelos clientes.

Campos:

id_pedido – Identificador do pedido (PK)

id_cliente – Cliente que realizou o pedido (FK)

data_pedido – Data e hora do pedido

status – Status do pedido

valor_total – Valor total da compra

Exemplos de status:

Pendente

Pago

Enviado

Entregue
---

# 📋 Item_Pedido

Tabela responsável por armazenar os produtos presentes em cada pedido.

Ela resolve o relacionamento N:N entre Pedido e Produto.

Campos:

id_item – Identificador do item (PK)

id_pedido – Pedido relacionado (FK)

id_produto – Produto relacionado (FK)

quantidade – Quantidade do produto no pedido

preco_unitario – Preço unitário do produto no momento da compra

# 💳 Pagamento

Armazena informações sobre os pagamentos realizados.

Campos:

id_pagamento – Identificador do pagamento (PK)

id_pedido – Pedido relacionado (FK)

tipo_pagamento – Forma de pagamento

status_pagamento – Status do pagamento

data_pagamento – Data do pagamento

Exemplos de pagamento:

Cartão

PIX

Boleto

🔗 Relacionamentos do Banco

O sistema possui os seguintes relacionamentos:

Cliente → Pedido

1 : N

Um cliente pode realizar vários pedidos.

Pedido → Item_Pedido

1 : N

Um pedido pode conter vários itens.

Produto → Item_Pedido

1 : N

Um produto pode aparecer em vários pedidos diferentes.

Categoria → Produto

1 : N

Uma categoria pode possuir vários produtos.

Pedido → Pagamento

1 : 1

Cada pedido possui um pagamento associado.

# 🗺️ Diagrama Entidade-Relacionamento (DER)

O diagrama abaixo representa a estrutura completa do banco de dados:

⚙️ Tecnologias Utilizadas

MySQL

MySQL Workbench

SQL (DDL)

📂 Estrutura do Projeto
📦 supermercado-banco
 ┣ 📜 script.sql
 ┣ 🖼️ DER.png
 ┣ 📜 dicionario_de_dados.pdf
 ┗ 📜 README.md
📚 Conceitos Aplicados

Durante o desenvolvimento do projeto foram aplicados os seguintes conceitos:

Modelagem de Banco de Dados

Diagrama Entidade Relacionamento (DER)

Chaves Primárias (PK)

Chaves Estrangeiras (FK)

Integridade Referencial

Normalização de Dados

SQL DDL

# 🎯 Objetivo Acadêmico

Este projeto foi desenvolvido como atividade prática da disciplina de Banco de Dados, com o objetivo de aplicar conceitos teóricos na construção de um banco de dados estruturado e funcional.
---

✅ Sistema modelado
✅ Banco criado em SQL
✅ DER implementado
✅ Documentação profissional
---

# 📌 Autor

Projeto desenvolvido por:

João Victor Seki
Henry Youji
Cauã Bolani
Nicolas Emanuel
