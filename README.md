# cSpell Dictionaries

This project is a collection of cspell dictionaries that can be added to a project as a submodule.

It's recommended that you add this project as a submodule to the root of your parent project with the directory `.cspell`.

## How to use

Once you've added the submodule you will configure your cspell configuration file to import the submodule `cspell.json` file. Additional information on [Importing/Extending Configurations](https://cspell.org/docs/Configuration/imports).

```json
    {
        "import": [
            "./.cspell/cspell-ext.json"
        ]
    }
```

Next you configure the dictionary files you want to use. Additional information on [Custom Dictionaries](https://cspell.org/docs/dictionaries/custom-dictionaries).

```json
    {
        "import": [
            "./.cspell/cspell-ext.json"
        ],
        "dictionaries: [
            "automotive"
        ]
    }
```
