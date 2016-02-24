# Must bool filter type
> A bool query allows you to combine multiple filter clauses using Boolean logic
[es docs](https://www.elastic.co/guide/en/elasticsearch/guide/current/_most_important_queries_and_filters.html#_bool_filter)

A must filter clause and for that matter a `must_not` and `should` parameter
can "accept a single filter clause or an array of filter clauses". However, even
if you pass in just one filter clause it can still be in a format of an array.
The example in the [docs](https://www.elastic.co/guide/en/elasticsearch/guide/current/_most_important_queries_and_filters.html#_bool_filter)
```
{
    "bool": {
        "must":     { "term": { "folder": "inbox" }},
        "must_not": { "term": { "tag":    "spam"  }},
        "should": [
                    { "term": { "starred": true   }},
                    { "term": { "unread":  true   }}
        ]
    }
}
```
Could also be written like:
```
{
    "bool": {
        "must":     [{ "term": { "folder": "inbox" }}],
        "must_not": { "term": { "tag":    "spam"  }},
        "should": [
                    { "term": { "starred": true   }},
                    { "term": { "unread":  true   }}
        ]
    }
}
```
If you are building out a querying library, it is wise to just format those filter
clauses as arrays at the beginning, as it is quite common to combine filters. That way
you can just push those filter clauses into the array instead of having to go back and reformat
that parameter(`must`, `must_not`, or `should`) into an array when you realize you need to add in more filter clauses later.
