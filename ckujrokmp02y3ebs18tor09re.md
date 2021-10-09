## All about python dictionary.

Python dictionary is one of the most used and powerful data structures in python. It is a collection of data in the form of key-value pairs. It is a feature-rich data structure used widely when working with structured data. Python dictionaries have many built-in methods that are used to access, update and delete the data from them which makes them easy to use. Python dictionaries and lists have similar properties but differ in how the data is accessed. Python lists use zero-based indexing whereas dictionaries use keys for referencing the data associated with it. Let's learn more about dictionaries and how to work efficiently with them.

## Scope
- The article explains the basic syntax and characteristics of python dictionaries.
- The article includes basic CRUD operations with dictionaries.
- The article has provided information about the built-in dictionary methods.

## Contents:
- [What is a Python dictionary?](#what-is-a-python-dictionary) 
- [Properties of dictionary](#properties-of-dictionary) 
- [Keys](#keys) 
- [Values](#values) 
- [CRUD operations with a dictionary](#crud-operations-with-a-dictionary) 
- [Built-in dictionary methods](#built-in-dictionary-methods)
- [Summary](#summary) 

### What is a Python dictionary?
The python Dictionary is a collection of data in the form of key-value pairs. Consider python Dictionary a "bag" or a "collection" of values, each with its own and unique label (key).

```
>>> my_dict = {"name": "Shantanu Nighot", "age": 21, "grade": "A" , "pass": True }
{"name": "Shantanu Nighot", "age": 21, "grade": "A" , "pass": True }
```

 In python dictionaries, data is stored as a pair of keys and their associated value separated by a colon (:) and wrapped inside the curly braces ({}). Each key-value pair is separated by a comma (,).

### Properties of Dictionary:
Some of the important properties of dictionaries are,

#### They are mutable.
Python dictionaries are mutable just like the lists. This means elements of the dictionary can be updated or deleted after the dictionary is defined.

#### They are ordered.
Python dictionaries are ordered. This means that the elements are stored in the order they are added.


> Do you know? Python dictionaries were unordered till Python version 3.6. After that, they were made ordered from version 3.7.
Try running the following code on python version 3.6 and the latest one, and see the difference in results.
```
>>> my_dict = {"name": "Shantanu Nighot", "age": 21, "grade": "A"}
>>> print(my_dict)
```

#### They can be nested.
Python dictionaries just like lists can have another dictionary or list as a value.

```
>>> bagpack = {"Books": 5, "Camera": 1, "Fruits": {"Apple": 1, "Orange": 2}}
{"Books": 5, "Camera": 1, "Fruits": {"Apple": 1, "Orange": 2}}
```

### Keys:

#### Keys must be unique.
Python dictionaries do not allow duplicate keys. This means any key is unique throughout the dictionary. If there are duplicate keys defined in the dictionary the last appeared key-value pair is considered only.
```
>>> mydict = {"name": "Shantanu", "age": 20, "grades": "A", "age": 22}
{'name': 'Shantanu', 'grades': 'A', 'age': 22}
```

You can see that the key ```“age”``` appeared multiple times with different values but only the last appearing value (```22```) is saved in a dictionary.

#### Keys must be immutable:

Keys in the dictionary can be of any immutable data type. For example string, number, boolean or binary data type can be used as a key in a python dictionary. Tuples being immutable can also be used as a dictionary key. 

```
>>> mydict = {"name": "Shantanu", 21: "age", False: "Palash", (1,2): "numbers"}
{"name": "Shantanu", 21: "age", False: "Palash", (1,2): "numbers"}
```

Amazingly, we can also use the python function as a key.

```
>>> def name(): pass
>>> mydict = {name(): "Shantanu", False: "Palash"}
{name(): "Shantanu", False: "Palash"}
>>> mydict[name()]
Shantanu
```
You can use any of the above-stated data types or a function as a key. But you should have proper reason and logic behind using them, mainly in the case of tuples and functions.


### Values

Unlike Keys, Values don't have any restrictions. They can be of any data type or even another dictionary or List. We can even use functions as a value associated with the dictionary key.

```
>>> def fruits(): return ["apple", "oranges"]
>>> mydict = {"name": "Shantanu", "things": fruits()}
>>> mydict["things"]
["apple", "oranges"]
```
When we access the function from the dictionary using its associated key, the function is executed and returns the value from it instead of the function itself. That's why, above code prints list ```["apple", oranges"]``` and not ```fruits()```.

### CRUD operations with a dictionary

Till now you got familiar with the dictionary, key, value and their properties. Now, it's time to see how dictionaries work. We will see basic CRUD (Create, Read, Update, Delete) operations on Dictionaries.

- Creating a dictionary
- Reading/Accessing a dictionary
- Updating a dictionary
- Deleting a dictionary

#### Creating dictionary

You are already familiar with the syntax of the dictionary and have already created it in previous examples. The dictionary can be created using one or many key-value pairs separated by a comma and enclosed inside curly braces. Each key and its associated value is separated by a colon.
```
>>> my_dict = {"name": "Shantanu Nighot", "age": 21, "grade": "A" , "pass": True }
{"name": "Shantanu Nighot", "age": 21, "grade": "A" , "pass": True }
>>> type(my_dict)
<class 'dict'>
```

It's not necessary to create a dictionary with some data. We can also define an empty dictionary by either using empty curly braces ```{}``` or the ```dict()``` keyword.
```
>>> dict1 = {}
{}
>>> dict2 = dict{}
{}
>>> print(type(dict1), type(dict2))
<class 'dict'> <class 'dict'>
>>> print(len(dict1), len(dict2))
0 0
```

#### Reading/Accessing dictionary
We can not use numerical indices in dictionaries as we do in lists. And if we do so, Python will raise an exception ```KeyError``` as it can not find a key in the dictionary.
```
>>> mydict = {"fruit": "Mango"}
>>> mydict[0]
Traceback (most recent call last):
  File "<pyshell#13>", line 1, in <module>
    mydict[0]
KeyError: 0
```
In python dictionaries, instead of indices, keys are used to access values associated with them.
```
>>> my_dict = {"name": "Shantanu Nighot", "age": 21, "grade": "A" , "pass": True }
>>> my_dict["name"]
Shantanu Nighot
```
From the nested dictionary, values of sublists or subdictionaries can be accessed using an extra index or a key just like in the following example.
```
>>> fav_list = {"colors": ["Skyblue", "grey"], "number": 21, "fruits": ["Orange", "Mango", "Blueberries"]}
>>> fav_list["fruits"][1]
Mango
>>> fav_list["fruits"][0:2]
['Orange', 'Mango']
```

There are few built-in dictionary methods like items(), keys(), values(), and get(). They can also be used for accessing the data from the dictionary. We are going to learn about them later in this article.

Now as you got familiar with accessing the data from the dictionaries, you can start working on using them with Python's operators and built-in functions.

```
>>> numbers = { "num1": 10, "num2": 13}
{ "num1": 10, "num2": 13}

>>> numbers["num1"] + numbers["num2"]
23

>>> "num2" in numbers
True

>>> sorted(mydict, reverse=True)
{ "num2": 13, "num1": 10}
```

#### Updating dictionary
Any value in the dictionary can be changed by referencing its key.
```
>>> numbers = { "num1": 10, "num2": 13}
>>> numbers["num1"] = 12
>>> numbers
{ "num1": 12, "num2": 13}
```
New data can be added using the same above syntax. If the key is present in the dictionary then Python reassigns a new value to a key and if a key is not found then it creates a new key and assigns value to it.
```
>>> numbers = { "num1": 10, "num2": 13}
>>> numbers["num3"] = 12
>>> numbers
{ "num1": 10, "num2": 13, "num3": 12}
```

There is a built-in dictionary method update() which is also used to update the data from a dictionary. We will learn about it later in this article.

#### Deleting dictionary

The del function can be used to delete the whole dictionary. After that, any reference to it will throw a NameError.
```
>>> numbers = { "num1": 10, "num2": 13}
>>> del(numbers)
>>> numbers["num1"]
File "main.py", line 3, in <module>
    numbers["num1"]
NameError: name 'fav_list' is not defined
```
If you do not want to delete the dictionary and just want to delete data in it, then you can assign an empty dictionary to it.
```
>>> numbers = { "num1": 10, "num2": 13}
{ "num1": 10, "num2": 13}

>>> numbers = {}
{}
```
There are few built-in dictionary methods used to perform deleting operations on dictionaries. We are going to learn about them in the next topic.

### Built-in dictionary methods

- [items()](#items) 
- [keys()](#keys) 
- [values()](#values) 
- [get()](#get-key-default_value) 
- [update()](#update) 
- [clear()](#clear) 
- [pop()](#pop-key-default_value) 
- [popitem()](#popitem) 

#### .items()
This method returns the list of tuples containing key-value pairs from a dictionary. The first element of each tuple is the key and the second element is the value associated with that key.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.items()
dict_items([('num2', 13), ('num3', 23), ('num1', 10)])
>>> type(numbers.items())
<class 'dict_items'>
```
You can see that the method returns the data of type "dict_items". Hence, we need to convert it into a list so that we can access them using normal indexing.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> list(numbers.items())
[('num2', 13), ('num3', 23), ('num1', 10)]

>>> list(numbers.items())[0]
('num2', 13)
>>> list(numbers.items())[1][1]
13
```
Mostly, the items() method is used while working with loops and dictionaries.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> for k, v in numbers.items(): print(k, v)
num2 13
num3 23
num1 10
```

#### .keys()
This method returns the list of all keys in the dictionary. The return type is "dict_keys", hence we need to convert it into a list using list() so that we can use normal indexing.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> list(numbers.keys())
['num1', 'num2', 'num3']

>>> for key in numbers.keys(): print(numbers[key])
10
13
23
```

#### .values()
This method returns the list of all values in the dictionary. The return type is "dict_values", hence we need to convert it into a list for using normal indexing.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> list(numbers.values())
[10, 13, 23]
```

#### .get(key, default_value)
This method returns the value associated with the key if it's present in the dictionary else returns None. This method does not raise KeyError if the key is not found in the dictionary and returns the default value which is None by default.

```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.get("num3")
23
>>> numbers.get("num4")
None
```
The second argument is optional but can be very helpful when we want to return a specific value when the key is not found.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.get("num5", 0)
0
```
#### .update()
This method is used to update existing data and to add new entries to the dictionary. There are several ways of using the update() method.

```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.update({"num2": 5, "num4": 10})
>>> numbers
{'num1': 10, 'num2': 5, 'num3': 23, 'num4': 10}

>>> numbers.update([("num5", 4), ("num2", 11)])
>>> numbers
{'num1': 10, 'num2': 11, 'num3': 23, 'num4': 10, 'num5': 4}

>>> numbers.update(num1=0, num6=2)
>>> numbers
{'num1': 0, 'num2': 11, 'num3': 23, 'num4': 10, 'num5': 4, 'num6': 2}
```

#### .clear()
This method is used to remove all key-value pairs from the dictionary.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.clear()
>>> numbers
{}
```

#### .pop(key, default_value)
This method returns the value associated with the key and removes the key-value pair from the dictionary.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.pop("num2")
13
>>> numbers
{ "num1": 10, "num3": 23}
```
If the key is not present in the dictionary then python raises an exception KeyError. Hence, it is recommended to provide default value as a second argument. This default value will be returned if the key is not found in the dictionary.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.pop("num4", 0)
0
>>> numbers
{ "num1": 10, "num2": 13, "num3": 23}
```

#### .popitem()
This method returns the last key-value pair as a tuple and removes it from the dictionary. If the dictionary is empty, it raises an exception KeyError.
```
>>> numbers = { "num1": 10, "num2": 13, "num3": 23}
>>> numbers.popitem()
('num3', 23)
>>> numbers
{ "num1": 10, "num2": 13}
```

## Summary

- Python dictionary is the collection where data is store in the form of key-value pairs.
- Python dictionaries are immutable, ordered and can be nested.
- Keys must be of immutable data type whereas values can be of any data type.
- Functions and few python keywords can also be used as keys and values.
- Few built-in dictionary methods make it easier to work with dictionaries.

I have also created a Jupyter notebook for this article on GitHub. This notebook will help you run the above codes effectively. Check it out by clicking  [here](https://github.com/magbanum/Learn-Python/blob/master/Python-Dictionaries.ipynb).

I hope you found this article helpful. Do comment below if I missed something to make this thread more informative.

You can also sign up for the newsletter to get my articles directly in your inbox.

See you in the next article.

> Be better than yesterday's you.