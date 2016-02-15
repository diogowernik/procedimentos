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

app/model/user.rb align the paramters and for tests comment the confirmable config!
(so we dont need to confirm email for tests):

    :confirmable,

### Create controllers for users

Criar controller

    rails g scaffold_controller User

edit app/controller/users_controller.rb

1. add that for authentication:

```ruby
before_action :authenticate_user!, except: [:show, :index]
```

2. delete post, that will be managed from devise_token_auth

```ruby
  # POST /users
  # POST /users.json
  def create
    @user = User.new(user_params)
    if @user.save
      render json: @user, status: :created, location: @user
    else
      render json: @user.errors, status: :unprocessable_entity
    end
  end
```

3. change the end for:

```ruby
def user_params
params.require(:user).permit(:email)
end
```

### Set the routes

edit config/routes.rb

    resources :users