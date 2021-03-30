# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Escolar
A empresa EdukaTec especialista em formação de profissionais na área de tecnologia solicitou para nossa fábrica de software desenvolver um sistema para gestão de alunos, professores, matrículas, turmas e boletins para seus cursos que possuem duração de 06 meses ao ano, onde no primeiro semestre são cursos de tecnologias backend como Java, .NET e Nodes e no segundo semestre cursos de frontend como React, Angular e VueJS. Cada semestre será composto por  03 turmas no horário MATUTINO, VESPERTINO, NOTURNO com duração de 02:00 segunda-quarta-sexta e prover um webservices com arquitetura REST para atender as demandas do site.

### Backend

#### Domínio - Modelagem de Dados

- [ ] Os alunos e professores terão um usuário no sistema que terão um campo: Login, Senha e Tipo {ALUNO, PROFESSOR} para acessar os recursos da aplicação.
- [ ] O cadastro de aluno será composto por : Id, Nome, Data de Nascimento, Telefone e E-mail, Sexo.
- [ ] O cadastro de professor será composto por : Id, Nome, Data de Nascimento, Telefone e E-mail.
- [ ] Tanto um cliente como o professor precisão consultar o seu endereço pelo CEP informado.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] O usuário deverá ter um identificador (TIPO) se será um ALUNO ou PROFESSOR.
- [ ] Após o cadastro dos alunos, teremos o cadastro das matrículas onde precisaremos informar o Id Aluno, Ano, Semestre, Situação {APROVADO, REPROVADO} e gerar um número de matrícula que é a composição do ANO (0000) + SEMESTRE (00) + ID DO ALUNO (0000). Exemplo:{2021+02+0058}
- [ ] Para o cadastro das Turmas deverá ter os campos: Id, Descrição (Ex.: Turma Java 2021-01) com seus respectivos horários: MATUTINO, VESPERTINO, NOTURNO.
- [ ] Cada turma ensinará uma disciplina e precisará dos campos: Id, Nome (Ex.: JAVA AVANÇADO)
- [ ] A matrícula terá o registro das 04 notas para resultar na média final em forma de Boletim com os campos Nota1, Nota2, Nota3, Nota4 e MediaFinal.  




- [ ] O cadastro de Cliente deverá ter o seu endereço através uma tabela de endereço com os campos: Id, Cep, Logradouro, Numero, Bairro, Localidade, Uf, IBGE.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 
- [ ] Será necessário também cadastrar os Produtos com os campos: Id, Codigo de Barras, Nome, Unidade Medida, Valor Unitário, Saldo, Marca e Modelo.
- [ ] Para o cadastro de Produtos serão necessárias a criação de duas tabelas: Marca e Categoria com os campos: Id e Nome.
	* Exemplo Marcas: APPLE, ESTRELA, BRATEMP e etc.
	* Exemplo Categorias: MOVEIS, ELETROS, BRINQUEDOS, ROUPAS e etc.
- [ ] Para a realização de Compras de produtos deverão ser informado os campos: Id, Data Compra, Valor Total Compra e os Produtos comprados com o campos: Id, Id Produto, Valor Unitário Compra, Quantidade Comprada, Valor Total Item Compra.
- [ ] Para a realização de Vendas de produtos deverão ser informado os campos: Id, Id Cliente, Data Venda, Valor Total Venda, Status {INICIADA, FINALIZADA, CANCELADA} e os Produtos vendidos com o campos: Id, Id Produto, Valor Unitário Venda, Quantidade Vendida, Valor Total Item Venda.


#### Regra de Negócio

1. O campo login pode conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
1. Não poderá ser duplicado os campos cpf e login na base de dados
1. Todo cadastro precisará de um endereço
1. Todo produto deverá ser cadastrado com saldo zero.
1. O saldo do produto não poderá ser alterado sem ser por uma compra ou venda.
1. Ao finalizar uma compra, o sistema deverá incrementar o saldo com a quantidade de cada item inserido na compra.
1. Toda venda deverá ser criada com o Status = INICIADA e Valor Total = 0,0
1. Na inclusão dos itens de de produto, cada item antes de ser incluído deverá validar se a quantidade solicitada é menor ou igual ao saldo do produto.
1. A cada item incluído na Venda deverá reduzir a quantidade informada no Saldo do Produto.
1. A cada item incluído na Venda deverá atualizar o Valor Total da Venda, exemplo:

| Descrição   | Quant | R$ Unit | R$ Total |
| ------------|-------|---------|----------|
| TV SEMP 40" | 3     | 1.600   |  4.800   |
| PS4         | 5     | 2.200   | 11.000   |
| GOD OF WAR  | 2     |   125   |    250   |
|             |       |         |          |
|       -     |	-     | R$ Venda | 16.050  |

1. Quando a Venda for FINALIZADA não poderá mais editar com a inclusão/remoção de novos produtos.
1. Quando a venda for CANCELADA a quantidade dos itens vendidos deverão retornar para o saldo dos Produtos.
1. Disponibilizar uma consulta de vendas pelos parâmetros: Cliente, Data Venda {Inicio e Fim} e Status. 
2. Disponibilizar uma listagem de produtos filtrados por Marca, Categoria e Classificados por Nome e Valor Venda {Crescente - Decrescente}. 

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

- Realização do Cadastro Clientes com Endereço, Cadastro de Produtos, Marcas e Categorias.
- Apresentar as funcionalidades de Compra e Venda
- Demonstrar a consolidação do Saldo dos Produtos com base nas Compras e Vendas realizadas.
- Apresentar as consultas das Vendas realizadas.
- Listar os produtos aplicando filtros e classificações conforme requisito.

- **Requisitos Técnicos:** Implementação aplicando as boas práticas de programação, uso de ORM, Framework de persistência, segurança na API, integridade do banco de dados. 

##### Referências

Diagrama de classe: 

