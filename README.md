<h1 align="center">echo-command-line-parameters</h1>
<h3 align="center">Figure Your Way Out of Command Line Quoting and Escaping Hell!</h3>
<p align="center">
<a href="https://github.com/leafac/echo-command-line-parameters"><img alt="Source" src="https://img.shields.io/badge/Source---"></a>
<a href="https://github.com/leafac/echo-command-line-parameters/actions"><img alt="Continuous Integration" src="https://github.com/leafac/echo-command-line-parameters/workflows/.github/workflows/main.yml/badge.svg"></a>
</p>

You call this program with some command-line parameters, and it echoes them back to you (as JSON). It’s useful to test how quotes and escapes are parsed in the command line, specially in weird contexts ([I created this to debug Windows issues when calling commands from within REAPER](https://youtu.be/E4R4wlfKdcw)!).

[It’s a single line of code, really.](index.js)

### Installation

<https://github.com/leafac/echo-command-line-parameters/releases/latest>

### Usage Examples

```console
$ ./echo-command-line-parameters-macos
[]

$ ./echo-command-line-parameters-macos hello
[
  "hello"
]

$ ./echo-command-line-parameters-macos hello world
[
  "hello",
  "world"
]

$ ./echo-command-line-parameters-macos "hello world"
[
  "hello world"
]

$ ./echo-command-line-parameters-macos "hello \" world"
[
  "hello \" world"
]

$ echo 'another parameter' | xargs ./echo-command-line-parameters-macos "hello \" world"
[
  "hello \" world",
  "another",
  "parameter"
]
```
