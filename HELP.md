git config push.recurseSubmodules check
git config push.recurseSubmodules on-demand
git config -f .gitmodules submodule.DbConnector.branch stable
git submodule update --remote
git config status.submodulesummary 1
git config submodule.recurse true
git submodule foreach 'git stash'
git submodule foreach 'git checkout -b featureA'
git diff; git submodule foreach 'git diff'

###### Useful Aliases

$ git config alias.sdiff '!'"git diff && git submodule foreach 'git diff'"
$ git config alias.spush 'push --recurse-submodules=on-demand'
$ git config alias.supdate 'submodule update --remote --merge'