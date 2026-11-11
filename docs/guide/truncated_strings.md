---
icon: lucide/scissors
---

# Truncated Strings

`stringz` provides two ways to truncate strings: the `trunc_str` function for one-off
truncation, and the `TStr` class for strings that stay truncated as you work with them.

## `trunc_str` for once off truncation

`trunc_str` truncates a string to a maximum number of characters, appending a
placeholder when truncation occurs.

```python
from stringz import trunc_str

trunc_str("hello world", max_chars=10)
# 'hello w...'
```

If the string already fits, it is returned unchanged:

```python
trunc_str("short", max_chars=10)
# 'short'
```

The placeholder is included in the character budget, and can be customized or left
empty to simply cut the string off:

```python
trunc_str("hello world", max_chars=10, placeholder=">>")  # weird, but sure!
# 'hello wo>>'

trunc_str("hello world", max_chars=5, placeholder="")
# 'hello'
```

## `TStr` for continuous truncation

`TStr` is a subclass of `str` (for type hinting reasons) that automatically truncates its content to a maximum
length. Not only does it truncate when it is created, but whenever string operations produce a new
value. It uses `trunc_str` under the hood.

```python
from stringz import TStr

s = TStr("hello world", max_chars=10)
print(s)  # hello w...
len(s)  # 10
```

Because `TStr` _is_ a `str`, it works anywhere a normal string does. The difference
is that operations such as concatenation, repetition, formatting and slicing return
new `TStr` instances that keep the `max_chars` limit:

```python
s1 = TStr("hello", max_chars=10)
s2 = s1 + " world"

type(s2)  # <class 'stringz.TStr'>
print(s2)  # hello w...
```

Pass `max_chars=None` (the default) to disable truncation entirely while still
getting a `TStr`:

```python
s = TStr("hello world")
print(s)  # hello world
```

The placeholder can be customized as well:

```python
s = TStr("hello world", max_chars=10, placeholder=">>")
print(s)  # hello wo>>
```
