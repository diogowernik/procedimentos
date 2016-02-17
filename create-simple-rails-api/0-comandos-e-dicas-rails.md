Deletar banco de dados e gerar outro novo.

    rake db:drop && rake db:create && rake db:migrate

need to delete models

    rails destroy model profile
    
need to delete db data

    rails c
    Profile.delete_all

When working on validation controllers:

    boolean do not use validate