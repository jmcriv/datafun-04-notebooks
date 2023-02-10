## Jim Crivello - Bonus Section - 2/5/23

## 1. Create a DataFrame


```python
import pandas as pd
```


```python
contacts = [['Mike Green', 'demo1@deitel.com', '5555555555'], ['Sue Brown', 'demo2@deitel.com', '5555551234']]
```


```python
contactsdf = pd.DataFrame(contacts, columns = ['Name', 'Email', 'Phone'])
```


```python
contactsdf
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
      <th>Name</th>
      <th>Email</th>
      <th>Phone</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Mike Green</td>
      <td>demo1@deitel.com</td>
      <td>5555555555</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sue Brown</td>
      <td>demo2@deitel.com</td>
      <td>5555551234</td>
    </tr>
  </tbody>
</table>
</div>



## 2. Improve the DataFrame


```python
import re
```


```python
def get_formatted_phone(value):
    result = re.fullmatch(r'(\d{3})(\d{3})(\d{4})', value)
    return '-'.join(result.groups()) if result else value
```


```python
formatted_phone = contactsdf['Phone'].map(get_formatted_phone)
```


```python
formatted_phone
```




    0    555-555-5555
    1    555-555-1234
    Name: Phone, dtype: object




```python
contactsdf['Phone'] = formatted_phone
```


```python
contactsdf
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
      <th>Name</th>
      <th>Email</th>
      <th>Phone</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Mike Green</td>
      <td>demo1@deitel.com</td>
      <td>555-555-5555</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Sue Brown</td>
      <td>demo2@deitel.com</td>
      <td>555-555-1234</td>
    </tr>
  </tbody>
</table>
</div>


