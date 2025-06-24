# ESM Loader Demo

This project demonstrates various ESM loader implementations for Node.js.

## Project Structure

The project contains three example loaders:

### 1. Basic Module Overrides (`/loader`)

A simple loader that demonstrates how to override module resolution based on a mapping file.

- `loader.js`: Implements the custom `resolve` hook to map module specifiers based on overrides
- `overrides.json`: Contains module specifier mappings
- `index.js`: Demo file that imports a module using the custom loader
- `abc.js`: Sample module that gets loaded via the override

**Usage:**
```bash
node --loader ./loader/loader.js loader/index.js
```

### 2. HTTP Resolution (`/http-resolver`)

Enables importing modules directly from HTTP URLs.

- `loader.js`: Implements the `load` hook to fetch and load modules from HTTP(S) URLs
- `index.js`: Demo file that imports a module from an HTTP URL

**Usage:**
```bash
node --loader ./http-resolver/loader.js http-resolver/index.js
```

### 3. TypeScript Support (`/typescript`)

Enables direct loading and execution of TypeScript files.

- `loader.js`: Implements the `load` hook to transform TypeScript to JavaScript using esbuild
- `index.ts`: Main TypeScript demo file
- `ts-module.ts`: Sample TypeScript module
- `js-module.js`: Sample JavaScript module

**Usage:**
```bash
node --loader ./typescript/loader.js typescript/index.ts
```

## Requirements

- Node.js version that supports ESM loaders (14+, with better support in 16+)
- For TypeScript loader: esbuild package is required (included in package.json)

## Learning Resources

This project demonstrates the core concepts of ESM loaders:
- Module resolution overriding
- Custom module loading from alternative sources
- Source code transformation during loading

For more information, check the [Node.js documentation on ESM loaders](https://nodejs.org/api/esm.html#loaders)
