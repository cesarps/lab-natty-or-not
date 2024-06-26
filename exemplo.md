# Exemplo 

## Criando um sistema de FAQ

Comece criando o projeto dessa maneira:

rails new faq_project

Entre no projeto logo em seguida.

## Crie o scaffold

Uma maneira de facilitar a criação do projeto é o uso de scaffold. Isso evitará que você crie cada parte do projeto separadamente. Você pode criar o scaffold dessa maneira.

rails new scaffold faq 

Isso vai gerar os arquivos básicos referentes à base do projeto: MVC.

## Gere os modelos do sistema 

Isso pode ser gerado via diretamente na linha do scaffold, mas você pode gerar cada modelo dessa forma:

###  Gerando o modelo User

rails generate model User name:string email:string

Aqui será gerado um arquivo user.rb que conterá esses dois campos (name e email) no formato string

### Gerando o modelo Question

rails generate model Question title:string content:text user:references

Aqui será gerado o arquivo question.rb, com os campos title e content, e um campo referente ao usuario.

### Gerando o modelo Answer

rails generate model Answer content:text question:references user:references

Aqui, o modelo Answer além de seu campo principal, ele vai criar mais dois campos que se referenciam ao usuário e à questão.

### Migração

Faça a migração desses campos para sua tabela correspondente dentro do banco de dados pré configurado através desse comando:

rails db:migrate

Você vai perceber que ele criará 3 tabelas em seu banco de dados, e algumas delas terão campos referentes a outras tabelas. Esses campos são numéricos e terminam com _id, que é a referência ao qual esse campo se relaciona. Por exemplo, na tabela question, haverá o campo user_id, que é uma chave estrangeira do campo user, indicando assim uma relação entre as tabelas user e question. 
 

### Relacionamentos

Esses modelos se relacionam de algum modo, por isso há a criação de chaves estrangeiras dentro das tabelas question (referente a user) e answer (referente à user e à question).

Cada user pode conter uma ou mais questions  e muitas answers.\
Uma question pode ter muitas answers e pertencer a um user.\
Cada answer pertence à um usuário e à  uma question.

Para especificar tudo isso e defina os seguintes comandos:

user.rb\
class User < ApplicationRecord\
  has_many :questions\
  has_many :answers\
end

question.rb\
class Question < ApplicationRecord\
  belongs_to :user\
  has_many :answers\
end

answer.rb\
class Answer < ApplicationRecord\
  belongs_to :user\
  belongs_to :question\
end

### Conclusão

Com a geração de scaffolds citados anteriormente, ele já criou as ações (controllers) e telas (views) necessárias para cada objeto, além de suas rotas específicas

Inicie o servidor através do comando

rails server

E acesse sua applicação em um navegador web em http://localhost:3000.  Você terá agora um projeto FAQ básico com modelos user, question e answer, onde poder-se-á criar, ler,  editar, atualizar e  apagar (CRUD) diversos registros, em cada modelo especificado. 





