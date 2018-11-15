# spdy web compiler

[![Build Status](https://travis-ci.org/swc-project/swc.svg?branch=master)](https://travis-ci.org/swc-project/swc)
[![codecov](https://codecov.io/gh/swc-project/swc/branch/master/graph/badge.svg)](https://codecov.io/gh/swc-project/swc)

-----

Make the web (development) faster.

swc is rust port of [babel][] and [closure compiler][].


# Installation

Requires nightly version of [rust][].

```sh
RUSTFLAGS='--cfg procmacro2_semver_exempt' cargo install --git https://github.com/swc-project/swc.git
```

# Features

## Transforms
New generation javascript to old-days javascript.

 - es3
    - [x] member expression literals
    - [x] peroperty literals
    - [ ] reserved words

 - es2015
    - [x] classes
    - [x] shorthand property
    - [x] spread element
    - [x] sticky regex (`y` flag)

 - es2016
    - [x] operator `**`


# Usage

`test.js`:
```js
8 + 8;
use(8 + 8, 8 ** 8);
```

## Example

```sh
swc jsc test.js
```

### Output

```
8 + 8;
use(8 + 8, Math.pow(8, 8));
```

## Example

```sh
swc jsc --optimize test.js
```

### Output

```
use(8 + 8, Math.pow(8, 8));
```




[babel]:https://github.com/babel/babel
[closure compiler]:https://github.com/google/closure-compiler
[rust]:https://www.rust-lang.org
