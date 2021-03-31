# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Locação de Véiculos
A empresa LocaTur especializada em locação de veículos de passeio solicita o desenvolvimento de uma solução para gestão dos agendamentos, locações e devoluções de véiculos.
Todas as funcionalidades deverão ser desenvolvidas em uma arquitetura de webservices com arquitetura REST para atender as demandas do site e app.

### Backend

#### Domínio - Modelagem de Dados

- [ ] Os clientes e operadores terão um usuário no sistema que terão um campo: Login, Senha e Tipo {CLIENTE, OPERADOR} para acessar os recursos da aplicação.
- [ ] O cadastro de cliente será composto por : Id, Nome, Data de Nascimento, Telefone e E-mail, Sexo.
- [ ] O cadastro de operador será composto por : Id, Nome, Matricula, Telefone e E-mail.
- [ ] Tanto um cliente como o operador precisão consultar o seu endereço pelo CEP informado.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] O usuário deverá ter um identificador (TIPO) se será um CLIENTE ou OPERADOR.
- [ ] Cadastro de Marcas e Modelos relacionados aos veículos da locadora.
- [ ] O cadastro do veículo deverá ter os campos: Placa, Marca, Modelo, Ano, Valor Hora, Disponivel, Combustivel {GASOLINA, ALCOOL, DIESEL}, Limite Porta Malas e Categoria {BASICO, COMPLETO, LUXO}.
- [ ] Disponbilizar um registro de agendamento do veiculos com os campos: Id, Data Hora Agendamento, Data Hora Retirada, Data Hora Devolucao, Id Cliente, Id Veiculo, Valor Total Locação, Status {RESERVADO, RETIRADO, DEVOLVIDO}.
- [ ] Registrar o checklist\vistoria de devolução do veículo com os campos: Id Locacao, Carro Limpo ?, Tanque Cheio ?, Amassados ? Arranhoes ?


#### Regra de Negócio

1. O campo login pode conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
1. Não poderá ser duplicado o campo login na base de dados
1. Todo cadastro precisará de um endereço
1. Todo agendamento iniciará com o status RESERVADO
1. Quando o veículo for retirado pelo cliente, mudar o Atatus do agendamento para RETIRADO e marcar veiculo como Disponivel = false
1. Quando o veículo for devolvido pelo cliente, mudar o Atatus do agendamento para DEVOLVIDO e marcar veiculo como Disponivel = true
1. No checklist de devolução a cada marcação acrescentar % no valor da locação.
    * Carro Limpo = false +15%
    * Tanque Cheio = false +20%
    * Amassados = true +30%
    * Arranhoes = true +20%
1. Gerar uma lista de matrículas por ano, semestre, situação.

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

- Realizar login; cadastro de alunos, professores, turmas, matrículas  e listagem em forma de consultas.
- Aplicação das notas em cada matrícula.
- Demonstração do boletim e situação da matricula como APROVADO / REPROVADO.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 

##### Referências

Diagrama de classe: 
![](https://github.com/educacao-gama/desafios-gama/blob/main/escolar/escolar-digrama.jpg)

