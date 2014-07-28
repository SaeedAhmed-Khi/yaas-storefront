# hybris Store Template for the Cloud-based Commerce Services

This is a store front application written in AngularJS that is meant to showcase the available commerce services and
act as starting point for creating a customized store front.

The out-of-the box payment provider is Stripe, configured with a test key.


## Project Organization

The project has been structured into domain modules under public/js/app.  Within each module, files are organized into
 controllers, directives, services, and templates.  API REST calls are made from the domain services.

Third party dependencies are copied to public/js/vendor via the bower-installer command as part of the npm postinstall target
(see package.json file).

### Application Events

'cart:updated' - fired when new cart information has been acquired from the service

## Testing

Tests are grouped by unit tests, end-to-end tests and styling tests under the "test" folder.  Unit tests can be run via
the scripts/test.sh; end-to-end tests can be run via scripts/e2e-test.sh.  Unit test code coverage is published to folder "coverage"
after running the unit test suite.


## Install

The following steps will demonstrate how to install and run the code on localhost.  At the end, you will be able to navigate
a pre-configured store.  Feel free to take items through checkout, using any Stripe test credit card number (https://stripe.com/docs/testing).

Please do not invoke any POST or PUT requests against the default tenant by programmatic means or through a REST console.
You may do so after setting up your own tenant.

###  1. System requirements

Install node and npm:

	$ brew install node	# on MacOS

Install grunt:

	$ npm install -g grunt-cli

Install bower:

	$ npm install -g bower


### 2. Project requirements

To locally install the project execute:

	$ npm install
	$ npm update 


### 3. Project startup

Start the project on localhost:9000 by executing:

	$ npm start

This will launch a storefront for an existing tenant.  Later, we will modify the application to go against your own tenant.

### 4. Project deployment

Preparing project for deployment (concatenation/minification/revisioning):

	$ grunt build

Then on index.html page only add a references to 2 generated static files from **dist** directory (dist/js/*.js, dist/css/*.css).

## Customization

Now, let's create a new tenant for your specific project so that you can modify your store and product offering as you see fit.

### 1.  Sign up for your a new store at [todo: MARKETPLACE link]

### 2.  Customize your store as defined in [todo: STORE ADMIN USER GUIDE link].  You may also want to create your own Stripe account,
so that you can use a unique Stripe API test key.

### 3.  Replace the default tenant id in the code base with your own.  You can find your tenant id at [todo: MARKETPLACE? link].
In file [todo: TENANT CONFIG FILE name], replace the default tenant id wity your own.

### 4.  Launch a new session against [todo: URL for storefront].  You should now see your customized store.

## Using a Web Server Other Than Node
TODO

## Limitations in the current service layer

- Checkout not done over SSL
- No tax support


## Resources

For in-depth API documentation, please visit [todo: DEV_PORTAL link]

## About this Project

### Why AngularJS?

With the rapid growth in JS frameworks, it is not feasible to evaluate all options, and it is still difficult to make a choice
among a small subset of options.
We were looking for a single-page framework with industry and community traction, support for unit testing,
decoupling of DOM manipulation and application logic, and terseness.  AngularJS fit these requirements very nicely.
Ultimately, the hybris commerce services support all needed business logic, and new client applications can be created with ease as needed.


### Infrastructure Tools

- [Bower](http://bower.io/) - package manager for all dependent libraries on the browser side
- [Grunt](http://gruntjs.com/) - JS task runner
- [Karma](http://karma-runner.github.io/) - test runner for AngularJS
- [Jasmine](http://jasmine.github.io/) - JS unit test framework
- [Protractor](https://github.com/angular/protractor) End-to-End (E2E) test framework for AngularJS
- [PhantomJS](http://phantomjs.org/) headless WebKit used for our E2E tests
- [Less](http://lesscss.org/) CSS pre-processor


### AngularJS & Other UI Packages
For a complete and up-to-date list of dependencies, please examine file bower.json.
- [Angular.js](http://angularjs.org/) AngularJS framework
- [Angular UI router](https://github.com/angular-ui/ui-router) State-based routing framework that helps achieve loose coupling
between modules.
- [Bootstrap](http://getbootstrap.com/) Enables responsiveness using the Bootstrap responsive grid.
- [Angular Bootstrap](http://angular-ui.github.io/bootstrap/) AngularJS implementation for Bootstrap widgets (for instance, pagination).
- [Restangular](https://github.com/mgonto/restangular) Library simplifying access of REST services through Angular's $resource service.
- [ngInfiniteScroll](http://binarymuse.github.io/ngInfiniteScroll/) Infinite scrolling in AngularJS. Used for the "browser product" pages.












