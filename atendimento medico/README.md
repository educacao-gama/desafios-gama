# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Atendimento Médico \ Prontuário
Criar um sistema para um consultório controlar o cadastro de seus clientes, atendimentos e prontuário dos pacientes.
### Backend

#### Domínio - Modelagem de Dados

- [ ] Cadastro de Usuário terá os campos: Login, Senha e Nome
- [ ] Cadastro de Cliente com os campos: Id, Nome, Cpf, Telefone, Celular, Email e Tipo Sanguineo
- [ ] O cadastro de Cliente deverá ter o seu endereço através de uma tabela de endereço com os campos: Id, Cep, Logradouro, Numero, Bairro, Localidade (cidade), Uf (estado) IBGE.
**NOTA: O sistema deverá utilizar de algum client API como (Java como RestTemplate e FeingClient) ou sua tecnologia para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] Será necessário também cadastrar o Especialista com os campos: Id, Nome, Registro, Telefone, Celular, Email e Profissão
- [ ] A mesma regra de endereço de Cliente se aplica ao cadastro de Especialista.
- [ ] Cadastro de Profissão para Especialista com os campos Id e Nome.
- [ ] Lançamento dos Atendimentos realizados na clínica com os campos Id, Data Agendamento, Data Atendimento, Hora Atendimento, Valor do Atendimento e Status da Atendimento {AGENDADO, REALIZADO, CANCELADO}
- [ ] Registro em Prontario informando o Id, Paciente, Data Abertura
- [ ] Registro de Histório dos atendimentos em forma de Histório Prontuário com os campos: Id, Data, Hora, Descricao e Especialista.
#### Regra de Negócio

1. O campo login pode conter caracteres com até 20 caracteres
1. Não poderá ser duplicado os campos cpf do cliente, registro do especialista e login do usuario.
1. Todo cadastro de cliente e especialista precisará de um endereço.
1. Todo Atendimento Médico com Status = REALIZADO deverá gerar um registro de histórico no prontuário do paciente.
1. Disponibilizar uma consulta dos atendimentos pelos parâmetros: Data Agendamento, Data Atendimento, Cliente, Status e Especialista. 

#### Noções de Arquitetura - DevOps

1. Disponibilizar uma API Rest que deverá disponibilizar o serviço de autenticação e autorização para usuários.
1. Disponibilizar uma API Rest com todas as funcionalidades citadas acima.
1. Disponibilizar a documentação dos recursos Web Services REST.
1. Em caso de Frontend - Disponibilizar o link para acesso ao sistema web 

#### Orientações \ Obrigatoriedade

##### Backend

###### 1° Entrega

- Disponibilizar as funcionalidades inclusão, alteração, processamento do negócio e consulta importantes.
- Os dados devem ser armazenados em um banco de dados utilizando frameworks ORM \ SQL.
- Aplicar as boas práticas de desenvolvimento, organização do projeto, testes unitários e código fonte no github.
- Código fonte no github com o arquivo README detalhando as funcionalidades, classe principal (main), nome do grupo e membros envolvidos e sua participação no projeto.

###### 2° Entrega

- Refatorar todo o sistema para a estrutura WEB com a finalidade de prover API Rest da aplicação
- Implementar funcionalidades de segurança usando Basic Auth, OAuth ou JWT (Preferencialmente)
- Criar uma camada de controller\resource para disponibilizar todos os serviços aplicando autenticação\autorização nos serviços para prover os recursos de forma segura. 
- Disponibilizar uma API Rest que exige autenticação e devidamente documentada pelo Swagger em um ambiente Azure, Heroku ou OnPromisse.

###### Projeto Final
- Apresentar a API projeto  devidamente documentada para uma demonstração de uma jornada de consumo dos recursos com ênfase nas funcionalidades do sistema solicitado e critérios de aceite.
- Detalhar no README do projeto modelo de consumo de endpoint para facilitar a utilização da API, exemplo:

##### Frontend

- Apresentar a estrutura do projeto no github;
- Demonstrar tela de login com fundamentos de autenticação e autorização
- Apresentar telas relacionadas as funcionalidades de cadastro de clientes, profissões, especialistas, atendimentos e consulta de prontuários.

###### Projeto Final
- Apresentar a aplicação WEB devidamente documentada para uma demonstração de uma jornada do usuário com ênfase nas funcionalidades do sistema solicitado e critérios de aceite.
- Detalhar no README do projeto as funcionalidades do sistema bem como menu, telas e navegabilidade:

##### Funcionalidades

- Realização do Cadastro de Clientes e Especialistas.
- Realizar registro de atendimentos e histórico em prontuários.
- Realizar a consulta dos atendimento por data de agendamento, data atendimento, cliente, especialista e status.

##### Critérios de Aceite
Disponibilizar o link do github do projeto bem descrito quanto às funcionalidades, implementações relevantes, participação dos membros da equipe, READEME com a jornada do projeto final com API Rest documentada pelo Swagger e\ou Front Interativo disponível em um ambiente Netlify, Azure, Heroku ou OnPromisse.

- Apresentar a estrutura do projeto no github;
- Apresentar a API do projeto devidamente documentada e preferencialmente no Heroku;
- Realizar uma demonstração de uma jornada de consumo dos recursos de autenticação e autenticação;
- Em caso de Frontend demonstrar os menus, telas e navegabilidade de todas as funcionalidades do sistema.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 


##### Referências

Diagrama de classe: 
![](https://github.com/educacao-gama/desafios-gama/blob/main/atendimento%20medico/atendimento-medico.PNG)
