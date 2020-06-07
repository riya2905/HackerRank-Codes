#!/bin/python3

import sys


n,k = input().strip().split(' ')
n,k = [int(n),int(k)]
x = [int(x_temp) for x_temp in input().strip().split(' ')]

x = sorted(x)
#logic
# 2 4 5 6 7 9 12
# Go as right as possible for first iteration
# Again go as right as possible for second iteration
# what does this mean that place transmitter in a such way that it will handle houses on left and right sides comfortably
# So first you are at left most position.. iterate over and find middle position where (middle-left==k) and then find right most position where (right-middle<=k)

count_trans = 0
last = x[0]
i = 0
while(i < n):
    count_trans = count_trans + 1
    next_point = x[i] + k
    while(i < n and x[i] <= next_point):
        i = i + 1
    next_point = x[i-1] + k
    while(i < n and x[i] <= next_point):
        i = i + 1

print(count_trans)
