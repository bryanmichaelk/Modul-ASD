## Daftar Isi

- [Pendahuluan](#pendahuluan)
    - [Apa itu Swing?](#apa-itu-swing)
    - [Top-Level Containers](#1-top-level-containers)
    - [Intermediat Containers](#2-intermediate-containers)
    - [Atomic Containers](#3-atomic-components)
- [GUI Sederhana](#membuat-gui-sederhana)
- [Layout Manager](#layout-manager)
- [Event Handling](#event-handling)
- [Membuat Multipanel GUI](#membuat-program-gui-multi-panel)
---

## **Pendahuluan**

### Apa itu Swing?

- Swing adalah library GUI yang merupakan bagian dari **Java Foundation Classes (JFC)**.
- Memberikan elemen GUI yang lebih canggih dibandingkan **AWT (Abstract Window Toolkit)**.
- Platform-independen karena berbasis Java.

---

#### **1. Top-level Containers**

##### Pengertian:

- **Top-level containers** adalah komponen tertinggi dalam hierarki Swing. Mereka bertindak sebagai "jendela utama" atau "jendela dialog" dalam sebuah aplikasi GUI.
- Tidak dapat ditambahkan ke komponen lain karena merupakan _root_ dari semua komponen GUI.

##### Contoh:

1. **`JFrame`**: Jendela utama aplikasi.
2. **`JDialog`**: Dialog (jendela pop-up) yang dapat bersifat modal atau non-modal.
3. **`JApplet`**: (Deprecated) Digunakan untuk aplikasi berbasis web.
4. **`JWindow`**: Jendela tanpa baris judul atau dekorasi.

##### Kenapa Diperlukan:

- Setiap aplikasi GUI membutuhkan satu **Top-level Container** untuk memuat semua komponen lainnya.

---

#### **2. Intermediate Containers**

##### Pengertian:

- **Intermediate Containers** adalah kontainer perantara yang digunakan untuk mengelompokkan dan mengatur tata letak komponen.
- Biasanya ditempatkan di dalam Top-level Container dan berisi komponen lain, termasuk Atomic Components atau Intermediate Containers lainnya.

##### Contoh:

1. **`JPanel`**: Kontainer fleksibel untuk menyusun komponen.
2. **`JScrollPane`**: Menyediakan area bergulir untuk komponen besar.
3. **`JTabbedPane`**: Menyusun komponen dalam bentuk tab.
4. **`JSplitPane`**: Membagi area menjadi dua bagian yang dapat diubah ukurannya.

##### Kenapa Diperlukan:

- **Intermediate Containers** membantu mengatur tata letak aplikasi dengan lebih modular.
- Mengelompokkan komponen yang memiliki fungsi serupa dalam satu kontainer mempermudah pemeliharaan.

---

#### **3. Atomic Components**

##### Pengertian:

- **Atomic Components** adalah komponen dasar dalam Swing yang tidak berfungsi sebagai kontainer. Mereka berfungsi untuk interaksi langsung dengan pengguna, seperti menampilkan teks, menerima input, atau memicu tindakan.

##### Contoh:

1. **`JButton`**: Tombol klik.
2. **`JLabel`**: Label untuk menampilkan teks atau ikon.
3. **`JTextField`**: Input teks satu baris.
4. **`JTextArea`**: Input teks multi-baris.
5. **`JCheckBox`**: Kotak centang untuk pilihan ganda.
6. **`JRadioButton`**: Tombol pilihan tunggal.
7. **`JComboBox`**: Dropdown menu.

##### Kenapa Diperlukan:

- **Atomic Components** adalah elemen yang langsung digunakan pengguna untuk berinteraksi dengan aplikasi.
---

## **Membuat GUI Sederhana**

### Langkah Dasar:

1. **Buat JFrame**: Sebagai jendela utama.
2. **Tambahkan Komponen**: Misalnya, tombol, label, dan lainnya.
3. **Tentukan Layout**: Mengatur tata letak komponen.
4. **Tambahkan Listener**: Untuk menangani interaksi pengguna.

### Contoh Kode Sederhana

```java
import javax.swing.*;

public class SimpleGUI {
    public static void main(String[] args) {
        // Membuat JFrame
        JFrame frame = new JFrame("GUI Sederhana");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Membuat JLabel
        JLabel label = new JLabel("Halo, Selamat Datang!", JLabel.CENTER);

        // Membuat JButton
        JButton button = new JButton("Klik Saya");
        button.addActionListener(e -> JOptionPane.showMessageDialog(frame, "Tombol diklik!"));

        // Menambahkan komponen ke JFrame
        frame.setLayout(new BorderLayout());
        frame.add(label, BorderLayout.CENTER);
        frame.add(button, BorderLayout.SOUTH);

        // Tampilkan JFrame
        frame.setVisible(true);
    }
}
```

---

## **Komponen Utama Swing**

1. **`JLabel`**: Menampilkan teks atau ikon.

   ```java
   JLabel label = new JLabel("Ini Label");
   ```

2. **`JButton`**: Tombol interaktif.

   ```java
   JButton button = new JButton("Tombol");
   ```

3. **`JTextField`**: Input teks satu baris.

   ```java
   JTextField textField = new JTextField(20);
   ```

4. **`JTextArea`**: Input teks multi-baris.

   ```java
   JTextArea textArea = new JTextArea(5, 20);
   ```

5. **`JCheckBox`**: Kotak centang.

   ```java
   JCheckBox checkBox = new JCheckBox("Pilihan");
   ```

6. **`JRadioButton`**: Tombol pilihan tunggal.

   ```java
   JRadioButton radioButton = new JRadioButton("Opsi");
   ```

7. **`JComboBox`**: Dropdown untuk memilih item.

   ```java
   JComboBox<String> comboBox = new JComboBox<>(new String[]{"A", "B", "C"});
   ```

8. **`JTable`**: Menampilkan data dalam tabel.
   ```java
   JTable table = new JTable(data, columnNames);
   ```

---

## **Layout Manager**

### 1. **`FlowLayout`**

Mengatur komponen secara horizontal.

```java
panel.setLayout(new FlowLayout());
```

### 2. **`BorderLayout`**

Membagi area menjadi lima bagian: **North**, **South**, **East**, **West**, dan **Center**.

```java
frame.setLayout(new BorderLayout());
```

### 3. **`GridLayout`**

Membagi area menjadi grid dengan baris dan kolom.

```java
panel.setLayout(new GridLayout(2, 2)); // 2x2 grid
```

### 4. **`BoxLayout`**

Mengatur komponen secara vertikal atau horizontal.

```java
panel.setLayout(new BoxLayout(panel, BoxLayout.Y_AXIS));
```

---

## **Event Handling**

Swing menggunakan model **Listener** untuk menangani aksi pengguna.

### Langkah Dasar:

1. Tambahkan **Listener** ke komponen.
2. Implementasikan metode yang sesuai untuk aksi tersebut.

### Contoh: Event pada Tombol

```java
JButton button = new JButton("Klik");
button.addActionListener(e -> System.out.println("Tombol diklik!"));
```

---

## **Membuat Program GUI Multi-Panel**

Untuk program dengan beberapa halaman, gunakan **CardLayout**.

### Contoh: Multi-Panel dengan CardLayout

```java
import javax.swing.*;
import java.awt.*;

public class MultiPanelGUI extends JFrame {
    private CardLayout cardLayout;
    private JPanel mainPanel;

    public MultiPanelGUI() {
        setTitle("Multi-Panel GUI");
        setSize(400, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        cardLayout = new CardLayout();
        mainPanel = new JPanel(cardLayout);

        // Tambahkan panel
        mainPanel.add(new HomePanel(), "Home");
        mainPanel.add(new SecondPanel(), "Second");

        add(mainPanel);
        cardLayout.show(mainPanel, "Home");
    }

    private class HomePanel extends JPanel {
        public HomePanel() {
            setLayout(new BorderLayout());
            JLabel label = new JLabel("Ini Halaman Utama", JLabel.CENTER);
            JButton button = new JButton("Ke Halaman Kedua");
            button.addActionListener(e -> cardLayout.show(mainPanel, "Second"));

            add(label, BorderLayout.CENTER);
            add(button, BorderLayout.SOUTH);
        }
    }

    private class SecondPanel extends JPanel {
        public SecondPanel() {
            setLayout(new BorderLayout());
            JLabel label = new JLabel("Ini Halaman Kedua", JLabel.CENTER);
            JButton button = new JButton("Kembali ke Halaman Utama");
            button.addActionListener(e -> cardLayout.show(mainPanel, "Home"));

            add(label, BorderLayout.CENTER);
            add(button, BorderLayout.SOUTH);
        }
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> {
            MultiPanelGUI gui = new MultiPanelGUI();
            gui.setVisible(true);
        });
    }
}
```


