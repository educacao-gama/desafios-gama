# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Ecommerce (Light)
Criar um sistema para uma loja virtual gerenciar a compra e venda de seus produtos e prover um webservices com arquitetura REST para atender as demandas do projeto.
### Backend

#### Domínio - Modelagem de Dados

- [ ] Cadastro de Cliente terá os campos Nome, Cpf, Telefone,Email,Senha.
- [ ] O cadastro de Cliente deverá ter o seu endereço através uma tabela de endereço com os campos: Id, Cep, Logradouro, Numero, Bairro, Localidade, Uf, IBGE.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] Será necessário também cadastrar os Produtos com os campos: Id, Codigo de Barras, Nome, Unidade Medida, Valor Unitário, Saldo, Marca e Modelo.
- [ ] Para o cadastro de Produtos serão necessárias a criação de duas tabelas: Marca e Categoria com os campos: Id e Nome.
	* Exemplo Marcas: APPLE, ESTRELA, BRATEMP e etc.
	* Exemplo Categorias: MOVEIS, ELETROS, BRINQUEDOS, ROUPAS e etc.
- [ ] Para a realização de Pedidos deverão ser informado os campos: Id, Id Cliente, Data Pedido, Valor Total Pedido, Status {INICIADA, FINALIZADA, CANCELADA} e os Produtos vendidos com o campos: Id, Id Produto, Valor Unitário Pedido, Quantidade Pedido, Valor Total Item Pedido.

#### Regra de Negócio

1. O Cliente usará o email + senha para realizar o login
1. Todo cadastro precisará de um endereço
1. Todo produto deverá ser cadastrado com saldo 100.
1. Ao finalizar um pedido, o sistema deverá diminuir o saldo com a quantidade de cada item inserido.
1. A cada item incluído no carrinho deverá atualizar o Valor Total do Pedido, exemplo:

| Descrição   | Quant | R$ Unit | R$ Total |
| ------------|-------|---------|----------|
| TV SEMP 40" | 3     | 1.600   |  4.800   |
| PS4         | 5     | 2.200   | 11.000   |
| GOD OF WAR  | 2     |   125   |    250   |
|             |       |         |          |
|       -     |	-     | R$ Venda | 16.050  |

1. Disponibilizar uma consulta dos pedidos pelos parâmetros: Cliente, Data Venda {Inicio e Fim} e Status. 
2. Disponibilizar uma listagem de produtos filtrados por Marca, Categoria e Classificados por Nome e Valor Venda {Crescente - Decrescente}. 

##### Backend

- Apresentar a estrutura do projeto no github;
- Apresentar a API do projeto devidamente documentada;
- Realizar uma demonstração de uma jornada de consumo dos recursos de autenticação e autenticação;

- Realização do Cadastro Clientes com Endereço, Cadastro de Produtos, Marcas e Categorias.
- Apresentar as funcionalidades de Compra e Venda
- Demonstrar a consolidação do Saldo dos Produtos com base nas Compras e Vendas realizadas.
- Apresentar as consultas dos Pedidos.
- Listar os produtos aplicando filtros e classificações conforme requisito.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 


