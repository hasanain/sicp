# Section 1.2

### Exercise 1.9

```scheme
(define (+ a b)
  (if (= a 0) 
      b 
      (inc (+ (dec a) b))))
; using substitution model calculate (+ 4 5)
(+ 4 5)
(inc (+ (dec 4) 5))
(inc (+ 3 5))
(inc (inc (+ (dec 3) 5)))
(inc (inc (+ 2 5)))
(inc (inc (inc (+ (dec 2) 5))))
(inc (inc (inc (+ 1 5))))
(inc (inc (inc (inc (+ (dec 1) 5)))))
(inc (inc (inc (inc (+ 0 5)))))
(inc (inc (inc (inc 5))))
(inc (inc (inc 6)))
(inc (inc 7))
(inc 8)
9
```

The process above is a linear recursive process. There are more information about the state than can not be contained in the parameters.

```scheme
(define (+ a b)
  (if (= a 0) 
      b 
      (+ (dec a) (inc b))))
; using substitution model calculate (+ 4 5)
(+ 4 5)
(+ (dec 4) (inc 5))
(+ 3 6)
(+ (dec 3) (inc 6))
(+ 2 7)
(+ (dec 2) (inc 7))
(+ 1 8)
(+ (dec 1) (inc 8))
(+ 0 9)
9
```

This process is iterative. The only information we need to represent the state of the process is in the parameters.

### Exercise 1.12

```scheme
(define (pascal r c)
  (cond ((< c 0) 0)
        ((> c r) 0)
        ((and (= c 0) (= r 0)) 1)
        (else (+ (pascal (- r 1) (- c 1)) (pascal (- r 1) c)))))
```

