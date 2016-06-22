# Ledger Docker Image

This docker image contains the `ledger` command line tool.  Ledger is
a double-entry accounting tool that uses plaintext files for keeping
records.

## Usage

This command will run `ledger` in your current directory.

```
docker run -it --rm \
  -v "$(pwd)":"/host/${PWD##*/}" \
  -w "/host/${PWD##*/}" \
  --name ledger \
  scottbrown/ledger "*.sh"
```

That's a lot to type. Instead of wrecking your fingers, make a shell alias so you can simply type `ledger` within any directory you want to run it against your ledger files.

```
# in ~/.bashrc
alias ledger='docker run -it --rm -v "$(pwd)":"/host/${PWD##*/}" -w "/host/${PWD##*/}" --name=ledger scottbrown/ledger "$@"'
```

Now you can do `ledger` and it will validate your ledger file. Awesome sauce!

