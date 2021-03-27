# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Biblioteca
Criar um sistema para uma biblioteca gerenciar a locação de seus livros provendo um webservices com arquitetura REST para atender as demandas do projeto.
### Backend

#### Domínio - Modelagem de Dados

- [ ] Cadastro de Usuário terá os campos Login, Senha, Nome e Cpf.
- [ ] O cadastro deverá ter o seu endereço através uma tabela de endereço com os campos: Id, Cep, Logradouro, Numero, Bairro, Localidade, Uf, IBGE.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] No processo de criação de Usuários serão criadas duas Contas com os campos Tipo da Conta {CB (Conta Banco), CC (Conta Credito)}, Numero, Saldo e Login do Usuario.
	- O Número será do tipo Texto contendo a seguinte atribuição: Login + Sigla Tipo Conta, exemplo.: JOSECB e  JOSECC
	- Conta Banco: Conta que representa tua conta corrente que pode realizar RECEITAS, DEPESAS e TRANSFERIR entre sua Conta Credito e ou Conta Banco de outros Usuários.
- [ ] Plano de Contas é a finalidade das transações realizadas na conta dos Usuários, exemplo: SALARIO, AGUA, LUZ, TRANSFERENCIA que serão quatro Planos de Contas padrão por Usuário, são elas: {R (RECEITA), D (DESPESA) , TC (TRANSFERENCIA ENTRE CONTAS) e TU (TRANSFERENCIAS ENTRE USUARIOS).
- [ ] Para o cadastro de Plano de Contas é necessário informar o Id, Descrição, Login, Tipo Movimento (R, D, TC, TU), Padrão (s/n)
- [ ] Lançamentos: toda Transação deverá armazenas os campos Id, Conta, Data, Descrição, Login, Valor, Tipo Movimento e em casa do tranferência informar a Conta de Destino

#### Regra de Negócio

1. O campo login pode conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
1. Não poderá ser duplicado os campos cpf e login na base de dados
1. Todo usuário precisará de um endereço
1. A Conta deverá ser salva com saldo Zero (0)
1. Deverão ter 4 Planos de Contas padrão para cada Usuário
1. Regras de Lançamentos
	1. O Usuário poderá criar novos Planos de Contas mas não alterar os Planos de Contas padrão
	1. O Usuário poderá transferir saldo da sua Conta Banco para a Conta Crédito mas não o contrário
	1. O Usuário poderá transferir saldo da sua Conta Banco somemente para Conta Banco de outro usuário
	1. Quando houve lançamento de Transferência deverá existir um novo Lançamento onde a Conta é a Conta Destino. 
1. Disponibilizar Extrato dos Lançamentos por Conta e Período de Datas inicial e final - Dashboard
2. Exibir as Contas com Saldos consolidados 

#### Noções de Arquitetura - DevOps

1. Disponibilizar uma API Rest que deverá disponibilizar o serviço de autenticação e autorização para usuários.
1. Disponibilizar uma API Rest com todas as funcionalidades citadas acima.
1. Disponibilizar a documentação dos recursos Web Services REST.

#### Orientações \ Obrigatoriedade

##### 1° Entrega

- Disponibilizar as funcionalidades inclusão, alteração, processamento do negócio e consulta importantes.
- Os dados devem ser armazenados em um banco de dados utilizando frameworks ORM \ SQL.
- Aplicar as boas práticas de desenvolvimento, organização do projeto, testes unitários e código fonte no github.
- Código fonte no github com o arquivo README detalhando as funcionalidades, classe principal (main), nome do grupo e membros envolvidos e sua participação no projeto.

##### 2° Entrega

- Refatorar todo o sistema para a estrutura WEB com a finalidade de prover API Rest da aplicação
- Implementar funcionalidades de segurança usando Basic Auth, OAuth ou JWT (Preferencialmente)
- Criar uma camada de controller\resource para disponibilizar todos os serviços aplicando autenticação\autorização nos serviços para prover os recursos de forma segura. 
- Disponibilizar uma API Rest que exige autenticação e devidamente documentada pelo Swagger em um ambiente Azure, Heroku ou OnPromisse.

##### Projeto Final
- Apresentar a API projeto  devidamente documentada para uma demonstração de uma jornada de consumo dos recursos com ênfase nas funcionalidades do sistema solicitado e critérios de aceite.
- Detalhar no README do projeto modelo de consumo de endpoint para facilitar a utilização da API, exemplo:


#### Critérios de Aceite
Disponibilizar o link do github do projeto bem descrito quanto às funcionalidades, implementações relevantes, participação dos membros da equipe, READEME com a jornada do projeto final com API Rest documentada pelo Swagger e\ou Front Interativo disponível em um ambiente Azure, Heroku ou OnPromisse.


##### Backend

- Apresentar a estrutura do projeto no github;
- Apresentar a API do projeto devidamente documentada e preferencialmente no Heroku;
- Realizar uma demonstração de uma jornada de consumo dos recursos de autenticação e autenticação;

- Realização do cadastro Usuários com Endereço e suas Contas.
- Realizar o cadastro de novos Planos de Contas.
- Gerar lançamentos de Receita, Despea e Tranferências.
- Apresentar o Dashboard com lançamentos por Usuário e Período (Data Inicial / Data Final)
- Demonstrar as Contas com seu Saldo consolidado.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 

##### Referências

Diagrama de classe: 

