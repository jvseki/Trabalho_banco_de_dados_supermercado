
# 📘 DICIONÁRIO DE DADOS
---
# 🛒 Sistema de Banco de Dados – Supermercado Online
---
# 👨‍💻 Integrantes do Projeto

João Victor Seki

Henry Youji

Cauã Bolani

Nicolas Emanuel
---

# 📌 1. Visão Geral

Este documento descreve detalhadamente a estrutura do banco de dados desenvolvido para o sistema de Supermercado Online, contendo especificações técnicas de cada tabela, seus atributos, tipos de dados, restrições e descrições funcionais.

O modelo foi estruturado seguindo boas práticas de modelagem relacional, garantindo:

Integridade referencial

Normalização até a 3ª Forma Normal (3FN)

Organização e clareza estrutural

🗄️ Estrutura das Tabelas
🔹 Tabela: cliente
📖 Descrição:

Armazena as informações dos usuários cadastrados no sistema.

Campo	Tipo de Dado	Tamanho/Precisão	Restrições	Descrição
id_cliente	INT	—	PK, AUTO_INCREMENT	Identificador único do cliente
nome	VARCHAR	100	NOT NULL	Nome completo do cliente
email	VARCHAR	150	NOT NULL, UNIQUE	Endereço de e-mail do cliente
senha	VARCHAR	255	NOT NULL	Senha criptografada do cliente
telefone	VARCHAR	20	—	Número de telefone para contato
data_cadastro	DATE	—	—	Data em que o cliente foi cadastrado
🔹 Tabela: categoria
📖 Descrição:

Responsável por classificar os produtos em categorias.

Campo	Tipo de Dado	Tamanho/Precisão	Restrições	Descrição
id_categoria	INT	—	PK, AUTO_INCREMENT	Identificador da categoria
nome	VARCHAR	100	NOT NULL	Nome da categoria
descricao	TEXT	—	—	Descrição detalhada da categoria
🔹 Tabela: produto
📖 Descrição:

Armazena as informações dos produtos disponíveis para venda.

Campo	Tipo de Dado	Tamanho/Precisão	Restrições	Descrição
id_produto	INT	—	PK, AUTO_INCREMENT	Identificador único do produto
nome	VARCHAR	100	NOT NULL	Nome do produto
descricao	TEXT	—	—	Descrição detalhada do produto
preco	DECIMAL	10,2	NOT NULL	Valor unitário do produto
estoque	INT	—	NOT NULL	Quantidade disponível em estoque
id_categoria	INT	—	FK	Identificador da categoria do produto
imagem_url	VARCHAR	255	—	Caminho ou URL da imagem do produto

🔗 Chave Estrangeira:

id_categoria → categoria(id_categoria)

🔹 Tabela: pedido
📖 Descrição:

Registra os pedidos realizados pelos clientes.

Campo	Tipo de Dado	Tamanho/Precisão	Restrições	Descrição
id_pedido	INT	—	PK, AUTO_INCREMENT	Identificador único do pedido
id_cliente	INT	—	FK	Cliente que realizou o pedido
data_pedido	DATETIME	—	NOT NULL	Data e hora da realização do pedido
status	VARCHAR	50	—	Status do pedido (Pendente, Enviado, Entregue)
valor_total	DECIMAL	10,2	—	Valor total calculado do pedido

🔗 Chave Estrangeira:

id_cliente → cliente(id_cliente)

🔹 Tabela: item_pedido
📖 Descrição:

Tabela intermediária responsável por resolver o relacionamento muitos-para-muitos entre pedido e produto.

Campo	Tipo de Dado	Tamanho/Precisão	Restrições	Descrição
id_item	INT	—	PK, AUTO_INCREMENT	Identificador do item do pedido
id_pedido	INT	—	FK	Pedido ao qual o item pertence
id_produto	INT	—	FK	Produto incluído no pedido
quantidade	INT	—	NOT NULL	Quantidade do produto adquirida
preco_unitario	DECIMAL	10,2	—	Valor do produto no momento da compra

🔗 Chaves Estrangeiras:

id_pedido → pedido(id_pedido)

id_produto → produto(id_produto)

🔹 Tabela: pagamento
📖 Descrição:

Armazena as informações referentes ao pagamento de cada pedido.

Campo	Tipo de Dado	Tamanho/Precisão	Restrições	Descrição
id_pagamento	INT	—	PK, AUTO_INCREMENT	Identificador do pagamento
id_pedido	INT	—	FK	Pedido relacionado ao pagamento
tipo_pagamento	VARCHAR	50	—	Forma de pagamento (Cartão, PIX, Boleto)
status_pagamento	VARCHAR	50	—	Status do pagamento
data_pagamento	DATETIME	—	—	Data e hora da confirmação do pagamento

🔗 Chave Estrangeira:

id_pedido → pedido(id_pedido)
