## Binary Search in Python

Binary search on already sorted sequences (list, tuple) to get the first element `>=` or `>`
a value (similar to C++'s `std::lower_bound` and `std::upper_bound`).

Requires python >=3.5 for the `typing` module and >= 3.4 for the `enum` module, but you can easily
extract the `search` function from `binary_search/__init__.py` if you need it for a lower version.

## Install
1. `pip install binary-search`

## Usage
See `tests.py` for more sample usage.
```python
import binary_search as bs

sorted_sequence = (2, 5, 7, 9)
a = bs.search(sorted_sequence, 5)
print(a) # 1 - the index of the first element >= 5

b = bs.search(sorted_sequence, 6)
print(b) # 2 - the index of the first element >= 6 (element 2 with value 7)
```

You can also use a custom key in the same way as `sorted`
```python
import binary_search as bs
import random

# sequence of 10 random pairs of integers
sequence = [(random.randint(), random.randint()) for _ in range(10)]
# sort and search just using the first integer
key = lambda pair: pair[0]

sorted_sequence = sorted(sequence, key=key)
bs.search(sorted_sequence, [5, None], key=key)
```

## Development and testing
1. Fork the repository
2. Clone your fork
3. Install it in editable mode `pip install -e .`
4. Make any changes and add new tests to `tests.py`
5. Run pytest `python -m pytest`
6. Commit and push to your fork
7. Make pull request (merge your fork back to main repo)

