# npm-scripts-help
prints documentation for npm scripts.



## Install
npm i --save-dev npm-scripts-help

add help script to you package json's scripts

```
scripts:{
  "build" : "node build.js",
  "start": "node start.js",
  "help": "node node_modules/npm-scripts-help"
}

```

## Run
To see all scripts run: npm run help
to filter scripts run : npm run help [regex]

## adding documentation to scripts:

# inside package.json
add a proptery call scriptshelp in the root of package.json like this:
```
"scriptshelp" : {
  "help-message" : [
    "some explanation that will show on the top",
    "it can be multiple lines if you use an array",
    "or a single line if you use a string"
  ],
  "build" :"this will build the project",
  "start" : {
    "Desciption": "will run the project",
    "Usage": "npm start [--arg1]",
    "Long Description" : [
      "this is the first line",
      "this is the second line"
    ]
  }
}
```

# in .scriptshelprc.js file
add a file in the root of the project, next to package.json called scriptshelprc.js and export the scriptshelp object
```
module.exports = {
  "help-message" : [
    "some explanation that will show on the top",
    "it can be multiple lines if you use an array",
    "or a single line if you use a string"
  ],
  "build" :"this will build the project",
  "start" : {
    "Desciption": "will run the project",
    "Usage": "npm start [--arg1]",
    "Long Description" : [
      "this is the first line",
      "this is the second line"
    ]
  }
};
```


## scripts help object syntax
* scriptshelp must be an object.
* "help-message" is a special property that will show a general message before the scripts docs.
* add a key with a name matching any script you have in your npm scripts.
script name keys can be strings for single line description, arrays for multiline or objects.
objects can contain any key and their value must be a string or a string array.







