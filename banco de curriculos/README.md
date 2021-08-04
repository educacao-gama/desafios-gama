# Gama Academy - Transformando Talentos para o Futuro

#### Autores
- [Gleyson Sampaio](https://github.com/gleyson-gama)

## Desafio Banco de Currículos
A empresa JobsNET especialista em recrutamento e seleção de profissionais nas mais diversas áreas para nossa fábrica de software desenvolver uma página para atração de profissionais para conectar as oportunidades de emprego.

### Backend

#### Domínio - Modelagem de Dados

- [ ] Cadastro de profissões com os campos: Id e Descrição
- [ ] Cadastro de candidatos com os campos: Id, Nome, Data Nascimento, Endereço {cep, logradouro, numero, bairro, cidade e estado}, Telefone, Email e Profissão (selecionada)
- [ ] Para a conclusão do cadastro, consultar o seu endereço pelo CEP informado.
**NOTA: O sistema deverá utilizar de algum client API Java como RestTemplate e FeingClient para buscar um endereço do serviço via cep conforme link: https://viacep.com.br/ws/{SEU_CEP}/json/** 

#### Regra de Negócio

1. Não pode haver 2 cadastros de profissões de mesmo nome
1. Não pode haver 2 cadastros de candidatos com o mesmo cpf
1. Todo candidato precisará preencher todos os campos

#### Noções de Arquitetura - DevOps

1. Disponibilizar uma API Rest com todas as funcionalidades citadas acima.
1. Disponibilizar a documentação dos recursos Web Services REST.


### Frontend

1. Apresentar a estrutura do projeto no github;
1. Landing page com formulário para prenchimento de candidatura.
1. Upload do currículo em formato pdf
1. Consulta dos currículos já cadastrados
