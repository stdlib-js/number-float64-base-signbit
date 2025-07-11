<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# signbit

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Return a boolean indicating if the sign bit for a [double-precision floating-point number][ieee754] is on (true) or off (false).

<section class="installation">

## Installation

```bash
npm install @stdlib/number-float64-base-signbit
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var signbit = require( '@stdlib/number-float64-base-signbit' );
```

#### signbit( x )

Returns a `boolean` indicating if the sign bit for a [double-precision floating-point number][ieee754] is on (`true`) or off (`false`).

```javascript
var bool = signbit( 4.0 );
// returns false

bool = signbit( -9.14e-307 );
// returns true

bool = signbit( 0.0 );
// returns false

bool = signbit( -0.0 );
// returns true
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var randu = require( '@stdlib/random-base-randu' );
var signbit = require( '@stdlib/number-float64-base-signbit' );

var sign;
var x;
var i;

for ( i = 0; i < 100; i++ ) {
    x = ( randu()*100.0 ) - 50.0;
    sign = signbit( x );
    sign = ( sign ) ? 'true' : 'false';
    console.log( 'x: %d. signbit: %s.', x, sign );
}
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->

* * *

<section class="c">

## C APIs

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- C usage documentation. -->

<section class="usage">

### Usage

```c
#include "stdlib/number/float64/base/signbit.h"
```

#### stdlib_base_float64_signbit( x )

Returns an integer indicating whether the sign bit for a double-precision floating-point number is on (`1`) or off (`0`).

```c
#include <stdint.h>

int8_t out = stdlib_base_float64_signbit( 3.14 );
```

The function accepts the following arguments:

-   **x**: `[in] double` input value.

```c
int8_t stdlib_base_float64_signbit( const double x );
```

</section>

<!-- /.usage -->

<!-- C API usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- C API usage examples. -->

<section class="examples">

### Examples

```c
#include "stdlib/number/float64/base/signbit.h"
#include <stdint.h>
#include <stdio.h>
#include <inttypes.h>

int main( void ) {
    double x[] = { 3.14, -3.14, 0.0, -0.0, 4.0, 1.0, -1.0, 1.0e308, -1.0e308 };

    int8_t out;
    int i;
    for ( i = 0; i < 9; i++ ) {
        stdlib_base_float64_signbit( x[ i ], &out );
        printf( "%lf => signbit: %" PRId8 "\n", x[ i ], out );
    }
}
```

</section>

<!-- /.examples -->

</section>

<!-- /.c -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/number-float32/base/signbit`][@stdlib/number/float32/base/signbit]</span><span class="delimiter">: </span><span class="description">return a boolean indicating if the sign bit for a single-precision floating-point number is on (true) or off (false).</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/number-float64-base-signbit.svg
[npm-url]: https://npmjs.org/package/@stdlib/number-float64-base-signbit

[test-image]: https://github.com/stdlib-js/number-float64-base-signbit/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/number-float64-base-signbit/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/number-float64-base-signbit/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/number-float64-base-signbit?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/number-float64-base-signbit.svg
[dependencies-url]: https://david-dm.org/stdlib-js/number-float64-base-signbit/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/number-float64-base-signbit/tree/deno
[deno-readme]: https://github.com/stdlib-js/number-float64-base-signbit/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/number-float64-base-signbit/tree/umd
[umd-readme]: https://github.com/stdlib-js/number-float64-base-signbit/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/number-float64-base-signbit/tree/esm
[esm-readme]: https://github.com/stdlib-js/number-float64-base-signbit/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/number-float64-base-signbit/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/number-float64-base-signbit/main/LICENSE

[ieee754]: https://en.wikipedia.org/wiki/IEEE_754-1985

<!-- <related-links> -->

[@stdlib/number/float32/base/signbit]: https://github.com/stdlib-js/number-float32-base-signbit

<!-- </related-links> -->

</section>

<!-- /.links -->
