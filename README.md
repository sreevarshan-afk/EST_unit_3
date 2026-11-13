# EST_unit_3


# **Unit 3 – Programming Basics**

## **1. Data Types – Basic Data Types**


```
i = int(input())l = int(input())c = input()f = float(input())d = float(input())print(i)print(l)print(c)print(f)print(d)
```

## **2. Input and Output – Input and Output (C++)**

```
n = int(input())numbers = list(map(int, input().split()))print(sum(numbers))
```

## **3. Java Stdin and Stdout I**

```
a = int(input())b = int(input())c = int(input())print(a)print(b)print(c)
```

## **4. Operators – Arithmetic Operators**

```
a = int(input())b = int(input())print(a + b)print(a - b)print(a * b)
```

## **5. Compare the Triplets**

```
def compareTriplets(a, b):    alice = 0    bob = 0    for i in range(3):        if a[i] > b[i]:            alice += 1        elif a[i] < b[i]:            bob += 1    return [alice, bob]a = list(map(int, input().split()))b = list(map(int, input().split()))print(*compareTriplets(a, b))
```

## **6. Decision Making – Python If-Else**

```
n = int(input())if n % 2 != 0:    print("Weird")elif 2 <= n <= 5:    print("Not Weird")elif 6 <= n <= 20:    print("Weird")else:    print("Not Weird")
```

## **7. Conditional Statements (C++) – Python equivalent**

```
n = int(input())if n == 1:    print("one")elif n == 2:    print("two")elif n == 3:    print("three")elif n == 4:    print("four")elif n == 5:    print("five")elif n == 6:    print("six")elif n == 7:    print("seven")elif n == 8:    print("eight")elif n == 9:    print("nine")else:    print("Greater than 9")
```

## **8. Loops**

```
n = int(input())for i in range(1, 11):    print(f"{n} x {i} = {n * i}")
```

## **9. For Loop (C++) – Python equivalent**

```
a, b = map(int, input().split())for i in range(a, b + 1):    if 0 <= i <= 9:        words = [            "zero", "one", "two", "three", "four",            "five", "six", "seven", "eight", "nine"        ]        print(words[i])    elif i > 9:        print("even" if i % 2 == 0 else "odd")
```

## **10. Simple Array Sum**

```
def simpleArraySum(ar):    return sum(ar)n = int(input())ar = list(map(int, input().split()))print(simpleArraySum(ar))
```

## **11. Arrays – DS (Reverse Array)**

```
def reverseArray(a):    return a[::-1]n = int(input())a = list(map(int, input().split()))print(*reverseArray(a))
```

## **12. Plus Minus**

```
def plusMinus(arr):    n = len(arr)    positive = sum(1 for x in arr if x > 0)    negative = sum(1 for x in arr if x < 0)    zero = sum(1 for x in arr if x == 0)    print(f"{positive / n:.6f}")    print(f"{negative / n:.6f}")    print(f"{zero / n:.6f}")n = int(input())arr = list(map(int, input().split()))plusMinus(arr)
```

## **13. 2D Array – DS (Hourglass Sum)**

```
def hourglassSum(arr):    maximum = float("-inf")    for i in range(4):        for j in range(4):            total = (                arr[i][j] + arr[i][j+1] + arr[i][j+2]                + arr[i+1][j+1]                + arr[i+2][j] + arr[i+2][j+1] + arr[i+2][j+2]            )            maximum = max(maximum, total)    return maximumarr = [list(map(int, input().split())) for _ in range(6)]print(hourglassSum(arr))
```

## **14. Diagonal Difference**

```
def diagonalDifference(arr):    n = len(arr)    primary = 0    secondary = 0    for i in range(n):        primary += arr[i][i]        secondary += arr[i][n - 1 - i]    return abs(primary - secondary)n = int(input())arr = [list(map(int, input().split())) for _ in range(n)]print(diagonalDifference(arr))
```

## **15. CamelCase**

```
def camelcase(s):    count = 1    for ch in s:        if ch.isupper():            count += 1    return counts = input()print(camelcase(s))
```

## **16. Super Reduced String**

```
def superReducedString(s):    stack = []    for ch in s:        if stack and stack[-1] == ch:            stack.pop()        else:            stack.append(ch)    return "".join(stack) if stack else "Empty String"s = input()print(superReducedString(s))
```

## **17. Funny String**

```
def funnyString(s):    r = s[::-1]    for i in range(1, len(s)):        if abs(ord(s[i]) - ord(s[i-1])) != abs(ord(r[i]) - ord(r[i-1])):            return "Not Funny"    return "Funny"t = int(input())for _ in range(t):    s = input()    print(funnyString(s))
```

## **18. Pangrams**

```
def pangrams(s):    letters = set(s.lower())    if all(ch in letters for ch in "abcdefghijklmnopqrstuvwxyz"):        return "pangram"    return "not pangram"s = input()print(pangrams(s))
```

## **19. Pointer (C++) / Pointers in C – Python equivalent**


```
def update(a, b):    total = a + b    difference = abs(a - b)    return total, differencea = int(input())b = int(input())total, difference = update(a, b)print(total)print(difference)
```

## **20. Functions – Write a Function**



```
def is_leap(year):    if year % 400 == 0:        return True    elif year % 100 == 0:        return False    elif year % 4 == 0:        return True    return Falseyear = int(input())print(is_leap(year))
```

## **21. Structs / Small Triangles, Large Triangles**


```
def triangle_area(a, b, c):    s = (a + b + c) / 2    return (s * (s-a) * (s-b) * (s-c)) ** 0.5n = int(input())triangles = []for _ in range(n):    a, b, c = map(int, input().split())    triangles.append((a, b, c))triangles.sort(key=lambda t: triangle_area(*t))for triangle in triangles:    print(*triangle)
```

## **22. Dynamic Array**

```
def dynamicArray(n, queries):    arr = [[] for _ in range(n)]    lastAnswer = 0    result = []    for query in queries:        q, x, y = query        idx = (x ^ lastAnswer) % n        if q == 1:            arr[idx].append(y)        else:            lastAnswer = arr[idx][y % len(arr[idx])]            result.append(lastAnswer)    return resultn, q = map(int, input().split())queries = [list(map(int, input().split())) for _ in range(q)]print(*dynamicArray(n, queries), sep="\n")
```

## **23. Variable Sized Arrays**

```
n, q = map(int, input().split())arr = []for _ in range(n):    values = list(map(int, input().split()))    k = values[0]    arr.append(values[1:k+1])for _ in range(q):    i, j = map(int, input().split())    print(arr[i][j])
```

## **24. Sherlock and Array – Balanced Sums**

```
def balancedSums(arr):    total = sum(arr)    left = 0    for num in arr:        right = total - left - num        if left == right:            return "YES"        left += num    return "NO"t = int(input())for _ in range(t):    n = int(input())    arr = list(map(int, input().split()))    print(balancedSums(arr))
```

## **25. Array Manipulation**

```
def arrayManipulation(n, queries):    arr = [0] * (n + 2)    for a, b, k in queries:        arr[a] += k        arr[b + 1] -= k    current = 0    maximum = 0    for i in range(1, n + 1):        current += arr[i]        maximum = max(maximum, current)    return maximumn, m = map(int, input().split())queries = [list(map(int, input().split())) for _ in range(m)]print(arrayManipulation(n, queries))
```

## **26. Max Min**

```
def maxMin(k, arr):    arr.sort()    minimum = float("inf")    for i in range(len(arr) - k + 1):        unfairness = arr[i + k - 1] - arr[i]        minimum = min(minimum, unfairness)    return minimumn = int(input())k = int(input())arr = [int(input()) for _ in range(n)]print(maxMin(k, arr))
```

## **27. Deque – Maximum of Every Subarray**

This is the sliding-window maximum problem, using a monotonic deque.

```
from collections import dequen, k = map(int, input().split())arr = list(map(int, input().split()))dq = deque()result = []for i in range(n):    while dq and dq[0] <= i - k:        dq.popleft()    while dq and arr[dq[-1]] <= arr[i]:        dq.pop()    dq.append(i)    if i >= k - 1:        result.append(arr[dq[0]])print(*result)
```

## **28. Counting Sort 1**

```
def countingSort(arr):    freq = [0] * 100    for num in arr:        freq[num] += 1    return freqn = int(input())arr = list(map(int, input().split()))print(*countingSort(arr))
```

## **29. Counting Sort 2**

```
def countingSort(arr):    freq = [0] * 100    for num in arr:        freq[num] += 1    result = []    for i in range(100):        result.extend([i] * freq[i])    return resultn = int(input())arr = list(map(int, input().split()))print(*countingSort(arr))
```

## **30. Fraudulent Activity Notifications**

```
def activityNotifications(expenditure, d):    freq = [0] * 201    notifications = 0    for i in range(d):        freq[expenditure[i]] += 1    for i in range(d, len(expenditure)):        count = 0        if d % 2 == 1:            for j in range(201):                count += freq[j]                if count > d // 2:                    median_twice = 2 * j                    break        else:            first = second = None            for j in range(201):                count += freq[j]                if first is None and count >= d // 2:                    first = j                if count >= d // 2 + 1:                    second = j                    break            median_twice = first + second        if expenditure[i] >= median_twice:            notifications += 1        freq[expenditure[i-d]] -= 1
```

## **31. Recursive Digit Sum**

```
def superDigit(n, k):    total = sum(int(digit) for digit in n) * k    def calculate(num):        if num < 10:            return num        digit_sum = sum(int(digit) for digit in str(num))        return calculate(digit_sum)    return calculate(total)n, k = input().split()print(superDigit(n, int(k)))
```

## **32. The Power Sum**

```
def powerSum(X, N):    def solve(remaining, current):        power = current ** N        if power == remaining:            return 1        if power > remaining:            return 0        include = solve(remaining - power, current + 1)        exclude = solve(remaining, current + 1)        return include + exclude    return solve(X, 1)X = int(input())N = int(input())print(powerSum(X, N))
```

## **33. Recursion – Davis' Staircase**

```
def stepPerms(n):    if n == 0:        return 1    dp = [0] * (n + 1)    dp[0] = 1    for i in range(1, n + 1):        dp[i] = dp[i - 1]        if i >= 2:            dp[i] += dp[i - 2]        if i >= 3:            dp[i] += dp[i - 3]    return dp[n] % 10000000007s = int(input())for _ in range(s):    n = int(input())    print(stepPerms(n))
```

## **34. Time Complexity – Primality**

```
def primality(n):    if n <= 1:        return "Not prime"    if n == 2:        return "Prime"    if n % 2 == 0:        return "Not prime"    i = 3    while i * i <= n:        if n % i == 0:            return "Not prime"        i += 2    return "Prime"p = int(input())for _ in range(p):    n = int(input())    print(primality(n))
```

## **35. Day 25 – Running Time and Complexity**

```
def is_prime(n):    if n <= 1:        return False    if n == 2:        return True    if n % 2 == 0:        return False    i = 3    while i * i <= n:        if n % i == 0:            return False        i += 2    return Truet = int(input())for _ in range(t):    n = int(input())    print("Prime" if is_prime(n) else "Not prime")
```

# **Unit 4 – Problems on Maths**

## **36. GCD – Restaurant**

Find the maximum number of equal square pieces that can be cut from a rectangle.

```
from math import gcddef restaurant(l, b):    side = gcd(l, b)    return (l // side) * (b // side)t = int(input())for _ in range(t):    l, b = map(int, input().split())    print(restaurant(l, b))
```

## **37. Between Two Sets**

Find how many integers are multiples of every number in array `a` and factors of every number in array `b`.

```
from math import gcddef lcm(a, b):    return a * b // gcd(a, b)def getTotalX(a, b):    lcm_a = a[0]    for num in a[1:]:        lcm_a = lcm(lcm_a, num)    gcd_b = b[0]    for num in b[1:]:        gcd_b = gcd(gcd_b, num)    count = 0    for x in range(lcm_a, gcd_b + 1, lcm_a):        if gcd_b % x == 0:            count += 1    return countn, m = map(int, input().split())a = list(map(int, input().split()))b = list(map(int, input().split()))print(getTotalX(a, b))
```

## **38. LCM – Between Two Sets**

This uses the same solution as Between Two Sets:

- Calculate the LCM of array `a`.
- Calculate the GCD of array `b`.
- Count the multiples of the LCM that divide the GCD.

Use the complete code in Problem 37.

## **39. Primality Test**

This is the same optimized algorithm used in Time Complexity: Primality.

```
def is_prime(n):    if n <= 1:        return False    if n == 2:        return True    if n % 2 == 0:        return False    i = 3    while i * i <= n:        if n % i == 0:            return False        i += 2    return Truet = int(input())for _ in range(t):    n = int(input())    print("Prime" if is_prime(n) else "Not prime")
```

## **40. Sieve – Project Euler #7: 10001st Prime**

Find the nth prime number using the Sieve of Eratosthenes.

```
def sieve(limit):    is_prime = [True] * (limit + 1)    is_prime[0] = is_prime[1] = False    for i in range(2, int(limit ** 0.5) + 1):        if is_prime[i]:            for j in range(i * i, limit + 1, i):                is_prime[j] = False    return [i for i in range(2, limit + 1) if is_prime[i]]t = int(input())queries = [int(input()) for _ in range(t)]limit = 200000while True:    primes = sieve(limit)    if len(primes) >= max(queries):        break    limit *= 2for n in queries:    print(primes[n - 1])
```

## **41. Project Euler #10 – Summation of Primes**

Find the sum of all primes strictly less than `n`.

```
def sieve(limit):    is_prime = [True] * (limit + 1)    if limit >= 0:        is_prime[0] = False    if limit >= 1:        is_prime[1] = False    for i in range(2, int(limit ** 0.5) + 1):        if is_prime[i]:            for j in range(i * i, limit + 1, i):                is_prime[j] = False    prefix = [0] * (limit + 1)    total = 0    for i in range(limit + 1):        if is_prime[i]:            total += i        prefix[i] = total    return prefixt = int(input())queries = [int(input()) for _ in range(t)]prefix = sieve(max(queries))for n in queries:    print(prefix[n - 1])
```

## **42. Modular Arithmetic – Summing the N Series**

The sum of cubes is:

\\[ 1^3+2^3+\cdots+n^3 = \left(\frac{n(n+1)}{2}\right)^2 \\]

```
MOD = 1000000007t = int(input())for _ in range(t):    n = int(input())    total = n * (n + 1) // 2    answer = (total * total) % MOD    print(answer)
```

## **43. Power of Large Numbers**

Calculate \\(a^b \bmod (10^9+7)\\), even when the exponent is supplied as a very large decimal string.

```
MOD = 1000000007def large_power(a, b):    a = int(a)    result = 1    for digit in b:        result = pow(result, 10, MOD)        result = (result * pow(a, int(digit), MOD)) % MOD    return resultt = int(input())for _ in range(t):    a, b = input().split()    print(large_power(a, b))
```

## **44. Permutation and Combination – Handshake**

Find the number of handshakes possible when every person shakes hands with every other person exactly once.

\\[ \text{Handshakes}=\frac{n(n-1)}{2} \\]

```
t = int(input())for _ in range(t):    n = int(input())    print(n * (n - 1) // 2)
```

## **45. Matrix Tracing**

The number of paths from the top-left to bottom-right of an `m × n` grid, moving only right or down, is:

\\[ \binom{m+n-2}{m-1} \\]

```
MOD = 1000000007def matrixTracing(m, n):    total = m + n - 2    r = min(m - 1, n - 1)    numerator = 1    denominator = 1    for i in range(1, r + 1):        numerator = numerator * (total - r + i) % MOD        denominator = denominator * i % MOD    return numerator * pow(denominator, MOD - 2, MOD) % MODt = int(input())for _ in range(t):    m, n = map(int, input().split())    print(matrixTracing(m, n))
```

## **46. nCr Table**

Calculate the binomial coefficient \\(nCr\\) modulo \\(10^9+7\\).

```
MOD = 1000000007def build_factorials(limit):    fact = [1] * (limit + 1)    for i in range(1, limit + 1):        fact[i] = fact[i - 1] * i % MOD    inv_fact = [1] * (limit + 1)    inv_fact[limit] = pow(fact[limit], MOD - 2, MOD)    for i in range(limit, 0, -1):        inv_fact[i - 1] = inv_fact[i] * i % MOD    return fact, inv_factdef nCr(n, r, fact, inv_fact):    if r < 0 or r > n:        return 0    return (        fact[n] * inv_fact[r] % MOD        * inv_fact[n-r] % MOD    )t = int(input())queries = [tuple(map(int, input().split())) for _ in range(t)]limit = max((n for n, r in queries), default=0)fact, inv_fact = build_factorials(limit)for n, r in queries:    print(nCr(n, r, fact, inv_fact))
```

## **47. Pascal's Triangle**

Print the first `n` rows of Pascal's Triangle.

```
def pascal_triangle(n):    for i in range(n):        value = 1        row = []        for j in range(i + 1):            row.append(value)            value = value * (i - j) // (j + 1)        print(*row)n = int(input())pascal_triangle(n)
```

# **Important corrections and additional entries**

A few of the introductory exercises have different exact requirements from their Python equivalents. Use these corrected versions when submitting.

## **A. Basic Data Types (C++) – Python equivalent**

```
import sysvalues = sys.stdin.read().split()i = int(values[0])l = int(values[1])c = values[2]f = float(values[3])d = float(values[4])print(i)print(l)print(c)print(f)print(d)
```

## **B. Java Datatypes – Python equivalent**

```
t = int(input())for _ in range(t):    n = int(input())    print(n, "can be fitted in:")    if -128 <= n <= 127:        print("* byte")    if -32768 <= n <= 32767:        print("* short")    if -2147483648 <= n <= 2147483647:        print("* int")    if -9223372036854775808 <= n <= 9223372036854775807:        print("* long")    if n < -9223372036854775808 or n > 9223372036854775807:        print("can't be fitted anywhere.")
```

## **C. Input and Output (C++) – Python equivalent**

```
a, b, c = map(int, input().split())print(a + b + c)
```

## **D. Loops – Correct solution**

The HackerRank Loops challenge asks you to print the square of each integer from 0 to `n-1`.

```
n = int(input())for i in range(n):    print(i * i)
```

## **E. Functions (C++) – Max of Four Numbers**

```
def max_of_four(a, b, c, d):    return max(a, b, c, d)a, b, c, d = map(int, input().split())print(max_of_four(a, b, c, d))
```

## **F. Structs (C++) – Python equivalent**

```
age = int(input())first_name = input()last_name = input()standard = int(input())student = {    "age": age,    "first_name": first_name,    "last_name": last_name,    "standard": standard}print(student["age"])print(student["last_name"] + ",", student["first_name"])print(student["standard"])
```

