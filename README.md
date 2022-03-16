# Lista de Desejos

Essa é a documentação de uso para a API da Lista de desejos.
baseURL: https://desirelist.herokuapp.com/

## Endpoints

Essa API possui 5 Endpoints, voltados para cadastro, login e informações de usuários e seus desejos pessoais.

1. Cadastro na API;
2. Login na API;
3. Acessando lista de desejos já cadastrados em nossa API: https://desirelist.herokuapp.com/desires (Qualquer pessoa pode acessar)
4. Cadastrando desejos;
5. Acessando Lista de usuários e seus desejos; (Apenas usuários logados possuem acesso);

## Cadastro

POST /register

Para se cadastrar em nossa API precisamos enviar no corpo de nossa requisição o seguinte:

{
email: "emailUser@teste.com",
password: "senhaFornecida",
nome: "Teste Máquina",
bio: "Usuário de criação da API"
}

## Login

POST /login

Para realizar o login em nossa API, é preciso enviar no corpo da requisição:

{
email: "emailUser@teste.com",
password: "SenhaFornecidaNoCadastro"
}

## Cadastrando Desejos

POST /desire

Para realizar o cadastro de desejos é preciso estar logado. O corpo dessa requisição inclui a descrição, a dificultadade de se alcançar o desejo e o ID do usuário que está cadastrando. O corpo da requisição ficará da seguinte forma:

{
description: "Desejo ter uma vida melhor",
dificulty: "Medium"
userId: idDoUsuário
}

## Desejos Cadastrados

GET /desires

Qualquer pessoa pode ter acesso aos desejos já cadastrados em nossa API. Não é necessário passar nada no corpo da requisição.

## Usuário e seus desejos

GET /users/?\_embed=desires

Nessa rota podemos obter os usuários e seus respectivos desejos. Apenas usuários logados podem ter acesso.
