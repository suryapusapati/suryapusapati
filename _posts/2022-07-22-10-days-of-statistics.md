---
title: Hackerrank - 10 Days of Statistics
tags: [Data Science, Statistics, Python, Scratch]
style: border
color: primary
description: Solutions of codeing questions in '10 days of statistics' solved using python.
---
<br/>
<div style='float: center; text-align: center; margin-bottom: 20px'>
  <a href='https://www.hackerrank.com/SuryaPusapati' target="_blank">
  <img width="300px" src="https://www.hackerrank.com/wp-content/uploads/2018/08/hackerrank_logo.png" />
  </a>
</div>
<br/>

## Hackerrank: 10 Days of Statistics
Source code: [GitHub](https://github.com/suryapusapati/10-Days-of-Statistics-by-Hackerrank)

Challenge: [Hackerrank: 10 Days of Statistics](https://www.hackerrank.com/domains/tutorials/10-days-of-statistics)

In this project I used python to solve basic statistics problems. I have not imported any python packages to solve any problems except for essentail math functions `from math import exp, sqrt, pi, erf`. Other type of questions in challenge such as multiple choice question are not included. This project only contins solutions for coding part. Happy learning!!

### Day 0: Mean, Median, and Mode
```
N = int(input())
sample = sorted(list(map(float, input().strip().split())))
if N == len(sample):
	# mean
	sum_ = 0
	for i in sample:
		sum_ += i
	mean = sum_/N
	# median
	if N%2 == 0:
		median = (sample[int(N/2-0.5)] + sample[int(N/2+0.5)])/2
	else:
		median = sample[int(N/2+0.5)]
	# mode
	mode = []
	count = {}
	for i in sample:
		if i in count:
			count[i] += 1
		else:
			count[i] = 1
	for key in count.keys():
		if count[key] == max(count.values()):
			mode.append(key)
		
	print(round(mean, 1))
	print(round(median, 1))
	print(mode[0])
```
### Day 0: Weighted Mean
```
def weightedMean(X, W):
	global n
	XW_sum = 0
	W_sum = 0
	for i in range(n):
		XW_sum += X[i] * W[i]
		W_sum += W[i]
	print(round((XW_sum/W_sum), 1))

if __name__ == '__main__':
	n = int(input().strip())
	vals = list(map(int, input().rstrip().split()))
	weights = list(map(int, input().rstrip().split()))
	weightedMean(vals, weights)
```
### Day 1: Quartiles
```
import os

def medium(arr):
	n = len(arr)
	if n%2 == 0:
		Q = (arr[int((n-1)*0.5)] + arr[int((n+1)*0.5)])/2
	else:
		Q = arr[int(n*0.5)]
	if Q - int(Q) == 0:
		return int(Q)
	else:
		return Q

def quartiles(arr):
	n = len(arr)
	Q2 = medium(arr)
	Q1 = medium(arr[:n//2])
	Q3 = medium(arr[int(n/2+0.5):])
	return Q1, Q2, Q3

if __name__ == '__main__':
	fptr = open(os.environ['OUTPUT_PATH'], 'w')
	n = int(input().strip())
	data = list(sorted(map(int, input().rstrip().split())))
	res = quartiles(data)
	fptr.write('\n'.join(map(str, res)))
	fptr.write('\n')
	fptr.close()
```
### Day 1: Standard Deviation
```
def mean(arr):
	global n
	sum_ = 0
	for i in range(n):
		sum_ += arr[i]
	return n, sum_/n

def stdDev(arr):
	n, mean_ = mean(arr)
	std = 0
	for i in range(n):
		std += ((mean_ - arr[i])**2)
	print((std/n)**0.5)

if __name__ == '__main__':
	n = int(input().strip())
	vals = list(map(int, input().rstrip().split()))
	stdDev(vals)
```
### Day 1: Interquartile Range
```
def median(arr):
	N = len(arr)
	if N%2==0:
		med = (arr[int((N-1)*0.5)] + arr[int((N+1)*0.5)])/2
	else:
		med = arr[int(N*0.5)]
	return float(med)

def interQuartile(values, freqs):
	global n
	value_list = []
	for i in range(n):
		for _ in range(freqs[i]):
			value_list.append(values[i])
	value_list.sort()
	n = len(value_list)
	print(round(\
	median(value_list[int((n+1)*0.5):]) - median(value_list[:n//2]), 1))

if __name__ == '__main__':
	n = int(input().strip())
	val = list(map(int, input().rstrip().split()))
	freq = list(map(int, input().rstrip().split()))
	interQuartile(val, freq)
```
### Day 4: Binomial Distribution I
```
p1, n = map(float, input().split())

# p for boys
gap = 1/(1 + (n/p1))
x = 3
n = 6

def fact(x):
	a = 1
	for i in range(1, x+1):
		a *= i
	return a

def comb(n, r):
	return float(fact(n)/(fact(r)*fact(n-r)))

def bino(x, n, p):
	q = 1 - p
	return (comb(n, x)*(p**x)*(q**(n-x)))

print(round(sum([bino(i, n, gap) for i in range(x, n+1)]), 3))
```
### Day 4: Binomial Distribution II
```
p, n = map(int, input().split())

p /= 100

def fact(x):
    if x == 0:
        a = 1
    else:
        a = 1
        for i in range(1, x+1):
            a *= i
    return a

def comb(n, r):
    return float(fact(n)/(fact(r)*fact(n-r)))

def bino(x, n, p):
    q = 1 - p
    return (comb(n, x)*(p**x)*(q**(n-x)))

def prob(from_, to_):
    print(round(sum([bino(i, n, p) for i in range(from_, to_+1)]), 3))

# no more than 2 rejects
prob(0, 2)

# at least 2 rejects
prob(2, n)
```
### Day 4: Geometric Distribution I
```
p1, p2 = map(int, input().split())
p0 = int(input())

p = p1/p2

def geo(n, p):
    return round((p*((1-p)**(n-1))), 3)

print(geo(p0, p))
```
### Day 4: Geometric Distribution II
```
p1, p2 = map(int, input().split())
p0 = int(input())

p = p1/p2

def geo(n, p):
    return round(sum([(p*((1-p)**(i-1))) for i in range(1, p0+1)]), 3)

print(geo(p0, p))
```
### Day 5: Poisson Distribution I
```
from math import exp

mean = float(input())
X = int(input())

def fact(x):
    if x == 0:
        n = 1
    else:
        n = 1
        for i in range(1, x+1):
            n *= i
    return n

def pois(X, mean):
    return round(((mean**X)*(exp(-mean)))/fact(X), 3)

print(pois(X, mean))
```
### Day 5: Poisson Distribution II
```
X, Y = map(float, input().split())

#def C_A(X):
print(round(160 + (40*(X+X**2)), 3))
    
#def C_B(Y):
print(round(128 + (40*(Y+Y**2)), 3))
```
### Day 5: Normal Distribution I
```
from math import exp, sqrt, pi, erf

# read input
mean, std = map(float, input().split())
X1 = float(input())
X2, X3 = map(float, input().split())

'''
# pdf: normal distribution
def norm(x, mean, std):
    con1 = exp(-((x - mean)**2)/(2*(std**2)))
    return con1/(std*sqrt(2*pi))
'''

# cdf: normal distribution
def norm(x, mean, std):
    return ((1 + erf((x - mean)/(sqrt(2)*std)))*0.5)

# Q01
print(round(norm(X1, mean, std), 3))

# Q02
print(round((norm(X3, mean, std) - norm(X2, mean, std)), 3))
```
### Day 5: Normal Distribution II
```
from math import sqrt, erf

mu, std = map(float, input().split())
X1 = float(input())
X2 = float(input())

# cdf: normal distribution
def norm(x, mean, std):
    return ((1 + erf((x - mean)/(sqrt(2)*std)))*0.5)*100

# X > X1
print(round(100 - norm(X1, mu, std), 2))

# X >= X2
print(round(100 - norm(X2, mu, std), 2))

# X < X2
print(round(norm(X2, mu, std), 2))
```
### Day 6: The Central Limit Theorem I
```
from math import sqrt, erf

# read inputs
max_ = int(input())
box = int(input())
mu = int(input())
std = int(input())

# cdf: normal distribution
def norm(x, mean, std):
    return ((1 + erf((x - mean)/(sqrt(2)*std)))*0.5)

mu_ = box*mu
std_ = sqrt(box)*std

print(round(norm(max_, mu_, std_), 4))
```
### Day 6: The Central Limit Theorem II
```
from math import sqrt, erf

# read all inputs
max_tic = int(input())
tic = int(input())
mu = float(input())
std = float(input())

# CDF: normal distribution
def norm(x, mean, std):
    return ((1 + erf((x - mean)/(sqrt(2)*std)))*0.5)

mu_ = tic * mu
std_ = sqrt(tic) * std

print(round(norm(250, mu_, std_), 4))
```
### Day 6: The Central Limit Theorem III
```
from math import sqrt

# read inputs
sample = int(input())
mu = int(input())
std = int(input())
inte = float(input())
z = float(input())

# lower limit
print(round(mu - z*(std/sqrt(sample)), 2))

# higher limit
print(round(mu + z*(std/sqrt(sample)), 2))
```
### Day 7: Pearson Correlation Coefficient I
```
# Read inputs 
n = int(input())
X = list(map(float, input().split()))
Y = list(map(float, input().split()))

# check n == len(X) == len(Y)

# mean
def mean(a):
    return sum(a)/len(a)

# standard deviation
def std(a):
    global n
    mu = mean(a)
    sum_ = 0.0
    for i in range(n):
        sum_ += ((a[i] - mu)**2)
    return (sum_/n)**0.5

# corr(X, Y)
def corr(arr1, arr2):
    global n
    mean1 = mean(arr1)
    mean2 = mean(arr2)
    conv = 0.0
    for i in range(n):
        conv += (arr1[i] - mean1) * (arr2[i] - mean2)
    print(round(conv/(n*std(arr1)*std(arr2)), 3))

corr(X, Y)
```
### Day 7: Spearman's Rank Correlation Coefficient
```
# Read inputs
n = int(input())
X = list(map(float, input().split()))
Y = list(map(float, input().split()))

# Ranking
def rank(arr):
    return [sorted(arr).index(x)+1 for x in arr]

# Spearman's rank correlation
def corr(arr1, arr2):
    global n
    r_arr1 = rank(arr1)
    r_arr2 = rank(arr2)
    sum_ = 0.0
    for i in range(n):
        sum_ += (r_arr1[i] - r_arr2[i])**2
    print(round(1-((6*sum_)/(n*((n**2)-1))), 3))

corr(X, Y)
```
### Day 8: Least Square Regression Line
```
# Read inputs into array
n = 5
X, Y = list(), list()
for _ in range(n):
    x, y = map(int, input().split())
    X.append(x)
    Y.append(y)

# mean
def mean(a):
    return sum(a)/len(a)

# standard deviation
def std(a):
    global n
    mu = mean(a)
    sum_ = 0.0
    for i in range(n):
        sum_ += ((a[i] - mu)**2)
    return (sum_/n)**0.5

# corr(X, Y)
def corr(arr1, arr2):
    global n
    mean1 = mean(arr1)
    mean2 = mean(arr2)
    conv = 0.0
    for i in range(n):
        conv += (arr1[i] - mean1) * (arr2[i] - mean2)
    return conv/(n*std(arr1)*std(arr2))

# fit the best-fit line using least squares and find the value of y
def liner(X, Y, x1):
    b = corr(X,Y)*(std(Y)/std(X))
    a = mean(Y) - (b*mean(X))
    print(round(a + (b*x1), 3))

liner(X, Y, 80)
```
### Day 8: Pearson Correlation Coefficient II
*Working on a bug. Will be posted soon.*

### Day 9: Multiple Linear Regression
*Working on a bug. Will be posted soon.*


I hope you this project is useful. If you encounter any error. Report your [issue](https://github.com/suryapusapati/10-Days-of-Statistics-by-Hackerrank/issues) in GitHub.

Ⓒ 2022 Surya Pusapati
