# cSpell Dictionaries

This project is a collection of cSpell dictionaries that can be added to a project as a submodule.

It's recommended that you add this project as a submodule to the root of your parent project with the directory `.cspell`.

## How to add submodule to a project

To add the submodule to an existing project, execute the following commands. When adding this submodule, it's recommended to use a clean branch since using submodules can be confusing to users.

```bash
git submodule add https://github.com/hype8912/cspell-dictionaries.git .cspell
git submodule update --init --recursive
```

## How to use in a project

Once you've added the submodule to the project, you will configure your cSpell configuration file to import the submodule `cspell-ext.json` file. Additional information on [Importing/Extending Configurations](https://cspell.org/docs/Configuration/imports).

```json
{
  "$schema": "https://raw.githubusercontent.com/streetsidesoftware/cspell/main/cspell.schema.json",
  "import": ["./.cspell/cspell-ext.json"],
  "version": "0.2"
}
```

Next, you configure the dictionary files you want to use in your cSpell configuration file. Additional information on [Custom Dictionaries](https://cspell.org/docs/dictionaries/custom-dictionaries).

```json
{
  "$schema": "https://raw.githubusercontent.com/streetsidesoftware/cspell/main/cspell.schema.json",
  "import": ["./.cspell/cspell-ext.json"],
  "version": "0.2",
  "dictionaries": ["automotive", "en"]
}
```

## cSpell Basic Usage

Below are some simple instructions for getting started using cSpell.

### Linting a repository

To lint a repository with cSpell, execute the following command in the terminal of the project.

```bash
# Locally installed.
cspell lint .
```

```bash
# Using the node package locally.
npx cspell lint .
```

### Searching for a word in a dictionary

To search for a word in the dictionaries, execute the following command in the terminal of the project.

```bash
# Locally installed.
cspell trace --all word
```

```bash
# Using the node package locally.
npx cspell trace --all word
```

### Adding additional dictionaries using Node

Execute the following command to include an extended [bundle of cSpell dictionaries](https://www.npmjs.com/package/@cspell/dict-cspell-bundle).

```bash
npm install -g -D @cspell/dict-cspell-bundle
```

## How to remove .cspell submodule

1. Delete the `.cspell` directory.
1. Either delete the `.gitmodules` if you only have one submodule. Otherwise, open the `.gitmodules` file and remove the lines for `.cspell`.
1. In File Explorer, navigate to the `.git/modules` directory of the project.
1. Delete the `.cspell` directory.
1. Commit the changes and the submodule will be removed from the project.
