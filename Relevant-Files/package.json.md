# package.json

The `package.json` is the application configuration file. All dependencies will be listed in this file.

Let's see what says this article by the website [docs.nodejitsu.com](https://docs.nodejitsu.com/articles/getting-started/npm/what-is-the-file-package-json/):
>All npm packages contain a file, usually in the project root, called package.json - this file holds various metadata relevant to the project. This file is used to give information to npm that allows it to identify the project as well as handle the project's dependencies. It can also contain other metadata such as a project description, the version of the project in a particular distribution, license information, even configuration data - all of which can be vital to both npm and to the end users of the package. The package.json file is normally located at the root directory of a Node.js project.

Now, let's take a look in the [Angular Guide](https://angular.io/guide/npm-packages):

>Both `npm` and `yarn` install packages identified in a package.json file.
The CLI `ng new` command creates a default `package.json` file for your project. This packages.json specifies a starter set of packages that work well together and jointly support many common application scenarios.
You will add packages to `package.json` as your application evolves. You may even remove some.

For example, you can find the default *scripts*, like: 

```javascript
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  }
```
Just for curiosity, in the above example we can see that we can use either `ng serve`, or `npm start` to start the application.

# Dependencies

The `package.json` file includes two sets of dependencies:
+ dev-dependencies
+ dependencies

The **dev-dependencies** are necessary to *develop* the application, while the **dependencies** are essential to *running* it.

Let's take a look at both of them:

```javascript
  "dependencies": {
    "@angular/animations": "^4.2.4",
    "@angular/common": "^4.2.4",
    "@angular/compiler": "^4.2.4",
    "@angular/core": "^4.2.4",
    "@angular/forms": "^4.2.4",
    "@angular/http": "^4.2.4",
    "@angular/platform-browser": "^4.2.4",
    "@angular/platform-browser-dynamic": "^4.2.4",
    "@angular/router": "^4.2.4",
    "core-js": "^2.4.1",
    "rxjs": "^5.4.2",
    "zone.js": "^0.8.14"
  }
```
See above, that is specified the version of each angular element.

Now, in the next example, we can find the version for the *TypeScript*, *Jasmine*, and many other libraries:

```javascript
  "devDependencies": {
    "@angular/cli": "1.4.9",
    "@angular/compiler-cli": "^4.2.4",
    "@angular/language-service": "^4.2.4",
    "@types/jasmine": "~2.5.53",
    "@types/jasminewd2": "~2.0.2",
    "@types/node": "~6.0.60",
    "codelyzer": "~3.2.0",
    "jasmine-core": "~2.6.2",
    "jasmine-spec-reporter": "~4.1.0",
    "karma": "~1.7.0",
    "karma-chrome-launcher": "~2.1.1",
    "karma-cli": "~1.0.1",
    "karma-coverage-istanbul-reporter": "^1.2.1",
    "karma-jasmine": "~1.1.0",
    "karma-jasmine-html-reporter": "^0.2.2",
    "protractor": "~5.1.2",
    "ts-node": "~3.2.0",
    "tslint": "~5.7.0",
    "typescript": "~2.3.3"
  }
```



