# GRUNT vs GULP

#### This project includes functional [Gulp](http://gulpjs.com/) and [Grunt](http://gruntjs.com/) setups for a production ready Angular-Typescript project.

![grunt vs gult](https://raw.githubusercontent.com/M-jerez/grunt-vs-gulp/master/docs/grunt-vs-gulp.png)

The Typescript project is based on [DanWahlin/AngularIn20TypeScript](https://github.com/DanWahlin/AngularIn20TypeScript)


---------------------------------

### Notes about each setup:
 - Both tasks manager generate the same assets.
 - Each task is written on it's own file. I use plugins that automatically load all tasks from a tasks directory.   [grunt-config-dir](https://www.npmjs.com/package/grunt-config-dir) & [gulp-load-plugins](https://www.npmjs.com/package/gulp-load-plugins)
 - Generated  CSS:
	 - **style.css** => Using Less preprocesor, Autoprefixer and css minification. Import are declared within the less files.
 - Generated  JAVASCRIPT: 
	 - **libs.js** => required libraries and dependencies for the app. 
	 - **app.js** => the Angular application, compiled from typescript.
	 - **views.js** => all angulart templates are compiled in to a single file.


### Conclusions on Grunt vs Gulp
 - Gulp better performance is a Myth. My personal opinion is that there is no performance diferrence, even though gulp task seems to finish faster, it takes almost the same time or more to refresh the browser. Performance depends a lot on how the watch task if configured, it can compile all project or jsut the relatred task.
 - SourceMaps works fine in Gulp, while in Grunt is almost impossible to produce SourceMaps that actually work.
 - Be extremely carefull with grunt async tasks execution. If you want to clean a directory, be sure do it syncronously, before any tother task is executed, or you might clean the directory after other tasks have finished.
 - Gulp watch may stop after some plugin fails.
