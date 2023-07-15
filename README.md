[![Release binaries](https://github.com/avvertix/franc-bin/actions/workflows/ci.yml/badge.svg)](https://github.com/avvertix/franc-bin/actions/workflows/ci.yml)

# Franc as Binary

The [Franc](https://github.com/wooorm/franc) Natural Language Detection library inside a single executable with no dependencies.

## Getting Started

Download the pre-built binary for your Operating System from the [Release page](https://github.com/avvertix/franc-bin/releases/latest).

```bash
franc-bin [options] <string>
```

where `<string>` is the text to recognize

Options:

- `-h`, `--help` output usage information
- `-v`, `--version` output Franc-Cli version number
- `-m`, `--min-length <number>` minimum length to accept
- `-o`, `--only <string>` allow specific languages
- `-i`, `--ignore <string>` disallow specific languages
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

ignore certain languages

```bash
$ franc --ignore por,glg "O Brasil caiu 26 posições"
# src
```

## Supported languages

Support 187 languages. See [Franc supported languages for more info](https://github.com/wooorm/franc/tree/franc@4.1.0/packages/franc#support).

> Franc can support more than 380 languages, but this packaged version stops at 187

## Compile from source

**Requirements:**

- NodeJS (16.0 or newer)
- NPM

> Yes, it is a Javascript project, but thanks to [PKG, by Vercel](https://github.com/vercel/pkg) can be packed into a real executable.

**Generate the binaries**

Download all the dependencies

```bash
# pull the dependencies
npm ci
```
Now generate the binaries for MacOS, Windows and Linux in the `./dist` folder

```bash
# Build the executables
npm run production
```

## Contribution

Contributions are welcomed, just make a pull request.

## License

This project is licensed under the [`MIT` license](./LICENSE.txt).
