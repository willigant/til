# Pluck every value from an array
[JQ](https://stedolan.github.io/jq/) is a super powerful command line `JSON`
processor. One of the many things it can do is iterate over an array
and pull out the value for a specified key.

Real world example:
```
curl http://api.citybik.es/citi-bike-nyc.json | jq '[.[] | .name]'
```

The above is the same as using `map` as specified in the 
[docs](https://stedolan.github.io/jq/manual/#Builtinoperatorsandfunctions)

```
curl http://api.citybik.es/citi-bike-nyc.json | jq 'map(.name)'
```
