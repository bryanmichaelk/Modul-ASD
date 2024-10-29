## Daftar Isi

- [Analisis Algoritma](#analisis-algoritma)
  - [Pendahuluan](#pendahuluan-analisa-algoritma)
  - [Mengukur Efisiensi Algoritma](#mengukur-efisiensi-algoritma)
  - [Tingkat Pertumbuhan](#tingkat-pertumbuhan-dan-analisis-asimtotik)
  - [Tingkat Pertumbuhan yang Umum](#tingkat-pertumbuhan-yang-umum)
  - [Contoh Penggunaan Big-O](#contoh-penggunaan-big-o)
- [Sort](#sort)
  - [Selection Sort](#selection-sort)
  - [Bubble Sort](#bubble-sort)
  - [Insertion Sort](#insertion-sort)
  - [Kesimpulan](#kesimpulan)


---

## Analisis Algoritma

### **Pendahuluan Analisis Algoritma**

- **Definisi**: Algoritma adalah sekumpulan instruksi tepat dan terbatas untuk menyelesaikan masalah atau melakukan komputasi.
- **Tujuan Analisis Algoritma**: Untuk membandingkan algoritma terutama berdasarkan waktu eksekusi (running time), serta aspek lain seperti penggunaan memori dan kemudahan pengembangan.

### **Mengukur Efisiensi Algoritma**

- **Waktu Eksekusi**: Analisis berfokus pada bagaimana waktu eksekusi meningkat seiring dengan bertambahnya ukuran input (\( n \)).
- **Jumlah Eksekusi Pernyataan**: Daripada mengukur waktu di komputer yang spesifik, kita menghitung jumlah pernyataan yang dieksekusi, yang memberikan metrik lebih umum.

### **Tingkat Pertumbuhan dan Analisis Asimtotik**

- **Tingkat Pertumbuhan (Growth Rate)**: Term yang mendominasi dalam fungsi \( f(n) \) saat \( n \to \infty \) menentukan efisiensi algoritma, mengabaikan konstanta dan term berorde rendah.
- **Notasi Asimtotik**: Notasi ini digunakan untuk menggambarkan tingkat pertumbuhan fungsi dalam urutan pentingnya:
  - **Notasi Big-O \( O(g(n)) \)**: Menggambarkan batas atas pertumbuhan fungsi (asymptotic upper bound).
  - **Notasi Big-Omega \( \Omega(g(n)) \)**: Menggambarkan batas bawah (asymptotic lower bound).
  - **Notasi Big-Theta \( \Theta(g(n)) \)**: Menggambarkan pertumbuhan fungsi yang ketat (tight bound).

### **Tingkatan Pertumbuhan yang Umum**

<img src="/img/modul-6/grafik-bigOnotation.png">

- Contoh beberapa tingkat pertumbuhan umum:
  - **\( O(1) \)**: Konstan (contoh: akses elemen array tertentu).
  - **\( O(\log n) \)**: Logaritmik (contoh: binary search).
  - **\( O(n) \)**: Linear (contoh: pencarian linear di daftar tidak terurut).
  - **\( O(n \log n) \)**: Linear-logaritmik (contoh: algoritma pengurutan efisien seperti Merge Sort).
  - **\( O(n^2) \)**: Kuadrat (contoh: Bubble Sort, pengurutan yang tidak efisien).
  - **\( O(2^n) \)**: Eksponensial (contoh: pencarian kombinasi brute-force).
  - **\( O(n!) \)**: Faktorial (contoh: algoritma yang memeriksa semua kemungkinan, seperti brute-force pada masalah Travelling Salesman).
- **Perbandingan Contoh Algoritma**:
  - **Pencarian Linear**: Kompleksitas \( O(n) \), karena setiap elemen diperiksa satu per satu.
  - **Pencarian Biner**: Kompleksitas \( O(\log n) \), karena setiap langkah mengurangi setengah dari elemen yang tersisa untuk diperiksa.

### **Contoh Penggunaan Big-O**

- **Contoh Masalah**:
  - Linear search di antara \( n \) elemen: \( O(n) \).
  - Binary search pada daftar terurut dengan \( n \) elemen: \( O(\log n) \).

### Cara Menghitung Kompleksitas Algoritma

#### Langkah-Langkah Menghitung Big-O pada Algoritma:

1. **Identifikasi Pernyataan Utama**: Tentukan operasi utama dalam algoritma yang paling sering dieksekusi dan akan memberikan kompleksitas terbesar.
2. **Hitung Iterasi atau Eksekusi Pernyataan**:
   - Untuk setiap loop, perkirakan berapa kali pernyataan di dalamnya dieksekusi.
   - Misalnya, pada `for` loop tunggal yang berjalan dari \( i = 1 \) hingga \( i = n \), waktu eksekusi adalah \( O(n) \).
   - Jika ada nested loop (loop di dalam loop) yang berjalan \( n \) kali di kedua tingkat, kompleksitasnya menjadi \( O(n^2) \).
3. **Gabungkan Kompleksitas Berdasarkan Dominansi**:
   - Jika algoritma memiliki beberapa bagian dengan kompleksitas yang berbeda, maka pilih tingkat kompleksitas terbesar sebagai kompleksitas akhir.
   - Contoh: Jika terdapat dua loop, satu dengan \( O(n) \) dan satu lagi dengan \( O(n^2) \), maka kompleksitas akhir adalah \( O(n^2) \).
4. **Abaikan Konstanta dan Faktor Ordo Rendah**:
   - Konstanta atau faktor berorde rendah seperti \( n \) pada \( n^2 + n \) dapat diabaikan, sehingga kompleksitas menjadi \( O(n^2) \).

#### Contoh Perhitungan 1:

<img src="/img/modul-6/Contoh Perhitungan.jpg">

#### Contoh Perhitungan 2:

<img src="/img/modul-6/Contoh Perhitungan 2.jpg>

#### Contoh Kasus:

Misalkan algoritma berikut:

```python
sum = 0
for i in range(n):
    for j in range(n):
        sum += i + j
```

- **Langkah 1**: Identifikasi loop. Ada dua `for` loop yang nested.
- **Langkah 2**: Setiap loop berjalan dari 0 hingga \( n-1 \), sehingga setiap loop berjalan \( n \) kali.
- **Langkah 3**: Kombinasikan kompleksitas dari nested loop ini menjadi \( O(n) \times O(n) = O(n^2) \).
- **Langkah 4**: Tidak ada konstanta tambahan yang perlu diperhatikan, sehingga hasil akhir kompleksitasnya adalah \( O(n^2) \).

## Sort

### Selection Sort

<img src="/img/modul-6/selection-sort.jpg">

Selection Sort adalah algoritma sorting dengan kompleksitas waktu \( O(n) \), yang berarti kecepatan eksekusinya sebanding dengan ukuran data. Algoritma ini biasanya digunakan untuk penyortiran yang sederhana.

#### Code

```java
public class SelectionSort {
    public static int[] SelectionSort(int[] arr) {
        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[i] > arr[j]) {  // Jika elemen lebih besar ditemukan
                    int temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp; // Tukar elemen
                }
            }
        }
        return arr;
    }
}

```

#### Kompleksitas
- **Worst Case (Kasus Terburuk)**: \(O(n^2)\)
  - Terjadi ketika algoritma harus memeriksa seluruh elemen untuk setiap posisi yang perlu diurutkan. Ini adalah kasus yang umum untuk algoritma ini karena tidak memanfaatkan informasi tentang data yang sudah terurut.

- **Average Case (Kasus Rata-rata)**: \(O(n^2)\)
  - Seperti dalam kasus terburuk, algoritma harus melakukan jumlah perbandingan yang sama untuk setiap elemen dalam array acak.

- **Best Case (Kasus Terbaik)**: \(O(n^2)\)
  - Selection Sort tidak memiliki skenario terbaik yang berbeda dari kasus rata-rata dan terburuk karena tetap harus memeriksa seluruh elemen yang belum diurutkan untuk menemukan elemen minimum, bahkan jika array sudah terurut.

### Bubble Sort

<img src="/img/modul-6/bubble-sorting.png">

Bubble Sort adalah algoritma sorting sederhana yang berfungsi dengan mengulang array dan menukar elemen yang berdampingan jika berada dalam urutan yang salah. Setiap iterasi akan “menggelembungkan” elemen terbesar ke posisi akhir, seperti gelembung yang naik ke permukaan.

#### Code

```java
public class BubbleSort {
    public static int[] bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;  // Tukar elemen
                }
            }
        }
        return arr;
    }
}

```

#### Kompleksitas

- **Worst Case (Kasus Terburuk)**: \(O(n^2)\)
  - Terjadi ketika array diurutkan dalam urutan terbalik. Algoritma harus melakukan \( n \) perulangan untuk memastikan setiap elemen berada di posisi yang benar.
  
- **Average Case (Kasus Rata-rata)**: \(O(n^2)\)
  - Untuk array acak, algoritma masih perlu melakukan banyak perbandingan dan pertukaran.
  
- **Best Case (Kasus Terbaik)**: \(O(n)\)
  - Terjadi ketika array sudah terurut sepenuhnya. Dalam kasus ini, hanya satu perulangan diperlukan untuk memastikan bahwa tidak ada elemen yang perlu dipertukarkan.

### Insertion Sort
<img src="/img/modul-6/Insertion-sorting.png">
Insertion Sort adalah algoritma pengurutan sederhana yang bekerja seperti cara seseorang mengurutkan kartu di tangannya. Algoritma ini mengurutkan elemen satu per satu dengan cara memilih elemen yang belum diurutkan dan menyisipkannya ke dalam posisi yang benar dalam bagian array yang sudah diurutkan. Algoritma ini bekerja dengan baik untuk kumpulan data kecil atau hampir terurut, tetapi menjadi tidak efisien untuk dataset besar.

#### Code

```java
public class InsertionSort {
    public static void insertionSort(int[] arr) {
        for (int i = 1; i < arr.length; i++) {
            int key = arr[i];
            int j = i - 1;

            // Pindahkan elemen yang lebih besar dari key ke posisi berikutnya
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            // Tempatkan key pada posisi yang benar
            arr[j + 1] = key;
        }
    }
}

```

#### Kompleksitas Waktu
- **Worst Case (Kasus Terburuk):** \( O(n^2) \) ketika array diurutkan secara terbalik.
- **Average Case (Kasus Rata-rata):** \( O(n^2) \) untuk array yang tidak diurutkan.
- **Best Case (Kasus Terbaik):** \( O(n) \) ketika array sudah terurut.

### Kesimpulan
Berikut adalah tabel yang mencakup **Bubble Sort**, **Selection Sort**, dan **Insertion Sort** dengan kompleksitas waktu dalam berbagai kasus:

| Algoritma        | Best Case    | Average Case | Worst Case  |
|------------------|--------------|--------------|-------------|
| **Bubble Sort**  | \(O(n)\)     | \(O(n^2)\)   | \(O(n^2)\)  |
| **Selection Sort** | \(O(n^2)\) | \(O(n^2)\)   | \(O(n^2)\)  |
| **Insertion Sort** | \(O(n)\)   | \(O(n^2)\)   | \(O(n^2)\)  |

---
