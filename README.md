# Lumino

![CI](https://github.com/AndreasJJ/Lumino/workflows/CI/badge.svg)
![.github/workflows/badge.yml](https://raw.githubusercontent.com/AndreasJJ/Lumino/badges/.github/badges/coverage.svg)

A simple library for handling conversion of color models and generating different color harmonies.

## Docs
### Transformations
#### `rgba2rgb`
Usage: ```import rgba2rgb from 'lumino/rgba2rgb'``` \
Alternative usage: ```import { rgba2rgb } from 'lumino'```

```typescript
import rgba2rgb from 'lumino/rgba2rgb';
import { OutputType } from 'lumino';

// Accepts an rgba-string, rgba object, or rgba array. It's also possible
// to specify output type to string, array or object. Object is default.
const res1 = rgba2rgb('rgb(255, 0, 0, 0.5)');
// => {r: 255, g: 128, b: 128 }
const res2 = rgba2rgb({r: 255, g: 0, b: 0, a: 0.5}, undefined, OutputType.STRING);
// => rgb(255, 128, 128)
const res3 = rgba2rgb([255, 0, 0, 0.5], undefined, OutputType.ARRAY);
// => [255, 128, 128]

// Accepts different backgrounds in rgb (default is white)
const res4 = rgba2rgb('rgb(255, 0, 0, 0.5)', 'rgb(0, 0, 0)');
const res5 = rgba2rgb('rgb(255, 0, 0, 0.5)', {r: 0, g: 0, b: 0});
const res6 = rgba2rgb('rgb(255, 0, 0, 0.5)', [0, 0, 0]);
// => {r: 128, g: 0, b: 0}
```

Alternative versions: \
Usage: ```import { rgba2rgbString } from 'lumino/rgba2rgb'``` \
Alternative usage: ```import { rgba2rgbString } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB string.

Usage: ```import { rgba2rgbObject } from 'lumino/rgba2rgb'``` \
Alternative usage: ```import { rgba2rgbObject } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB object.

Usage: ```import { rgba2rgbArray } from 'lumino/rgba2rgb'``` \
Alternative usage: ```import { rgba2rgbArray } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB array.

#### `hex2rgb`
Usage: ```import hex2rgb from 'lumino/hex2rgb'``` \
Alternative usage: ```import { hex2rgb } from 'lumino'```

```typescript
import hex2rgb from 'lumino/hex2rgb';
import { OutputType } from 'lumino';

// Accepts an hex-string, either of length 3, 4, 6 or 8 (not including the #).
// It's also possible to specify output type to string, array or object. Object is default.
const res1 = hex2rgb('#FF0000');
// => {r: 255, g: 0, b: 0 }
const res2 = hex2rgb('#F00', undefined, OutputType.STRING);
// => rgb(255, 0, 0)
const res3 = hex2rgb('#F00', undefined, OutputType.ARRAY);
// => [255, 0, 0]

// Accepts different backgrounds in hex (default is white)
const res4 = hex2rgb('#FF0000', '#000000');
const res5 = hex2rgb('#FF0000', '#000000');
const res6 = hex2rgb('#FF0000', '#000000');
// => {r: 128, g: 0, b: 0}
```

Alternative versions: \
Usage: ```import { hex2rgbString } from 'lumino/hex2rgb'``` \
Alternative usage: ```import { hex2rgbString } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB string.

Usage: ```import { hex2rgbObject } from 'lumino/hex2rgb'``` \
Alternative usage: ```import { hex2rgbObject } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB object.

Usage: ```import { hex2rgbArray } from 'lumino/hex2rgb'``` \
Alternative usage: ```import { hex2rgbArray } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB array.

#### `hex2rgba`
Usage: ```import hex2rgba from 'lumino/hex2rgba'``` \
Alternative usage: ```import { hex2rgba } from 'lumino'```

```typescript
import hex2rgba from 'lumino/hex2rgba';
import { OutputType } from 'lumino';

// Accepts an hex-string, either of length 3, 6 (automatically sets opacity to 1), 4 or 8 
// (not including the #).
// It's also possible to specify output type to string, array or object. Object is default.
const res1 = hex2rgb('#FF000099');
// => {r: 255, g: 0, b: 0, a: 0.6 }
const res2 = hex2rgb('#F009', OutputType.STRING);
// => rgb(255, 0, 0, 0.6)
const res3 = hex2rgb('#F009', OutputType.ARRAY);
// => [255, 0, 0, 0.6]
```

Alternative versions: \
Usage: ```import { hex2rgabString } from 'lumino/hex2rgba'``` \
Alternative usage: ```import { hex2rgbaString } from 'lumino'``` \
Description: Works as the main function, but only returns a RGBA string.

Usage: ```import { hex2rgbaObject } from 'lumino/hex2rgba'``` \
Alternative usage: ```import { hex2rgbaObject } from 'lumino'``` \
Description: Works as the main function, but only returns a RGBA object.

Usage: ```import { hex2rgbaArray } from 'lumino/hex2rgba'``` \
Alternative usage: ```import { hex2rgabArray } from 'lumino'``` \
Description: Works as the main function, but only returns a RGBA array.

#### `hsl2rgb`
**Notice**: This function rounds to the closest integer, as such some accuracy from hsl will be lost.
Usage: ```import hsl2rgb from 'lumino/hsl2rgb'``` \
Alternative usage: ```import { hsl2rgb } from 'lumino'```

```typescript
import hsl2rgb from 'lumino/hsl2rgb';

// Accepts an hsl-string, hsl object, or hsl array. It's also possible
// to specify output type to string, array or object. Object is default.
const res1 = hsl2rgb('hsl(0, 0%, 100%)');
// => {r: 255, g: 255, b: 255}
const res2 = hsl2rgb({h: 209, s: 100, l: 57.8}, undefined, OutputType.STRING);
// => rgb(40, 150, 255)
const res3 = hsl2rgb([120, 100, 50], undefined, OutputType.ARRAY);
// => [0, 255, 0]
```

Alternative versions: \
Usage: ```import { hsl2rgbString } from 'lumino/hsl2rgb'``` \
Alternative usage: ```import { hsl2rgbString } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB string.

Usage: ```import { hsl2rgbObject } from 'lumino/hsl2rgb'``` \
Alternative usage: ```import { hsl2rgbObject } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB object.

Usage: ```import { hsl2rgbArray } from 'lumino/hsl2rgb'``` \
Alternative usage: ```import { hsl2rgbArray } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB array.

#### `rgb2hsl`
**Notice**: This function rounds to a float with 2 decimals accuracy, as such some accuracy will be lost.
Usage: ```import rgb2hsl from 'lumino/rgb2hsl'``` \
Alternative usage: ```import { rgb2hsl } from 'lumino'```

```typescript
import rgb2hsl from 'lumino/rgb2hsl';

// Accepts an rgb-string, rgb object, or rgb array. It's also possible
// to specify output type to string, array or object. Object is default.
const res1 = rgb2hsl('rgb(255, 255, 255)');
// => {h: 0, s: 0%, l: 100%}
const res2 = rgb2hsl({r: 40, g: 150, b: 255}, undefined, OutputType.STRING);
// => hsl(209.3, 100%, 57.84%)
const res3 = rgb2hsl([0, 255, 0], undefined, OutputType.ARRAY);
// => [120, 100, 50]
```

Alternative versions: \
Usage: ```import { rgb2hslString } from 'lumino/rgb2hsl'``` \
Alternative usage: ```import { rgb2hslString } from 'lumino'``` \
Description: Works as the main function, but only returns a HSL string.

Usage: ```import { rgb2hslObject } from 'lumino/rgb2hsl'``` \
Alternative usage: ```import { rgb2hslObject } from 'lumino'``` \
Description: Works as the main function, but only returns a HSL object.

Usage: ```import { rgb2hslArray } from 'lumino/rgb2hsl'``` \
Alternative usage: ```import { rgb2hslArray } from 'lumino'``` \
Description: Works as the main function, but only returns a HSL array.

#### `cmyk2rgb`
**Notice**: You should be careful with conversion between cmyk and rgb as it brings in inaccuracies
Usage: ```import cmyk2rgb from 'lumino/cmyk2rgb'``` \
Alternative usage: ```import { cmyk2rgb } from 'lumino'```

```typescript
import cmyk2rgb from 'lumino/cmyk2rgb';

// Accepts an rgb-string, rgb object, or rgb array. It's also possible
// to specify output type to string, array or object. Object is default.
const res1 = cmyk2rgb('device-cmyk(98%, 0%, 51%, 25%)');
// => { r: 4, g: 191, b: 94 }
const res2 = cmyk2rgb({ c: 59.09, m: 86.36, y: 0, k: 13.73 }, undefined, OutputType.STRING);
// => rgb(90, 30, 220)
const res3 = cmyk2rgb([85, 0, 22, 44], undefined, OutputType.ARRAY);
// => [21, 143, 111]
```

Alternative versions: \
Usage: ```import { cmyk2rgbString } from 'lumino/cmyk2rgb'``` \
Alternative usage: ```import { cmyk2rgbString } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB string.

Usage: ```import { cmyk2rgbObject } from 'lumino/cmyk2rgb'``` \
Alternative usage: ```import { cmyk2rgbObject } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB object.

Usage: ```import { cmyk2rgbArray } from 'lumino/cmyk2rgb'``` \
Alternative usage: ```import { cmyk2rgbArray } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB array.

#### `rgb2cmyk`
**Notice**: You should be careful with conversion between cmyk and rgb as it brings in inaccuracies
Usage: ```import rgb2cmyk from 'lumino/rgb2cmyk'``` \
Alternative usage: ```import { rgb2cmyk } from 'lumino'```

```typescript
import rgb2cmyk from 'lumino/rgb2cmyk';

// Accepts an rgb-string, rgb object, or rgb array. It's also possible
// to specify output type to string, array or object. Object is default.
const res1 = rgb2cmyk('rgb(90, 30, 220)');
// => { c: 59.09, m: 86.36, y: 0, k: 13.73 }
const res2 = rgb2cmyk({r: 22, g: 143, b: 111}, undefined, OutputType.STRING);
// => device-cmyk(84.62%, 0%, 22.38%, 43.92%)
const res3 = rgb2cmyk([255, 128, 0], undefined, OutputType.ARRAY);
// => [0, 49.8, 100, 0]
```

Alternative versions: \
Usage: ```import { rgb2cmykString } from 'lumino/rgb2cmyk'``` \
Alternative usage: ```import { rgb2cmykString } from 'lumino'``` \
Description: Works as the main function, but only returns a CMYK string.

Usage: ```import { rgb2cmykObject } from 'lumino/rgb2cmyk'``` \
Alternative usage: ```import { rgb2cmykObject } from 'lumino'``` \
Description: Works as the main function, but only returns a CMYK object.

Usage: ```import { rgb2cmykArray } from 'lumino/rgb2cmyk'``` \
Alternative usage: ```import { rgb2cmykArray } from 'lumino'``` \
Description: Works as the main function, but only returns a CMYK array.

#### `hwb2rgb`
Usage: ```import hwb2rgb from 'lumino/hwb2rgb'``` \
Alternative usage: ```import { hwb2rgb } from 'lumino'```

```typescript
import hwb2rgb from 'lumino/hwb2rgb';

const res1 = hwb2rgb('hwb(3.38, 0.39%, 43.92%)');
// => { r: 143, g: 9, b: 1 }
const res2 = hwb2rgb({ h: 120, w: 0, b: 0 }, undefined, OutputType.STRING);
// => rgb(0, 255, 0)
const res3 = hwb2rgb([258.95, 11.76, 13.73], undefined, OutputType.ARRAY);
// => [90, 30, 220]
```

Alternative versions: \
Usage: ```import { hwb2rgbString } from 'lumino/hwb2rgb'``` \
Alternative usage: ```import { hwb2rgbString } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB string.

Usage: ```import { hwb2rgbObject } from 'lumino/hwb2rgb'``` \
Alternative usage: ```import { hwb2rgbObject } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB object.

Usage: ```import { hwb2rgbArray } from 'lumino/hwb2rgb'``` \
Alternative usage: ```import { hwb2rgbArray } from 'lumino'``` \
Description: Works as the main function, but only returns a RGB array.

#### `rgb2hwb`
Usage: ```import rgb2hwb from 'lumino/rgb2hwb'``` \
Alternative usage: ```import { rgb2hwb } from 'lumino'```

```typescript
import rgb2hwb from 'lumino/rgb2hwb';

const res1 = rgb2hwb('rgb(90, 30, 220)');
// => { h: 258.95, w: 11.76, b: 13.73 }
const res2 = rgb2hwb({r: 22, g: 143, b: 111}, undefined, OutputType.STRING);
// => hwb(164.13, 8.63%, 43.92%)
const res3 = rgb2hwb([255, 128, 0], undefined, OutputType.ARRAY);
// => [30.12, 0, 0]
```

Alternative versions: \
Usage: ```import { rgb2hwbString } from 'lumino/rgb2hwb'``` \
Alternative usage: ```import { rgb2hwbString } from 'lumino'``` \
Description: Works as the main function, but only returns a HWB string.

Usage: ```import { rgb2hwbObject } from 'lumino/rgb2hwb'``` \
Alternative usage: ```import { rgb2hwbObject } from 'lumino'``` \
Description: Works as the main function, but only returns a HWB object.

Usage: ```import { rgb2hwbArray } from 'lumino/rgb2hwb'``` \
Alternative usage: ```import { rgb2hwbArray } from 'lumino'``` \
Description: Works as the main function, but only returns a HWB array.

### Generators
#### `complementary`
Usage: ```import complementary from 'lumino/harmony/complementary'``` \
Alternative usage: ```import { complementary } from 'lumino'```

```typescript
import complementary from 'lumino/harmony';

// Takes in a RGB object and returns a RGB object of the complementary color
const res1 = complementary({r: 0, g: 0, b: 0});
// => {r: 0, g: 0, b: 0}
const res2 = complementary({r: 128, g: 128, b: 128});
// => {r: 128, g: 128, b: 128}
const res3 = complementary({r: 45, g: 230, b: 73});
// => {r: 230, g: 45, b:202}
const res4 = complementary({r: 89, g: 0, b: 240});
// => {r: 152, g: 240, b: 0}
```

#### `triadic`
Usage: ```import triadic from 'lumino/harmony'``` \
Alternative usage: ```import { triadic } from 'lumino'```

```typescript
import triadic from 'lumino/harmony';

// Takes in a RGB object and returns an array of 3 RGB object of the triadic colors
const res1 = triadic({r: 0, g: 0, b: 0});
// => [{r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}]
const res2 = triadic({r: 40, g: 120, b: 200});
// => [{r: 40, g: 120, b: 200}, {r: 200, g: 40, b: 120}, {r: 120, g: 200, b: 40}]
const res3 = triadic({r: 200, g: 34, b: 89});
// => [{r: 200, g: 34, b: 89}, {r: 89, g: 200, b: 34}, {r: 34, g: 89, b: 200}]
const res4 = triadic({r: 44, g: 222, b: 111});
// => [{r: 44, g: 222, b: 111}, {r: 111, g: 44, b: 222}, {r: 222, g: 111, b: 44}]
```

#### `tetradic`
Usage: ```import tetradic from 'lumino/harmony'``` \
Alternative usage: ```import { tetradic } from 'lumino'```

NB: It defaults to a 60% distance difference, but it's possible to give a custom distance as a second argument.

```typescript
import tetradic from 'lumino/harmony';

// Takes in a RGB object and returns an array of 4 RGB object of the tetradic colors
const res1 = tetradic({r: 0, g: 0, b: 0});
// => [{r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}]
const res2 = tetradic({r: 40, g: 120, b: 200});
// => [{r: 40, g: 120, b: 200}, {r: 120, g: 40, b: 200}, {r: 120, g: 200, b: 40}, {r: 200, g: 120, b: 40}]
const res3 = tetradic({r: 200, g: 34, b: 89});
// => [{r: 200, g: 34, b: 89},  {r: 200, g: 145, b: 34}, {r: 34, g: 89, b: 200}, {r: 34, g: 200, b: 145}]

// Custom distance difference set to 90
const res4 = tetradic({ r: 44, g: 222, b: 111 }, 90));
// => [{r: 44, g: 222, b: 111}, {r: 44, g: 66, b: 222}, {r: 222, g: 200, b: 44}, {r: 222, g: 44, b: 155}]
```

#### `analogous`
Usage: ```import analogous from 'lumino/harmony'``` \
Alternative usage: ```import { analogous } from 'lumino'```

```typescript
import analogous from 'lumino/harmony';

// Takes in a RGB object and returns an array of 3 RGB object of the analogous colors
const res1 = analogous({r: 0, g: 0, b: 0});
// => [{r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}]
const res2 = analogous({r: 40, g: 120, b: 200});
// => [{r: 40, g: 120, b: 200}, {r: 40, g: 40, b: 200}, {r: 40, g: 200, b: 200}]
const res3 = analogous({r: 200, g: 34, b: 89});
// => [{r: 200, g: 34, b: 89}, {r: 200, g: 62, b: 34}, {r: 200, g: 34, b: 172}]
const res4 = analogous({r: 44, g: 222, b: 111});
// => [{r: 44, g: 222, b: 111}, {r: 44, g: 222, b: 200}, {r: 66, g: 222, b: 44}]
```

#### `splitComplementary`
Usage: ```import splitComplementary from 'lumino/harmony'``` \
Alternative usage: ```import { splitComplementary } from 'lumino'```

```typescript
import splitComplementary from 'lumino/harmony';

// Takes in a RGB object and returns an array of 3 RGB object of the split-complementary colors
const res1 = analogous({r: 0, g: 0, b: 0});
// => [{r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}, {r: 0, g: 0, b: 0}]
const res2 = analogous({r: 40, g: 120, b: 200});
// => [{r: 40, g: 120, b: 200}, {r: 200, g: 200, b: 40}, {r: 200, g: 40, b: 40}]
const res3 = analogous({r: 200, g: 34, b: 89});
// => [{r: 200, g: 34, b: 89}, {r: 34, g: 172, b: 200}, {r: 34, g: 200, b: 62}]
const res4 = analogous({r: 44, g: 222, b: 111});
// => [{r: 44, g: 222, b: 111}, {r: 222, g: 44, b: 66}, {r: 200, g: 44, b: 222}]
```

## TODO
### Conversion
* HSL(A) to RGBA
* RGBA to HEX

### Harmony Generation
* Monochromatic
