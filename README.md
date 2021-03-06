<h1 align="center">
    Laravel Mix Versionhash
    <br>
    <a href="https://www.npmjs.com/package/laravel-mix-versionhash"><img src="https://img.shields.io/npm/v/laravel-mix-versionhash.svg?style=for-the-badge" alt="npm" /></a> <a href="https://www.npmjs.com/package/laravel-mix-versionhash"><img src="https://img.shields.io/npm/dt/laravel-mix-versionhash.svg?style=for-the-badge" alt="npm" /></a>
</h1>

Auto append hash to file instead of using virtual one [Read More](https://github.com/JeffreyWay/laravel-mix/issues/1022)

## Installation

```bash
npm install laravel-mix-versionhash --save
```

## Usage

```js
require('laravel-mix-versionhash')

mix.versionHash();
```

- for removing old files use [Clean for WebPack](https://github.com/johnagan/clean-webpack-plugin)

## Options

|   option  |  type  | default |                                            description                                            |
|-----------|--------|---------|---------------------------------------------------------------------------------------------------|
| length    | int    | `6`     | the hash string length                                                                            |
| delimiter | string | `'.'`   | the delimiter for filename and hash, <br> note that anything other than `. - _` will be removed |



## Known Issues

### Bug when combined with BrowserSync

Currently **v1.1.1**, there's a bug which causes BrowserSync to not start
after compiling the code. to get around that you can use `mix.versionHash()` like so

```js
// …

if (mix.inProduction()) {
  require('laravel-mix-versionhash')
  mix.versionHash()
}
```
