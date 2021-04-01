# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Seguro Auto
Criar uma solução de Seguro Auto para a realização de registro de Usuário, Veiculo, Cadastro (pode ser estipulante, beneficiário, seguradora), Endereço, Cotação, Apólice, Parcelas e Endossos.

* Link Glossário Seguros: https://www.sonhoseguro.com.br/glossario/
* Link ViaCep: https://viacep.com.br/ws/01001000/json


### Backend

#### Domínio - Modelagem de Dados

- [ ] Todo cadastro terá os campos: Id, CpfCnpj, Telefone, Email, Nome, DataNascimento.
- [ ] O cadastro terá precisará realizar um Login com os campos: Username e Password
- [ ] O cadastro precisará consultar o seu endereço pelo CEP informado.
- [ ] **NOTA: O sistema deverá utilizar de algum client API para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] Os Veiculos cadastrados precisarão ter os campos Id, Placa, Chassi, Descricao, Valor Mercado, Ano Fabricacao, Zero KM
- [ ] Para gerar uma cotação será necessário informar os campos Id, Inicio Vigencia, Fim Vigencia,Valor Cobertura, Valor Premio, Apolice ?, Cancelada ?, Veiculo Trabalho, Pernoita Garagem.
- [ ] Um cotação terá Parcela(s) com os campos: Id, Id Cotacao, Numero, Data Vencimento, Valor, Compensanda ?
- [ ] Um cotação poderá sofrer alterações (Endossos) com 03 finalidades: CANCELAMENTO, MUDANCA_ENDERECO, TROCA_VEICULO
- [ ] Um Endosso terá os campos: Id, Id Cotacao, Data Hora
- [ ] Um Endosso de cancelamento terá mais os campos: Data Hora Cancelamento, Motivo Cancelamento (Tabela com Id e Descrição).
- [ ] Um Endosso de mudança de endereço terá mais o campo: Id Endereço Antigo e Id Endereço Novo
- [ ] Um Endosso troca de veiculo terá mais os campos Id Veiculo Antigo, Id Veiculo Novo.

#### Regra de Negócio

1. No Login o campo Paswword poderá conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
1. Não poderá ser duplicado o Login na base de dados
1. Todo cadastro precisará de um endereço
1. As apólices inicialmente serão cotações no sistema Apolice = false (se a cotação se tornou uma apólice válida = true)
**NOTA: Se tiver alguma dúvida quanto a nomenclatura dos campos, consultar o glossário:  https://www.sonhoseguro.com.br/glossario/**
1. Parcela: Uma cotação ao se tornar apólice deverá ter 01 ou até 06 parcelas referentes ao valor do prémio com as suas respectivas datas de vencimento conforme campos: Id, Numero, Data Vencimento, Valor, Compensada.
1. Endosso: Alterações da apólice do tipo cancelamento, mudança de endereço, troca de veículo deverão gerar endossos conforme descrição abaixo.
    - Endosso de CANCELAMENTO: Esta ação tornará a apólice como cancelada.
    - Endosso de MUDANCA DE ENDERECO: Quando o beneficiário mudar seu endereço gerar um registro de endosso para a apólice
    - Endosso de TROCA DE VEICULO: Quando o estipulante resolver mudar o veiculo assegurado. 
1. Cálculo valor prémio:
    - O valor de prémio será referente a 3% do valor de mercado do veículo.
    - Se o beneficiário da apólice tiver entre 18 a 25 anos, acrescentar 1% do valor de mercado do veículo
    - Se o veículo for considerado veículo de trabalho, acrescentar 0,5% do valor de mercado do veículo.
    - Se o veículo NÃO pernoitar em garagem, acrescentar 0,5% do valor de mercado do veículo.
1. Realizar uma consulta de cotações, apólices e parcelas por estipulante e data de vigência ou vencimento das parcelas.

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
- Realizar uma demonstração de uma jornada de consumo dos recursos de autenticação;

- Realizar login.
- Realizar cadastro de veículos, estipulantes, beneficiários.
- Realizar operações de cotação, geração de apólices, endossos.
- Realizar a consulta de cotações, apólices e parcelas por estipulante.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 

##### Referências

Diagrama de classe: 


