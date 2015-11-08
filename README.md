# node-variable-replacer
The simplest templating engine: replace variables in files

### Templating language

Surround variables names by percents.
Supports nested variables
Works with any text file.

```
the value of var1 variable is: %var1%
the value of the key1 attr of var2 is %var2.key1%
```

### Usage

##### Command line

```shell
npm install -g variable-replacer
```

```shell
variable-replacer sourcepath1 [sourcepath2 sourcepath3] destpath --data=datasource.json [--data-myvarname=value]
```

##### Node JS

```shell
npm install innosetup-compiler
```

```javascript
require('variable-replacer')({
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
Type: string or array of string
Note: glob pattern supported

Files to process (input files)

#### options.dest
Mandatory
Type: string

Destination file or directory, where output file will be written.

#### options.dataSource
Optional
Type: string or array of string

Path(s) of json file(s) containing source of data for variable replacement.

#### options.inlineData
Optional
Type: Object

Inline source of data for variable replacement

#### options.loglevel
Optional
Default: info
Type: "debug", "info", "warn", "error", "none"

Change logging level
