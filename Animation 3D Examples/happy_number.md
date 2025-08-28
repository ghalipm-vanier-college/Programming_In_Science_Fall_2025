## Happy Number
```python
def sum_of_square_of_digits(n):
  return sum( int(c)**2 for c in str(n) )

def happy_or_sad(n):
  if n == 1:
    return "happy"
  elif n == 4:
    return "sad"
  else:
    return happy_or_sad(sum_of_square_of_digits(n))

def filter_happy_numbers_until(n):
  happy_numbers=[]
  for i in range(1, n+1):
    if happy_or_sad(i)=='happy':
      happy_numbers.append(i)
  return happy_numbers

filter_happy_numbers_until(10)
```
     
