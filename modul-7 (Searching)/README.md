## Daftar Isi

- [Linear Search](#linear-search)
  - [Cara Kerja](#cara-kerja-linear-search)
  - [Contoh Implementasi](#contoh-implementasi-dalam-java)
  - [Kompleksitas Waktu](#kompleksitas-waktu)
- [Binary Search](#binary-search)
  - [Cara Kerja](#cara-kerja-binary-search)
  - [Contoh Implementasi](#contoh-implementasi-dalam-java-iteratif)
  - [Kompleksitas Waktu](#kompleksitas-waktu)
- [Perbandingan Linear Search vs Binary Search](#perbandingan-linear-search-vs-binary-search)

---

## Linear Search
Linear Search adalah metode pencarian yang sederhana di mana kita mencari elemen tertentu dalam array dengan memeriksa setiap elemen satu per satu hingga elemen yang dicari ditemukan atau seluruh array sudah diperiksa.

### **Cara Kerja Linear Search**:
   - Mulai dari elemen pertama di array.
   - Bandingkan elemen saat ini dengan elemen yang dicari.
   - Jika sama, pencarian selesai dan elemen ditemukan.
   - Jika berbeda, lanjutkan ke elemen berikutnya.
   - Jika semua elemen sudah diperiksa dan elemen tidak ditemukan, maka elemen tersebut tidak ada dalam array.

### **Contoh Implementasi dalam Java**:
   ```java
   public class LinearSearch {
       public static int linearSearch(int[] arr, int target) {
           for (int i = 0; i < arr.length; i++) {
               if (arr[i] == target) {
                   return i; // Mengembalikan indeks jika elemen ditemukan
               }
           }
           return -1; // Mengembalikan -1 jika elemen tidak ditemukan
       }

       public static void main(String[] args) {
           int[] arr = {10, 23, 5, 32, 45};
           int target = 32;
           int result = linearSearch(arr, target);
           System.out.println(result == -1 ? "Elemen tidak ditemukan" : "Elemen ditemukan di indeks " + result);
       }
   }
   ```

### **Kompleksitas Waktu**:
   - **Worst-case**: \( O(n) \) (ketika elemen berada di akhir atau tidak ada di array).
   - **Best-case**: \( O(1) \) (ketika elemen berada di posisi awal array).

---

## Binary Search
Binary Search adalah metode pencarian yang efisien untuk mencari elemen dalam array yang terurut. Binary Search bekerja dengan membagi dua array secara berulang sampai elemen yang dicari ditemukan atau dipastikan tidak ada dalam array.

### **Cara Kerja Binary Search**:
   - Tentukan indeks awal dan akhir array.
   - Hitung indeks tengah: \( \text{mid} = \text{(start + end) / 2} \).
   - Bandingkan elemen tengah dengan elemen yang dicari:
     - Jika sama, elemen ditemukan.
     - Jika elemen yang dicari lebih kecil, ulangi pencarian di bagian kiri (start hingga mid-1).
     - Jika elemen yang dicari lebih besar, ulangi pencarian di bagian kanan (mid+1 hingga end).
   - Ulangi langkah ini sampai elemen ditemukan atau start > end.

### **Contoh Implementasi dalam Java Iteratif**:
   ```java
   public class BinarySearch {
       public static int binarySearch(int[] arr, int target) {
           int start = 0;
           int end = arr.length - 1;

           while (start <= end) {
               int mid = start + (end - start) / 2;

               if (arr[mid] == target) {
                   return mid; // Mengembalikan indeks jika elemen ditemukan
               }
               if (arr[mid] < target) {
                   start = mid + 1; // Fokus pada bagian kanan
               } else {
                   end = mid - 1; // Fokus pada bagian kiri
               }
           }
           return -1; // Mengembalikan -1 jika elemen tidak ditemukan
       }

       public static void main(String[] args) {
           int[] arr = {5, 10, 23, 32, 45};
           int target = 32;
           int result = binarySearch(arr, target);
           System.out.println(result == -1 ? "Elemen tidak ditemukan" : "Elemen ditemukan di indeks " + result);
       }
   }
   ```

### **Kompleksitas Waktu**:
   - **Worst-case**: \( O(\log n) \).
   - **Best-case**: \( O(1) \) (ketika elemen berada di posisi tengah).

---

## Perbandingan Linear Search vs Binary Search
- **Kecepatan**: Binary Search lebih cepat daripada Linear Search untuk array yang besar.
- **Syarat**: Binary Search hanya bisa diterapkan pada array yang **terurut**.
- **Kapan Menggunakan**:
  - Gunakan Linear Search jika data **tidak terurut** atau ukuran data relatif kecil.
  - Gunakan Binary Search jika data **terurut** dan ukuran data besar. 
