# **_Structure and Interpretation of Computer Programs_**

## 1—Building Abstractions with Procedures

LISP:

- stands for LISt Processing
- second oldest language after Fortran
- the dialect used in this book is called Scheme

### 1.1—The Elements of Programming

Every powerful language has three mechanisms for combining simple ideas to form more complex ideas:

1. **primitive expressions**, which represent the simplest entities the language is concerned with,
2. **means of combination**, by which compound elements are built from simpler ones, and
3. **means of abstraction**, by which compound elements can be named and manipulated as units.

In this chapter we will deal only with simple numerical data so that we can focus on the rules for building procedures.

#### 1.1.1—Expressions

Examples of _combinations_:

```
(+ 21 35 12 7)
75
(- 1000 334)
666
(+ 2.7 10)
12.7
```

Nested expressions (which here are pretty-printed):

```
(+ (* 3
      (+ (* 2 4)
         (+ 3 5)))
   (+ (- 10 7)
      6))
```

#### 1.1.2—Naming and the Environment

`(define size 2)` causes the interpreter to associate the value 2 with the name `size`

The memory that keeps track of the name-object pairs is called the _environment_ (more precisely the _global environment_, since we will see later that a computation may involve a number of different environments)

#### 1.1.3—Evaluating Combinations

To evaluate a combination, do the following:

1. Evaluate the subexpressions of the combination.
2. Apply the procedure that is the value of the leftmost subexpression (the operator) to the arguments that are the values of the other subexpressions (the operands).

Thus, the evaluation rule is _recursive_ in nature.

Notice that the evaluation rule given above does not handle definitions. (That is, `(define x 3)` is not a combination.)

Such exceptions to the general evaluation rule are called _special forms_. Each special form has its own evaluation rule.

#### 1.1.4—Compound Procedures

_procedure definitions_ is a powerful abstraction technique by which a compound operation can be given a name and then referred to as a unit.

The general form of a procedure definition is `(define (<name> <formal parameters>) <body>)`

We can use procedures as building blocks in defining other procedures:

```
(define (square x) (* x x))

(define (sum-of-squares x y)
  (+ (square x) (square y)))

(define (f a)
  (sum-of-squares (+ a 1) (* a 2)))

```

Compound procedures are used in exactly the same way as primitive procedures.

#### 1.1.5—The Substitution Model for Procedure Application

- To apply a compound procedure to arguments, evaluate the body of the procedure with each formal parater replaced by the corresponding argument.

```
(f 5)
(sum-of-squares (+ a 1) (* a 2))
<!-- Then we replace the formal parameter a by the argument 5: -->
(sum-of-squares (+ 5 1) (* 5 2))
(+ (square 6) (square 10))
(+ (* 6 6) (* 10 10))
(+ 36 100)
136
```

This process is called the _substitution model_ for procedure application.

- The purpose of the substitution is to help us think about procedure application, not to provide a description of how the interpreter really works.

An alternative evaluation model would not evaluate the operands until their values were needed.

This alternative is known as _normal-order evaluation_, in contrast to the "evaluate the arguments and then apply" method that the interpreter actually uses, which is called _applicative-order evaluation_.

#### 1.1.6—Conditional Expressions and Predicates

#### 1.1.7—Example: Square Roots by Newton's Method

#### 1.1.8—Procedures as Black-Box Abstractions

### 1.2—Procedures and the Processes They Generate

### 1.3—Formulating Abstractions with Higher-Order Procedures
