check with rubocop the code
---------------------------

    rubocop

Update your entire project to Ruby 1.9 hash syntax 
http://effectif.com/ruby/update-your-project-for-ruby-19-hash-syntax

    find . -name \*.rb -exec perl -p -i -e 's/([^:]):(\w+)\s*=>/\1\2:/g' {} \;
