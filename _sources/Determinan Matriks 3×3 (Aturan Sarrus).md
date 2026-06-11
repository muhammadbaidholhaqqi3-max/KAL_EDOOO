# Determinan Matriks 3×3 (Aturan Sarrus)

## Matriks

Diketahui matriks:

$$
A=
\begin{bmatrix}
2 & -1 & 3\
1 & 0 & 2\
4 & 1 & -1
\end{bmatrix}
$$

Matriks tersebut memiliki:

* 3 baris
* 3 kolom

Ordo matriks:

$$
3 \times 3
$$

---

# Langkah 1: Salin Dua Kolom Pertama

Tuliskan matriks dan salin dua kolom pertama ke sebelah kanan.

$$
\begin{array}{ccc|cc}
2 & -1 & 3 & 2 & -1\
1 & 0 & 2 & 1 & 0\
4 & 1 & -1 & 4 & 1
\end{array}
$$

---

# Langkah 2: Hitung Diagonal Turun (↘)

## Diagonal 1

$$
(2)(0)(-1)
$$

$$
=0
$$

---

## Diagonal 2

$$
(-1)(2)(4)
$$

$$
=-8
$$

Karena:

$$
(-1)\times2=-2
$$

$$
-2\times4=-8
$$

---

## Diagonal 3

$$
(3)(1)(1)
$$

$$
=3
$$

---

## Jumlah Diagonal Turun

$$
0+(-8)+3
$$

$$
=-5
$$

Jadi:

$$
\boxed{\text{Diagonal Turun}=-5}
$$

---

# Langkah 3: Hitung Diagonal Naik (↗)

## Diagonal 1

$$
(4)(0)(3)
$$

$$
=0
$$

---

## Diagonal 2

$$
(1)(2)(2)
$$

$$
=4
$$

---

## Diagonal 3

$$
(-1)(1)(-1)
$$

$$
=1
$$

Karena:

$$
(-1)\times(-1)=1
$$

---

## Jumlah Diagonal Naik

$$
0+4+1
$$

$$
=5
$$

Jadi:

$$
\boxed{\text{Diagonal Naik}=5}
$$

---

# Langkah 4: Hitung Determinan

Rumus Sarrus:

$$
\det(A)
=======

## \text{Diagonal Turun}

\text{Diagonal Naik}
$$

Substitusikan hasil yang diperoleh:

$$
\det(A)
=======

(-5)-5
$$

# $$

-10
$$

---

# Hasil Akhir

$$
\boxed{\det(A)=-10}
$$

---

# Cara Cepat Mengingat

## Aturan Tanda Perkalian

| Operasi   | Hasil |
| --------- | ----- |
| (+) × (+) | +     |
| (-) × (-) | +     |
| (+) × (-) | -     |
| (-) × (+) | -     |

## Aturan Sarrus

1. Salin dua kolom pertama.
2. Jumlahkan tiga diagonal turun (↘).
3. Jumlahkan tiga diagonal naik (↗).
4. Determinan = diagonal turun − diagonal naik.

Rumus umum:

$$
\det(A)
=======

## (aei+bfg+cdh)

(ceg+bdi+afh)
$$
