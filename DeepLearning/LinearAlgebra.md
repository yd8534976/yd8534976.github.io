## Singular Value Decomposition

### Eigendecomposition

- A = V diag(&lambda) V<sup>-1</sup>

### SVD

- A = U D V<sup>T</sup>

  - Suppose that **A** is an m*n matrix. Then **U** is defined to be an m*m martix, **D** to be an m*n matrix, and **V** to be an n*n matrix.

  - **U** and **V** are both defined to be orthogonal matrices. ( 直交矩阵 )

  - **D** is defined to be a diagonal matrix. it is not necessarily square.

  - The elements along the diagonal of D are known as the _singular values_ of the matrix A. The columns of U are known as the _left-singular vectors_. The columns of V are known as the _right-singhlar vectors_.

  - The left-singular vectors of A are the eigenvectors of AA<sup>T</sup>

  - The right-singular vectors of A are the eigenvectors of A<sup>T</sup>A

  - The non-zero singular values of A are the square roots of the eigenvalues of A<sup>T</sup>A.


## The Moore-Penrose Pseudoinverse (伪逆矩阵)

- Ax = y

- x = By

- A<sup>+</sup> = lim<sub>a</sub>(A<sup>T</sup>A + &alpha I)<sup>-1</sup>A<sup>T</sup>

- A<sup>+</sup> = VD<sup>+</sup>U<sup>T</sup>

- When A has more columns than rows, it provides the solution x = A<sup>+</sup>y with minimal Euclidean norm ||x|| among all possible solutions.

- When A has more rows than columns, it is possible for there to be no solution. In this case, using the pseudoinverse gives us the x for which Ax is as close as possible to y in terms of Euclidean norm ||Ax-y||.

