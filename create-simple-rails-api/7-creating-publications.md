## 5 - Creating Publications

### Generate model and controller for publications

For publication this are the fields created for the moment:

```ruby
title:string
description:text
type:string
is_published:boolean
```

**terminal**

    rails generate model publication title:string description:text type:string is_published:boolean

    rails g scaffold_controller Publication

set relation profile and publications (in db)

**db/migrate/____create_publications**

```ruby
t.belongs_to :profile, index: true
```
set relation publication and profile and valitations (in models), can be has_one or has_many

**app/models/profile.rb**

```ruby
has_many :publication
```

**app/models/publication.rb**

```ruby
belongs_to :profile
```

```ruby
validates :title, presence: true
validates :description, presence: true
validates :type, presence: true
validates :profile, presence: true
```
**config/routes.rb**  

```ruby
resources :publications
```

**app/controllers/publication_controller.rb**

And change the params:

```ruby
  def publication_params
    params.require(:publication).permit
    (
      :title,
      :description
      :type
      :profile_id
    )
  end
```


It will be like that:

```ruby
class PublicationsController < ApplicationController
  before_action :set_publication, only: [:show, :update, :destroy]

  # GET /publications
  # GET /publications.json
  def index
    @publications = Publication.all

    render json: @publications
  end

  # GET /publications/1
  # GET /publications/1.json
  def show
    render json: @publication
  end

  # POST /publications
  # POST /publications.json
  def create
    @publication = Publication.new(publication_params)

    if @publication.save
      render json: @publication, status: :created, location: @publication
    else
      render json: @publication.errors, status: :unprocessable_entity
    end
  end

  # PATCH/PUT /publications/1
  # PATCH/PUT /publications/1.json
  def update
    @publication = Publication.find(params[:id])

    if @publication.update(publication_params)
      head :no_content
    else
      render json: @publication.errors, status: :unprocessable_entity
    end
  end

  # DELETE /publications/1
  # DELETE /publications/1.json
  def destroy
    @publication.destroy

    head :no_content
  end

  private

  def set_publication
    @publication = Publication.find(params[:id])
  end

  def publication_params
    params.require(:publication).permit
    (
      :name,
      :description
      :user_id
    )
  end
end
```

**app/controllers/publication_controller_spec.rb**

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


db install:

    rake db:migrate

Run rspec to check the app

    rspec