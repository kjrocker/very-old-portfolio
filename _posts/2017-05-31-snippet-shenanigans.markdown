---
layout: post
title:  "Code Snippet Shenanigans"
date:   2017-05-31 16:54:12 -0400
description: A selection of code snippets from various languages that I find interesting.

---
This is my first post! I have a blog now! I'll put tech things on it as I work through various projects.

Until then, I need a first post. Why not a small collection of code snippets?

---
Recursive SQL
```sql
WITH RECURSIVE t(n) AS (
    VALUES (1)
  UNION ALL
    SELECT n+1 FROM t WHERE n < 100
)
SELECT sum(n) FROM t;
```

---
Function Currying
```js
const mul = y => x => x * y;

const sqr = x => mul(x) (x);

const times10 = x = mul(10) (x);
```

---
Factorial in Haskell
```haskell
facAcc a 0 = a
facAcc a n = facAcc (n*a) (n-1)

fac = facAcc 1
```

alternatively...
```haskell
fac n = product [1..n]
```

For those not in on the joke, go read [this][haskell].

---
Metaprogramming in Ruby
```ruby
COLORS = { black:   "000",
           red:     "f00",
           green:   "0f0",
           yellow:  "ff0",
           blue:    "00f",
           magenta: "f0f",
           cyan:    "0ff",
           white:   "fff" }

class String
  COLORS.each do |color,code|
    define_method "in_#{color}" do
      "<span style=\"color: ##{code}\">#{self}</span>"
    end
  end
end
```

---
Process Spawning in Elixir
```elixir
for num <- 1..1000, do: spawn fn -> IO.puts "#{num * 2}" end
```

[haskell]: https://www.willamette.edu/~fruehr/haskell/evolution.html
