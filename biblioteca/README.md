# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Biblioteca
Criar um sistema para uma biblioteca gerenciar a locação de seus livros provendo um webservices com arquitetura REST para atender as demandas do projeto.
### Backend

#### Domínio - Modelagem de Dados

- [ ] Para iniciar será necessário o Cadastro contendo os campos, Id, Nome, CPF, Email, Telefone, Login, Senha
- [ ] O cadastro deverá ter o seu endereço através uma tabela de endereço com os campos: Id, Cep, Logradouro, Numero, Bairro, Localidade, Uf, IBGE.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] Será necessário também cadastrar os livros com os campos: Id, ISBN, Titulo, Valor da Diaria, Número de exemplares do livro e Número dos exemplares reservados.
- [ ] Para realizar a locação deverá armazenar as informações abaixo: Id, Data Agendamento, Data Retirada, Data Finalizacao,  Valor Total e o Status Locação **(RESERVADA, EFETIVADA, FINALIZADA)**.
- [ ] Como será possivel retirar mais de um livro em cada Locação, deverá registrar estes livros selecionados incluindo os campos: Data Previsao Entrega, Data Entrega, Numero de diarias **(data entrega - data retirada)**, Valor Diaria, Valor Locação **(valor diaria * diarias)**;

#### Regra de Negócio

1. O campo login pode conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
1. Não poderá ser duplicado os campos cpf e login na base de dados
1. Todo cadastro precisará de um endereço
1. Toda locação iniciará com Data Agendamento,  Status = RESERVADA e Valor Total = 0,0. Somente o campo Data Retirada aceitará nulo
1. Na inclusão dos itens de livro na locação, deverá ser considerado se o campo número de exemplares do livro maior ou igual a 1
1. A cada inclusão de livro na  locação deverá ser informada uma previsão de data de entrega e manipular os campos do livro da seguinte maneira.
	1. Decrementar o campo exemplares em 1
	1. Incrementar o campo reservados em 1
1. Toda vez que for selecionada uma locação através da consulta de locações, deverá ser acionado a rotina que analisa todos os livros da locação atualizando os campos: número de diárias já realizadas, valor da locação de cada livro com as seguintes regras:
	1. O cálculo só será executado em livros que ainda não entregues **(Data Entrega igual null)**
	1. Cálculo de número de diárias : Data de Hoje - Data Retirada **(Locacao)**
	1. Cálculo de valor de locação: **(Numero de Diárias x Valor Diária)** 
	1. Valor Total da Locação é o resultante da soma do Valor Locação de todos os livros da locação.
1. Quando o usuário vier retirar os livros atualizar o campo Data de Retirada e mudar o Status para **EFETIVADA**
1. Quando o usuário entregar todos os livros da locação, atualizar o campo Data Finalização e Status para FINALIZADA e atualizar os campos do livro conforme abaixo:
	1. Incrementar o campo exemplares em 1
	1. Decrementar o campo reservados em 1
1. Disponibilizar uma consulta de locações pelos parâmetros: Data Agendamento, Data Retirada, Cadastro (usuario), Status Locação. 

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

- Realização do Cadastro com Endereço e Cadastro de Livros.
- Realizar operações de locação de livros considerando as fases conforme requisitos.
- Realizar a consulta das locações por data de agendamento, data retirada, cadastro e status.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 

##### Referências

Diagrama de classe: 
![](https://github.com/educacao-gama/desafios-gama/blob/main/biblioteca/biblioteca-diagrama.jpg)
