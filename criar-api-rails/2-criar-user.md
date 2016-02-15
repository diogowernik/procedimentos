Creating Users
--------------

### 1 - Create Model for users

Create users model and url address auth/

    rails g devise_token_auth:install User auth
    
Edit migrate file, on line 37, delete:

    t.string :name
    t.string :nickname
    t.string :image

Install the migrate generated

    rake db:migrate

In the folder:

app/model/user.rb align the paramters and delete for now (so we dont need to confirm email for tests):

    :confirmable,

### Create controllers for users

Criar controller

    rails g scaffold_controller User

inserir em app/controller/users_controller.rb

    before_action :authenticate_user!, except: [:show, :index]

check with rubocop the code.

    rubocop

Update your entire project to Ruby 1.9 hash syntax 
http://effectif.com/ruby/update-your-project-for-ruby-19-hash-syntax

    find . -name \*.rb -exec perl -p -i -e 's/([^:]):(\w+)\s*=>/\1\2:/g' {} \;

