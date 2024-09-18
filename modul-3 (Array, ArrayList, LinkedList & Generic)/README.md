## Daftar Isi

- [Array](#array)
  - [Deklarasi dan Inisialisasi Array](#deklarasi-dan-inisialisasi-array)
  - [Kelebihan dan Kekurangan Array](#kelebihan-dan-kekurangan-array)
- [ArrayList](#arraylist)
  - [Deklarasi dan Penggunaan](#deklarasi-dan-penggunaan)
  - [Fitur Penting ArrayList](#fitur-penting-arraylist)
  - [Kelebihan dan Kekurangan ArrayList](#kelebihan-dan-kekurangan-arraylist)
- [LinkedList](#linkedlist)
  - [Deklarasi dan Penggunaan](#deklarasi-dan-penggunaan-1)
  - [Fitur Penting LinkedList](#fitur-penting-linkedlist)
  - [Kelebihan dan Kekurangan LinkedList](#kelebihan-dan-kekurangan-linkedlist)
- [Generics](#generics)
  - [Penggunaan Generic](#penggunaan-generic)
  - [Manfaat Generics](#manfaat-generics)
  - [Contoh dengan Multiple Parameters](#contoh-dengan-multiple-parameters)
- [Latihan](#latihan)

---

## **Array**

Array adalah struktur data yang digunakan untuk menyimpan sekumpulan elemen dengan tipe data yang sama dalam satu variabel.

### Deklarasi dan Inisialisasi Array

```java
// Deklarasi Array
int[] angka = new int[5];  // Array dengan ukuran 5
angka[0] = 10;  // Menetapkan nilai pada indeks 0

// Inisialisasi dengan nilai langsung
int[] nilai = {10, 20, 30, 40, 50};

// Akses elemen dan cetak
for (int i = 0; i < nilai.length; i++) {
	System.out.println(nilai[i]);
}
```

### Kelebihan dan Kekurangan Array

- **Kelebihan:**
  - Memiliki performa cepat karena menggunakan direct memory access.
  - Ideal untuk data yang ukurannya diketahui di awal.
- **Kekurangan:**
  - Ukuran tetap setelah didefinisikan, tidak dapat diubah.
  - Tidak fleksibel untuk menambah atau mengurangi elemen setelah deklarasi.

---

## **ArrayList**

`ArrayList` adalah versi dinamis dari array yang memungkinkan kita untuk menambah atau menghapus elemen sesuai kebutuhan.

<img src="/img/ArrayList_Integer_Object.png">

### Deklarasi dan Penggunaan

```java
import java.util.ArrayList;  // Impor ArrayList

public class Main {
	public static void main(String[] args) {
		// Membuat objek ArrayList
		ArrayList<String> mobil = new ArrayList<String>();

		// Menambah elemen ke ArrayList
		mobil.add("Volvo");
		mobil.add("BMW");
		mobil.add("Ford");
		mobil.add("Mazda");

		// Mengakses elemen dari ArrayList
		System.out.println(mobil.get(0)); // Output: Volvo
	}
}
```

### Fitur Penting ArrayList

- **add()**: Menambahkan elemen.
- **get()**: Mengakses elemen menggunakan indeks.
- **set()**: Mengganti elemen yang ada.
- **remove()**: Menghapus elemen di posisi tertentu.
- **size()**: Mengetahui jumlah elemen dalam `ArrayList`.

### Kelebihan dan Kekurangan ArrayList

- **Kelebihan:**
  - Ukuran dinamis, bisa menambah atau mengurangi elemen.
  - Dapat menyimpan elemen duplikat.
- **Kekurangan:**
  - Operasi pada posisi tengah list relatif lambat karena harus menggeser elemen.

---

## **LinkedList**

`LinkedList` menggunakan node yang saling terhubung untuk menyimpan elemen-elemen dalam urutan tertentu.

<img src="/img/Singlelinkedlist.png">

**Data:** Menyimpan nilai atau data yang terkait dengan node.
**Next Pointer or Reference:** Menyimpan alamat memori (referensi) dari node berikutnya dalam urutan.

**Head dan Tail:** Linked list diakses melalui node head, yang menunjuk ke node pertama dalam daftar. Node terakhir dalam daftar menunjuk ke NULL atau nullptr, yang menandakan akhir dari daftar. Node ini dikenal sebagai node tail.

### Deklarasi dan Penggunaan

```java
import java.util.LinkedList;  // Impor LinkedList

public class Main {
	public static void main(String[] args) {
		// Membuat objek LinkedList
		LinkedList<String> hewan = new LinkedList<String>();

		// Menambah elemen ke LinkedList
		hewan.add("Kucing");
		hewan.add("Anjing");
		hewan.add("Kelinci");
	}
}
```

### Fitur Penting LinkedList

- **addFirst()**: Menambahkan elemen di awal list.
- **addLast()**: Menambahkan elemen di akhir list.
- **removeFirst()**: Menghapus elemen pertama.
- **removeLast()**: Menghapus elemen terakhir.
- **getFirst()**: Mengambil elemen pertama.
- **getLast()**: Mengambil elemen terakhir.

### Kelebihan dan Kekurangan LinkedList

- **Kelebihan:**
  - Operasi penambahan/penghapusan di awal atau akhir list sangat cepat.
- **Kekurangan:**
  - Akses elemen berdasarkan indeks lebih lambat dibandingkan `ArrayList`.

---

## **Generics**

Generics memungkinkan kita untuk membuat kelas atau metode yang bisa menangani tipe data yang berbeda tanpa perlu melakukan cast.

### Penggunaan Generic

```java
class Kotak<T> {
	private T data;

	// Konstruktor
	public Kotak(T data) {
		this.data = data;
	}

	// Getter
	public T getData() {
		return data;
	}
}

public class Main {
	public static void main(String[] args) {
		// Menggunakan class generic dengan tipe Integer
		Kotak<Integer> kotakAngka = new Kotak<>(10);
		System.out.println(kotakAngka.getData());  // Output: 10
	}
}
```

### Manfaat Generics

- **Code Reusability**: Dapat digunakan kembali dengan berbagai tipe data.
- **Type Safety**: Menghindari kesalahan tipe data pada waktu kompilasi.

### Contoh dengan Multiple Parameters

```java
class Duo<T, U> {
	private T pertama;
	private U kedua;

	public Duo(T pertama, U kedua) {
		this.pertama = pertama;
		this.kedua = kedua;
	}

	public T getPertama() {
		return pertama;
	}

	public U getKedua() {
		return kedua;
	}
}

public class Main {
	public static void main(String[] args) {
		// Contoh dengan tipe String dan Integer
		Duo<String, Integer> duo = new Duo<>("Angka", 100);
		System.out.println(duo.getPertama() + ": " + duo.getKedua());  // Output: Angka: 100
	}
}
```
Berikut adalah beberapa latihan soal untuk **ArrayList**, **LinkedList**, dan **Generics** di Java:

---

## Latihan
## **Latihan Soal untuk ArrayList**

1. **Soal 1: Membuat Daftar Siswa**
   Buatlah program yang menggunakan `ArrayList` untuk menyimpan daftar nama siswa. Program harus memiliki fitur:
   - Menambah nama siswa ke dalam daftar.
   - Menghapus siswa berdasarkan nama.
   - Menampilkan semua nama siswa yang ada di daftar.

   **Contoh Output**:
   ```
   1. Tambah siswa
   2. Hapus siswa
   3. Tampilkan daftar siswa
   4. Keluar
   Pilih opsi: 1
   Masukkan nama siswa: Bryan
   Siswa Bryan telah ditambahkan.
   ```

2. **Soal 2: Daftar Nilai Matematika**
   Buatlah program yang menggunakan `ArrayList` untuk menyimpan nilai matematika dari siswa dalam satu kelas. Program harus dapat:
   - Menambah nilai baru.
   - Menghapus nilai tertentu berdasarkan indeks.
   - Menampilkan nilai rata-rata seluruh siswa.

   **Contoh Output**:
   ```
   Nilai siswa: [80, 90, 70]
   Rata-rata nilai: 80
   ```

3. **Soal 3: Menukar Elemen ArrayList**
   Buatlah sebuah program yang meminta user untuk memasukkan sejumlah elemen ke dalam `ArrayList`. Kemudian program harus menukar elemen pertama dengan elemen terakhir dari `ArrayList` tersebut.

   **Contoh**:
   ```
   Input: [10, 20, 30, 40]
   Output: [40, 20, 30, 10]
   ```

---

## **Latihan Soal untuk LinkedList**

1. **Soal 1: Mengelola Antrian Rumah Sakit**
   Buatlah program menggunakan `LinkedList` untuk mensimulasikan sistem antrian pasien di rumah sakit. Program harus mampu:
   - Menambahkan pasien baru ke antrian.
   - Memproses pasien (menghapus pasien yang sudah dilayani dari antrian).
   - Menampilkan daftar antrian saat ini.

   **Contoh Output**:
   ```
   Pasien dalam antrian: [Andi, Budi, Cici]
   Pasien diproses: Andi
   Pasien dalam antrian: [Budi, Cici]
   ```

2. **Soal 2: Menambahkan Elemen di Tengah LinkedList**
   Buatlah program yang meminta user untuk memasukkan sejumlah elemen ke dalam `LinkedList`. Kemudian program harus menambahkan elemen baru tepat di tengah `LinkedList`.

   **Contoh**:
   ```
   Input: [1, 2, 4, 5]
   Tambah elemen di tengah: 3
   Output: [1, 2, 3, 4, 5]
   ```

3. **Soal 3: Mencari Elemen Tertentu di LinkedList**
   Buat program yang meminta user memasukkan sejumlah elemen ke dalam `LinkedList`, lalu meminta user untuk memasukkan elemen tertentu yang ingin dicari. Jika elemen ditemukan, tampilkan indeksnya; jika tidak, tampilkan pesan "Tidak ditemukan".

   **Contoh Output**:
   ```
   Input: [10, 20, 30, 40]
   Cari elemen: 30
   Elemen ditemukan di indeks: 2
   ```

---

## **Latihan Soal untuk Generics**

1. **Soal 1: Kotak Penyimpanan Generik**
   Buatlah class generik `Kotak<T>` yang dapat menyimpan data dari tipe apapun. Class tersebut harus memiliki:
   - Satu atribut yang menyimpan data.
   - Metode `get()` dan `set()` untuk mengambil dan mengubah data.

   **Contoh**:
   ```java
   Kotak<Integer> kotakAngka = new Kotak<>();
   kotakAngka.set(100);
   System.out.println("Isi kotak: " + kotakAngka.get());  // Output: Isi kotak: 100
   ```

2. **Soal 2: Menangani Daftar Generik**
   Buat class generik `Daftar<T>` yang menggunakan `ArrayList` untuk menyimpan elemen. Class ini harus memiliki metode untuk:
   - Menambahkan elemen ke dalam daftar.
   - Menghapus elemen dari daftar.
   - Menampilkan seluruh elemen dalam daftar.

   **Contoh**:
   ```java
   Daftar<String> daftarNama = new Daftar<>();
   daftarNama.add("Andi");
   daftarNama.add("Budi");
   daftarNama.printList();  // Output: [Andi, Budi]
   ```

3. **Soal 3: Pasangan Generik**
   Buatlah class generik `Pasangan<K, V>` yang dapat menyimpan dua tipe data berbeda. Class ini harus memiliki:
   - Konstruktor untuk menginisialisasi pasangan data.
   - Metode `getKey()` dan `getValue()` untuk mengambil nilai kunci dan nilai.

   **Contoh**:
   ```java
   Pasangan<String, Integer> pasangan = new Pasangan<>("Umur", 25);
   System.out.println("Kunci: " + pasangan.getKey());  // Output: Kunci: Umur
   System.out.println("Nilai: " + pasangan.getValue());  // Output: Nilai: 25
   ```
