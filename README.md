# Desafio Dio - Crie Seu Próprio Blog com Ruby On Rails



Criar um **blog** completo usando **Ruby on Rails**. Abaixo, apresento uma estrutura abrangente com exemplos de código para cada parte do projeto.



## 1. **Configuração Inicial**:

Antes de começar, certifique-se de ter o Ruby e o Rails instalados. Se ainda não tiver, siga as instruções de instalação para o seu sistema operacional.

## 2. **Criando o Projeto**:

Abra o terminal e execute os seguintes comandos:

```bash
# Crie um novo projeto Rails chamado "MeuBlog"
rails new MeuBlog

# Acesse a pasta do projeto
cd MeuBlog
```



## 3. **Modelo de Dados**:

Vamos criar um modelo para os posts do blog. Execute o seguinte comando:

```bash
rails generate model Post title:string content:text
```



Isso criará um arquivo de migração para criar a tabela de posts no banco de dados. Execute a migração:

```bash
rails db:migrate
```



## 4. **Controladores e Rotas**:

Crie um controlador para gerenciar os posts:

```bash
rails generate controller Posts
```



Defina as rotas no arquivo `config/routes.rb`:

Ruby



```ruby
resources :posts
```

Código gerado por IA. Examine e use com cuidado. [Mais informações em perguntas frequentes](https://www.bing.com/new#faq).



## 5. **Views**:

Crie as views para exibir os posts. Na pasta `app/views/posts`, crie os arquivos:

- `index.html.erb` (lista de posts)
- `show.html.erb` (detalhes de um post)
- `new.html.erb` (criação de um novo post)
- `edit.html.erb` (edição de um post)



## 6. **Modelo e Controlador**:

No arquivo `app/models/post.rb`, defina o modelo “Post”:

Ruby



```ruby
class Post < ApplicationRecord
  validates :title, presence: true
  validates :content, presence: true
end
```



Código gerado por IA. Examine e use com cuidado. [Mais informações em perguntas frequentes](https://www.bing.com/new#faq).

No controlador `PostsController`, implemente as ações para listar, exibir, criar e editar posts.



## 7. **Estilize o Blog**:

Adicione CSS e personalize o visual do seu blog. Você pode usar frameworks como Bootstrap ou criar seu próprio estilo.



## 8. Teste a Aplicação:

Inicie o servidor Rails (`rails server`) e acesse o blog no navegador.



## 9. **Funcionalidades Adicionais**:

- Adicione autenticação de usuários (usando Devise ou similar).
- Implemente comentários nos posts.
- Crie categorias para os posts.

Lembre-se de adaptar o projeto conforme suas necessidades e adicionar mais funcionalidades.



**projeto completo e abrangente para criar um blog com Ruby on Rails, com muitos códigos e sua aplicabilidade:**

### **Introdução**

Ruby on Rails é um framework web poderoso que torna o desenvolvimento de aplicativos rápido e fácil. Neste projeto, usaremos Ruby on Rails para criar um blog simples.



### **Pré-requisitos**

- Ruby 2.6 ou superior
- Rails 6 ou superior
- Banco de dados MySQL ou PostgreSQL



### **Configuração**

1. Crie um novo aplicativo Rails:

plaintext



```plaintext
rails new blog
```



1. #### Adicione o Gemfile:

plaintext



```plaintext
gem 'mysql2' # Se estiver usando MySQL
# Ou
gem 'pg' # Se estiver usando PostgreSQL
```



1. #### Execute `bundle install` para instalar as gems.

2. #### Crie o banco de dados:

plaintext



```plaintext
rails db:create
```



### **Modelos**

Vamos criar um modelo `Post` para armazenar os posts do blog:

plaintext



```plaintext
rails generate model Post title:string body:text
```



### **Migrações**

Execute a migração para criar a tabela de posts:

plaintext



```plaintext
rails db:migrate
```



### **Controladores**

Vamos criar um controlador `PostsController` para gerenciar os posts:

plaintext



```plaintext
rails generate controller Posts
```



### **Rotas**

Adicione as seguintes rotas ao arquivo `config/routes.rb`:

plaintext



```plaintext
Rails.application.routes.draw do
  resources :posts
  root to: "posts#index"
end
```



### **Views**

Crie as views para exibir os posts:

- `app/views/posts/index.html.erb`:

plaintext



```plaintext
<h1>Todos os Posts</h1>

<ul>
  <% @posts.each do |post| %>
    <li><%= link_to post.title, post_path(post) %></li>
  <% end %>
</ul>
```



- ### `app/views/posts/show.html.erb`:

plaintext



```plaintext
<h1><%= @post.title %></h1>

<p><%= @post.body %></p>
```



- ### `app/views/posts/new.html.erb`:

plaintext



```plaintext
<h1>Novo Post</h1>

<%= form_with(model: @post) do |form| %>
  <p>
    <%= form.label :title %><br>
    <%= form.text_field :title %>
  </p>

  <p>
    <%= form.label :body %><br>
    <%= form.text_area :body %>
  </p>

  <p>
    <%= form.submit %>
  </p>
<% end %>
```



- ### `app/views/posts/edit.html.erb`:

plaintext



```plaintext
<h1>Editando Post</h1>

<%= form_with(model: @post) do |form| %>
  <p>
    <%= form.label :title %><br>
    <%= form.text_field :title %>
  </p>

  <p>
    <%= form.label :body %><br>
    <%= form.text_area :body %>
  </p>

  <p>
    <%= form.submit %>
  </p>
<% end %>
```



### **Inicializador**



Crie um inicializador para carregar dados de amostra:

plaintext



```plaintext
# config/initializers/sample_data.rb
Post.create!(title: 'Bem-vindo ao meu blog!', body: 'Este é o meu primeiro post!')
```



### **Testes**

Execute os testes para verificar se o aplicativo está funcionando corretamente:

plaintext



```plaintext
rails test
```



## **Conclusão**

Este é um exemplo básico de como criar um blog usando Ruby on Rails. Você pode expandir este projeto adicionando recursos como autenticação de usuário, comentários e muito mais.
