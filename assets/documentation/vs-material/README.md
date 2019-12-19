![angular](https://cdn-images-1.medium.com/max/2600/1*1EyPLwkaQ8aWK4ziht0Pfg.png)

# @vs/material

![node version](https://img.shields.io/badge/%40angular%2Fmaterial-v8.0.2-informational.svg)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)
[![website](https://img.shields.io/website/http/ng-showcase.vs.it.ru.svg)](http://ng-showcase.vs.it.ru)
![Build passing](https://img.shields.io/badge/build-passing-success.svg)

This library is wrapper for [Angular Material](https://material.angular.io) library
that contains components, directives, pipes and etc.

See [Demo](http://ng-showcase.vs.it.ru) page.

## Dependencies

> NOTE: If you want to use this library you should add dependencies below to your project.

- [@angular/material](https://material.angular.io/) _Component infrastructure and Material Design components for Angular_

## Available features

| Feature   | Module           |
| --------- | ---------------- |
| _input_   | VsMatInputModule |

## Custom pages

| Page                                | Module                                |
| ----------------------------------- | ------------------------------------- |
| _403 Forbidden_ (first)             | PageForbiddenFirstModule              |
| _404 Not found_ (cloud)             | PageNotFoundCloudModule               |
| _Under construction_ (blacksmith)   | PageUnderConstructionBlacksmithModule |
| _Under construction_ (godzilla)     | PageUnderConstructionGodzillaModule   |

## Using the library

### Step 1: Install `vs-material`:

##### via NPM:

```bash
npm install --save @vs/material
```

### Step 2: Import the modules:

```diff
import { NgModule } from '@angular/core';
+ import { VsMatInputModule } from '@vs/material/form-fields';

@NgModule({
  declarations: [AppComponent],
  imports: [
+   VsMatInputModule
  ],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

### Step 3: Include a theme:

To allow customization and theming, `@vs/material` bundle includes [Angular Material theming](https://material.angular.io/guide/theming#defining-a-custom-theme).
You should add this to your `styles.scss` or custom file `_theme.scss`.

```scss
@import '~@vs/material/scss/theming';
// Include the common styles for Angular Material.
@include mat-core();
// Define the palettes for your theme using the Material Design palettes available in palette.scss
// (imported above). For each palette, you can optionally specify a default, lighter, and darker
// hue. Available color palettes: https://material.io/design/color/
$app-primary: mat-palette($mat-indigo);
$app-accent: mat-palette($mat-pink, A200, A100, A400);
// The warn palette is optional (defaults to red).
$app-warn: mat-palette($mat-red);

// Create the theme object (a Sass map containing all of the palettes).
$app-theme: mat-light-theme($app-primary, $app-accent, $app-warn);

// Include theme styles for core and each component used in your app.
@include vs-material-theme($app-theme);
```

## Develop

### Build

To build this project run the command below in the applications root folder.

```bash
$ npm run lib:vs-material:build
```

The build artifacts will be stored in the `dist/vs-material` directory.

### Package

After building library we can package it. Just run the command below in the applications root folder.

```bash
$ npm run lib:vs-material:pack
```

The _\*.pkg_ artifact will be stored in the `dist/vs-material` directory.

### Publish

After building your library, go to the dist folder `cd dist/vs-material` and run `npm publish`.

### Documentation

To generate the documentation, this starter uses [compodoc](https://github.com/compodoc/compodoc):

```bash
npm run compodoc
npm run compodoc:serve
```

### Commits

> NOTE: If installed globally (`npm i -g commitizen`), you can use `git cz` instead of `git commit` when committing code.

Used [Commitizen](https://github.com/commitizen/cz-cli) that gives conventional commit messages,
that can be analyzed to determine the next version.

That's why **for commit we should use the command below**:

```bash
npm run commit
```

> NOTE: No dot at the end of the line. Only lower-case letters.
See all [Rules](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional#rules).

## Versioning

Used [SemVer](http://semver.org/) specification and [@lerna/version](https://github.com/lerna/lerna/tree/master/commands/version#lernaversion) tool.
Bump version of packages changed since the last release, just run the command below:

```bash
npm run version
```

### Changelog

Used [Conventional changelog](https://github.com/conventional-changelog/conventional-changelog) for generating a CHANGELOG.md from git metadata.
This tool only works when we follow Conventional Commits rules.

### Code scaffolding

Run `ng generate component component-name --project vs-material` to generate a new component.
You can also use `ng generate directive | pipe | service | class | guard | interface | enum | module --project vs-common`.

> Note: Don't forget to add `--project vs-material` or else it will be added to the default project in your `angular.json` file.

### Running unit tests

Run `ng test vs-material` to execute the unit tests via [Karma](https://karma-runner.github.io).

### Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
