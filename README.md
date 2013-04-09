# Keboola Public Projects Guidelines

This document contains requirements and recommendations for open source projects, specifically for PHP a Javascript projects.

## Common project requirements

 - README.md file
   - Purpose of project
   - Installation and usage
   - Development of project - tests execution, build process, etc.
   - Travis build status
 - [MIT license](http://en.wikipedia.org/wiki/MIT_License)
 - Follow [Semantic Versioning](http://semver.org/)
 - [Travis](https://travis-ci.org/) Continuous Integration
   - lint
   - unit tests
   - e2e tests


## PHP project requirements
 - Define as [Composer](https://getcomposer.org/) package - `composer.json` file
 - Register project to [Packagist](https://packagist.org/) by [Keboola user](https://packagist.org/packages/keboola)
   - Package name must follow: `keboola/project-name`
   - Register package using the Packagist web UI
   - Set up Github service hook (Use keboola user and token)
 - Project build using ANT
   - lint
   - phpmd
   - phpcs - Keboola coding style check
   - unit and e2e tests
 - Follow [PSR-0](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md) standard for class a namespace naming, base namespace must be `Keboola`
 - Example project: [Keboola PHP CSV](https://github.com/keboola/php-csv)

## Javascript/css/html project requirements
 - Define and register as [Bower](http://twitter.github.io/bower/) package - `component.json` file
 - Project build using [Grunt](http://gruntjs.com/)
   - lint
   - optionally coffee
   - concat, minify
   - unit and e2e tests -  [Karma runner](http://karma-runner.github.io/0.8/index.html) and [Jasmine](http://pivotal.github.com/jasmine/)
 - Github pages pages with live demos
 - Example project: [Angular KB](https://github.com/keboola/angular-kb)