# Shellcheck Docker Image

This docker image contains the `shellcheck` command line tool.  Shellcheck
ensures that Bash scripts are valid and conform to best practices.

Maintaining shellcheck on your local system requires you to have a Haskell
runtime (cabal, ghc), which can be onerous when shellcheck updates.
Instead, you can make an alias to use this docker image whenever you want
to call shellcheck locally.

## Usage

This command will test all the shell scripts in your current directory.

```
docker run -it --rm \
  -v "$(pwd)":"/host/${PWD##*/}" \
  -w "/host/${PWD##*/}" \
  --name shellcheck \
  scottbrown/shellcheck "*.sh"
```

That's a lot to type.  Instead of wrecking your fingers, make a shell
alias so you can simply type shellcheck within any directory you want
to test your shell scripts.

```
# in ~/.bashrc
alias shellcheck='docker run -it --rm -v "$(pwd)":"/host/${PWD##*/}" -w "/host/${PWD##*/}" --name=shellcheck scottbrown/shellcheck "$@"'
```

Now you can do `shellcheck test.sh` and it will check your shell script.
Awesome sauce!

