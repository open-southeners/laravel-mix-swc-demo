# Laravel Mix SWC demo

This is a repro of how to use SWC on a Laravel project.

The project includes the following:

- Laravel 9 (with Jetstream)
- InertiaJS
- Vue 3 (using JS)
- TailwindCSS 3

## Getting started

You could do this same thing just by running the following commands:

```sh
laravel new --jet swc_playground
cd swc_playground
yarn add -D laravel-mix-swc
```

Now you can use either [_FMM_](https://github.com/Schniz/fnm) or [_NVM_](https://github.com/nvm-sh/nvm) for managing the node version specified in the project (**not required and completely optional**)

```sh
fnm use
nvm use
```

And editing the webpack.mix.js file. More info in the repo: https://github.com/open-southeners/laravel-mix-swc

## Benchmarks

**Note: Before going into more details, these benchmarks were generating using the following:**

- My Macbook Pro 16" 2019 with a 6-core Intel i7 2.6GHz and 64GB of RAM, on charger.
- Versions: Node (16.15.0), 1.2.177 (SWC Rust core), 0.3.0 (laravel-mix-swc).
- No additional config provided, just using the default from the extension.

### Development builds

| Compiler         | 1st / 2nd / 3rd run      | Average time |
| ---------------- | ------------------------ | ------------ |
| SWC (`.swc`)     | 4.70s / 3.93s / 3.90s    | 4.17s        |
| Babel (`.js`)    | 5.05s / 4.16s / 4.14s    | 4.45s        |

### Production builds

| Compiler         | 1st / 2nd / 3rd run      | Average time |
| ---------------- | ------------------------ | ------------ |
| SWC (`.swc`)     | 5.86s / 5.36s / 5.39s    | 5.54s        |
| Babel (`.js`)    | 9.28s / 8.58s / 9.01s    | 8.96s        |
