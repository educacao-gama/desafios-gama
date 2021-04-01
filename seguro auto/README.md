# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Seguro Auto
Criar uma solução de Seguro Auto para a realização de registro de Usuário, Veiculo, Cadastro (pode ser estipulante, beneficiário, seguradora), Endereço, Cotação, Apólice, Parcelas e Endossos.
Link Glossário Seguros: https://www.sonhoseguro.com.br/glossario/
Link ViaCep: https://viacep.com.br/ws/01001000/json


### Backend

#### Domínio - Modelagem de Dados

- [ ] Todo cadastro terá os campos: Id, CpfCnpj, Nome, DataNascimento.
- [ ] O cadastro terá precisará realizar um Login com os campos: Username e Password
- [ ] O cadastro precisará consultar o seu endereço pelo CEP informado.
- [ ] **NOTA: O sistema deverá utilizar de algum client API para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] Os Veiculos cadastrados precisarão ter os campos Id, Placa, Chassi, Descricao, Valor Mercado, Ano Fabricacao, Zero KM
- [ ] Para gerar uma cotação será necessário informar os campos Id, Inicio Vigencia, Fim Vigencia,Valor Cobertura, Valor Premio, Apolice ?, Cancelada ?, Veiculo Trabalho, Pernoita Garagem.
- [ ] Um cotação terá Parcela(s) com os campos: Id, Numero, Data Vencimento, Valor, Compensanda ?
- [ ] Um cotação poderá sofrer alterações (Endossos) com 03 finalidades: CANCELAMENTO, MUDANCA_ENDERECO, TROCA_VEICULO
- [ ] Um Endosso terá os campos: Id, Data Hora
- [ ] Um Endosso de cancelamento terá mais os campos: Data Hora Cancelamento, Motivo Cancelamento (Tabela com Id e Descrição).
- [ ] Um Endosso de mudança de endereço terá mais o campo: Id Endereço Antigo e Id Endereço Novo
- [ ] Um Endosso troca de veiculo terá mais os campos Id Veiculo Antigo, Id Veiculo Novo.

#### Regra de Negócio

1. O campo login pode conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
1. Não poderá ser duplicado o campo login na base de dados
1. Todo cadastro precisará de um endereço
1. Se a média final for inferior a 7 a matrícula do aluno informará como REPROVADO, do contrário APROVADO.
1. Gerar uma lista de alunos, professores por nome e turmas por descrição.
2. Gerar uma lista de matrículas por ano, semestre, situação.

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

