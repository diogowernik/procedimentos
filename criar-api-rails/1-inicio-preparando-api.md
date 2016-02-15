Inicio e preparo do projeto
----------------------------

Install gem rails-api

    gem install rails-api


Create rails-api

    rails-api new simple-api
    
Delete test folder, because we are going to use rspec for tests

Edit gem file, installing all gems for the api:

Gems devise_token_auth e omniauth (for authentication)

Gems rspec (for tests) and rubocop (for code quality verification)

    gem 'devise_token_auth'

    gem 'omniauth'

    group :development, :test do
      gem 'rspec-rails', '~> 3.0'
      gem 'rubocop', '~> 0.37.2', require: false
    end

On teminal

    bundle install
    rake db:migrate

Insert .rubocop.yml na raiz do projeto

    # This is the configuration used to check the rubocop source code.
    # Check out: https://github.com/bbatsov/rubocop

    AllCops:
      Include:
        - '**/Rakefile'
        - '**/config.ru'
      Exclude:
        - 'vendor/**/*'
        - 'spec/fixtures/**/*'
        - 'db/**/*'
        - 'db/schema.rb'
        - 'db/seeds.rb'
        - 'client/node_modules/**/*'
        - 'bin/**/*'
        - 'config/initializers/secret_token.rb'
        - !ruby/regexp /old_and_unused\.rb$/
        
    Metrics/LineLength:
      Max: 120
      
    Style/Documentation:
      Enabled: false

    Style/BlockDelimiters:
      Enabled: false

    Style/StringLiterals:
      Enabled: false
      
    Style/SymbolArray:
      Enabled: true

Gerar rpec 

    rails generate rspec:install

Test all

    rspec
    rubocop

First Commit with git

    git init
    git add -A .
    git commit -m "Project Start"