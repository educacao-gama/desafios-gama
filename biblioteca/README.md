# Gama Academy - Transformando Talentos para o Futuro

## Desafio Biblioteca
Criar um sistema para uma biblioteca gerenciar a locação de seus livros provendo um webservices com arquitetura REST para atender as demandas do projeto.

### Backend

#### Domínio - Modelagem de Dados

- [ ] Para iniciar será necessário o Cadastro contendo os campos, Id, Nome, CPF, Email, Telefone, Login, Senha
- [ ] O campo login pode conter caracteres que representam cpf, telefone ou apelido com até 20 caracteres
- [ ] Não poderá ser duplicado os campos cpf e login na base de dados
- [ ] Para o cadastro deverá ter o seu endereço através uma tabela de endereço com os campos: Id, Cep, Logradouro, Numero, Bairro, Localidade, Uf, IBGE.
<p>** NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/ ** 
- [ ] Será necessário também cadastrar os livros com os campos: Id, ISBN, Titulo, Valor da Diaria, Número de exemplares do livro e Número dos exemplares reservados.
- [ ] Para realizar a locação deverá armazenar as informações abaixo: Id, Data Agendamento, Data Retirada, Data Finalizacao,  Valor Total e o Status Locação **(RESERVADA, EFETIVADA, FINALIZADA)**.
- [ ] Como será possivel retirar mais de um livro em cada Locação, deverá registrar estes livros selecionados incluindo os campos: Data Previsao Entrega, Data Entrega, Numero de diarias **(data entrega - data retirada)**, Valor Diaria, Valor Locação **(valor diaria * diarias)**;

#### Regra de Negócio

1. Item A
2. Item B
3. Item C