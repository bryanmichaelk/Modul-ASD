## Daftar Isi
- [Stack](#stack)
   - [Implementasi Stack di Java](#implementasi-stack-di-java)
   - [Ilustrasi Stack](#ilustrasi-stack)
   - [Rangkuman Method Stack](#rangkuman-method-stack)
-  [Queue](#queue)
   - [Implementasi Queue di Java](#implementasi-queue-di-java)
   - [Ilustrasi Queue](#ilustrasi-queue)
   - [Rangkuman Method Queue](#rangkuman-method-queue)
-  [Deque](#deque)
   - [Implementasi Deque di Java](#implementasi-deque-di-java)
   - [Ilustrasi Deque](#ilustrasi-deque)
   - [Rangkuman Method Deque](#rangkuman-method-deque)
-  [Latihan](#latihan)

---

## Stack

Stack adalah struktur data yang menggunakan prinsip **LIFO (Last In, First Out)**, di mana elemen terakhir yang dimasukkan akan menjadi elemen pertama yang keluar.

### Implementasi Stack di Java
```java
import java.util.Stack;

public class StackExample {
	public static void main(String[] args) {
		Stack<Integer> stack = new Stack<>();

		// Push elements
		stack.push(10);
		stack.push(20);
		stack.push(30);

		// Pop elements
		System.out.println("Popped: " + stack.pop());  // 30
		System.out.println("Peek: " + stack.peek());   // 20
		System.out.println("Is stack empty? " + stack.isEmpty());  // false
	}
}
```

### Ilustrasi Stack
<img src="/img/modul-4/stack.png" alt="stack">

### Rangkuman Method Stack

| Method           | Deskripsi                                                    |
|------------------|--------------------------------------------------------------|
| `push(E item)`   | Menambahkan elemen ke bagian atas stack.                     |
| `pop()`          | Menghapus dan mengembalikan elemen dari bagian atas stack.   |
| `peek()`         | Melihat elemen di bagian atas tanpa menghapusnya.            |
| `isEmpty()`      | Memeriksa apakah stack kosong.                               |
| `search(Object o)`| Mengembalikan posisi elemen dalam stack (1-based index).    |

#### Contoh Penggunaan:
```java
stack.push(10);   // Menambahkan elemen 10
stack.pop();      // Menghapus elemen dari atas
stack.peek();     // Melihat elemen paling atas
stack.isEmpty();  // Memeriksa apakah stack kosong
```

## Queue

Queue menggunakan prinsip **FIFO (First In, First Out)**, di mana elemen pertama yang masuk akan menjadi elemen pertama yang keluar.

### Implementasi Queue di Java
```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
	public static void main(String[] args) {
		Queue<Integer> queue = new LinkedList<>();

		// Enqueue elements
		queue.add(10);
		queue.add(20);
		queue.add(30);

		// Dequeue elements
		System.out.println("Dequeued: " + queue.poll());  // 10
		System.out.println("Peek: " + queue.peek());      // 20
		System.out.println("Is queue empty? " + queue.isEmpty());  // false
	}
}
```

### Ilustrasi Queue
<img src="/img/modul-4/queu.png">

### Rangkuman Method Queue

| Method           | Deskripsi                                                    |
|------------------|--------------------------------------------------------------|
| `add(E e)`       | Menambahkan elemen ke akhir queue (lempar exception jika gagal). |
| `offer(E e)`     | Menambahkan elemen ke akhir queue (mengembalikan `false` jika gagal). |
| `poll()`         | Menghapus dan mengembalikan elemen dari awal queue, atau `null` jika kosong. |
| `remove()`       | Sama seperti `poll()` tetapi lempar exception jika kosong.   |
| `peek()`         | Melihat elemen di awal queue tanpa menghapusnya, atau `null` jika kosong. |
| `isEmpty()`      | Memeriksa apakah queue kosong.                               |

#### Contoh Penggunaan:
```java
queue.add(10);    // Menambahkan elemen ke akhir
queue.poll();     // Menghapus elemen dari awal
queue.peek();     // Melihat elemen paling depan
queue.isEmpty();  // Memeriksa apakah queue kosong
```

---

## Deque

Deque (Double Ended Queue) adalah struktur data yang memungkinkan penambahan dan penghapusan elemen di kedua ujung, baik depan maupun belakang.

### Implementasi Deque di Java
```java
import java.util.Deque;
import java.util.ArrayDeque;

public class DequeExample {
	public static void main(String[] args) {
		Deque<Integer> deque = new ArrayDeque<>();

		// Add elements to both ends
		deque.addFirst(10);
		deque.addLast(20);
		deque.addFirst(5);

		// Remove elements from both ends
		System.out.println("Removed from front: " + deque.removeFirst());  // 5
		System.out.println("Removed from back: " + deque.removeLast());    // 20
		System.out.println("Peek front: " + deque.peekFirst());            // 10
		System.out.println("Peek back: " + deque.peekLast());              // 10
	}
}
```

### Ilustrasi Deque
<img src="/img/modul-4/deque.png">

### Rangkuman Method Deque

| Method              | Deskripsi                                                    |
|---------------------|--------------------------------------------------------------|
| `addFirst(E e)`     | Menambahkan elemen ke depan deque.                           |
| `addLast(E e)`      | Menambahkan elemen ke belakang deque.                        |
| `removeFirst()`     | Menghapus dan mengembalikan elemen dari depan deque.         |
| `removeLast()`      | Menghapus dan mengembalikan elemen dari belakang deque.      |
| `peekFirst()`       | Melihat elemen di depan deque tanpa menghapusnya.            |
| `peekLast()`        | Melihat elemen di belakang deque tanpa menghapusnya.         |
| `pollFirst()`       | Menghapus dan mengembalikan elemen dari depan deque, atau `null` jika kosong. |
| `pollLast()`        | Menghapus dan mengembalikan elemen dari belakang deque, atau `null` jika kosong. |
| `offerFirst(E e)`   | Menambahkan elemen ke depan deque, mengembalikan `false` jika gagal. |
| `offerLast(E e)`    | Menambahkan elemen ke belakang deque, mengembalikan `false` jika gagal. |
| `isEmpty()`         | Memeriksa apakah deque kosong.                               |

#### Contoh Penggunaan:
```java
deque.addFirst(5);    // Menambahkan elemen ke depan
deque.addLast(10);    // Menambahkan elemen ke belakang
deque.removeFirst();  // Menghapus elemen dari depan
deque.removeLast();   // Menghapus elemen dari belakang
deque.peekFirst();    // Melihat elemen paling depan
deque.peekLast();     // Melihat elemen paling belakang
```

## Latihan
https://docs.google.com/document/d/1K08p3b0UN6xNo4zul2q3syPO82zWhRvMfEJvsyDaBjQ/edit?usp=sharing
