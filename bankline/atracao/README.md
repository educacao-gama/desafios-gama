# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Bankline - Atração
Criar um sistema para gerenciamento de contas e lançamentos e extratos provendo um webservices com arquitetura REST para atender as demandas do projeto.

### Backend \ Front

#### Domínio - Modelagem de Dados

- [ ] Cadastro de Conta com os campos: Id, Nome, Cpf, Login e Senha, Saldo.
- [ ] Registro de Lançamentos de Crédito e Débito com os campos: Id, Data, Descrição, Id Conta, Valor e Tipo (Crédito ou Débito) 

#### Regra de Negócio

1. O campo Login só permitirá até 20 caracteres
1. Não poderá ser duplicado os campos cpf e login na base de dados
1. Regras de Lançamentos
	1. Quando o lançamento for do tipo Crédito o Saldo deve ser acrescido o seu valor
	2. Quando o lançamento for do tipo Débito o Saldo deve ser deduzido o seu valor 
1. Disponibilizar Extrato dos Lançamentos por Conta e Período de Datas inicial e final - Dashboard
2. Exibir a(s) Conta(s) com Saldos consolidados 

#### Extras

1. Disponibilizar o link do github do projeto bem descrito quanto às funcionalidades, implementações relevantes, participação dos membros da equipe
1. Disponibilizar uma API Rest \ Telas com todas as funcionalidades citadas acima.
