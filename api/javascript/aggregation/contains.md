---
layout: api-command
language: JavaScript
permalink: api/javascript/contains/
command: contains
io:
    -   - sequence
        - value
related_commands:
    map: map/
    reduce: reduce/
---

# Command syntax #

{% apibody %}
sequence.contains(value1[, value2...]) &rarr; bool
{% endapibody %}

# Description #

Returns whether or not a sequence contains all the specified values, or if functions are
provided instead, returns whether or not a sequence contains values matching all the
specified functions.

__Example:__ Has Iron Man ever fought Superman?

```js
r.table('marvel').get('ironman')('opponents').contains('superman').run(conn, callback)
```

__Example:__ Has Iron Man ever defeated Superman in battle?

```js
r.table('marvel').get('ironman')('battles').contains(function (battle) {return battle('winner').eq('ironman').and(battle('loser').eq('superman'));})
```

