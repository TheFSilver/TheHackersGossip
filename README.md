# README

Dans le terminal, tapez les commandes suivantes :
```
cd Desktop/
git clone https://github.com/TheFSilver/TheHackersGossip.git
rails new TheHackersGossip -d postgresql
cd TheHackersGossip
open Gemfile
```
Ajoutez la ligne suivante au Gemfile
```
gem 'devise'
gem "jquery-rails"
gem 'jquery-ui-rails'
gem 'bootstrap'
```
De retour dans le Terminal, tapez ceci:
```
bundle install
rails generate devise:install
rails generate controller Home index
```
Ajoutez la ligne suivante au fichier routes.rb
```
root 'home#index'
```
De retour dans le Terminal, tapez ceci:
```
rails g devise Moussaillon
rails db:create
rails g migration AddAnonymousUsernameToMoussaillons anonymous_username:string
rails g scaffold Gossip content:text date:timestamp moussaillon:references
rails db:migrate
rails g devise:views
```
Dans /app/models/ on ajoute à moussaillon.rb la ligne suivante :
```
has_many :gossips
```
Dans /app/views/layouts/ on crée un fichier \_header.html.erb
Dans /app/views/layouts/ on ajoute à application.html.erb la ligne suivante après la balise <body> :
```
<%= render 'header' %>
```
Dans /app/views/layouts/ on modifie le fichier \_header.html.erb
```

```
Et on obtient un beau header avec les liens apparaissant en fonction de l'état logged_in / logged_out
Dans /app/assets/javascripts/ remplacez les lignes 13 à 16 dans le fichier application.js par :
```
//= require popper
//= require jquery3
//= require jquery-ui
//= require jquery_ujs
//= require rails-ujs
//= require bootstrap
//= require activestorage
//= require_tree .
```
Dans /app/assets/stylesheets/ modifiez le fichier application.css
```
 *= require jquery-ui
```
