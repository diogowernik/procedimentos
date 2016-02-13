Para api authenticação baseado em token

Adicionar as gems:

    gem 'devise_token_auth'
    gem 'omniauth'

Criar users auth

    rails g devise_token_auth:install User auth

Deletar banco de dados e gerar outro novo.

    rake db:drop && rake db:create && rake db:migrate

Criar controller

    rails g scaffold_controller User

Ferramenta para analise de codigo

  Estatica

  Execução