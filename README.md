# React Shopping Cart

[![Netlify Status](https://api.netlify.com/api/v1/badges/3015988c-0069-4d65-8e29-4a7e3ceaa9c5/deploy-status)](https://app.netlify.com/sites/deeleman-react-shopping-cart/deploys) 
[![Build Status](https://travis-ci.org/deeleman/react-shopping-cart.svg?branch=master)](https://travis-ci.org/deeleman/react-shopping-cart)
[![Coverage Status](https://coveralls.io/repos/github/deeleman/react-shopping-cart/badge.svg?branch=master)](https://coveralls.io/github/deeleman/react-shopping-cart?branch=master)
[![Website deeleman-react-shopping-cart.netlify.app](https://img.shields.io/website-up-down-green-red/https/deeleman-react-shopping-cart.netlify.app.svg)](https://deeleman-react-shopping-cart.netlify.app)
[![GitHub license](https://img.shields.io/github/license/deeleman/react-shopping-cart.svg)](https://github.com/deeleman/react-shopping-cart/blob/master/LICENSE)
[![GitHub version](https://badge.fury.io/gh/deeleman%2Freact-shopping-cart.svg)](https://github.com/deeleman/react-shopping-cart)

Interactive, customisable shopping cart demo with discounts computation functionality and real-time total order price tracking, built on top of HTML, [SASS](https://sass-lang.com/), [TypeScript](https://www.typescriptlang.org/), [React](https://reactjs.org/) and the [Redux Toolkit](https://redux-toolkit.js.org/), and leveraging the [React Testing Library](https://testing-library.com/docs/react-testing-library/intro) for comprehensive features validation in a UI enhanced by (limited) responsiveness.

A **live running build** of this project is available at https://deeleman-react-shopping-cart.netlify.app.

![Example image](./public/docs/example.png?raw=true)

## Setting up your environment
The minimum requirements for running this project, either on development or production mode, and its development scripts are `node v12.16.0` and `npm v.6.14.15`, or later versions. Probably this project will run seamlessly on older versions of `node` and `npm` but we recommend using the latest [LTS versions](https://nodejs.org/).

This project relies on [Parcel](https://parceljs.org/) for spawning dev environments, running builds and handling code optimisations. All interaction with Parcel has been abstracted in custom npm commands for your convenience.

### Installing dependencies
As a first step to spawn a development environment or production build, please run either `yarn` or `npm install` to pull all the required dependencies for this project.

### Configuring the project settings

> **Please note**: This step is optional if you aim to run the application in dev mode only. The project is shipped with all settings preconfigured by default so you can leverage data fixtures already baked into the development server environment. Feel free to skip to the next section if you do not want to customize your data preferences.

The project is designed to fetch all data regarding products and discounts rules from a given REST API. Particularly, the project will fetch the information required to populate a full product catalogue and pricing rules for prices and discounts by fetching data from two separate endpoints.

You can update this setup by accessing [/src/settings.ts](https://github.com/deeleman/react-shopping-cart/blob/master/src/settings.ts#L5-L6) and editing the following parameters:
* `items`: URL for the remote REST API endpoint that exposes product items for our store.
* `discountRules`: URL for the remote REST API endpoint that exposes configuration rules for discounts applicable.

You will want to rebuild the project after updating these settings, although this action will be automatically triggered by Parcel when running the application in development mode.

#### Type schemas to abide when configuring custom API endpoints

The application comes preconfigured with testing URLs pointing to local JSON resources. In case you want to fetch data from any other third-party API of your choice, please refer to the [API model schemas](https://github.com/deeleman/react-shopping-cart/blob/master/src/app/types/api.ts), corresponding to product items and discount rules. Feel free to check the examples provided in the [API fixtures](public/api/fixtures) folder.

#### Color themes
The overall aplication theme and minor responsiveness settings have been striped out from the application stylesheets and made available as an editable SASS map available at [src/sass/_theme.scss](src/sass/_theme.scss) for your editing delight.

## Firing up a development environment
You can spawn a development environment by running `yarn dev` or `npm run dev` in the console.

The system will generate all the artifacts and assets and the compiled site will be available at http://localhost:9000 in _watch mode_, so the application will be recompiled upon changes on the source code.

## Building the project for production
Please execute `yarn build` or `npm run build` in your terminal window. 

Parcel will navigate through the entire application tree and build the site into the `/dist` folder. All files will be conveniently hashed to prevent caching issues.

## Code linting and testing
The code in this application is audited with 
[ESLint](https://eslint.org/) to ensure code consistency, and unit tests built on top of [Jest](https://jestjs.io/) and the [React Testing Library](https://testing-library.com/docs/react-testing-library/intro). The following commands have been made available for your convenience:

- `yarn lint`: lints all TypeScript files, reporting code quality issues if any.
- `yarn test`: runs all the application tests.

### Code coverage reports
[Jest](https://jestjs.io/) has been configured to generate a full code coverage report in HTML format on every time run of the `test` command. This coverage report can be found at `/coverage/lcov-report` after tests are run successfully.

Code coverage reports are also [available online at Coveralls.io](https://coveralls.io/github/deeleman/react-shopping-cart?branch=master).


