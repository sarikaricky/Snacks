## Reporting Issues and Asking Questions
Before opening an issue, please search the [issue tracker](https://github.com/instacart/Snacks/issues) to make sure your issue hasn't already been reported.

## Development

Visit the [Issue tracker](https://github.com/instacart/Snacks/issues) to find a list of open issues that need attention.

Clone the repo:
```
git clone git@github.com:instacart/Snacks.git
```

Then install dependencies:
```
cd ./Snacks
yarn
```
or
```
cd ./Snacks
npm install
```

### Working on a component
Start stylguide locally
```
yarn styleguide
```
or
```
npm styleguide
```

Go to http://0.0.0.0:6060 to see all components. This environment has hot reloading and components can be added on the fly though the various doc files. Look for any file in a component's folder with `.md` for examples of component code that the styeguide will run automatically.

You can also enable continous testing (linting, snapshot and unit tests) on every file save by following instructions in the testing step below.

### Building

Running the `build` task will run tests and create a lib/dist.js file
```
yarn build
```
or
```
npm run build
```

Running the `styleguide:build` command will generate a static style guide site under the `styleguide` directory
```
yarn stlyeguide:build
```
or
```
npm run stlyeguide:build
```

### Testing

To run tests:
```
yarn test
```
or
```
npm run test
```

To continuously watch and run tests, run the following:
```
yarn test:watch
```
or
```
npm run test:watch
```

## Submitting Changes

* If it's a bug fix, open a new issue in the [Issue tracker](https://github.com/instacart/Snacks/issues).
* Create a new feature branch based off the `master` branch.
* Make sure all tests pass.
* Submit a pull request, referencing any issues it addresses.

Please try to keep your pull request focused in scope and avoid including unrelated commits.

If you're creating a new component, that component must be snapshot tested and follow the general coding practices

## Creating a new component
New components must:
* have comprehensive tests
* have comprehensive documentation
* follow our code conventions
* be reviewed and approved

## Code Conventions
* Do not use semicolons ;
* 2 spaces for indentation (no tabs)
* Prefer ' over "
* 120 character line length (except documentation)
* Readability over trickiness or performance
* Use the decorator pattern when applicable - ie @Radium
* Create stateless components when possible
* Create React `PureComponent`s if not stateless
* Create es6 classes inheriting from React's `Component` class if not pure or stateless
* Always include propTypes with as much specificity as possible - ie propTypes.shape is better than propTypes.object

Linting will run when you run tests, and most of the above rules will be caught.

### Tests
Tests are done using a few frameworks/libraries:
* [Jest](https://facebook.github.io/jest/) - Snapshot tests + assertion library
* [Sinon](http://sinonjs.org/) - Spies for testing function calling
* [Enzyme](https://github.com/airbnb/enzyme) - Testing DOM interactions like clicking

Tests are co-located with their components in a `__tests__` directory and are named `ComponentName.spec.js`, per Jest convention.

### Test Conventions
* Reliable over comprehensive
* Simple over convoluted  
* Fast over slow

## Documentation

Documentation is generated by [React Styleguidist](https://react-styleguidist.js.org) and can be augmented by a combination of JSDoc comments and by adding readme files for your components. Readme files for new components are required, and should be co-located with your component under a `docs` directory and be named `<YourComponent>.md`.

Running the `styleguide` command will start up a local server running the style guide on http://localhost:6060
```
yarn styleguide
```
or
```
npm run styleguide
```

Running the `styleguide:build` command will generate a static style guide site under the top-level `docs` directory. This gets built and hosted at https://instacart.github.io/Snacks/
```
yarn styleguide:build
```
or
```
npm run styleguide:build
```
