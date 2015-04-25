[![Build Status](https://travis-ci.org/twbs/grunt-sed.svg?branch=twbs)](https://travis-ci.org/twbs/grunt-sed)
[![Dependency Status](https://david-dm.org/twbs/grunt-sed.svg)](https://david-dm.org/twbs/grunt-sed)
[![devDependency Status](https://david-dm.org/twbs/grunt-sed/dev-status.svg)](https://david-dm.org/twbs/grunt-sed#info=devDependencies)

# grunt-sed

*This is a fork of the original repo with the changes we needed since things were going pretty slow upstream.*

Built on top of [replace][replace], grunt-sed is a Grunt plugin for performing search and replace on files.

[replace]: https://github.com/harthur/replace

## Usage

This plugin is a [multi task][types_of_tasks], meaning that Grunt will automatically iterate over all exec targets if a target is not specified.

[types_of_tasks]: https://github.com/gruntjs/grunt/blob/master/docs/types_of_tasks.md#multi-tasks

### Properties

* `path` - File or directory to search. Defaults to `'.'`.
* `pattern` -  String or regex that will be replaced by `replacement`. **Required**.
* `replacement` - The string that will replace `pattern`. Can be a function. **Required**.
* `recursive` - If `true`, will recursively search directories. Defaults to `false`.
* `include` - String or array of files to include.
* `exclude` - String or array of files/folders to exclude.

### Example

```js
grunt.initConfig({
  pkg: grunt.file.readJSON('package.json'),

  sed: {
    version: {
      pattern: '%VERSION%',
      replacement: '<%= pkg.version %>',
      recursive: true,
      exclude: ['*.min.js', 'node_modules']
    }
  }
});
```

## License

Copyright (c) 2013 [Jake Harding](http://thejakeharding.com)  
Licensed under the MIT License.
