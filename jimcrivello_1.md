# Jim Crivello's Module 4 Project - Part 1

## Task1 - Series


```python
import pandas as pd
```


```python
grades = pd.Series([95, 86, 74, 88, 92, 98, 93])
```


```python
grades[0]
```




    95




```python
grades.count()
```




    7




```python
grades.mean()
```




    89.42857142857143




```python
grades.min()
```




    74




```python
grades.max()
```




    98




```python
grades.std()
```




    7.913219801006895




```python
grades.describe()
```




    count     7.000000
    mean     89.428571
    std       7.913220
    min      74.000000
    25%      87.000000
    50%      92.000000
    75%      94.000000
    max      98.000000
    dtype: float64



## Task 2 - Series from Dictionary


```python
grades = pd.Series([87, 100, 94], index=['Wally', 'Eva', 'Sam'])
```


```python
grades
```




    Wally     87
    Eva      100
    Sam       94
    dtype: int64




```python
grades = pd.Series({'Wally': 87, 'Eva': 100, 'Sam': 94})
```


```python
grades
```




    Wally     87
    Eva      100
    Sam       94
    dtype: int64




```python
print("Eva's grade")
```

    Eva's grade
    


```python
grades['Eva']
```




    100




```python
grades.Wally
```




    87




```python
grades.dtype
```




    dtype('int64')




```python
grades.values
```




    array([ 87, 100,  94], dtype=int64)



## Self Check


```python
import numpy as np
```


```python
import pandas as pd
```


```python
temps = np.random.randint(60, 101, 6)
```


```python
temperatures = pd.Series(temps)
```


```python
temperatures
```




    0    96
    1    74
    2    67
    3    96
    4    99
    5    81
    dtype: int32




```python
temperatures.min()
```




    67




```python
temperatures.max()
```




    99




```python
temperatures.mean()
```




    85.5




```python
temperatures.describe()
```




    count     6.000000
    mean     85.500000
    std      13.397761
    min      67.000000
    25%      75.750000
    50%      88.500000
    75%      96.000000
    max      99.000000
    dtype: float64


