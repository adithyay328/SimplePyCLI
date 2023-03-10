# PyCLI
PyCLI is a really simple library for interactive python CLIs. I mostly built
it for personal use on side projects, but feel free to use it.

## Install Instructions
To install:
```python
pip install simplepycli
```

## Basic API Example
The API is really simple, so here is a comprehensive example of how it works. This is also available at example.py:

```python
from simplepycli import PyCLIApp

# The only paramater for PyCLIApp is the marker to use in front of the terminal; defaults to "> "
app = PyCLIApp("> ")

@app.command("egg", "Prints egg to the console")
def egg(params):
  print("egg")

@app.command("echotwice", "Echos the string passed in as a paramater twice")
def echotwice(params):
  for i in range(2):
    print(params)

app.run()
```

This outputs a terminal that behaves like this
```
> egg
egg
> echotwice abc
abc
abc
> help
exit : Exit the current CLI session and close the program.
help : List available commands and their help messages.
clear : Clear the current command line.
egg : Prints egg to the console
echotwice : Echos the string passed in as a paramater twice
> |
```
