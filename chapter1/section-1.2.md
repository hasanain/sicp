# Section 1.2

### Exercise 1.12

```scheme
(define (pascal r c)
  (cond ((< c 0) 0)
        ((> c r) 0)
        ((and (= c 0) (= r 0)) 1)
        (else (+ (pascal (- r 1) (- c 1)) (pascal (- r 1) c)))))
```



