Steps to make use of this:

1. Install repo:
    1. `curl "http://php.webtutor.pl/en/wp-content/uploads/2011/09/repo" > ~/bin/repo`
    2. `chmod a+x ~/bin/repo`
2. `mkdir oe-repo`
3. `cd oe-repo`
4. `repo init -u https://github.com/kergoth/oe-repo-manifest`
5. `repo sync`
6. `make` (to start a build)

You may run `make help` to see the available targets in the makefile wrapper.

Now you can use repo subcommands to interact with the repositories. Useful ones:

- sync
- start
- branch
- status
- diff
- forall

By default, each repository's HEAD is floating on the most recent upstream
commit. To start development in one or more of the projects, use 'repo start'.
E.g. `repo start master oe-core`. Now this branch is created, pointing at the
commit which it was floating on, and you're free to hack away, commit, and
push. Once the changes have been pushed upstream, you can run `repo prune` to
drop the now unnecessary local branches and be floating again.
