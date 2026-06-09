# Tugas Determinan & Invers Matriks

---

## Soal 1

Diketahui:

\[
A =
\begin{bmatrix}
-7 & -5 \\
1 & 4
\end{bmatrix}
\]

### Determinan

\[
\det(A) = (-7)(4) - (-5)(1)
\]

\[
= -28 + 5
\]

\[
= -23
\]

### Invers

\[
A^{-1}
=
\frac{1}{-23}
\begin{bmatrix}
4 & 5 \\
-1 & -7
\end{bmatrix}
\]

---

## Soal 2

Diketahui:

\[
A =
\begin{bmatrix}
0 & 2 & -3 \\
1 & -2 & -1 \\
0 & 0 & 1
\end{bmatrix}
\]

### Ekspansi Baris Pertama

\[
\det(A)
=
0\cdot M_{11}
-2\cdot M_{12}
+(-3)\cdot M_{13}
\]

#### Minor \(M_{11}\)

\[
M_{11}
=
\begin{vmatrix}
-2 & -1 \\
0 & 1
\end{vmatrix}
=
(-2)(1)-(-1)(0)
=
-2
\]

#### Minor \(M_{12}\)

\[
M_{12}
=
\begin{vmatrix}
1 & -1 \\
0 & 1
\end{vmatrix}
=
(1)(1)-(-1)(0)
=
1
\]

#### Minor \(M_{13}\)

\[
M_{13}
=
\begin{vmatrix}
1 & -2 \\
0 & 0
\end{vmatrix}
=
(1)(0)-(-2)(0)
=
0
\]

### Menghitung Determinan

\[
\det(A)
=
0-2(1)+(-3)(0)
\]

\[
=-2
\]

### Kesimpulan

\[
\det(A)\neq0
\]

Maka matriks **memiliki invers**.

---

## Soal 3

Diketahui:

\[
A =
\begin{bmatrix}
1 & -3 & 1 & 1 \\
-3 & 1 & 1 & 1 \\
1 & 1 & -3 & 1 \\
1 & 1 & 1 & -3
\end{bmatrix}
\]

### Determinan

\[
\det(A) = -128
\]

### Kesimpulan

Karena

\[
\det(A)\neq0
\]

maka matriks **memiliki invers**.

---

## Soal 4

Sama seperti Soal 1.

### Determinan

\[
\det(A)=-23
\]

---

## Soal 5

Sama seperti Soal 2.

### Determinan

\[
\det(A)=-2
\]

---

## Soal 6

Sama seperti Soal 3.

### Determinan

\[
\det(A)=-128
\]

---

## Ringkasan Hasil

| Soal | Determinan |
|------|------------|
| 1 | -23 |
| 2 | -2 |
| 3 | -128 |
| 4 | -23 |
| 5 | -2 |
| 6 | -128 |

### Kesimpulan Umum

Seluruh matriks pada soal memiliki determinan yang tidak sama dengan nol:

\[
\det(A)\neq0
\]

Sehingga seluruh matriks tersebut **invertible (memiliki invers)**.