
# Daftar Isi

- [Map Interface](#1-map-interface)

- [HashMap Class](#2-hashmap-class)

- [TreeMap Class](#3-treemap-class)

- [Set Interface](#4-set-interface)

- [HashSet Class](#5-hashset-class)

- [LinkedHashSet Class](#6-linkedhashset-class)

- [TreeSet Class](#7-treeset-class)

- [Ringkasan](#ringkasan)

## Map Interface

### Metode Utama
- **`put(K key, V value)`**: Menambahkan pasangan key-value ke dalam map.
- **`get(Object key)`**: Mengambil nilai yang terkait dengan key tertentu.
- **`remove(Object key)`**: Menghapus entri berdasarkan key.
- **`containsKey(Object key)`**: Memeriksa apakah map mengandung key tertentu.
- **`containsValue(Object value)`**: Memeriksa apakah map mengandung value tertentu.
- **`size()`**: Mengembalikan jumlah pasangan key-value dalam map.
- **`isEmpty()`**: Memeriksa apakah map kosong.
- **`keySet()`**: Mengembalikan set dari semua key dalam map.
- **`values()`**: Mengembalikan koleksi dari semua value dalam map.
- **`entrySet()`**: Mengembalikan set dari semua entri (key-value) dalam map.

### Contoh Kegunaan
```java
import java.util.Map;
import java.util.HashMap;

public class MapExample {
    public static void main(String[] args) {
        Map<String, Integer> ageMap = new HashMap<>();

        // Menambahkan elemen
        ageMap.put("Alice", 30);
        ageMap.put("Bob", 25);
        ageMap.put("Charlie", 35);

        // Mengambil nilai
        int age = ageMap.get("Alice");
        System.out.println("Usia Alice: " + age);

        // Menghapus elemen
        ageMap.remove("Bob");

        // Memeriksa keberadaan key
        boolean hasCharlie = ageMap.containsKey("Charlie");
        System.out.println("Map mengandung key 'Charlie': " + hasCharlie);

        // Menampilkan semua key
        System.out.println("Key: " + ageMap.keySet());

        // Menampilkan semua value
        System.out.println("Value: " + ageMap.values());

        // Menampilkan semua entri
        System.out.println("Entries: " + ageMap.entrySet());
    }
}
```

## HashMap Class

### Metode Utama
- **`put(K key, V value)`**: Menambahkan pasangan key-value.
- **`get(Object key)`**: Mengambil nilai berdasarkan key.
- **`remove(Object key)`**: Menghapus entri berdasarkan key.
- **`containsKey(Object key)`**: Memeriksa keberadaan key.
- **`containsValue(Object value)`**: Memeriksa keberadaan value.
- **`size()`**, **`isEmpty()`**, **`clear()`**, dll.

### Contoh Kegunaan
```java
import java.util.HashMap;

public class HashMapExample {
    public static void main(String[] args) {
        HashMap<String, String> capitalMap = new HashMap<>();

        // Menambahkan elemen
        capitalMap.put("Indonesia", "Jakarta");
        capitalMap.put("Malaysia", "Kuala Lumpur");
        capitalMap.put("Thailand", "Bangkok");

        // Mengambil nilai
        String capital = capitalMap.get("Indonesia");
        System.out.println("Ibu kota Indonesia: " + capital);

        // Menghapus elemen
        capitalMap.remove("Malaysia");

        // Menampilkan semua elemen
        System.out.println("HashMap: " + capitalMap);
    }
}
```

## TreeMap Class

### Metode Utama
- **`put(K key, V value)`**: Menambahkan pasangan key-value.
- **`get(Object key)`**: Mengambil nilai berdasarkan key.
- **`remove(Object key)`**: Menghapus entri berdasarkan key.
- **`firstKey()`**: Mengambil key terkecil.
- **`lastKey()`**: Mengambil key terbesar.
- **`subMap(K fromKey, K toKey)`**: Mengambil subset map.
- **`keySet()`**, **`values()`**, **`entrySet()`**, dll.

### Contoh Kegunaan
```java
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        TreeMap<Integer, String> treeMap = new TreeMap<>();

        // Menambahkan elemen
        treeMap.put(3, "Tiga");
        treeMap.put(1, "Satu");
        treeMap.put(2, "Dua");

        // Menampilkan TreeMap (urut berdasarkan key)
        System.out.println("TreeMap: " + treeMap);

        // Mengambil key pertama dan terakhir
        System.out.println("Key pertama: " + treeMap.firstKey());
        System.out.println("Key terakhir: " + treeMap.lastKey());

        // Mengambil subset map
        System.out.println("Subset (1-2): " + treeMap.subMap(1, 3));
    }
}
```

## Set Interface

### Metode Utama
- **`add(E e)`**: Menambahkan elemen ke set.
- **`remove(Object o)`**: Menghapus elemen dari set.
- **`contains(Object o)`**: Memeriksa apakah set mengandung elemen tertentu.
- **`size()`**, **`isEmpty()`**, **`clear()`**, **`iterator()`**, dll.

### Contoh Kegunaan
```java
import java.util.Set;
import java.util.HashSet;

public class SetExample {
    public static void main(String[] args) {
        Set<String> fruits = new HashSet<>();

        // Menambahkan elemen
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Apple"); // Duplikat, tidak akan ditambahkan

        // Menampilkan set
        System.out.println("Set: " + fruits);

        // Menghapus elemen
        fruits.remove("Banana");
        System.out.println("Set setelah penghapusan: " + fruits);

        // Memeriksa keberadaan elemen
        boolean hasApple = fruits.contains("Apple");
        System.out.println("Set mengandung 'Apple': " + hasApple);
    }
}
```

## HashSet Class

### Metode Utama
- **`add(E e)`**: Menambahkan elemen ke set.
- **`remove(Object o)`**: Menghapus elemen dari set.
- **`contains(Object o)`**: Memeriksa keberadaan elemen.
- **`size()`**, **`isEmpty()`**, **`clear()`**, **`iterator()`**, dll.

### Contoh Kegunaan
```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<Integer> numbers = new HashSet<>();

        // Menambahkan elemen
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(20); // Duplikat, tidak akan ditambahkan

        // Menampilkan HashSet
        System.out.println("HashSet: " + numbers);

        // Menghapus elemen
        numbers.remove(20);
        System.out.println("HashSet setelah penghapusan: " + numbers);

        // Memeriksa keberadaan elemen
        boolean has30 = numbers.contains(30);
        System.out.println("HashSet mengandung 30: " + has30);
    }
}
```

## LinkedHashSet Class

### Metode Utama
- **`add(E e)`**: Menambahkan elemen ke set.
- **`remove(Object o)`**: Menghapus elemen dari set.
- **`contains(Object o)`**: Memeriksa keberadaan elemen.
- **`size()`**, **`isEmpty()`**, **`clear()`**, **`iterator()`**, dll.

### Fitur Utama
- Mempertahankan urutan penyisipan elemen.
- Tidak mengizinkan elemen duplikat.
- Mengizinkan satu `null` elemen.

### Contoh Kegunaan
```java
import java.util.LinkedHashSet;

public class LinkedHashSetExample {
    public static void main(String[] args) {
        LinkedHashSet<String> languages = new LinkedHashSet<>();

        // Menambahkan elemen
        languages.add("Java");
        languages.add("Python");
        languages.add("JavaScript");
        languages.add("Python"); // Duplikat, tidak akan ditambahkan

        // Menampilkan LinkedHashSet
        System.out.println("LinkedHashSet: " + languages);

        // Menghapus elemen
        languages.remove("Python");
        System.out.println("LinkedHashSet setelah penghapusan: " + languages);

        // Memeriksa keberadaan elemen
        boolean hasJava = languages.contains("Java");
        System.out.println("LinkedHashSet mengandung 'Java': " + hasJava);
    }
}
```

## TreeSet Class

### Metode Utama
- **`add(E e)`**: Menambahkan elemen ke set.
- **`remove(Object o)`**: Menghapus elemen dari set.
- **`contains(Object o)`**: Memeriksa keberadaan elemen.
- **`first()`**: Mengambil elemen pertama (terkecil).
- **`last()`**: Mengambil elemen terakhir (terbesar).
- **`subSet(E fromElement, E toElement)`**: Mengambil subset set.
- **`size()`**, **`isEmpty()`**, **`clear()`**, **`iterator()`**, dll.

### Fitur Utama
- Mempertahankan urutan alami (natural order) elemen.
- Tidak mengizinkan elemen duplikat.
- Tidak mengizinkan elemen `null`.

### Contoh Kegunaan
```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        TreeSet<String> countries = new TreeSet<>();

        // Menambahkan elemen
        countries.add("India");
        countries.add("Australia");
        countries.add("South Africa");
        countries.add("Australia"); // Duplikat, tidak akan ditambahkan

        // Menampilkan TreeSet (urut secara alami)
        System.out.println("TreeSet: " + countries);

        // Menghapus elemen
        countries.remove("Australia");
        System.out.println("TreeSet setelah penghapusan: " + countries);

        // Mengambil elemen pertama dan terakhir
        System.out.println("Elemen pertama: " + countries.first());
        System.out.println("Elemen terakhir: " + countries.last());

        // Mengambil subset
        System.out.println("Subset (India - South Africa): " + countries.subSet("India", "South Africa"));
    }
}
```

---

## Ringkasan

| Kelas          | Interface Implemented | Fitur Utama                                     |
|----------------|-----------------------|-------------------------------------------------|
| **Map**        | -                     | Menyimpan pasangan key-value, key unik          |
| **HashMap**    | `Map`                 | Tidak sinkron, mengizinkan 1 `null` key, tidak urut |
| **TreeMap**    | `NavigableMap`        | Mengurutkan berdasarkan key, tidak mengizinkan `null` key |
| **Set**        | -                     | Koleksi elemen unik                              |
| **HashSet**    | `Set`                 | Tidak sinkron, mengizinkan 1 `null` elemen, tidak urut |
| **LinkedHashSet** | `Set`              | Mempertahankan urutan penyisipan, mengizinkan 1 `null` elemen |
| **TreeSet**    | `NavigableSet`        | Mengurutkan elemen secara alami atau sesuai `Comparator`, tidak mengizinkan `null` |
