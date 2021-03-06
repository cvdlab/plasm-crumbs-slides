# PLaSM.js transformations

- - - 

## Transformations

### Translate

### `T(axis)(values)(model)`

Clone `model` and translate the cloned model by `values` along `axis`

#### I/O

> **&rArr;** `Array` `axis`: an array of `Number` specifying which dimensions translate
>
> **&lArr;** `Function`: anonymous function
>
> > **&rArr;** `Array` `values`: an array of `Number` specifying translation quantity for every dimension in `dims`
> >
> > **&lArr;** `Function`: anonymous function
> >
> > > **&rArr;** `plasm.Model` or `plasm.Struct` `object`: the object to translate
> > >
> > > **&lArr;** `plasm.Model` or `plasm.Struct`: the translated object

#### Example

```js
c = CUBE(3)
DRAW(c)
```

```js
c1 = T([1,2])([2,3])(c)
DRAW(c1)
```

- - -

## Transformations

### Rotate

### `R(axis)(angle)(model)`

Clone `model` and rotate the cloned model by `angle` on the plane described by `axis`

#### I/O

> **&rArr;** `Array` `axis`: rotational plane axis (in 3D `[1,2]`, `[1,3]` or `[2,3]`)
>
> **&lArr;** `Funciton`: an anonymous function
>
> > **&rArr;** `Number` `angle`: rotational angle (in radiant, from `0` to `2π`)
> >
> > **&lArr;** `Function`: an anonymous function
> >
> > > **&rArr;** `plasm.Model` or `plasm.Struct` `object`: the object to rotate
> > >
> > > **&lArr;** `plasm.Model` or `plasm.Struct`: the rotated object

#### Example

```js
c = CUBE(3)
DRAW(c)
```

```js
c1 = R([1,2])(PI/4)(c)
DRAW(c1)
```

- - -

## Transformations

### Scale

### `S(axis)(values)(model)`

Clone `model` and scale the cloned model by `values` along `axis`

#### I/O

> **&rArr;** `Array` `axis`: axis to scale along
>
> **&lArr;** `Function`: an anonymous function
>
> > **&rArr;** `Array` `values`: scaling factors
> >
> > **&lArr;** `Function`: an anonymous function
> >
> > > **&rArr;** `plasm.Model` or `plasm.Struct` `object`: the object to scale
> > >
> > > **&lArr;** `plasm.Model` or `plasm.Struct`: the scaled object

#### Example

```js
c = CUBE(3)
DRAW(c)
```

```js
c1 = S([1,2])([10,15])(c)
DRAW(c1)
```

- - -

## Transformations

### Struct

#### `STRUCT(items)`

Create a struct of items.  
If a transformation is encountered in items,  
it is applied to all of the following items.

#### I/O

> **&rArr;** `Array` `items`: an array of `Model` or `Struct` or `Function`
> 
> **&lArr;** `Struct`: the struct.

#### Example

```js
var cube1 = CUBE(3);
var t = T([0])([1.5]);
var cube2 = t(cube1);
var struct1 = STRUCT([cube1, cube2]);
DRAW(struct1);
```

```js
var cube1 = CUBE(3);
var t = T([0])([1.5]);
var struct1 = STRUCT([cube1, t, cube1]);
DRAW(struct1);
```

- - -

## Transformation

### Extrude

#### `EXTRUDE(quotes)(object)`

Extrude an object

#### I/O

> **&rArr;** `Array` `quotes`: a list of quotes of extrusion
> 
> **&lArr;** `Function`: an anonimous function
> 
> > **&rArr;** `Model` or `Struct` `object`: the object to extrude
> > 
> > **&lArr;** `Model` or `Struct` the object extruded 

#### Example

```js
var model = SIMPLEX(1);
var extruded = EXTRUDE([1])(model);
DRAW(extruded);
```
