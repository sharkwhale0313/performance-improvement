### for문 성능 개선

dot 연산이 for문 안에 들어가면 속도가 느려짐

```
# 일반적인 for문 : 느림
def f1():
	a = []
	for i in range(1000000):
		a.append(i)

# . 연산을 for문밖으로 뺀 경우 : 빠름
def f2():
	a = []
	append = a.append
	
	f in range(1000000):
		append(i)

# list comprehension : 가장빠름
def f3():
	a = [i for i in range(100000)]

%timeit f1() # 109ms per loop
%timeit f2() # 77.3ms per loop
%timeit f3() # 62.9ms per loop
```
