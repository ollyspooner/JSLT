# Array operations

## Push an object onto the end of a JSON Array

```JSLT
flatten([.,
    {
        "key": "newobject",
        "value": "Y3VzdG9tZXJfODkxOTE4Njc4MTY"
    }
])
```

## Unshift an object onto the start of a JSON Array

```JSLT
flatten([
    {
        "key": "newobject",
        "value": "Y3VzdG9tZXJfODkxOTE4Njc4MTY"
    }
,.])
```

## Pop the last object from a JSON Array

Get the shifted object:

``` JSLT
.[-1]
```

Get the remaining array:

``` JSLT
.[:-1]
```

## Shift the first object from a JSON Array

Get the shifted object:

``` JSLT
.[0]
```

Get the remaining array:

``` JSLT
.[1:]
```
