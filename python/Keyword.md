**assert** - condition  
`
if not condition:
    raise AssertionError()
`

**continue** v.s **break** 

**del** - delete variables, lists, or parts of a list

**global** - global x

**lambda** - anonymous function

x=lambda a,b: a*b x(a,b)   (make a function powerful)

**filter** - filter(function, iterable) return filter list 

**map** - map(function, iterable, ...) return map list

**reduce** - (functools) reduce(function, iterable[, initializer])  (a+b)+c

**yield** - 

**collections** - d = collections.deque([])

d.append('a') # 在最右边添加一个元素，此时 d=deque('a')

d.appendleft('b') # 在最左边添加一个元素，此时 d=deque(['b', 'a'])

d.extend(['c','d']) # 在最右边添加所有元素，此时 d=deque(['b', 'a', 'c', 'd'])

d.extendleft(['e','f']) # 在最左边添加所有元素，此时 d=deque(['f', 'e', 'b', 'a', 'c', 'd'])

d.pop() # 将最右边的元素取出，返回 'd'，此时 d=deque(['f', 'e', 'b', 'a', 'c'])

d.popleft() # 将最左边的元素取出，返回 'f'，此时 d=deque(['e', 'b', 'a', 'c'])

d.rotate(-2) # 向左旋转两个位置（正数则向右旋转），此时 d=deque(['a', 'c', 'e', 'b'])

d.count('a') # 队列中'a'的个数，返回 1

d.remove('c') # 从队列中将'c'删除，此时 d=deque(['a', 'e', 'b'])

d.reverse() # 将队列倒序，此时 d=deque(['b', 'e', 'a'])






