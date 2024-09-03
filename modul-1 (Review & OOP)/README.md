## Daftar Isi

- [Percabangan](#percabangan)
  - [If-Else](#if-else)
  - [Switch-Case](#switch-case)
- [Perulangan](#perulangan)
  - [For Loop](#for-loop)
  - [While Loop](#while-loop)
  - [Do-While Loop](#do-while-loop)
- [Fungsi](#fungsi)
  - [Mendeklarasikan Fungsi](#mendeklarasikan-fungsi)
  - [Parameter dan Return Value](#parameter-dan-return-value)
  - [Overloading Fungsi](#overloading-fungsi)
- [Array](#array)
  - [Array 1 Dimensi](#array-1-dimensi)
  - [Array 2 Dimensi](#array-2-dimensi)
- [Pengenalan Object Oriented Programming](#pengenalan-object-oriented-programming)
  - [Konsep Dasar OOP](#konsep-dasar-oop)
  - [Hak Akses (Access Modifier)](#hak-akses-access-modifier)
  - [Class, Method, Attributes, dan Constructor](#class-method-attributes-dan-constructor)
  - [Enkapsulasi](#enkapsulasi)
  - [Pewarisan](#pewarisan)
  - [Polimorfisme](#polimorfisme)

---

## Percabangan

### If-Else
Percabangan `if-else` digunakan untuk mengeksekusi kode berdasarkan kondisi yang diberikan.

```java
public class Main {
  public static void main(String[] args) {
    int nilai = 85;

    if (nilai >= 90) {
      System.out.println("A");
    } else if (nilai >= 80) {
      System.out.println("B");
    } else {
      System.out.println("C");
    }
  }
}
```

### Switch-Case
`Switch-case` adalah alternatif dari `if-else` ketika ada beberapa kondisi yang harus diperiksa.

```java
public class Main {
  public static void main(String[] args) {
    int hari = 3;
    String namaHari;

    switch (hari) {
      case 1:
        namaHari = "Senin";
        break;
      case 2:
        namaHari = "Selasa";
        break;
      case 3:
        namaHari = "Rabu";
        break;
      default:
        namaHari = "Hari tidak valid";
        break;
    }

    System.out.println(namaHari);
  }
}
```

## Perulangan

### For Loop
`For loop` digunakan untuk mengulang blok kode dengan jumlah iterasi yang sudah ditentukan.

```java
public class Main {
  public static void main(String[] args) {
    for (int i = 0; i < 5; i++) {
      System.out.println("Iterasi ke-" + i);
    }
  }
}
```

### While Loop
`While loop` mengulang blok kode selama kondisi yang diberikan adalah benar.

```java
public class Main {
  public static void main(String[] args) {
    int i = 0;
    while (i < 5) {
      System.out.println("Iterasi ke-" + i);
      i++;
    }
  }
}
```

### Do-While Loop
`Do-while loop` mirip dengan `while loop`, tetapi selalu mengeksekusi blok kode setidaknya sekali.

```java
public class Main {
  public static void main(String[] args) {
    int i = 0;
    do {
      System.out.println("Iterasi ke-" + i);
      i++;
    } while (i < 5);
  }
}
```

## Fungsi

### Mendeklarasikan Fungsi
Fungsi adalah blok kode yang dapat dipanggil dari bagian lain program untuk menjalankan tugas tertentu.

```java
public class Main {
  public static void main(String[] args) {
    int hasil = tambah(5, 3);
    System.out.println("Hasil: " + hasil);
  }

  public static int tambah(int a, int b) {
    return a + b;
  }
}
```

### Parameter dan Return Value
Fungsi dapat menerima parameter dan mengembalikan nilai.

```java
public class Main {
  public static void main(String[] args) {
    int hasil = kali(4, 7);
    System.out.println("Hasil: " + hasil);
  }

  public static int kali(int a, int b) {
    return a * b;
  }
}
```

### Overloading Fungsi
Overloading memungkinkan kita membuat beberapa fungsi dengan nama yang sama tetapi parameter yang berbeda.

```java
public class Main {
  public static void main(String[] args) {
    System.out.println(kali(5, 2));
    System.out.println(kali(5.0, 2.0));
  }

  public static int kali(int a, int b) {
    return a * b;
  }

  public static double kali(double a, double b) {
    return a * b;
  }
}
```

## Array

### Array 1 Dimensi
Array adalah struktur data yang menyimpan beberapa nilai dalam satu variabel.

```java
public class Main {
  public static void main(String[] args) {
    int[] angka = {1, 2, 3, 4, 5};
    for (int i = 0; i < angka.length; i++) {
      System.out.println(angka[i]);
    }
  }
}
```

### Array 2 Dimensi
Array 2D adalah array dari array, sering digunakan untuk merepresentasikan matriks.

```java
public class Main {
  public static void main(String[] args) {
    int[][] matriks = {
      {1, 2, 3},
      {4, 5, 6},
      {7, 8, 9}
    };

    for (int i = 0; i < matriks.length; i++) {
      for (int j = 0; j < matriks[i].length; j++) {
        System.out.print(matriks[i][j] + " ");
      }
      System.out.println();
    }
  }
}
```

## Object-Oriented Programming (OOP)

### Konsep Dasar OOP
OOP adalah paradigma pemrograman yang menggunakan objek untuk merepresentasikan data dan metode.

- **Class**: Cetak biru untuk membuat objek.
- **Object**: Instance dari kelas.
- **Method**: Fungsi yang didefinisikan dalam kelas.

### Hak Akses (Access Modifier)

Access Modifier dalam Java menentukan tingkat aksesibilitas anggota kelas (seperti variabel dan metode) atau kelas itu sendiri. Berikut adalah jenis-jenis Access Modifier dalam Java:

- **`public`**: Dapat diakses dari mana saja.
- **`protected`**: Dapat diakses dalam paket yang sama dan subclass.
- **`default`** (tanpa modifier): Hanya dapat diakses dalam paket yang sama.
- **`private`**: Hanya dapat diakses dalam kelas itu sendiri.

Contoh penggunaan Access Modifier:

```java
public class Contoh {
    public int publicVar;       // Dapat diakses dari mana saja
    protected int protectedVar; // Dapat diakses dalam paket yang sama atau subclass
    int defaultVar;             // Hanya dapat diakses dalam paket yang sama
    private int privateVar;     // Hanya dapat diakses dalam kelas ini sendiri

    public void publicMethod() { ... }
    protected void protectedMethod() { ... }
    void defaultMethod() { ... }
    private void privateMethod() { ... }
}
```

### Class, Method, Attributes, dan Constructor

#### Class
Kelas adalah cetak biru atau template untuk membuat objek. Kelas mendefinisikan properti (atribut) dan perilaku (metode) yang dimiliki oleh objek.

```java
public class Mobil {
    // Atribut (Properties)
    String merek;
    String model;
    int tahun;

    // Konstruktor
    public Mobil(String merek, String model, int tahun) {
        this.merek = merek;
        this.model = model;
        this.tahun = tahun;
    }

    // Metode (Behavior)
    public void jalan() {
        System.out.println("Mobil " + merek + " sedang berjalan.");
    }
}
```

#### Attributes
Atribut adalah variabel yang dideklarasikan dalam kelas dan digunakan untuk menyimpan data terkait objek.

```java
String merek; // Atribut merek
String model; // Atribut model
int tahun;    // Atribut tahun
```

#### Method
Metode adalah fungsi yang didefinisikan di dalam kelas dan digunakan untuk menggambarkan perilaku objek.

```java
public void jalan() {
    System.out.println("Mobil " + merek + " sedang berjalan.");
}
```

#### Constructor
Konstruktor adalah metode khusus yang dipanggil saat objek diinisialisasi. Konstruktor biasanya digunakan untuk menetapkan nilai awal pada atribut.

```java
public Mobil(String merek, String model, int tahun) {
    this.merek = merek;
    this.model = model;
    this.tahun = tahun;
}
```

Contoh Membuat dan Menggunakan Kelas, Atribut, Metode, dan Konstruktor:

```java
public class Main {
    public static void main(String[] args) {
        // Membuat objek Mobil
        Mobil mobil1 = new Mobil("Toyota", "Avanza", 2020);

        // Memanggil metode
        mobil1.jalan();
    }
}
```

### Enkapsulasi
Menyembunyikan data objek dari akses langsung dan hanya memungkinkan akses melalui metode.

```java
public class Pelanggan {
  private String nama;
  private int umur;

  public Pelanggan(String nama, int umur) {
    this.nama = nama;
    this.umur = umur;
  }

  public String getNama() {
    return nama;
  }

  public void setNama(String nama) {
    this.nama = nama;
  }

  public int getUmur() {
    return umur;
  }

  public void setUmur(int umur) {
    this.umur = umur;
  }
}
```

### Pewarisan
Memungkinkan sebuah kelas mewarisi atribut dan metode dari kelas lain.

```java
public class Hewan {
  public void suara() {
    System.out.println("Hewan bersuara");
  }
}

public class Anjing extends Hewan {
  @Override
  public void suara() {
    System.out.println("Anjing menggonggong");
  }
}
```

### Polimorfisme
Memungkinkan metode yang sama untuk memiliki perilaku berbeda pada objek yang berbeda.

```java
public class Main {
  public static void main(String[] args) {
    Hewan hewan = new Anjing();
    hewan.suara();  // Menggunakan method suara() milik kelas Anjing
  }
}
```
