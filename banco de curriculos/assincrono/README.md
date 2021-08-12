# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Banco de Currículos
A empresa JobsNET especialista em recrutamento e seleção de profissionais nas mais diversas áreas solicitou para a nossa fábrica de software desenvolver uma página para atração de profissionais para conectar as oportunidades de emprego.

### Frontend

##### Fase 1 - Criação da Página
1. Apresentar a estrutura do projeto no github;
1. Landing page com formulário para prenchimento de candidatura.


**IMAGEM MERAMENTE ILUSTRATIVA**

![](https://github.com/educacao-gama/desafios-gama/blob/main/banco%20de%20curriculos/formulario.PNG)

### Backend

#### Domínio - Modelagem de Dados

- [ ] Cadastro de candidatos com os campos: Id, Nome, Data Nascimento, Endereço {cep, logradouro, numero, bairro, cidade e estado}, Telefone, Email e Profissão e demais campos mencionados na imagem de ilustração de formulário de candidatos.
- [ ] Para a conclusão do cadastro, consultar o seu endereço pelo CEP informado (Consultar a API VIA Cep)
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 

#### Regra de Negócio

1. Não pode haver 2 cadastros de candidatos com o mesmo cpf
1. Todo candidato precisará preencher os campos: CPF, Nome, Data Nascimento, Cep, Logradouro, Número, Bairro, Cidade, Email, Profissão e Celular

#### Integração entre o Pagina de Formulário o  Back-end

1. Disponibilizar uma API Rest com a funcionalidade de cadastro de candidatos armazenando em um banco de dados.
1. Disponibilizar a documentação dos recursos Web Services REST - Uso do Swagger.



