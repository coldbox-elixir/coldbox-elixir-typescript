ColdBox Elixir TypeScript Integration
========================

**(forked from laravel-elixir-typescript by [okaufmann](https://github.com/okaufmann/laravel-elixir-typescript))**

## Prerequirement
[ColdBox Elixir 2.0+](https://github.com/coldbox-elixir/core)

For optimal TypeScript development, consider installing typescript globally:

```bash
npm install -g typescript
```

## Installation
Install through Node.js

```js
npm install coldbox-elixir-typescript --save-dev
```

## Usage
A simple [gulp-typescript](https://github.com/ivogabe/gulp-typescript) wrapper for ColdBox Elixir.

Add it to your Elixir-enhanced Gulpfile, like so:

```js
var elixir = require( "coldbox-elixir" );

// import the dependency
require( "coldbox-elixir-typescript" );

elixir( function( mix ) {
  mix.typescript( "app.ts" );
} );
```

This will compile the `app.ts` file in `resources/assets/typescript/` and concat the compiled content into `includes/js/app.js`.

If you'd like to output to a different directory than the default `includes/js`, then you may override this by provide a path for `output` as well.

```js
mix.typescript( "app.ts", null, "includes/js/foo/bar.js" );
```

Further you could insert multiple files like

```js
elixir( function( mix ) {
  mix.typescript( [ "module1.ts", "module2.ts" ] );
} );
```

### tsconfig.json
Just put `tsconfig.json` into the root folder (where your gulpfile.js lives) and the plugin will automatically use it.

## Parameters

Bellow is the list of the available parameters:

- **src**: Filename for output
- **output**(optional): Where to place the output file. Default: `includes/js/`
- **baseDir,**(optional): Where to search your ts files. Default: `null`
- **options** (optional): Options to forward to the `gulp-typescript` used for compiling. All options under https://github.com/ivogabe/gulp-typescript#options
