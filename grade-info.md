# Grade Information

## Test 1: Compilation

No dead/leftover/unnecessary code should be highlighted here. [1 pts]

```
+ gcc -Wall -g -pthread -std=c99 mine.c -o mine
+ test_end
+ return=0
+ [Output Lines: 0]
+ [Time elapsed: 0.09394]
```

## Test 2: Invalid number of threads

```
+ timeout 5 ./mine 0 1 'this is a test'
+ test_end
+ return=124
+ [Output Lines: 0]
+ [Time elapsed: 5.02849]
```

## Test 3: Invalid difficulty I

```
+ timeout 5 ./mine 1 -5 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 11111111111111111111111111111111
Number of threads: 1

Solution found by thread 1:
Nonce: 0
Hash: F72EFCE3D41ED1615327D9FAE17E99C3AC866B62
100 hashes in 0.00s (934143.43 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 0.0192099]
```

## Test 4: Invalid difficulty II

```
+ timeout 5 ./mine 1 50 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000000000000000
Number of threads: 1
....+ test_end
+ return=124
+ [Output Lines: 4]
+ [Time elapsed: 5.02021]
```

## Test 5: Difficulty Calculation

```
+ timeout 5 ./mine 1 1 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 01111111111111111111111111111111
Number of threads: 1

Solution found by thread 1:
Nonce: 1
Hash: 6DE0956F29E6A2412F4CCA4C2CDDA38F640688BE
100 hashes in 0.00s (953250.91 hashes/sec)
+ timeout 5 ./mine 1 2 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00111111111111111111111111111111
Number of threads: 1

Solution found by thread 1:
Nonce: 9
Hash: 05041C0563085614A00F3E3BE2FD8E8DFC53FFE2
100 hashes in 0.00s (892405.11 hashes/sec)
+ timeout 5 ./mine 1 4 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00001111111111111111111111111111
Number of threads: 1

Solution found by thread 1:
Nonce: 9
Hash: 05041C0563085614A00F3E3BE2FD8E8DFC53FFE2
100 hashes in 0.00s (875637.58 hashes/sec)
+ timeout 5 ./mine 1 10 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000001111111111111111111111
Number of threads: 1

Solution found by thread 1:
Nonce: 365
Hash: 00232C20F5C1515D9941C6D064F6113AFC257B8A
400 hashes in 0.00s (776722.96 hashes/sec)
+ timeout 5 ./mine 1 17 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000111111111111111
Number of threads: 1

Solution found by thread 1:
Nonce: 94812
Hash: 000064550882C04EAB59A44C84E7B9D3861E8C92
94900 hashes in 0.11s (854862.68 hashes/sec)
+ timeout 5 ./mine 1 32 'this is a test'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000000000000000
Number of threads: 1
....+ test_end
+ return=124
+ [Output Lines: 44]
+ [Time elapsed: 5.1618]
```

## Test 6: Single thread run

With one thread, the number of hashes should (roughly) equal the nonce.

```
+ timeout 10 ./mine 1 21 'testing testing 1 2 3'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000011111111111
Number of threads: 1
.
Solution found by thread 1:
Nonce: 1702342
Hash: 000000B9810F2B8F5D0A34CBCD29574093B3E3F7
1702400 hashes in 2.01s (847455.12 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 2.02953]
```

## Test 7: Input String: testing testing 1 2 3

```
+ timeout 60 ./mine 8 24 'testing testing 1 2 3'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000000011111111
Number of threads: 8
.
Solution found by thread 5:
Nonce: 1702342
Hash: 000000B9810F2B8F5D0A34CBCD29574093B3E3F7
1851500 hashes in 1.52s (1214409.66 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 1.54553]
```

## Test 8: Input String: iewoijeoiwfjwiojpqwjj

```
+ timeout 5 ./mine 1 22 iewoijeoiwfjwiojpqwjj
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 1
...
Solution found by thread 1:
Nonce: 3168785
Hash: 0000016372746C5082E89AE5928F2240E6510B64
3168800 hashes in 3.73s (849455.40 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 3.75067]
```

## Test 9: Input String: what what what what what what what

```
+ timeout 5 ./mine 4 10 'what what what what what what what'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000001111111111111111111111
Number of threads: 4

Solution found by thread 1:
Nonce: 36
Hash: 001ACDB3672251A8B9DFB362969ECB0F9BCF2407
900 hashes in 0.00s (5843457.59 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 0.0193999]
```

## Test 10: Input String: hellooooooooooo world!

```
+ timeout 5 ./mine 8 3 'hellooooooooooo world!'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00011111111111111111111111111111
Number of threads: 8

Solution found by thread 6:
Nonce: 1
Hash: 07BDF4385CFCE9372851FD051CE9777C4C02E6F2
800 hashes in 0.00s (6156776.51 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 0.0194199]
```

## Test 11: Input String: long computation

```
+ timeout 5 ./mine 8 22 'long computation'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 8
...
Solution found by thread 6:
Nonce: 3074929
Hash: 00000225B93963B335FA91EF5F339A2ECA04AA53
3539000 hashes in 4.40s (804571.98 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 8]
+ [Time elapsed: 4.41965]
```

## Test 12: Baseline (single thread) vs four threads

```
+ timeout 10 ./mine 1 22 'Hello CS220!'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 1
.
Solution found by thread 1:
Nonce: 1079495
Hash: 000002FEE38B31856A2F75732B0297F98AC6FE6B
1079500 hashes in 1.22s (882513.28 hashes/sec)
+ timeout 10 ./mine 4 22 'Hello CS220!'
Mask now: 00000000000000000000000000000000
Difficulty Mask: 00000000000000000000001111111111
Number of threads: 4
.
Solution found by thread 3:
Nonce: 1079495
Hash: 000002FEE38B31856A2F75732B0297F98AC6FE6B
1085400 hashes in 0.32s (3407484.09 hashes/sec)
+ test_end
+ return=0
+ [Output Lines: 16]
+ [Time elapsed: 1.56906]
```


## Deductions

* Missing some function documentation [-1]
* Question 3, 4 [-2]
* (Test 2): Ran anyway [-1]
* (Test 4): Ran anyway [-1]

