# grunt-less

LESS task for grunt.

## Getting Started
Install this grunt plugin next to your project's [grunt.js gruntfile][getting_started] with: `npm install grunt-less`

Then add this line to your project's `grunt.js` gruntfile:

```javascript
task.loadNpmTasks('grunt-less');
```

[grunt]: https://github.com/cowboy/grunt
[getting_started]: https://github.com/cowboy/grunt/blob/master/docs/getting_started.md

## Documentation
This task is a [multi task][types_of_tasks], meaning that grunt will automatically iterate over all `less` targets if a target is not specified.

### Target Properties
*   __src__*(required)*: The LESS file(s) to be compiled. Can be either a string or an array of strings. If more than one LESS file is provided, each LESS file will be compiled individually and then concatenated together.
*   __dest__*(required)*: The path where the output from the LESS compilation should be placed. Must be a string as there can be only one destination.
*   __options__*(optional)*: An object of LESS options. As of right now, the only options supported are ```compress``` and ```yuicompress```.

### Example

```javascript
// project configuration
grunt.initConfig({
    less: {
        signup: {
            src: 'signup.less',
            dest: 'signup.css'
        },
        homepage: {
            src: ['banner.less', 'app.less'],
            dest: 'homepage.css',
            options: {
                yuicompress: true
            }
        }
        all: {
            src: ['signup.less', 'banner.less', 'app.less'],
            dest: 'all.css',
            options: {
                compress: true
            }
        }

    }
});
```

[types_of_tasks]: https://github.com/cowboy/grunt/blob/master/docs/types_of_tasks.md

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt][grunt].

## Release History
*   __04/04/2012 - 0.1.0__: Initial release.

## License
Copyright (c) 2012 Jake Harding  
Licensed under the MIT license.
