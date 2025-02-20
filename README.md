# node-variable-replace
The simplest templating engine: replace variables in files

### Templating language

Surround variables names by percents.
Supports nested variables
Works with any text file.

```
the value of var1 variable is: %var1%
the value of the key1 attr of var2 is %var2.key1%
```

Replace with values from either inline data or json file(s).

### Usage

##### Command line

```shell
npm install -g variable-replace
```

```shell
variable-replace sourcepath1 [sourcepath2 sourcepath3] --dest=destpath --data=datasource.json [--data-myvarname=value]
```

##### Node JS

```shell
npm install variable-replace
```

```javascript
require('variable-replace')({
    source: 'source/path',
    dest: 'dest/path',
    dataSource: 'data.json',
    inlineData: {
        var1 : 'val1',
        var2 : {
        	key1: 'val2'
        }
    }
})
```

### Options

#### options.source (Mandatory)
Mandatory
Type: String or array of String
Note: glob pattern supported

Files to process (input files)

#### options.dest
Mandatory
Type: String

Destination file or directory, where output file will be written.

#### options.dataSource
Optional
Type: String or array of String

Path(s) of json file(s) containing source of data for variable replacement.

#### options.inlineData
Optional
Type: Object

Inline source of data for variable replacement

#### options.variablePattern
Optional
Type: String or RegExp

The [Regular Expresssion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) used to match variables.
The first group must return the variable path.
Defaults to `/%([\w._-]+)%/g`

#### options.logLevel
Optional
Default: info
Type: "debug", "info", "warn", "error", "none"

Change logging level


##### Forked Project

This project is forked from https://www.npmjs.com/package/variable-replacer.

The purpose of the fork was to introduce the following features : 

> dest argument : allow to clearly separate and make it optionnal.

Now when no argument is provided for dest, the dest path is equal to file source path. 

## Contributing

Pull requests are welcome


## TODO

- Add support for inline input and output
- Add support for reusable replacer
- Improve error handling and logging
