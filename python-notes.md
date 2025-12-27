---
title: python-notes
draft: false
tags:
  - python
---
 
*true division* = ` / ` returns a floating point decimal result, even if the result is a whole number
*floor division* = ` // ` returns the largest integer less than or equal to the quotient i.e. discards the fractional part and returns a whole number
*rounding down to the nearest integer* = `math.floor()`

**splitting integer into a list of the digits**
```python
digits_list = [int(digit) for digit in str(number)]
```

**to join a list into a string**
- using a separator between list items = 
```python
mylist = [a, b, c]
separator = ", "
mystring = separator.join(mylist)

## output: a, b, c
```
- for no separator =
```python
no_space_string = "".join(mylist)

## output: abc
```

**slicing strings/list**
general syntax `list[start:stop:step]` or  `string[start:stop:step]`
- start = the starting index of the slice (inclusive)
- stop = the index of where the slice ends (exclusive)
- step = the interval between indices

| description                     | syntax   |
| ------------------------------- | -------- |
| full slice (copy of the string) | `s[:]`   |
| first character                 | `s[:5]`  |
| characters from index n to end  | `s[n:]`  |
| last character                  | `s[-1]`  |
| last n characters               | `s[-n:]` |

**to see if a number n is a multiple of m**
```python
def multiple(n,m):
	"""
	checks if n is a multiple of m.
	"""
	if m == 0:
		return False # cannot be a mulltiple of zero
	if n % m == 0:
		return True
```

**listing multiples of 3 or 5 below n**
```python
def multiples(n):
	multiples = []
	for i in range(n):
		if (i % 3) == 0 or (i % 5) == 0:
			multiples.append(i)
	print(multiples)
```
