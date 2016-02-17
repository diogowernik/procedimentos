## 5 - Creating Profiles

### Generate model and controller for profile

For profile this are the fields created for the moment:

```ruby
name:string
description:text
site_url:string
state:string
```

**terminal**

    rails generate model profile name:string description:text site_url:string state:string

    rails g scaffold_controller Profile

**db/____create_profiles**

Say that the profile belongs_to user

```ruby
t.belongs_to :user, index: true
```

**config/routes.rb**  

```ruby
resources :profiles
```

**app/models/profile.rb**

```ruby
validates :name, presence: true
validates :description, presence: true
```


**app/controllers/profile_controller.rb**

delete because is for rails full application, not needed for only rails-api:

```ruby
describe "GET #new" do
(...)
end

describe "GET #new" do
(...)
end

describe "GET #edit" do
(...)
end

it "redirects to the created membership" do
(...)
end
  
it "re-renders the 'new' template" do
(...)
end

it "re-renders the 'edit' template" do
(...)
end
```

It will be like that:

```ruby
class ProfilesController < ApplicationController
  before_action :set_profile, only: [:show, :update, :destroy]

  # GET /profiles
  # GET /profiles.json
  def index
    @profiles = Profile.all

    render json: @profiles
  end

  # GET /profiles/1
  # GET /profiles/1.json
  def show
    render json: @profile
  end

  # POST /profiles
  # POST /profiles.json
  def create
    @profile = Profile.new(profile_params)

    if @profile.save
      render json: @profile, status: :created, location: @profile
    else
      render json: @profile.errors, status: :unprocessable_entity
    end
  end

  # PATCH/PUT /profiles/1
  # PATCH/PUT /profiles/1.json
  def update
    @profile = Profile.find(params[:id])

    if @profile.update(profile_params)
      head :no_content
    else
      render json: @profile.errors, status: :unprocessable_entity
    end
  end

  # DELETE /profiles/1
  # DELETE /profiles/1.json
  def destroy
    @profile.destroy

    head :no_content
  end

  private

  def set_profile
    @profile = Profile.find(params[:id])
  end

  def profile_params
    params.require(:profile).permit(:name, :description)
  end
end
```

db install:

    rake db:migrate

Run rspec to check the app

    rspec