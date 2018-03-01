## Exercise 1.1

* `10 -> 10`
* `(+ 5 3 4) -> 12`
* `(-9 1) -> 8`
* `(/ 6 2) -> 3`
* `(+ (* 2 4) (- 4 6))`
* `(define a 3) -> a <- 3 but there is no result from the expression`
* `(define b (+ a 1)) -> b <- 4 but there is no result from the expression`
* `(+ a b (* a b)) -> 19`
* `(= a b) -> #f`
* `(if (and (> b a) (< b (* a b))) b a) -> 4`
* `(cond ((= a 4) 6) ((= b 4) (+ 6 7 a)) (else 25)) -> 16`
* `(+ 2 (if (> b a) b a)) -> 6`
* `(* (cond ((> a b) a) ((< a b) b) (else -1)) (+ a 1)) -> 16`

## Exercise 1.2

```scheme
(/ 
  (+ 5 4 (- 2 (- 3 (+ 6 (/ 4 5))))) 
  (* 3 (- 6 2) (- 2 7))
) ;-37/150
```

## Exercise 1.3

```scheme
(define (sum-square-largest-two a b c)
  (cond
    ((or (and (>= a b) (>= b c))
        (and (>= b a) (>= a c)))
    (+ (* a a) (* b b)))
    ((and (>= a b)) (+ (* a a) (* c c) ))
    (else (+ ( * b b) (* c c)))))

; tests
(sum-square-largest-two 1 1 1) ; 2
(sum-square-largest-two 1 1 2) ; 5
(sum-square-largest-two 2 1 1) ; 5
(sum-square-largest-two 1 2 2) ; 8
(sum-square-largest-two 2 2 1) ; 8
(sum-square-largest-two 1 2 3) ; 13
(sum-square-largest-two 1 3 2) ; 13
(sum-square-largest-two 2 1 3) ; 13
(sum-square-largest-two 3 1 2) ; 13
(sum-square-largest-two 3 2 1) ; 13
(sum-square-largest-two 2 3 1) ; 13
```

## Exercise 1.4

```scheme
(define (a-plus-abs-b a b)
  ((if (> b 0) + -) a b))
```

The if expression will resolve to either `-` or `+` based on the value of `b` so if `b` is negative then the expression will look like `( - a b)` and if b is positive then the expression will look like `(+ a b)`

## Excercise 1.5

```scheme
(define (p) (p))

(define (test x y)
  (if (= x 0) 
    0
    y))

(test 0 (p))
```

**applicative order:** using applicative order the interpereter will evaluate both arguments to the procedure test before passing them to the procedure thus attempting to evaluate `(p)` before passing it. But since the value of `(p)` is `(p)` then the interpeter will get stuck in a loop trying to evaluate `(p)` and `(test 0 (p)`

**normal order:**  
using normal order the interpeter will pass the arguments first and evaluate them when needed. So the evaluation will look like this

```scheme
(test 0 (p)) -> (if (= 0 0) 0 (p)) -> 0
```



