## Exercise 1.1
* 10
* 12
* 8
* 3
* 8
* a <- 3 but there is no response from the expression
* b <- 4 but there is no response from the expression
* #f
* 4
* 16
* 6
* 16

## Exercise 1.2
    ```scheme
    (/ (+ 5 4 (- 2 (- 3 (+ 6 (/ 4 5))))) (* 3 (- 6 2) (- 2 7))) ;-37/150
    ```

## Exercise 1.3
    ```scheme
    (define (sum-of-squares a b c)
      (cond
        ((and (> a b) (> b c)) (+ (* a a) (* b b) ))
        ((and (> a b) (> c b)) (+ (* a a) (* c c) ))
        (else (+ ( * b b) (* c c)))))

    ;tests

    (sum-of-squares 1 2 3) ; 13
    (sum-of-squares 3 1 2) ; 13
    (sum-of-squares 3 2 1) ; 13
    ```
