# Notes
Personal notes
## Algorithms
#### Fibonacci sequence
```python
def fib(i: int) -> None:
	numbers = [0, 1]
	while i:
		numbers.append(numbers[-2] + numbers[-1])
		i -= 1
	print(*numbers, sep=', ')
```
#### Partitions count
```python
def count_partitions(n: int, m: int) -> int:
    if n == 0:
        return 1
    elif n < 0:
        return 0
    elif m == 0:
        return 0

    return count_partitions(n - m, m) + count_partitions(n, m - 1)
```
#### Elementary cellular automaton
```python
def cellular_automaton(rule: int = 90 ) -> None:
	line = '.'*40 + '#' + '.'*40
	b = format(rule, 'b').replace('1', '#').replace('0', '.')
	b = f'{b:.>8}'
	state = dict(zip(('###', '##.', '#.#', '#..', '.##', '.#.', '..#', '...'), b))
	for i in range(40):
	    s = ''
	    for j in range(79):
	        s += state[line[j:j + 3]]
	    print(line[1:-1])
	    line = s[-1] + s + s[0]
```
### Sorting
#### Selection sort
```python
def sort(l: list) -> list:
	l_copy = list(l)
	sorted_list = []
	while l:
		el = l.pop()
		for i, val in enumerate(l):
			if el > val:
				l[i], el = el, val
		sorted_list.append(el)
		
	return sorted_list
```
#### Bubble sort
```python
def bubble_sort(l: list) -> None:
	_sorted = False
	while not _sorted:
		_sorted = True
		for i in range(len(l) - 1):
			if l[i] > l[i+1]:
				l[i], l[i+1] = l[i+1], l[i]
				_sorted = False
```