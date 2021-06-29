Algorithm
========

# 1，排序算法

对array=[5,3,1,2,0]进行排序

### 选择排序 (选出最小index，插入新list)
```
def findsmallest(arr):
  
  smallest_num=arr[0]
  smallest_index=0
  
  for i in range(len(arr)):
    if smallest_num < arr[i]:
      smallest_num = arr[i]
      smallest_index = i
  return smallest_index

def sortarray(arr):
  
  sortedarr=[]
  
  for i in range(len(arr)):
    smallest_index=findsmallest(arr)
    sortedarr.append(arr.pop(smallest_index))
  return sortedarr,
```
### 冒泡排序
```
def bubblesort(arr):
    for i in range(1,len(arr)):
        for j in range(0,len(arr)-1):
            if arr[j] < arr[j+1]:
                arr[j] , arr[j+1] = arr[j+1] ,arr[j]
    return arr
```

### 快速排序
```
def quicksort(arr):
    if len(arr) < 2:
        return arr

    else:
        pivot = arr[0]
        less = [i for i in arr[1:] if i > pivot]
        greater = [i for i in arr[1:] if i <= pivot]
        sortedarr = quicksort(less) + [pivot] + quicksort(greater)
        return sortedarr
 
```







