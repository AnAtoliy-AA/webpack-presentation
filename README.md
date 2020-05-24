# webpack-presentation

DEMO: https://anatoliyak.github.io/webpack-presentation

using https://github.com/hakimel/reveal.js/

//0 slide

Hello today we'll talk about webpack 

//1 slide

At its core, webpack is a static module bundler for modern JavaScript applications. When webpack processes your application, it internally builds a dependency graph which maps every module your project needs and generates one or more bundles.

Any time one file depends on another, webpack treats this as a dependency. This allows webpack to take non-code assets, such as images or web fonts, and also provide them as dependencies for your application.

//2 slide

To get started you only need to understand its Core Concepts:
• Installation
•	Entry
•	Output
•	Loaders
•	Plugins
•	Mode
•	Browser Compatibility

An entry point indicates which module webpack should use to begin building out its internal dependency graph. webpack will figure out which other modules and libraries that entry point depends on (directly and indirectly).

The output property tells webpack where to emit the bundles it creates and how to name these files.

Out of the box, webpack only understands JavaScript and JSON files. Loaders allow webpack to process other types of files and convert them into valid modules that can be consumed by your application and added to the dependency graph.

While loaders are used to transform certain types of modules, plugins can be leveraged to perform a wider range of tasks like bundle 
optimization, asset management and injection of environment variables.

By setting the mode parameter to either development, production or none, you can enable webpack's built-in optimizations that correspond to each environment. The default value is production

//3 slide
Lets speak about Local installation.
Firstly You should install Node.js .Webpack runs on Node.js version 8.x and higher.


Installing locally is what recommended for most projects. This makes it easier to upgrade projects individually when breaking changes are introduced. 

//4 slide
Webpack easier to use than install)
you should import in one module and export in another

//5 slide
here you can see custom webpack.config.js
Since version 4.0.0, webpack does not require a configuration file to bundle your project. But it`s better to use it

I will show you the ways you can configure the entry property, in addition to explaining why it may be useful to you.
Here You can see the default value, but you can specify a different (or multiple entry points) by setting an entry property in the webpack configuration. Also you can use object syntax and Separate App and Vendor Entries.


Configuring the output configuration options tells webpack how to write the compiled files to disk. Note that, while there can be multiple entry points, only one output configuration is specified.

//6 slide

Here you can see you standart HTML file. You can write your code here as usual.

Then run webpack on the command-line to create bundle.js

//7 slide
Loaders
At a high level, loaders have two properties in your webpack configuration:
1.	The test property identifies which file or files should be transformed.
2.	The use property indicates which loader should be used to do the transforming.
webpack.config.js

Loaders are transformations that are applied to the source code of a module. They allow you to pre-process files as you import or “load” 
them. Thus, loaders are kind of like “tasks” in other build tools and provide a powerful way to handle front-end build steps. Loaders can transform files from a different language (like TypeScript) to JavaScript or load inline images as data URLs. Loaders even allow you to do things like import CSS files directly from your JavaScript modules!
To do this, you would start by installing the loaders you need

//8 slide

Plugins
In order to use a plugin, you need to require() it and add it to the plugins array. Most plugins are customizable through options. Since you can use a plugin multiple times in a configuration for different purposes, you need to create an instance of it by calling it with the new operator.
In the example above, the html-webpack-plugin generates an HTML file for your application by injecting automatically all your generated 
bundles.
Using plugins in your webpack configuration is straightforward. 

Plugins are the backbone of webpack. webpack itself is built on the same plugin system that you use in your webpack configuration!
They also serve the purpose of doing anything else that a loader cannot do.

//9 slide
UnusedFilesWebpackPlugin
After installation, you will receive warnings about any unused files.

CaseSensitivePathsPlugin
Now when importing a module with the wrong case in the path, you will always get an error

CircularDependencyPlugin 
During development, sometimes there are problems with resolving dependencies - two modules import each other and a circular dependency is obtained. Now, when a circular dependency appears, you will receive a warning

SpeedMeasurePlugin
The build output will add information about the total build time, the execution time of each plugin and each chain of loaders.

DefinePlugin
The DefinePlugin allows you to create global constants which can be configured at compile time. This can easily be used to manage import 
configurations like API keys and other constants that can be changed easily. The best way to use this plugin is to create a .env file with different constants and access them in our configuration using dotenv package then we can directly refer to these constants in our code.

//10 slide

Hot Module Replacement
Hot Module Replacement (HMR) exchanges, adds, or removes modules while an application is running, without a full reload. This can 

significantly speed up development in a few ways:
•	Retain application state which is lost during a full reload.
•	Save valuable development time by only updating what's changed.
•	Instantly update the browser when modifications are made to CSS/JS in the source code, which is almost comparable to changing styles 
directly in the browser's dev tools.

//11 slide

Webpack supports all browsers that are ES5-compliant (IE8 and below are not supported). webpack needs Promise for import() and 
require.ensure(). If you want to support older browsers, you will need to load a polyfill before using these expressions.

If you want to know more about webpack, please read the official documentation!
