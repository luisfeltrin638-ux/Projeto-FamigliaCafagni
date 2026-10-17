# Projeto-FamigliaCafagni


## Descrição do projeto:

O projeto Famiglia Cafagni contempla o desenvolvimento de um software para uma pequena empresa de pastifício que enfrenta problemas com a gestão de pedidos dos clientes. Além disso, o desenvolvimento do sistema é justificado pela informalidade dos métodos atuais da empresa, como o uso do Whatsapp como principal meio de comunicação, e pelo elevado custo ou taxas para a compra ou a contratação de um sistema ERP.


## Principais problemas:

- Gerir os pedidos dos clientes
- Lidar com clientes desonestos


## Solução:

Desenvolvimento de um sistema de Ponto de Venda (PDV), onde o cliente realiza e controla seus pedidos e os administradores, que são os cozinheiros, recebem esses pedidos, os produzem e os repassam para a entrega.


## Tecnologias:

- HTML5 e CSS3 (Penpot: Software de wireframe do Front-End)
- C# e ASP.NET Core
- SQL server
- Github e Git


## Funcionalidades:

- Administrador

Controle de produtos
Controle de pedidos
Controle de trabalho

- Cliente

Controle de pedidos


## Banco de dados:


| Entidade | Colunas | Observações |
| --- | --- | --- |
| Usuario | <strong>id</strong> nome | Entidade pai de cliente e administrador. Sua função é armazenar o id e o nome das pessoas. |
| Cliente | logradouro, telefone(UNIQUE), cep | - |
| Administrador | senha | - |
| Cidade | <strong>id</strong>, nome | - |
| Pedido | <strong>id</strong>, preco, data_pedido, data_entrega, tipo_entrega, status | data_entrega: data que o cliente recebará o pedido, data_pedido: data que aconteceu o pedido. Status: entre "Pendente" e "Não pronto" |
| Massa | <strong>id</strong>, nome, descricao, preco, imagem, tipo, status | Imagem: seria um link. Status: Entre "Ativo" e "Inativo" |
| Caldo | <strong>id</strong>, nome, descricao, preco, imagem | - |
| Recheio | <strong>id</strong>, nome, descricao, imagem | - |
| Itens_pedido | <strong>id</strong>, qtd_massa, qtd_caldo, subtotal | Esta tabela diz a quantidade da massa e caldo de um pedido e seu subtotal (valor_massa * qtd_massa + valor_caldo * qtd_caldo). |
| Massa_caldo | - | Perceba que esta tabela N : N conecta quais massas são apropriadas para cada caldo |
| Massa_recheio | - | Perceba que esta tabela N : N conecta quais massas são apropriadas para cada recheio |


Entidades:

- Usuario 

Entidade pai de cliente e administrador. Sua função é armazenar o id e o nome das pessoas.

- Administrador

Entidade que armazena a senha do administrador que fez o pedido.

- Clientes

Entidade que armazena o logradouro, o telefone e o CEP do cliente.

- Massas

Entidade que armazena o id, nome, preço, tipo e o status da massa.

Há dois tipo de massa: congelada e não congelada.

- Caldos

Entidade que armazena o id, nome e preço do caldo.

O caldo pode ser comprado com a massa, mas deve estar junto à massa.

- Recheios

Entidade que armazena o id e o nome do recheio

O recheio deve estar junto a massa, mas nem toda massa tem recheio.

Observação: Os caldos ou recheios só podem estar em massas respectivas ás regras de negócio, ou seja, um caldo ou recheio da massa x pode ser inapropriado para massa y.

- Pedidos

Entidade que id, preço, data, status, data_agendada e tipo_entrega.

o atributo data é a data e o tempo que foi realizado o pedido e data_agendada é a data que o cliente agendou o pedido.

- Delivery

Entidade que armazena id, frete, distancia e status.

O atributo frete é uma coluna usada para calcular o preço líquido dos proprietários (preco - frete = receita_liquida_frete).

- Itens_pedidos

Entidade que armazena id, pedido_id, id_massa, id_caldo e id_recheio, qtd_massa, qtd_caldo, um subtotal (calculado por valor_massa * qtd_massa + valor_caldo * qtd_caldo) do pedido.

Tabela que agrega qual recheio e caldo estão em uma massa (N : N)

- massa_caldo

Entidade que armazena id_massa e id_caldo

Usada para restringir quais caldos podem acompanhar uma massa

- massa_recheio

Entidade que armazena id_massa e id_recheio

Usada para restringir quais recheios podem estar em uma massa

## Próximos passos

- Aplicar JavaScript
- Usar API's de pagamento PIX 