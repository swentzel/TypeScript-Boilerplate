LoxNode Server
======================
Description


GruntJS - Getting Started
----------

__Install NPM Modules__

```
npm install
```

#### Grunt Tasks

__Develop and Test__

```
grunt server
```

__Gruntfile.js with RequireJS Plugin__

```
module.exports = function(grunt) {

	grunt.initConfig({
		pkg: grunt.file.readJSON('package.json'),

		// Add plugins configuration options.
		requirejs: {
			compile: {
    			options: {
    	  			baseUrl: "path/to/base",
    	  			mainConfigFile: "path/to/config.js",
    	  			out: "path/to/optimized.js"
    			}
    		}
  		}
  	
  		// Loads the RequireJS plugin so we have access to it into this file.
  		grunt.loadNpmTasks('grunt-contrib-requirejs');

  		// Registers the default task to run the RequireJS plugin. 
  		// In Terminal/Command Line you will be able to type 'grunt' and
  		// this will run the 'requirejs' plugin in this file.
  		grunt.registerTask('default', ['requirejs']);
	});
	
};
```

Like I said in the comments you can just type `grunt` and that will run the 'requirejs' plugin.

__Create Other Tasks__

We can do the following to create/register other shortcut command tasks:

```
  grunt.registerTask('default', ['requirejs']);
  
  grunt.registerTask('src', ['pluginName1', 'pluginName2', 'pluginName3']);
  grunt.registerTask('web', ['pluginName1', 'pluginName2', 'pluginName3', 'pluginName4'])

```
Above you would call `grunt src` or `grunt web` depending on what series of plugins you would want to run.

One thing to point out is most plugins allow you to have multiple sub tasks. For example checkout the 'grunt-env' plugin below.

```
env: {
	src: {
		NODE_ENV : '../src/'
	},
	web : {
		NODE_ENV : '../web/'
	}
}
```
You can call `grunt env:src` or `grunt env:web` to run each sub task. If you were to call `grunt env` it would run both sub tasks.


####Installing Grunt

1. Install Node.js (This is required in order to run grunt).
	* Download and install Node.js from http://nodejs.org
       
2. Install grunt command line interface (CLI)
	* On the command line, run the following command: `npm install grunt-cli -g`

3. Install grunt packages
	* Change to the directory(where package.json is located
	* On the command line, run the following command: `npm install`
	* It take several minutes to completely download the dependencies. 
	* If this works successfully, a `node_modules` directory will be created. These files do not need to be redistributed or committed into source control.
	
If you have issues installing, please see the following tutorials:

* [Install Grunt on Mac](http://www.codebelt.com/javascript/install-grunt-js-on-a-mac/)
* [Install Grunt on Windows](http://www.codebelt.com/javascript/install-grunt-js-on-windows/)
