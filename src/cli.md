# Command-line interface

Oxiby's command line interface is the program `obc`, which is short for "Oxiby compiler."

Here is a summary of its interface, which we can also see by running `obc` without any arguments:

```
The Oxiby compiler

Usage: obc <COMMAND>

Commands:
  check  Type checks an Oxiby program
  build  Builds an Oxiby program
  run    Builds and runs an Oxiby program
  clean  Removes the output directory and its contents
  new    Creates a new Oxiby project
  lex    Lexes an Oxiby source file and produces tokens
  parse  Parses an Oxiby source file and produces an abstract syntax tree
  help   Print this message or the help of the given subcommand(s)

Options:
  -h, --help     Print help
  -V, --version  Print version
```

In this guide, we'll use the `obc new` command to create a new Oxiby project.
After that, we'll use `obc run` to run our programs.

`obc run` will run the type checker, then build the Ruby output, and then execute Ruby with the built output.
If we just want to build our code without running it, we can use `obc build`.
And if we just want to type check our code without building it, we can use `obc check`.

To see all the options available for a particular command, execute the command with the `--help` argument, such as:

```
$ obc run --help
```

> [!WARNING]
> Since the type checker is still in development, there are cases where a valid Oxiby program will produce a type error or cause the compiler to crash.
> If this happens, and we want to ignore the errors and build the code anyway, we can use the `--no-check` option.
> This works for both `obc run` and `obc build`.
> Use it like this:
>
> ```
> $ obc run --no-check
> ```
