# Problem

Given an sorted array and size of the array as arguments to a function. Write a function that moves all the distinct elements present in the array to the front and returns the size of the new array. 
![[Pasted image 20240122043453.png]]

# Naive approach to the solution
## Main Idea

- Create a temporary array equivalent the size of the given array, because in the worst case, all elements of the previous array may be distinct.
- Initialize a variable(size of the temporary array) $res=1$
- Initialize the temporary array as $temp[0] = arr[0]$
- Iterate over the main array, from index 1 to n
- Create a conditional statement, which checks whether the element is same as the last copied element.
- Then initialize the temp array with new distinct variable of the main array and increment the $res$ variable.

## Code
```python
def removeDuplicates(li,size):
    temp = [None] * size
    temp[0] = li[0]
    res = 1
    for i in range(1,size):
        if (temp[res-1]!=li[i]):
            temp[res] = li[i]
            res+=1
    li_1 = [None] * res
    for j in range(0,res):
        li_1[j] = temp[j]
    return res
```
## Working
![[Pasted image 20240122050701.png]]

## Efficiency
- Time complexity of the solution is $O(n)$.
- Space Complexity of the solution is $O(n)$.
# Efficient approach to the solution
## Main Idea
- Initialize a variable $res=1$
- Iterate over the array from 1 to $n$.
- Whenever the current element of the array is not equal to the $(res-1)^{th}$ element then assign that element to the $res^{th}$ position and increment the $res$ variable.
- Return the $res$ variable
## Code
```python
def removeDuplicatesEfficient(li,size):
    res = 1
    for i in range(1,size):
        if li[res-1]!=li[i]:
            li[res] = li[i]
            res = res + 1
    return res
```

## Working
![[Pasted image 20240122054924.png]]

## Efficiency

- Time complexity of the solution is $O(n)$.
- Space Complexity of the solution is $O(n)$.