---
layout: post
title: Python Iterator vs Iterable
---

Python language has an abstraction of iterator and iterable.
This post describes and differentiates between the two.


#### Iterator

Iterator is an abstraction that enables walking/looping over a collection.
It is a stateful object that represents the state of an iteration over the
collection.
The state specifies the current location of the iterator in the collection.
Iterator also provides the functions to get the value in the collection 
at the current position and to move to the next element of the collection.

In case of Python, an iterator has to implement
the dunder function ```__next__```, which returns the next element
of the collection and updates the state to the next position.
Any object in Python, that implements ```__next__``` is an iterator.

#### Iterable

In the context of Python, any object (commonly a collection) 
that returns an iterator is called iterable, i.e., one can iterate over it.
Formally, any object that implements the dunder function ```__iter__```, 
which returns a fresh iterator (iterator with position set to the start) is called an iterable.
The returned iterator is used for iterating over the collection.
Note that an iterable can also implement ```__getitem__``` in case of a sequential index based collection.

Whenever we write a code like ```for x in y: ...```, then it is expected that
the variable ```y``` is an iterable. Python implementation will get a fresh iterator 
(using ```iter = y.__iter__()```)
and then iterate over it using (```x = next(iter)```).

The following for loop is equivalent to the subsequent while loop.
```
for x in y:
  print(x)
```

```
iter = y.__iter__()
while True:
    try:
        print(iter.__next__())
    except StopIteration:   # part of iter protocol
        break
```

#### Example
Following is an example of iterator and iterable. 
RandGen is a class to generate a series of random number given a max count.
RandGen is implemented as an iterable, and it returns an iterator (_RandGenIter) in the function ```__iter__```.

_RandGenIter is an iterator, it stores the state in the variable pos.
State is initialized to the start (0) and the function ```__next__``` increments the
in each call.
When the max count is attained it throws the exception ```StopIteration``` as per the protocol
of the iteration mechanism.

```
class _RandGenIter():
    def __init__(self, randgen):
        self._randgen = randgen
        self._pos = 0
    
    def __next__(self):
        if self._pos < self._randgen._max:
            self._pos += 1
            return self._randgen.get_rand()
        else:
            raise StopIteration
```
```
class RandGen():
    def __init__(self, max):
        self._max = max
    
    def __iter__(self):
        return _RandGenIter(self)

    def get_rand(self):
        import random
        return random.random()
```
```
for x in RandGen(4):
    print(x)
```

Note: At times, the class supports ```__iter__``` and ```__next__``` both. 
It allows to have the same class supporting both the functionalities.
In the above example, we can get rid of _RandGenIter and move its functionality 
inside RandGen.
In this case, the class is both iterator and iterable.

Also, iterators commonly implement the dunder function ```__iter__``` (returning itself), it allows them
to be used in places where iterables are required. For example, we will be able to use
an iterator in a for loop.
