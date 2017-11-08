[![Build Status](https://travis-ci.org/avvertix/franc-bin.svg?branch=master)](https://travis-ci.org/avvertix/franc-bin)

# Franc as Binary

The [Franc](https://github.com/wooorm/franc) Natural Language Detection library inside a single executable with no dependencies.

## Getting Started

Download the pre-built binary for your Operating System from the [Release page](https://github.com/avvertix/tus-client-cli/releases/latest).

```bash
franc-bin [options] <string>
```

where `<string>` is the text to recognize

Options:

- `-h`, `--help` output usage information
- `-v`, `--version` output Franc version number
- `-m`, `--min-length <number>` minimum length to accept
- `-w`, `--whitelist <string>` allow specific languages
- `-b`, `--blacklist <string>` disallow specific languages
- `-a`, `--all` display all guesses with probability score

**Usage examples**

output language

```bash
$ franc "Alle menslike wesens word vry"
# afr
```

output language from stdin (expects utf8)

```bash
$ echo "এটি একটি ভাষা একক IBM স্ক্রিপ্ট" | franc
# ben
```

blacklist certain languages

```bash
$ franc --blacklist por,glg "O Brasil caiu 26 posições"
# src
```

## Supported languages

Support 186 languages. See [Franc supported languages for more info](https://github.com/wooorm/franc/tree/3.1.1/packages/franc#support).

> Franc can support more than 380 languages, but I this package stops at 186

## Compile from source

**Requirements:**

- NodeJS (8.0 or newer)
- NPM

> Yes, it is a Javascript project, but thanks to [PKG, by Zeit](https://github.com/zeit/pkg) can be packed into a real executable.

**Generate the binaries**

Download all the dependencies

```bash
# pull the dependencies
npm install
```
Now generate the binaries for MacOS, Windows and Linux in the `./dist` folder

```bash
# Build the executables
npm run production
```

## Contribution

Contributions are welcomed, just make a pull request.

## License

This project is licensed under the MIT license, see `LICENSE.txt`.
