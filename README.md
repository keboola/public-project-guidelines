# Keboola Public Projects Guidelines

This document contains requirements and recommendations for open source projects, specifically for PHP a Javascript projects.

## Common project requirements

 - README.md file
   - Purpose of project
   - Installation and usage
   - Development of project - tests execution, build process, etc.
   - Travis build status
 - CHANGELOG.md
   - Changes summary for each released version
   - Date should be added for each release
   - [View Example](https://github.com/keboola/storage-api-php-client/blob/master/CHANGELOG.md)
 - [MIT license](http://en.wikipedia.org/wiki/MIT_License)
 - Follow [Semantic Versioning](http://semver.org/)
 - [Travis](https://travis-ci.org/) Continuous Integration
   - lint
   - unit tests
   - e2e tests


## PHP project 
 - Define as [Composer](https://getcomposer.org/) package - `composer.json` file
 - Register project to [Packagist](https://packagist.org/) by [Keboola user](https://packagist.org/packages/keboola)
   - Package name must follow: `keboola/project-name`
   - Register package using the Packagist web UI
   - Set up Github service hook (Use keboola user and token)
 - Project build recommended tasks
   - lint
   - phpmd
   - phpcs 
   - unit and e2e tests
 - Follow coding style defined in [PSR-0](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md), [PSR-1](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md) and [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) documents.
 - Only exception of PSR rules - use **tab** character for indenting
 - Follow [PSR-0](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md) standard for class a namespace naming, base namespace must be `Keboola`
 - Example project: [Keboola PHP CSV](https://github.com/keboola/php-csv)

## Javascript/css/html project
 - Use [Bower](http://twitter.github.io/bower/) as a package manager - `component.json` file
 - Register as [Bower](http://twitter.github.io/bower/) package if project is reusable component
 - Project build using [Grunt](http://gruntjs.com/) - You can use [Yeoman](http://yeoman.io/) for project scaffolding
   - lint
   - optionally coffee
   - concat, minify
   - unit and e2e tests -  [Karma runner](http://karma-runner.github.io/0.8/index.html) and [Jasmine](https://jasmine.github.io/)
 - Github pages pages with live demos
 - Coffeescript
 - Example project: [Angular KB](https://github.com/keboola/angular-kb)


## Recommended web libraries and frameworks

 - [Twitter Bootstrap](http://keboola.github.com/angular-kb) - front-end framework 
 - [Underscore](http://underscorejs.org/) set of handy functions
 - [AngularJS](http://angularjs.org/) Javascript framework
   - [Angular JS Resources and tutorials](https://github.com/kahlil/angular-resources?source=cr) 
 - Angular js modules
   - [Angular UI](http://angular-ui.github.com/) - UI directives
   - [Angular UI Bootstrap](http://angular-ui.github.io/bootstrap/) - native AngularJS directives based on Twitter Bootstrap's markup and CSS
   - [Angular KB](http://keboola.github.com/angular-kb) - Keboola projects specific directives and services

## Javascript project scaffolding and development
Example of initialization and development of new project using **Angular**, **Twitter bootstrap** written in Coffeescript.
Project is scaffolded by [Yeoman](http://yeoman.io/).
Development on local machine is assumed.

```bash
npm install -g yo grunt-cli bower generator-angular generator-karma # global libraries
mkdir sapi-demo
cd sapi-demo
yo angular sapi-demo --coffee --minsafe # create project structure
grunt server # development server with liveReload
```

Add Twitter Bootstrap, jQuery, Angular-KB library:

```bash
bower install jquery#~1.9.1 bootstrap#~2.3.1 angular-kb#~0.1.0 --save
```

Libraries will be downloaded into `app/components/` folder. Javascript and CSS files must be manually added to `app/index.html` to be included:

```html
<link rel="stylesheet" href="components/bootstrap/docs/assets/css/bootstrap.css">
<link rel="stylesheet" href="components/angular-kb/docs/build/angular-kb.css">


<script src="components/angular-sanitize/angular-sanitize.js"></script>
<script src="components/angular-kb/docs/build/angular-kb.js"></script>
```

Read more about project scaffolding: [Yeoman](http://yeoman.io/gettingstarted.html)

See [Demo Project](https://github.com/keboola/sapi-demo).
