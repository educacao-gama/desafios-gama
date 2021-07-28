# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Ecommerce (VTex)

Integração de nosso site para dispor de serviços comuns no mercado como Market Place, Gestão de Pedidos, Ordem de Pagamentos entre outros são muito comuns, para isto a VTex disponibiliza o VTex IO, uma maneira de oferecer estes recursos para o seu negócio.

### Sua plataforma

- [ ] Cadastro de Cliente terá os campos Nome, Cpf, Telefone,Email,Senha.
- [ ] Cadastro de Produtos com os campos: Id, Codigo de Barras, Nome, Unidade Medida, Valor Unitário, Saldo, Marca e Modelo.
- [ ] Para o cadastro de Produtos serão necessárias a criação de duas tabelas: Marca e Categoria com os campos: Id e Nome.
	* Exemplo Marcas: APPLE, ESTRELA, BRATEMP e etc.
	* Exemplo Categorias: MOVEIS, ELETROS, BRINQUEDOS, ROUPAS e etc.
- [ ] Você já controle de Pedidos sendo informado os campos: Id, Id Cliente, Data Pedido, Valor Total Pedido, Status {INICIADA, FINALIZADA, CANCELADA} e os Produtos vendidos com o campos: Id, Id Produto, Valor Unitário Pedido, Quantidade Pedido, Valor Total Item Pedido.

#### Regra de Negócio

1. Validar campos essencias para cadastro de clientes e produtos
1. Todo produto deverá ser cadastrado com saldo 100.
1. Geração de pedidos

##### Backend

- Apresentar a estrutura do projeto no github;
- Apresentar a API do projeto devidamente documentada;
- Realização do Cadastro Clientes com Endereço, Cadastro de Produtos, Marcas e Categorias;
- Apresentar as funcionalidades de Geração de Pedido;

##### Frontend

- Apresentar a estrutura do projeto no github;
- Site Oficial
	* Exibir a listagem dos produtos filtrando por categoria e ordenando por preço (crescente e decrescente);
	* Gerenciar carrinho de compras (pedidos);
	* Consulta dos pedidos já realizados;
	* Integração com API (backend)

- Template do site ecommerce

