# submodules-test-parent
Used the following command to create the child submodule.  Note this also creates the .gitmodules file in the parent repo.

    git submodule add git@github.com:amcginlay/submodules-test-child child

Later, when child_file.txt is updated, the parent does not know because its submodule was pinned at 4886452.  This command:

    git submodule foreach 'git checkout master && git reset --hard origin/master'

will move the submodule reference to the latest SHA
