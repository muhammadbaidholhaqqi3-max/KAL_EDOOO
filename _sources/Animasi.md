# ANIMASI TRANSFORMASI MATRIX – KONSEP CERMIN (REFLEKSI)

## Refleksi terhadap Sumbu Y

Transformasi refleksi terhadap sumbu Y mengubah setiap titik:

\[
(x,y)\rightarrow(-x,y)
\]

---

# 1. Konsep Transformasi Matrix Refleksi

Refleksi terhadap sumbu Y menggunakan matriks transformasi:

\[
R=
\begin{bmatrix}
-1 & 0\\
0 & 1
\end{bmatrix}
\]

Jika terdapat titik:

\[
P=(x,y)
\]

maka hasil refleksinya adalah:

\[
P'=(-x,y)
\]

atau dapat ditulis:

\[
P'=RP
\]

---

# 2. Cara Kerja Animasi

Animasi memperlihatkan perpindahan titik dari posisi awal menuju posisi hasil refleksi.

Tahapan animasi:

1. Titik asli bergerak menuju hasil refleksi.
2. Digunakan interpolasi linear untuk menghasilkan gerakan yang halus.
3. Nilai parameter \(t\) berubah dari:

\[
0 \rightarrow 1 \rightarrow 0
\]

Rumus interpolasi:

\[
P(t)=P_{awal}+(P_{tujuan}-P_{awal})\times t
\]

Keterangan:

- \(P_{awal}\) = posisi titik sebelum refleksi
- \(P_{tujuan}\) = posisi titik hasil refleksi
- \(t\) = parameter animasi

---

# 3. Contoh Perhitungan

Misalkan titik:

\[
A=(2,3)
\]

Ditulis dalam bentuk vektor:

\[
P=
\begin{bmatrix}
2\\
3
\end{bmatrix}
\]

Matriks refleksi:

\[
R=
\begin{bmatrix}
-1 & 0\\
0 & 1
\end{bmatrix}
\]

Maka:

\[
P'
=
R \cdot P
=
\begin{bmatrix}
-1 & 0\\
0 & 1
\end{bmatrix}
\begin{bmatrix}
2\\
3
\end{bmatrix}
\]

\[
=
\begin{bmatrix}
-2\\
3
\end{bmatrix}
\]

Jadi hasil refleksi titik \(A(2,3)\) terhadap sumbu Y adalah:

\[
A'=(-2,3)
\]

---

# 4. Keterangan Warna Animasi

- **Biru** = Titik asli
- **Merah** = Hasil refleksi
- **Grid** = Membantu membaca koordinat pada bidang kartesius

---

# Kesimpulan

Refleksi terhadap sumbu Y merupakan transformasi matriks yang mengubah tanda koordinat \(x\) dan mempertahankan koordinat \(y\).

\[
(x,y)\rightarrow(-x,y)
\]

Transformasi ini dapat dituliskan dalam bentuk matriks:

\[
\begin{bmatrix}
-1 & 0\\
0 & 1
\end{bmatrix}
\]

Animasi menunjukkan proses perpindahan titik dari posisi awal menuju posisi hasil refleksi menggunakan interpolasi linear sehingga perubahan posisi dapat diamati secara visual.