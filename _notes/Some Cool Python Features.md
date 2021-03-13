---
title: Some Cool Python Features
tree_state: 🌱
---

## Dataclasses
```
import dataclasses

@dataclasses.dataclass
class FruitBasket:
	fruits: List[str]
	basket_type: str

```

## Operator Overloading
```

@dataclasses.dataclass
class FruitBasket:
	fruits: List[str]
	basket_type: str

def __add__(self, other_basket: FruitBasket):
    return FruitBasket(fruits=self.fruits + other_basket.fruits, basket_type="multiple baskets")

my_basket = FruitBasket(["banana", "orange", "apple"], "wicker")
michael_basket = FruitBasket(["clementine", "lemon", "peach"], "wicker")
combined_basket = my_basket + michael_basket
combined_basket
```

Outputs:
```
FruitBasket(fruits=\['banana', 'orange', 'apple', 'clementine', 'lemon', 'peach'\], basket\_type='multiple baskets')
```

Can do this with a bunch of different operations:
`<, >, ==, >=, <=, len(), [], bool()`

## Decorators
```
def smart_divide(func):
    def inner(a, b):
        print("I am going to divide", a, "and", b)
        if b == 0:
            print("Whoops! cannot divide")
            return
        return func(a, b)
    return inner
```
This nested function `smart_divide` takes in an input function `func` and then creates a function around it called `inner` which it returns. `inner` is a function object itself.

In order to apply this decorator function on something there are wo ways that are equivalent:
### 1
```
def divide(a, b):
	print(a/b)

inner_func = smart_divide(divide)
inner_func(1,2)
```
1. Create function `divide`
2. The nested function `smart_divide` takes in this `divide` function and returns the `inner` function object. This object can be called normally like any other function
### 2
```
@smart_divide
def divide(a, b):
    print(a/b)
	
divide(1,2)
```
This is equivalent to the above method.
1. `smart_divide` sets `divide` to be the function `inner`.  So now whenever `divide` is called, it is actually the inner function of `smart_divide` that's being called.


### Abstract Base Classes

```
import abc
import pandas as pd

class MyClass(abc.ABC):  
    @abc.abstractmethod  
 	def some_function1(self, arg1: list, arg2: pd.DataFrame) -> pd.DataFrame:  
    	pass
		
	@abc.abstractmethod  
 	def some_function2(self, arg1: pd.Series, arg2: int, arg3: str):  
    	pass
```

Any class that inherits from `MyClass` is required to declare the functions that have the `@abc.abstractmethod` decorator. We can just specify the types that the function takes, and the functions we declare must have the same types.