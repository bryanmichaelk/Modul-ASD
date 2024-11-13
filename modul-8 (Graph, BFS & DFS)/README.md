## Daftar Isi

- [Graph](#graph)
- [Breadth First Search](#breadth-first-search-bfs)
- [Depth First Search](#depth-first-search-dfs)
- [Perbandingan BFS dan DFS](#perbandingan-bfs-dan-dfs)

## **Graph**

- **Definisi**: Graph adalah struktur data yang terdiri dari himpunan **node** (atau **vertex**) dan **edge** (atau **sisi**) yang menghubungkan node-node tersebut. Graph banyak digunakan untuk merepresentasikan jaringan seperti jaringan sosial, jaringan komputer, atau rute transportasi.

- **Jenis Graph**:
  <img src="/img/modul-12/directed-graph.jpg">

  - **Directed Graph (Digraph)**: Setiap edge memiliki arah.
  - **Undirected Graph**: Edge tidak memiliki arah (dua arah).
    <img src="/img/modul-12/weighted-graph.png">

  - **Weighted Graph**: Setiap edge memiliki "berat" atau nilai, berguna untuk menunjukkan biaya atau jarak.
  - **Unweighted Graph**: Edge tidak memiliki nilai atau bobot khusus.

- **Representasi Graph**:
  <img src="/img/modul-12/adjacency_mat.webp">

  - **Adjacency Matrix**: Matrix yang menunjukkan hubungan antara setiap pasangan node. - Keunggulan: Memudahkan pencarian edge, tetapi memakan banyak ruang untuk graph besar yang jarang terhubung (sparse graph).
    <img src="/img/modul-12/adjacency_list.jpg">

  - **Adjacency List**: Setiap node memiliki daftar tetangga yang terhubung.
    - Keunggulan: Lebih hemat ruang, terutama untuk sparse graph.

## **Breadth First Search (BFS)**

- **Definisi**: BFS adalah algoritma pencarian yang mulai dari node awal dan menjelajahi semua node di tingkat yang sama sebelum melanjutkan ke tingkat berikutnya. BFS bekerja dengan mengunjungi node terdekat dari node awal, lalu beranjak ke node yang lebih jauh.

- **Langkah-langkah BFS**:
  1.  Tambahkan node awal ke dalam **queue**.
  2.  Tandai node tersebut sebagai telah dikunjungi.
  3.  Ambil node dari depan queue, lalu kunjungi semua tetangganya yang belum dikunjungi dan tambahkan mereka ke queue.
  4.  Ulangi proses hingga queue kosong.
- **Kelebihan**: BFS berguna untuk menemukan **shortest path** pada graph unweighted (berat edge tidak diperhitungkan).
- **Kompleksitas Waktu**: \(O(V + E)\), di mana \(V\) adalah jumlah node dan \(E\) adalah jumlah edge.

- **Contoh Implementasi BFS dalam Python**:

  ```java
  class BFS {
  	public static void bfs(Graph graph, String start) {
  		Set<String> visited = new HashSet<>();
  		Queue<String> queue = new LinkedList<>();

  		queue.add(start);
  		visited.add(start);

  		while (!queue.isEmpty()) {
  			String node = queue.poll();
  			System.out.print(node + " "); // Proses node

  			for (String neighbor : graph.getNeighbors(node)) {
  				if (!visited.contains(neighbor)) {
  					visited.add(neighbor);
  					queue.add(neighbor);
  				}
  			}
  		}
  	}
  }
  ```

## **Depth-First Search (DFS)**

- **Definisi**: DFS adalah algoritma pencarian yang mulai dari node awal, lalu menjelajahi node tetangga sedalam mungkin sebelum kembali untuk menjelajahi cabang lainnya. DFS bekerja dengan prinsip "backtracking", yaitu menjelajahi satu jalur sampai habis sebelum beralih ke jalur lain.

- **Langkah-langkah DFS**:
  1.  Mulai dari node awal, tambahkan ke dalam **stack** atau gunakan rekursi.
  2.  Tandai node sebagai telah dikunjungi.
  3.  Kunjungi tetangga yang belum dikunjungi dengan melanjutkan ke dalam stack (untuk pendekatan iteratif) atau melalui panggilan rekursif.
  4.  Ulangi proses hingga semua node dijelajahi.
- **Kelebihan**: DFS sering digunakan untuk mencari jalur atau komponen yang terhubung, serta dalam kasus graph yang berbobot.
- **Kompleksitas Waktu**: \(O(V + E)\), sama seperti BFS.

- **Contoh Implementasi DFS dalam Java**:

  ```java
  class DFS {
  public static void dfs(Graph graph, String start, Set<String> visited) {
  if (visited.contains(start)) {
  return;
  }
  visited.add(start);
  System.out.print(start + " "); // Proses node

      	for (String neighbor : graph.getNeighbors(start)) {
      		if (!visited.contains(neighbor)) {
      			dfs(graph, neighbor, visited);
      		}
      	}
      }

  }
  ```

## **Perbandingan BFS dan DFS**

<img src="/img/modul-12/bfs-dfs.png">

- **BFS**:

  - Cocok untuk menemukan jalur terpendek dalam graph tanpa bobot.
  - Menggunakan struktur **queue**, menjelajahi level demi level.

- **DFS**:
  - Cocok untuk menjelajahi semua node dan mencari komponen yang terhubung.
  - Menggunakan **stack** (atau rekursi) dan menelusuri satu jalur sedalam mungkin sebelum backtracking.

### Contoh Graph untuk Uji Coba

```java
public class Main {
	public static void main(String[] args) {
		Graph graph = new Graph();
		graph.addEdge("A", "B");
		graph.addEdge("A", "C");
		graph.addEdge("B", "D");
		graph.addEdge("B", "E");
		graph.addEdge("C", "F");
		graph.addEdge("E", "F");

		System.out.println("BFS mulai dari A:");
		BFS.bfs(graph, "A"); // Output: A B C D E F

		System.out.println("\nDFS mulai dari A:");
		Set<String> visited = new HashSet<>();
		DFS.dfs(graph, "A", visited); // Output: A B D E F C
	}
}
```
