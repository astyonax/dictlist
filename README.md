# dictlist [![Build Status](https://travis-ci.org/astyonax/dictlist.svg?branch=master)](https://travis-ci.org/astyonax/dictlist)
A one-to-many dictionary: python implementation of a dictionary mapping one key to a list of values.


## Examples
### Dictionary creation and update
``` python
>>> from dictlist import dictlist
>>> dl = dictlist()
>>> dl['A']='a'
>>> dl.update({'B':'b','C':'c'})
>>> dl.update({'B':'b1','C':'c1'})
>>> dl
{'A': ['a'], 'C': ['c', 'c1'], 'B': ['b', 'b1']}
```
### Removal of one element
```python
>>> from dictlist import dictlist
>>> dl = dictlist()
>>> dl.update({'B':'b','C':'c'})
>>> dl.update({'C':'c1'})
>>> dl == {'C': ['c', 'c1'], 'B': ['b']}
True
>>> dl.minus({'C':'c1'})
>>> dl == {'C': ['c'], 'B': ['b']}
True
>>> dl.update({'C':'c1'})
>>> dl.minus(C='c1')
>>> dl == {'C': ['c'], 'B': ['b']}
True
>>> dl.update({'C':'c1'})
>>> dl.minus([('C','c1'),])
>>> dl == {'C': ['c'], 'B': ['b']}
True
```
