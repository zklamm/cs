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

#### 1.1.3—Evaluating Combinations

#### 1.1.4—Compound Procedures

#### 1.1.5—The Substitution Model for Procedure Application

#### 1.1.6—Conditional Expressions and Predicates

#### 1.1.7—Example: Square Roots by Newton's Method

#### 1.1.8—Procedures as Black-Box Abstractions

### 1.2—Procedures and the Processes They Generate

### 1.3—Formulating Abstractions with Higher-Order Procedures
