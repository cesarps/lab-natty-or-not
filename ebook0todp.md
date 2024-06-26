# Ruby on Rails: desenvolva um sistema do zero

## Introdução ao Ruby on Rails

Ruby é uma linguagem de programação fácil de ler e escrever, criada para tornar a programação mais agradável. Ruby on Rails, ou simplesmente Rails, é um framework que facilita o desenvolvimento de aplicações web usando a linguagem Ruby. Isso tudo é baseado em MVC (Model-view-controller), onde um projeto é criado usando essas três partes através da criação de scaffolds. 

Os comandos em Ruby são usados de forma muito simples, podendo executar qualquer tarefa, desde uma conta simples de matemática até no desenvolvimento de queries de pesquisa em banco de dados.  

Abaixo há uma descriçao de como se começa um projeto do modo mais simples, explicando apenas o básico para sua instalçaõ e como se iniciar um projeto.

## Como iniciar um projeto do zero

### Instalar Ruby e Rails:

Primeiro, você precisa instalar Ruby no seu computador. Depois, instale o Rails. Use os comandos no terminal:

sudo apt-get install ruby-full # Instalação do Ruby em Linux)\
brew install ruby  (instalação do Ruby em MacOS)\
gem install rails  (Instalação do rails) 

### Criar um novo projeto:

Depois de instalar, crie um novo projeto Rails. No terminal, execute:

rails new nome_do_projeto


Não se esqueça de abrir o diretório do projeto.

### Iniciar o servidor Rails:

Para ver sua aplicação em funcionamento, inicie o servidor:

rails server (ou rails s, um facilitador)


### Gerar um controlador:

Um controlador gerencia as requisições e envia respostas. Para criar um, use:

rails generate controller nome_do_controlador


### Adicionar uma ação no controlador:

No arquivo app/controllers/nome_do_controlador_controller.rb, adicione uma ação:

def nome_da_ação\
   Código da ação aqui\
end


### Criar uma rota:

No arquivo config/routes.rb, adicione uma rota para o controlador:

get 'nome_do_controlador/nome_da_ação'


### Criar uma visão:

Crie um arquivo em app/views/nome_do_controlador/nome_da_ação.html.erb e adicione o HTML para exibir no navegador.

Isso tudo é criado automaticamente usando-se scaffolds, que vai gerar um projeto nteiro da maneira mais simples, criando modelos de relacionamentos(M), visões em arquivos html (e outros modos) do resultado (V) e controladores para cada ação necessária dentro de um projeto (C). Por isso essa é a base do Rails, a técnica MVC.


