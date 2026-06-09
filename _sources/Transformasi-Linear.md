# CHAPTER 6 - TRANSFORMASI LINIER

## Pengertian Transformasi Linier

Transformasi linier adalah fungsi yang memetakan suatu ruang vektor ke ruang vektor lain.

Ditulis:

```text
T : V → W
```

Keterangan:
- V = domain
- W = codomain
- T = fungsi transformasi

Transformasi linier mempertahankan:
1. Penjumlahan vektor
2. Perkalian skalar

---

# Syarat Transformasi Linier

Suatu fungsi T disebut transformasi linier jika memenuhi:

## 1. Penjumlahan Vektor

```text
T(u + v) = T(u) + T(v)
```

## 2. Perkalian Skalar

```text
T(cu) = cT(u)
```

Keterangan:
- u dan v = vektor
- c = skalar

Jika salah satu syarat tidak terpenuhi maka bukan transformasi linier.

---

# Contoh Transformasi Linier

Misal:

```text
T(x, y) = (2x, 3y)
```

## Uji Penjumlahan

```text
T((x1,y1) + (x2,y2))
= T(x1+x2, y1+y2)

= (2(x1+x2), 3(y1+y2))

= (2x1+2x2, 3y1+3y2)

= T(x1,y1) + T(x2,y2)
```

Memenuhi.

---

## Uji Perkalian Skalar

```text
T(c(x,y))
= T(cx, cy)

= (2cx, 3cy)

= c(2x,3y)

= cT(x,y)
```

Memenuhi.

Jadi T adalah transformasi linier.

---

# Fungsi Yang Bukan Transformasi Linier

Contoh:

```text
T(x,y) = (x+1, y)
```

Bukan transformasi linier karena terdapat konstanta +1.

Karena:

```text
T(0,0) ≠ (0,0)
```

---

# Transformasi Nol

Transformasi nol memetakan semua vektor menjadi nol.

```text
T(v) = 0
```

Contoh:

```text
T(x,y) = (0,0)
```

---

# Transformasi Identitas

Transformasi identitas tidak mengubah vektor.

```text
T(v) = v
```

Contoh:

```text
T(x,y) = (x,y)
```

Matriks identitas:

```text
|1 0|
|0 1|
```

---

# Sifat-Sifat Transformasi Linier

Jika T transformasi linier maka:

```text
1. T(0) = 0
2. T(u - v) = T(u) - T(v)
3. T(cu + dv) = cT(u) + dT(v)
```

---

# Transformasi Linier Dengan Matriks

Transformasi linier dapat dinyatakan dengan matriks.

Jika:

```text
A = matriks m × n
```

Maka:

```text
T(x) = Ax
```

Transformasi:

```text
Rn → Rm
```

---

# Contoh Matriks Transformasi

Misal:

```text
A =
|2 1|
|0 3|
```

dan:

```text
x =
|x|
|y|
```

Maka:

```text
T(x,y) =
|2x + y|
|3y|
```

---

# Rotasi Bidang pada R2

Rotasi digunakan untuk memutar vektor pada bidang.

## Matriks Rotasi

Rotasi berlawanan arah jarum jam sebesar θ:

```text
| cos θ   -sin θ |
| sin θ    cos θ |
```

---

# Contoh Rotasi 90 Derajat

```text
|0 -1|
|1  0|
```

Digunakan untuk memutar titik 90°.

---

# Refleksi

Refleksi adalah pencerminan terhadap:
- sumbu x
- sumbu y

## Refleksi terhadap sumbu x

```text
|1  0|
|0 -1|
```

## Refleksi terhadap sumbu y

```text
|-1 0|
| 0 1|
```

---

# Dilatasi

Dilatasi adalah transformasi memperbesar atau memperkecil objek.

```text
|k 0|
|0 k|
```

Keterangan:
- k > 1 → diperbesar
- 0 < k < 1 → diperkecil

---

# Shear (Geser)

## Shear pada sumbu x

```text
|1 k|
|0 1|
```

## Shear pada sumbu y

```text
|1 0|
|k 1|
```

---

# Proyeksi dalam R3

Proyeksi adalah transformasi yang memetakan vektor ke bidang tertentu.

Contoh:
- Proyeksi ke sumbu x
- Proyeksi ke bidang xy

---

# Matriks Standar

Matriks standar diperoleh dari:

```text
A = [T(e1) T(e2)]
```

Keterangan:
- e1 = (1,0)
- e2 = (0,1)

---

# Gabungan Transformasi

Gabungan transformasi dilakukan dengan perkalian matriks.

Contoh:

```text
T = T2 × T1
```

---

# Invers Transformasi Linier

Jika transformasi dapat dibalik maka memiliki invers.

Ditulis:

```text
T⁻¹
```

Sifat:

```text
T⁻¹(T(v)) = v
```

---

# Syarat Matriks Memiliki Invers

Determinan tidak boleh nol.

```text
det(A) ≠ 0
```

---

# Invers Matriks 2x2

Jika:

```text
A =
|a b|
|c d|
```

Maka:

```text
A⁻¹ = 1/(ad-bc)
| d -b|
|-c  a|
```

---

# Keuntungan Representasi Matriks

1. Mudah ditulis
2. Mudah dibaca
3. Mudah dihitung
4. Praktis untuk komputer

---

# Penerapan Transformasi Linier

Digunakan pada:
- Grafika komputer
- Animasi
- Game
- Robotika
- AI
- Machine Learning
- Pengolahan citra
- Teknik
- Fisika

---

# Kesimpulan

Transformasi linier adalah fungsi matematika yang:
- Memetakan ruang vektor
- Mempertahankan operasi aljabar
- Direpresentasikan menggunakan matriks

Jenis transformasi:
1. Rotasi
2. Refleksi
3. Dilatasi
4. Proyeksi
5. Shear

Transformasi linier sangat penting dalam matematika dan teknologi modern.