# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Escolar - Atração de Leads
A empresa EdukaTec especialista em formação de profissionais na área de tecnologia solicitou para nossa fábrica de software desenvolver uma página para atração de alunos para cursos de EDUCAÇÃO BÁSICA, GRADUAÇÃO, PÓS GRADUAÇÃO e EDUCAÇÃO A DISTÂNCIA. A página deverá ter um formulário para registrar os dados básicos para contato e o curso desejado.


### Backend

#### Domínio - Modelagem de Dados

- [ ] Conforme diagrama abaixo, o sitema deverá ter o registro de Cursos e Contatos.
- [ ] O Curso será composto por : Id, Nome e Categoria (EDUCACAO_BASICA, GRADUACAO, POS_GRADUACAO e EDUCACAO_DISTANCIA).
- [ ] O Contato terá informações como : Id, Data, Nome, CPF, Endereço, Email, Telefone e Curso Desejado (ver mais detalhes no diagrama).
**NOTA: O sistema deverá utilizar de algum client API para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] O Contato também terá um status para informar a situação como: NOVO, EM_ATENDIMENTO, CONTRATATO, DESISTENTE.

#### Regra de Negócio

1. Não poderá existir um NOVO contato com mesmo CPF
1. O campos: CPF, Nome, Telefone, Whatsapp e Email são obrigatórios 
1. No preenchimento do formulário, também será obrigatório informar o curso de preferência.



#### Orientações \ Obrigatoriedade
- Apresentar a estrutura do projeto no github;
- Apresentar a API do projeto devidamente documentada;

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, integridade do banco de dados. 


##### Frontend

1. Disponibilizar uma pagina para preenchimento dos dados de contato interessados na realização de um curso.
2. Utilizar algum framework de stilo e validação de regras de preenchimento.


##### Projeto Final
- Apresentar a API projeto  devidamente documentada para uma demonstração de uma jornada de consumo dos recursos com ênfase nas funcionalidades do sistema solicitado e critérios de aceite.
- Detalhar no README do projeto modelo de consumo de endpoint para facilitar a utilização da API, exemplo:


#### Critérios de Aceite
Disponibilizar o link do github do projeto bem descrito quanto às funcionalidades, implementações relevantes, participação dos membros da equipe, READEME com a jornada do projeto final com API Rest documentada pelo Swagger e\ou Front Interativo disponível em um ambiente Azure, Heroku ou OnPromisse.

#### Plus+
1. Realizar uma listagem dos contatos por data e status
2. Criar um fluxo de atualização de status que reflita novos endpoints e uma simulação de backoffice de atendimento. 


##### Referências

Diagrama de classe: 
![](https://github.com/educacao-gama/desafios-gama/blob/main/escolar/leads/diagrama.PNG)

