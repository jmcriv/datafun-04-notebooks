# Jim Crivello's Module 4 Project - Part 2

## Task 1. Create DataFrame


```python
import pandas as pd
```


```python
grades_dict = {'Wally': [87, 96, 70], 'Eva': [100, 87, 90], 'Sam': [94, 77, 90], 'Katie': [100, 81, 82], 'Bob': [83, 65, 85]}
```


```python
grades = pd.DataFrame(grades_dict)
```


```python
grades
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>1</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
    <tr>
      <th>2</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>



## Task 2. Custom Index


```python
pd.DataFrame(grades_dict, index=['Test1', 'Test2', 'Test3'])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.index = ['Test1', 'Test2', 'Test3']
```


```python
grades
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades['Eva']
```




    Test1    100
    Test2     87
    Test3     90
    Name: Eva, dtype: int64




```python
grades.Sam
```




    Test1    94
    Test2    77
    Test3    90
    Name: Sam, dtype: int64



## Task 3. Assessing Rows (loc, iloc)


```python
grades.loc['Test1']
```




    Wally     87
    Eva      100
    Sam       94
    Katie    100
    Bob       83
    Name: Test1, dtype: int64




```python
grades.iloc[1]
```




    Wally    96
    Eva      87
    Sam      77
    Katie    81
    Bob      65
    Name: Test2, dtype: int64




```python
grades.loc['Test1' : 'Test3']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.iloc[0:2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.loc[['Test1', 'Test3']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.iloc[[0,2]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
##   Answer to question -- My preference would be the grades.iloc[[0,2]] approach
```

## Task 3. Accessing Subsets (at, iat)


```python
grades.loc['Test1':'Test2', ['Eva', 'Katie']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Eva</th>
      <th>Katie</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>100</td>
      <td>100</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>87</td>
      <td>81</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.iloc[[0,2], 0:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>



## Task 4. Describe (By Column)


```python
grades.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>84.333333</td>
      <td>92.333333</td>
      <td>87.000000</td>
      <td>87.666667</td>
      <td>77.666667</td>
    </tr>
    <tr>
      <th>std</th>
      <td>13.203535</td>
      <td>6.806859</td>
      <td>8.888194</td>
      <td>10.692677</td>
      <td>11.015141</td>
    </tr>
    <tr>
      <th>min</th>
      <td>70.000000</td>
      <td>87.000000</td>
      <td>77.000000</td>
      <td>81.000000</td>
      <td>65.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>78.500000</td>
      <td>88.500000</td>
      <td>83.500000</td>
      <td>81.500000</td>
      <td>74.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>87.000000</td>
      <td>90.000000</td>
      <td>90.000000</td>
      <td>82.000000</td>
      <td>83.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>91.500000</td>
      <td>95.000000</td>
      <td>92.000000</td>
      <td>91.000000</td>
      <td>84.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>96.000000</td>
      <td>100.000000</td>
      <td>94.000000</td>
      <td>100.000000</td>
      <td>85.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.set_option("display.precision", 2)
```


```python
grades.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3.00</td>
      <td>3.00</td>
      <td>3.00</td>
      <td>3.00</td>
      <td>3.00</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>84.33</td>
      <td>92.33</td>
      <td>87.00</td>
      <td>87.67</td>
      <td>77.67</td>
    </tr>
    <tr>
      <th>std</th>
      <td>13.20</td>
      <td>6.81</td>
      <td>8.89</td>
      <td>10.69</td>
      <td>11.02</td>
    </tr>
    <tr>
      <th>min</th>
      <td>70.00</td>
      <td>87.00</td>
      <td>77.00</td>
      <td>81.00</td>
      <td>65.00</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>78.50</td>
      <td>88.50</td>
      <td>83.50</td>
      <td>81.50</td>
      <td>74.00</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>87.00</td>
      <td>90.00</td>
      <td>90.00</td>
      <td>82.00</td>
      <td>83.00</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>91.50</td>
      <td>95.00</td>
      <td>92.00</td>
      <td>91.00</td>
      <td>84.00</td>
    </tr>
    <tr>
      <th>max</th>
      <td>96.00</td>
      <td>100.00</td>
      <td>94.00</td>
      <td>100.00</td>
      <td>85.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.mean()
```




    Wally    84.33
    Eva      92.33
    Sam      87.00
    Katie    87.67
    Bob      77.67
    dtype: float64



## Task 5. Transpose (rows <--> columns)


```python
grades.T
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Test1</th>
      <th>Test2</th>
      <th>Test3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Wally</th>
      <td>87</td>
      <td>96</td>
      <td>70</td>
    </tr>
    <tr>
      <th>Eva</th>
      <td>100</td>
      <td>87</td>
      <td>90</td>
    </tr>
    <tr>
      <th>Sam</th>
      <td>94</td>
      <td>77</td>
      <td>90</td>
    </tr>
    <tr>
      <th>Katie</th>
      <td>100</td>
      <td>81</td>
      <td>82</td>
    </tr>
    <tr>
      <th>Bob</th>
      <td>83</td>
      <td>65</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.T.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Test1</th>
      <th>Test2</th>
      <th>Test3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>5.00</td>
      <td>5.00</td>
      <td>5.00</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>92.80</td>
      <td>81.20</td>
      <td>83.40</td>
    </tr>
    <tr>
      <th>std</th>
      <td>7.66</td>
      <td>11.54</td>
      <td>8.23</td>
    </tr>
    <tr>
      <th>min</th>
      <td>83.00</td>
      <td>65.00</td>
      <td>70.00</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>87.00</td>
      <td>77.00</td>
      <td>82.00</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>94.00</td>
      <td>81.00</td>
      <td>85.00</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>100.00</td>
      <td>87.00</td>
      <td>90.00</td>
    </tr>
    <tr>
      <th>max</th>
      <td>100.00</td>
      <td>96.00</td>
      <td>90.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.T.mean()
```




    Test1    92.8
    Test2    81.2
    Test3    83.4
    dtype: float64



## Task 6. Sort


```python
grades.sort_index(ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.sort_index(axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Bob</th>
      <th>Eva</th>
      <th>Katie</th>
      <th>Sam</th>
      <th>Wally</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>83</td>
      <td>100</td>
      <td>100</td>
      <td>94</td>
      <td>87</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>65</td>
      <td>87</td>
      <td>81</td>
      <td>77</td>
      <td>96</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>85</td>
      <td>90</td>
      <td>82</td>
      <td>90</td>
      <td>70</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.sort_values(by='Test1', axis=1, ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Eva</th>
      <th>Katie</th>
      <th>Sam</th>
      <th>Wally</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>100</td>
      <td>100</td>
      <td>94</td>
      <td>87</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>87</td>
      <td>81</td>
      <td>77</td>
      <td>96</td>
      <td>65</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>90</td>
      <td>82</td>
      <td>90</td>
      <td>70</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>




```python
grades.loc['Test1'].sort_values(ascending=False)
```




    Eva      100
    Katie    100
    Sam       94
    Wally     87
    Bob       83
    Name: Test1, dtype: int64




```python
grades.sort_index(inplace=True)
```


```python
grades
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Wally</th>
      <th>Eva</th>
      <th>Sam</th>
      <th>Katie</th>
      <th>Bob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Test1</th>
      <td>87</td>
      <td>100</td>
      <td>94</td>
      <td>100</td>
      <td>83</td>
    </tr>
    <tr>
      <th>Test2</th>
      <td>96</td>
      <td>87</td>
      <td>77</td>
      <td>81</td>
      <td>65</td>
    </tr>
    <tr>
      <th>Test3</th>
      <td>70</td>
      <td>90</td>
      <td>90</td>
      <td>82</td>
      <td>85</td>
    </tr>
  </tbody>
</table>
</div>


