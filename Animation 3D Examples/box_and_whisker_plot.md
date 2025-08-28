## box_and_whisker_plot:
```python
#nums=[-50, 3,4,6,8,12,10,7,100]
nums=[10, 12, 11, 13, 15, 100, 14, 11]
print('original numbers:',nums)
nums.sort() # sorting the numbers
print('sorted numbers:',nums)
n=len(nums) # number of elements
# define a function for finding the middle element
def find_middle(list):
  n=len(list)
  if n%2==1:
    middle=list[int(n/2)]
  else:
    middle=(list[int(n/2)]+list[int((n-1)/2)])/2
  # print('middle:', middle)
  return middle

q2=find_middle(nums)

# left list
left_list=[]
for i in range(int(n/2)):
  left_list.insert(i, nums[i])
print(left_list)

# right list
right_list=[]
for i in range(int((n+1)/2), n):
  right_list.insert(i, nums[i])
print(right_list)

q1=find_middle(left_list)
q3=find_middle(right_list)
print('q1:',q1)
print('q3:',q3)
iqr=q3-q1
```
