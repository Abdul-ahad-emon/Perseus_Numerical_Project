<div align="center">

# Pseudocode – Romberg Integration Project
# Group - Perseus

</div>

---

## 1. Composite Trapezoidal Rule

Algorithm Composite_Trapezoidal(a, b, n)

```
1. h ← (b - a) / n
2. sum ← 0.5 × ( f(a) + f(b) )

3. For i = 1 to n - 1
       x ← a + i × h
       sum ← sum + f(x)
   End For

4. result ← sum × h
5. Return result

```

---
## 2. Romberg Integration

Algorithm Romberg(a, b, maxLevel)

```
1. Create 2D array R[maxLevel][maxLevel]

2. For k = 0 to maxLevel - 1
       n ← 2^k
       R[k][0] ← Composite_Trapezoidal(a, b, n)

3.     For j = 1 to k
           R[k][j] ← R[k][j - 1]
                      + ( R[k][j - 1] - R[k - 1][j - 1] ) / ( 4^j - 1 )
       End For
   End For

4. Return R

```
## 3. Simpson’s 1/3 Rule

Algorithm Simpson(a, b, n)

```
1. h ← (b - a) / n
2. sum ← f(a) + f(b)

3. For i = 1 to n - 1
       x ← a + i × h

4.     If i is even
           sum ← sum + 2 × f(x)
       Else
           sum ← sum + 4 × f(x)
       End If
   End For

5. result ← (sum × h) / 3
6. Return result

```

---


