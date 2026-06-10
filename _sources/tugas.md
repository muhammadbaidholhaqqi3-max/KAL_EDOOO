# Tugas
---
## **A. Perhitungan Determinan (Ekspansi Baris)**

Rumus Umum: $det(A) = \sum_{k=1}^{n} (-1)^{i+k} a_{ik} M_{ik}$

### **1. Matriks 2x2**
$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$

*   **Langkah (Ekspansi Baris 1):**
    $det(A) = (-7 \times 4) - (-5 \times 1)$
    $det(A) = -28 - (-5)$
    $det(A) = -28 + 5$
*   **Hasil:** **-23**

### **2. Matriks 3x3**
$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$

*   **Langkah (Ekspansi Baris 3 - Paling Mudah karena banyak nol):**
    $det(A) = a_{31}C_{31} + a_{32}C_{32} + a_{33}C_{33}$
    $det(A) = 0 + 0 + (1) \times (-1)^{3+3} \begin{vmatrix} 0 & 2 \\ 1 & -2 \end{vmatrix}$
    $det(A) = 1 \times (0 - 2)$
*   **Hasil:** **-2**

### **3. Matriks 4x4**
$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$

*   **Langkah:** Menggunakan operasi baris (OBE) untuk membuat nol atau ekspansi kofaktor secara bertahap.
*   **Hasil Akhir:** **-128**

---

## **B. Perhitungan Invers (Matriks Adjoin)**

Rumus: $A^{-1} = \frac{1}{det(A)} adj(A)$

### **4. Invers Matriks 2x2**
$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$, $det(A) = -23$

*   **Adjoin A:** Tukar elemen diagonal utama, kali negatif diagonal samping.
    $adj(A) = \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$
*   **Invers:**
    $A^{-1} = \frac{1}{-23} \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$
*   **Hasil:** **$\begin{bmatrix} -4/23 & -5/23 \\ 1/23 & 7/23 \end{bmatrix}$**

### **5. Invers Matriks 3x3**
$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$, $det(A) = -2$

*   **Matriks Kofaktor:**
    $C_{11} = -2, C_{12} = -1, C_{13} = 0$
    $C_{21} = -2, C_{22} = 0, C_{23} = 0$
    $C_{31} = -8, C_{32} = -3, C_{33} = -2$
*   **Adjoin A (Transpose Kofaktor):**
    $adj(A) = \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix}$
*   **Hasil ($A^{-1} = adj(A) / -2$):**
    **$\begin{bmatrix} 1 & 1 & 4 \\ 0.5 & 0 & 1.5 \\ 0 & 0 & 1 \end{bmatrix}$**

### **6. Invers Matriks 4x4**
$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$, $det(A) = -128$

*   **Hasil Akhir:**
    **$A^{-1} = \begin{bmatrix} -3/8 & -1/8 & -1/8 & -1/8 \\ -1/8 & -3/8 & -1/8 & -1/8 \\ -1/8 & -1/8 & -3/8 & -1/8 \\ -1/8 & -1/8 & -1/8 & -3/8 \end{bmatrix}$**
    *(Atau $-1/8 \times$ matriks yang elemen diagonalnya 3 dan sisanya 1)*

---

# Tugas Operasi Baris Elementer (OBE)

## **A. Perhitungan Matriks dengan Coding Python**

Berikut adalah implementasi kode Python menggunakan library NumPy untuk menyelesaikan soal-soal matriks yang telah dibahas.

### **1. Penyelesaian Soal 1**
**Persamaan:**
$ \begin{cases} x + 2y + z = 9 \\ 2x + 3y + 4z = 20 \\ 3x + y + 3z = 13 \end{cases} $
```python
import numpy as np

# Membuat matriks augmented
A = np.array([
    [1, 2, 1, 9],
    [2, 3, 4, 20],
    [3, 1, 3, 13]
], dtype=float)

n = len(A)

# Proses Eliminasi Gauss
for i in range(n):
    if A[i][i] != 0:
        A[i] = A[i] / A[i][i]
    for j in range(i+1, n):
        A[j] = A[j] - A[j][i] * A[i]

# Substitusi Mundur
x = np.zeros(n)
for i in range(n-1, -1, -1):
    x[i] = A[i][-1] - np.dot(A[i, i+1:n], x[i+1:n])

print("Solusi Soal 1:")
for i in range(n):
    print(f"x{i+1} = {x[i]}")
```
---

### **Soal 2: Sistem Persamaan Linear**
Selesaikan sistem berikut menggunakan metode Eliminasi Gauss:
$$ \begin{cases} 2x - y + 3z = 7 \\ 4x + 2y - z = 1 \\ -2x + y + 2z = 4 \end{cases} $$

#### **Penyelesaian Secara Markdown (Langkah Detail)**
1. **Matriks Augmented:**
   $$\left( \begin{array}{ccc|c} 2 & -1 & 3 & 7 \\ 4 & 2 & -1 & 1 \\ -2 & 1 & 2 & 4 \end{array} \right)$$
2. **Hasil OBE (Eselon Baris):**
   $$\left( \begin{array}{ccc|c} 1 & -0.5 & 1.5 & 3.5 \\ 0 & 1 & -1.75 & -3.25 \\ 0 & 0 & 1 & 2.2 \end{array} \right)$$
3. **Solusi Akhir:**
   * $x = 0.5$
   * $y = 0.6$
   * $z = 2.2$

```python
import numpy as np

# Matriks augmented untuk Soal 2
A = np.array([
    [2, -1, 3, 7],
    [4, 2, -1, 1],
    [-2, 1, 2, 4]
], dtype=float)

n = len(A)

# Eliminasi Gauss (OBE)
for i in range(n):
    # Normalisasi pivot menjadi 1
    if A[i][i] != 0:
        A[i] = A[i] / A[i][i]
        
    # Eliminasi elemen di bawah pivot
    for j in range(i+1, n):
        A[j] = A[j] - A[j][i] * A[i]

# Substitusi Mundur
x = np.zeros(n)
for i in range(n-1, -1, -1):
    x[i] = A[i][-1] - np.dot(A[i, i+1:n], x[i+1:n])

print("Solusi Soal 2:")
print("x =", x[0])
print("y =", x[1])
print("z =", x[2])
```
---

### **Soal PPT: Latihan Implementasi**
Selesaikan sistem persamaan linear berikut menggunakan metode Eliminasi Gauss:
$$ \begin{cases} 8x_1 + x_2 + x_3 = 19 \\ x_1 + 2x_2 + 3x_3 = 9 \\ 2x_1 + x_2 - x_3 = 5 \end{cases} $$

#### **1. Bentuk Matriks Augmented**
Berdasarkan koefisien dari persamaan di atas, kita peroleh matriks berikut:
$$\left( \begin{array}{ccc|c} 8 & 1 & 1 & 19 \\ 1 & 2 & 3 & 9 \\ 2 & 1 & -1 & 5 \end{array} \right)$$

#### **2. Proses Eliminasi Gauss (Python)**
Kode berikut melakukan normalisasi pivot menjadi 1 dan mengeliminasi elemen di bawahnya untuk mendapatkan bentuk eselon baris:
```python
import numpy as np

# Matriks augmented Soal PPT
A = np.array([
    [8, 1, 1, 19],
    [1, 2, 3, 9],
    [2, 1, -1, 5]
], dtype=float)

n = len(A)

# Eliminasi Gauss
for i in range(n):
    # Normalisasi pivot ke 1
    if A[i][i] != 0:
        A[i] = A[i] / A[i][i]
    
    # Eliminasi baris di bawahnya
    for j in range(i+1, n):
        A[j] = A[j] - A[j][i] * A[i]

# Menampilkan matriks setelah eliminasi
print("Matriks Eselon Baris:")
print(A)

# Substitusi Mundur
x = np.zeros(n)
for i in range(n-1, -1, -1):
    x[i] = A[i][-1] - np.dot(A[i, i+1:n], x[i+1:n])

print("\nSolusi Akhir:")
print(f"x1 = {x[0]}")
print(f"x2 = {x[1]}")
print(f"x3 = {x[2]}")
```
---

# Matrix Transformasi

## **A.Implementasi menggunakan GeoGebra**
<iframe src="https://www.geogebra.org/calculator/ykfwhnys?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

### Penjelasan Logika Matriks Transformasi (Translasi)

#### 1. Rumus Dasar Translasi
Untuk memindahkan titik awal $(x, y)$ ke titik baru $(x', y')$, kita menggunakan vektor atau matriks translasi $T = \begin{bmatrix} a \\ b \end{bmatrix}$. Hubungannya adalah:

$$x' = x + a$$
$$y' = y + b$$

Untuk mencari nilai matriks $T$, rumusnya dibalik: **$T = \text{Tujuan} - \text{Awal}$**.

#### 2. Analisis Kasus Per Kasus
Berdasarkan koordinat yang diinput di GeoGebra:

*   **A ke B:**
    *   Titik $A = (2, 3)$, Titik $B = (2, 1)$.
    *   Sumbu $x$: $2 - 2 = 0$.
    *   Sumbu $y$: $1 - 3 = -2$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 0 \\ -2 \end{bmatrix}$.
*   **B ke C:**
    *   Titik $B = (2, 1)$, Titik $C = (4, 1)$.
    *   Sumbu $x$: $4 - 2 = 2$.
    *   Sumbu $y$: $1 - 1 = 0$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 2 \\ 0 \end{bmatrix}$.
*   **D ke E:**
    *   Titik $D = (2, 4)$, Titik $E = (2, 0)$.
    *   Sumbu $x$: $2 - 2 = 0$.
    *   Sumbu $y$: $0 - 4 = -4$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 0 \\ -4 \end{bmatrix}$.
*   **E ke F:**
    *   Titik $E = (2, 0)$, Titik $F = (4, 0)$.
    *   Sumbu $x$: $4 - 2 = 2$.
    *   Sumbu $y$: $0 - 0 = 0$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 2 \\ 0 \end{bmatrix}$.

#### 3. Mekanisme di GeoGebra
Saat mengetik perintah `Translate(A, (0, -2))`, GeoGebra melakukan operasi berikut:
1.  Koordinat $x$ dari $A$ ($2$) ditambah $0 = 2$.
2.  Koordinat $y$ dari $A$ ($3$) ditambah $-2 = 1$.
Hasilnya muncul titik baru di **$(2, 1)$**, tepat di posisi titik **B**.

---

## **B.Implementasi Menggunakan Python**

```python
import numpy as np

# Definisi koordinat titik sesuai gambar
points = {
    'A': np.array([2, 3]),
    'B': np.array([2, 1]),
    'C': np.array([4, 1]),
    'D': np.array([2, 4]),
    'E': np.array([2, 0]),
    'F': np.array([4, 0])
}

# Fungsi untuk menghitung matriks translasi
def hitung_translasi(awal, tujuan, nama):
    matriks = points[tujuan] - points[awal]
    print(f"Matriks Transformasi {nama} ({awal} ke {tujuan}):")
    print(f"T = {matriks}\n")

# Jalankan tugasnya
hitung_translasi('A', 'B', 'T1')
hitung_translasi('B', 'C', 'T2')
hitung_translasi('D', 'E', 'T3')
hitung_translasi('E', 'F', 'T4')
```
---

## **C.Animasi Transformasi Refleksi terhadap Sumbu Y**

### Code Program

```python
from IPython.display import HTML
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

# Titik awal
points = {
    "A": (2, 3),
    "B": (2, 4),
    "C": (3, 4),
    "D": (3, 3),
    "I": (2, 2),
    "J": (3, 2),
    "K": (2, 1),
    "L": (3, 1),
    "M": (2, -1),
    "N": (3, -1),
    "O": (2, -2),
    "P": (3, -2),
    "E": (2, -3),
    "F": (3, -3),
    "G": (2, -4),
    "H": (3, -4)
}

# Membuat figure
fig, ax = plt.subplots(figsize=(8,8))

# Menyimpan objek titik
titik_asli = {}
titik_cermin = {}

# Membuat titik asli dan titik cermin
for nama, (x, y) in points.items():

    # Titik asli
    p1 = ax.plot(x, y, 'bo', markersize=8)[0]
    t1 = ax.text(x + 0.1, y + 0.1, nama)

    # Titik hasil cermin
    p2 = ax.plot(-x, y, 'ro', markersize=8)[0]
    t2 = ax.text(-x + 0.1, y + 0.1, nama + "'")

    titik_asli[nama] = (p1, t1)
    titik_cermin[nama] = (p2, t2)

# Tampilan grafik
ax.set_xlim(-5, 5)
ax.set_ylim(-5, 5)

ax.axhline(0, color='black')
ax.axvline(0, color='black')

ax.grid(True)

# Fungsi animasi
def animate(frame):

    # Gerak maju lalu kembali
    if frame <= 100:
        t = frame / 100
    else:
        t = (200 - frame) / 100

    for nama, (x, y) in points.items():

        # Posisi bertukar
        x_asli = x + (-x - x) * t
        x_cermin = -x + (x + x) * t

        # Update titik asli
        titik_asli[nama][0].set_data([x_asli], [y])
        titik_asli[nama][1].set_position((x_asli + 0.1, y + 0.1))

        # Update titik cermin
        titik_cermin[nama][0].set_data([x_cermin], [y])
        titik_cermin[nama][1].set_position((x_cermin + 0.1, y + 0.1))

# Membuat animasi
animasi = FuncAnimation(
    fig,
    animate,
    frames=201,
    interval=40,
    repeat=True
)

# Judul
plt.title("Animasi Transformasi Cermin Bertukar Tempat")

# Simpan GIF
animasi.save("animasi.gif", writer="pillow")

# Tampilkan animasi
plt.show()
```

### Hasil Output
### Animasi
![Animasi](animasi.gif)

---

# Tugas Dekomposisi Matrix QR (Metode Gram-Schmidt)

Matriks awal A yang diberikan adalah:
$$
A = \begin{bmatrix} 
3 & 7 & 1 & 9 \\ 
0 & 5 & 8 & 2 \\ 
4 & 6 & 3 & 7 \\ 
8 & 1 & 5 & 4 
\end{bmatrix}
$$

Kita definisikan kolom-kolom matriks A sebagai vektor basis awal:
$$
a_1 = \begin{bmatrix} 3 \\ 0 \\ 4 \\ 8 \end{bmatrix}, \quad 
a_2 = \begin{bmatrix} 7 \\ 5 \\ 6 \\ 1 \end{bmatrix}, \quad 
a_3 = \begin{bmatrix} 1 \\ 8 \\ 3 \\ 5 \end{bmatrix}, \quad 
a_4 = \begin{bmatrix} 9 \\ 2 \\ 7 \\ 4 \end{bmatrix}
$$

---

## **Langkah 1: Menghitung $v_1$ dan $q_1$**

Vektor basis pertama diambil langsung dari $a_1$:
$$
v_1 = a_1 = \begin{bmatrix} 3 \\ 0 \\ 4 \\ 8 \end{bmatrix}
$$

Menghitung panjang (norm) dari $v_1$:
$$
|v_1| = \sqrt{3^2 + 0^2 + 4^2 + 8^2} = \sqrt{9 + 0 + 16 + 64} = \sqrt{89} \approx 9.4340
$$

Normalisasi vektor $v_1$ untuk mendapatkan $q_1$:
$$
q_1 = \frac{v_1}{|v_1|} = \frac{1}{\sqrt{89}} \begin{bmatrix} 3 \\ 0 \\ 4 \\ 8 \end{bmatrix} \approx \begin{bmatrix} 0.3180 \\ 0.0000 \\ 0.4240 \\ 0.8480 \end{bmatrix}
$$

---

## **Langkah 2: Menghitung $v_2$ dan $q_2$**

Formulasi proyeksi sesuai di papan tulis:
$$
v_2 = a_2 - (a_2 \cdot q_1)q_1
$$

Hitung nilai *dot product* $a_2 \cdot q_1$:
$$
a_2 \cdot q_1 = 7(0.3180) + 5(0) + 6(0.4240) + 1(0.8480) = \frac{21 + 0 + 24 + 8}{\sqrt{89}} = \frac{53}{\sqrt{89}} \approx 5.6180
$$

Maka komponen vektor projeksinya:
$$
(a_2 \cdot q_1)q_1 = \frac{53}{89} \begin{bmatrix} 3 \\ 0 \\ 4 \\ 8 \end{bmatrix} \approx \begin{bmatrix} 1.7865 \\ 0.0000 \\ 2.3820 \\ 4.7640 \end{bmatrix}
$$

Hitung vektor ortogonal $v_2$:
$$
v_2 = \begin{bmatrix} 7 \\ 5 \\ 6 \\ 1 \end{bmatrix} - \begin{bmatrix} 1.7865 \\ 0.0000 \\ 2.3820 \\ 4.7640 \end{bmatrix} = \begin{bmatrix} 5.2135 \\ 5.0000 \\ 3.6180 \\ -3.7640 \end{bmatrix}
$$

Menghitung panjang (norm) dari $v_2$:
$$
|v_2| \approx \sqrt{5.2135^2 + 5.0000^2 + 3.6180^2 + (-3.7640)^2} \approx \sqrt{79.4382} \approx 8.9128
$$

Normalisasi vektor $v_2$ untuk mendapatkan $q_2$:
$$
q_2 = \frac{v_2}{|v_2|} \approx \begin{bmatrix} 0.5849 \\ 0.5610 \\ 0.4059 \\ -0.4223 \end{bmatrix}
$$

---

## **Langkah 3: Menghitung $v_3$ dan $q_3$**

Formulasi proyeksi sesuai di papan tulis:
$$
v_3 = a_3 - \sum_{i=1}^{2}(a_3 \cdot q_i)q_i = a_3 - \left[ (a_3 \cdot q_1)q_1 + (a_3 \cdot q_2)q_2 \right]
$$

Hitung nilai *dot product*:
- $a_3 \cdot q_1 = 1(0.3180) + 8(0) + 3(0.4240) + 5(0.8480) \approx 5.8300$
- $a_3 \cdot q_2 = 1(0.5849) + 8(0.5610) + 3(0.4059) + 5(-0.4223) \approx 4.1791$

Hitung vektor ortogonal $v_3$:
$$
v_3 = \begin{bmatrix} 1 \\ 8 \\ 3 \\ 5 \end{bmatrix} - 5.8300 \begin{bmatrix} 0.3180 \\ 0.0000 \\ 0.4240 \\ 0.8480 \end{bmatrix} - 4.1791 \begin{bmatrix} 0.5849 \\ 0.5610 \\ 0.4059 \\ -0.4223 \end{bmatrix} = \begin{bmatrix} -3.2984 \\ 5.6556 \\ -1.1683 \\ 1.8211 \end{bmatrix}
$$

Menghitung panjang (norm) dari $v_3$:
$$
|v_3| \approx \sqrt{(-3.2984)^2 + 5.6556^2 + (-1.1683)^2 + 1.8211^2} \approx \sqrt{47.5467} \approx 6.8954
$$

Normalisasi vektor $v_3$ untuk mendapatkan $q_3$:
$$
q_3 = \frac{v_3}{|v_3|} \approx \begin{bmatrix} -0.4784 \\ 0.8202 \\ -0.1694 \\ 0.2641 \end{bmatrix}
$$

---

## **Langkah 4: Menghitung $v_4$ dan $q_4$**

Formulasi proyeksi sesuai di papan tulis:
$$
v_4 = a_4 - \sum_{i=1}^{3}(a_4 \cdot q_i)q_i = a_4 - \left[ (a_4 \cdot q_1)q_1 + (a_4 \cdot q_2)q_2 + (a_4 \cdot q_3)q_3 \right]
$$

Hitung nilai *dot product*:
- $a_4 \cdot q_1 = 9(0.3180) + 2(0) + 7(0.4240) + 4(0.8480) \approx 9.2220$
- $a_4 \cdot q_2 = 9(0.5849) + 2(0.5610) + 7(0.4059) + 4(-0.4223) \approx 7.5387$
- $a_4 \cdot q_3 = 9(-0.4784) + 2(0.8202) + 7(-0.1694) + 4(0.2641) \approx -2.7944$

Hitung vektor ortogonal $v_4$:
$$
v_4 = \begin{bmatrix} 9 \\ 2 \\ 7 \\ 4 \end{bmatrix} - 9.2220 \begin{bmatrix} 0.3180 \\ 0.0000 \\ 0.4240 \\ 0.8480 \end{bmatrix} - 7.5387 \begin{bmatrix} 0.5849 \\ 0.5610 \\ 0.4059 \\ -0.4223 \end{bmatrix} - (-2.7944) \begin{bmatrix} -0.4784 \\ 0.8202 \\ -0.1694 \\ 0.2641 \end{bmatrix} = \begin{bmatrix} 0.3210 \\ 0.0628 \\ -0.4438 \\ 0.1015 \end{bmatrix}
$$

Menghitung panjang (norm) dari $v_4$:
$$
|v_4| \approx \sqrt{0.3210^2 + 0.0628^2 + (-0.4438)^2 + 0.1015^2} \approx \sqrt{0.3142} \approx 0.5605
$$

Normalisasi vektor $v_4$ untuk mendapatkan $q_4$:
$$
q_4 = \frac{v_4}{|v_4|} \approx \begin{bmatrix} 0.5726 \\ 0.1121 \\ -0.7917 \\ 0.1811 \end{bmatrix}
$$

---

## **Hasil Akhir Matriks $Q$ dan Matriks $R$**

Berdasarkan struktur matriks komponen $R$ segitiga atas yang dituliskan pada papan tulis:

### Matriks $Q$ (Vektor Kolom Berupa Ortonormal $q_1, q_2, q_3, q_4$)
$$
Q = \begin{bmatrix}
0.3180 & 0.5849 & -0.4784 & 0.5726 \\
0.0000 & 0.5610 & 0.8202 & 0.1121 \\
0.4240 & 0.4059 & -0.1694 & -0.7917 \\
0.8480 & -0.4223 & 0.2641 & 0.1811
\end{bmatrix}
$$

### Matriks $R$ (Segitiga Atas dengan Elemen $R_{ij} = a_j \cdot q_i$)
$$
R = \begin{bmatrix}
a_1 \cdot q_1 & a_2 \cdot q_1 & a_3 \cdot q_1 & a_4 \cdot q_1 \\
0 & a_2 \cdot q_2 & a_3 \cdot q_2 & a_4 \cdot q_2 \\
0 & 0 & a_3 \cdot q_3 & a_4 \cdot q_3 \\
0 & 0 & 0 & a_4 \cdot q_4
\end{bmatrix}
$$

Jika dimasukkan nilai numeriknya:
$$
R = \begin{bmatrix}
9.4340 & 5.6180 & 5.8300 & 9.2220 \\
0.0000 & 8.9128 & 4.1791 & 7.5387 \\
0.0000 & 0.0000 & 6.8954 & -2.7944 \\
0.0000 & 0.0000 & 0.0000 & 0.5605
\end{bmatrix}
$$
