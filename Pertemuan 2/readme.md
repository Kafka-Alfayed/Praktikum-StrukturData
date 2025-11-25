# Implementasi LinkedList pada Python

Program LinkedList menunjukkan cara kerja Single Linked List,  yaitu sebuah struktur data linier di mana setiap elemennya (node) terhubung satu sama lain melalui pointer (next). Tiap node menyimpan informasi dan alamat dari node yang ada setelahnya.
Berbeda dengan array, Linked List tidak menyimpan data secara berurutan di dalam memori, melainkan terhubung satu sama lain layaknya sebuah rantai.

## Kode Program

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer


class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_first(self, data):
        node = Node(data, self.head)
        self.head = node

    def insert_at_last(self, data):
        if self.head is None:
            self.head = Node(data)
        else:
            node_sekarang = self.head
            while node_sekarang.next:
                node_sekarang = node_sekarang.next

            node = Node(data)
            node_sekarang.next = node

    def insert_at(self, index, data):
        if index < 0 or index > self.length() - 1:
            print("index tidak valid")
        elif index == 0:
            self.insert_at_first(data)
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                urutan += 1
                node_sekarang = node_sekarang.next

            node = Node(data, node_sekarang.next)
            node_sekarang.next = node

    def remove_first(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        else:
            self.head = self.head.next

    def remove_last(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        elif self.head.next is None:
            self.head = None
        else:
            node_sebelumnya = None
            node_sekarang = self.head

            while node_sekarang.next:
                node_sebelumnya = node_sekarang
                node_sekarang = node_sekarang.next

            node_sebelumnya.next = None

    def remove_at(self, index):
        if index < 0 or index > self.length():
            print("index invalid")
        elif index == 0:
            self.remove_first()
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                node_sekarang = node_sekarang.next
                urutan += 1

            node_sekarang.next = node_sekarang.next.next

    def print(self):
        if self.head is None:
            print("data kosong")
        else:
            text_print = ''
            node_sekarang = self.head

            while node_sekarang:
                text_print += str(node_sekarang.data) + " -> "
                node_sekarang = node_sekarang.next

            print(text_print)

    def length(self):
        urutan = 0
        data_sekarang = self.head

        while data_sekarang:
            data_sekarang = data_sekarang.next
            urutan += 1

        return urutan


ll = LinkedList()

# insert
ll.insert_at_first("avanza")
ll.insert_at_first("yaris")
ll.insert_at_first("raize")
ll.insert_at_last("veloz")
ll.insert_at(2, "agya")

# remove
ll.remove_first()
ll.remove_last()
ll.remove_at(1)
ll.remove_at(1)

# print
ll.print()
print(ll.length())
```

## Penjelasan

1. **Pembuatan Class Node**

Pembentuk elemen paling dasar dalam sebuah linked list.

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

Node menyimpan sebuah nilai pada variabel "data" dan memiliki penunjuk "next" yang akan mengarah ke node berikutnya. Dengan adanya struktur ini, setiap elemen bisa terhubung dan membentuk sebuah rangkaian data.

2. **Inisialisasi Linked List**

Pada tahap ini, Linked List dibuat dalam keadaan kosong. Variabel head digunakan sebagai penanda awal dari list. Jika nilainya masih None, artinya belum ada node yang tersimpan.

```python
class LinkedList:
    def __init__(self):
        self.head = None
```

Variabel head digunakan sebagai penanda awal dari list. Jika nilainya masih None, artinya belum ada node yang tersimpan.

3. **insert_at_first**

Memasukkan data baru di posisi paling awal.

```python
 def insert_at_first(self, data):
        node = Node(data, self.head)
        self.head = node
```

Node yang baru akan menjadi head, sedangkan head sebelumnya akan menjadi elemen berikutnya.

4. **insert_at_last**

Menambahkan data di bagian paling akhir dari linked list.

```python
 def insert_at_last(self, data):
        if self.head is None:
            self.head = Node(data)
        else:
            node_sekarang = self.head
            while node_sekarang.next:
                node_sekarang = node_sekarang.next

            node = Node(data)
            node_sekarang.next = node
```

Program akan menelusuri node satu per satu hingga mencapai ujung list, kemudian menambahkan node baru setelah node terakhir tersebut.

5. **insert_at**

Menyisipkan data pada posisi tertentu (berdasarkan index).

```python
def insert_at(self, index, data):
        if index < 0 or index > self.length() - 1:
            print("index tidak valid")
        elif index == 0:
            self.insert_at_first(data)
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                urutan += 1
                node_sekarang = node_sekarang.next

            node = Node(data, node_sekarang.next)
            node_sekarang.next = node
```

Program akan mengecek terlebih dahulu apakah posisi yang dimasukkan valid atau tidak. Jika index bernilai 0, maka prosesnya sama seperti "insert_at_first". Jika lebih dari itu, maka program akan berjalan sampai ke node sebelum index yang dimaksud, lalu menyisipkan elemen baru di antaranya.

6. **remove_first**

Menghapus data paling depan.

```python
def remove_first(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        else:
            self.head = self.head.next
```

Jika list kosong, akan muncul pesan peringatan. Jika tidak, maka head akan dipindahkan ke node setelahnya.

7. **remove_last**

Menghapus elemen terakhir.

```python
 def remove_last(self):
        if self.head is None:
            print("tidak ada data yang bisa dihapus")
        elif self.head.next is None:
            self.head = None
        else:
            node_sebelumnya = None
            node_sekarang = self.head

            while node_sekarang.next:
                node_sebelumnya = node_sekarang
                node_sekarang = node_sekarang.next

            node_sebelumnya.next = None
```

Jika hanya ada satu node, maka head akan dikosongkan. Jika terdapat lebih dari satu node, maka sistem akan mencari node terakhir dan memutuskan hubungan dari node sebelumnya.

8. **remove_at**

Menghapus data di posisi tertentu.

```python
def remove_at(self, index):
        if index < 0 or index > self.length():
            print("index invalid")
        elif index == 0:
            self.remove_first()
        else:
            urutan = 0
            node_sekarang = self.head

            while urutan < index - 1:
                node_sekarang = node_sekarang.next
                urutan += 1

            node_sekarang.next = node_sekarang.next.next
```

Melalui fungsi ini, data bisa dihapus dari posisi tertentu. Apabila index bernilai 0, maka node pertama yang dihapus. Jika lebih dari itu, maka program akan menuju ke node sebelum target lalu menghapus node yang berada setelahnya.

9. **Menampilkan Isi Linked List**

```python
def print(self):
        if self.head is None:
            print("data kosong")
        else:
            text_print = ''
            node_sekarang = self.head

            while node_sekarang:
                text_print += str(node_sekarang.data) + " -> "
                node_sekarang = node_sekarang.next

            print(text_print)
```

Prosesnya dimulai dari head, lalu berpindah ke node berikutnya hingga mencapai None. Hasilnya ditampilkan dalam bentuk rangkaian panah (->) yang menunjukkan hubungan antar node.

10. **Menghitung Jumlah Elemen**

```python
def length(self):
        urutan = 0
        data_sekarang = self.head

        while data_sekarang:
            data_sekarang = data_sekarang.next
            urutan += 1

        return urutan
```

Method ini digunakan untuk mengetahui berapa banyak node yang tersimpan dalam Linked List. Perhitungan dilakukan dengan cara menelusuri setiap node satu per satu hingga ke bagian akhir.

10. **Bagian Kode Utama (Program yang Dijalankan)**

Bagian ini adalah contoh penggunaan seluruh fungsi di atas:

```python
ll = LinkedList()

# insert
ll.insert_at_first("avanza")
ll.insert_at_first("yaris")
ll.insert_at_first("raize")
ll.insert_at_last("veloz")
ll.insert_at(2, "agya")

# remove
ll.remove_first()
ll.remove_last()
ll.remove_at(1)
ll.remove_at(1)

# print
ll.print()
print(ll.length())
```

## Output

```python
yaris -> 
1
```

## Kesimpulan

Berdasarkan program yang telah disusun, dapat disimpulkan bahwa Linked List adalah jenis struktur data yang terbuat dari node-node yang saling terhubung melalui pointer. Setiap node menyimpan informasi dan juga referensi menuju node berikutnya, memungkinkan proses penambahan dan penghapusan elemen yang lebih fleksibel tanpa perlu menggeser data lain seperti yang terjadi pada array. Program ini menawarkan berbagai fungsi penting, termasuk menambah data di awal, akhir, atau posisi tertentu, serta menghapus elemen dari berbagai tempat. Selain itu, terdapat juga fungsi untuk menampilkan seluruh konten Linked List serta menghitung jumlah elemen yang ada. Ini menunjukkan bahwa Linked List sangat sesuai digunakan dalam situasi di mana data sering berubah dengan cepat, terutama ketika penambahan dan penghapusan elemen lebih sering terjadi dibandingkan pencarian berdasarkan indeks.
