# Implementasi Stack pada Python

Program stack menunjukkan cara kerja tumpukan dengan prinsip LIFO (Last In, First Out). Elemen yang terakhir masuk adalah yang pertama keluar.

## Kode Program

```python
stack = []

# Push
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)

# Pop
element = stack.pop()
print("Pop: ", element)

# Peek
topElement = stack[-1]
print("Peek: ", topElement)

# isEmpty
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(stack))
```

## Penjelasan

1. **Inisialisasi Stack**
Membuat struktur data stack menggunakan list kosong.

```python
stack = []
```

2. **Push (Menambah Data)**
Menambahkan Elemen kedalam list Stack menggunakan `append()`:

```python
stack.append('A')
stack.append('B')
stack.append('C')
print("Stack: ", stack)
```

Setelah bagian ini, isi antrian: `['A', 'B', 'C']`.

3. **Pop (Menghapus Data)**
Menghapus Elemen paling kiri pada list Stack menggunakan `pop()`:

```python
element = stack.pop()
print("Pop: ", element)
```

Setelah bagian ini, isi antrian: `['A', 'B',]`.

4. **Peek (Melihat Elemen Teratas Tanpa Menghapus)**
Mengambil Elemen paling kiri pada list Stack tanpa menghapusnya:

```python
topElement = stack[-1]
print("Peek: ", topElement)
```

5. **isEmpty (Memeriksa Apakah Stack Kosong)**
Mengecek apakah list Stack kosong:

```python
isEmpty = not bool(stack)
print("isEmpty: ", isEmpty)
```
6. **Size (Menghitung Jumlah Elemen pada Stack)**
menghitung berapa banyak elemen yang tersisa dalam list Stack:

```python
print("Size: ", len(stack))
```

## Output

```python
Stack:  ['A', 'B', 'C']
Pop:  C
Peek:  B
isEmpty:  False
Size:  2
```

## Kesimpulan

Dari kode tersebut, dapat disimpulkan bahwa struktur data stack dapat diimplementasikan dengan mudah menggunakan list pada Python. Operasi stack dimulai seperti push, pop, peek, isEmpty, dan size dilakukan menggunakan metode bawaan list seperti `append()`, `pop()`, dan indeks negatif. Kode ini menunjukkan pada browser bahwa bagaimana stack bekerja berdasarkan prinsip LIFO Last In, First Out. Ini berarti dengan memasukkan elemen ke dalam stack, elemen yang terakhir direkatkan akan dikeluarkan pertama kali. Python menyediakan metode sederhana dan efisien untuk mewakili proses penyimpanan data yang diselesaikan dengan bagian yang disusun, seperti manajemen undo-redo, navigasi halaman, dan berbagai proses rekursif.

# Implementasi Queue pada Python

Program queue menunjukkan cara kerja antrian dengan prinsip FIFO (First In, First Out).
Elemen yang pertama masuk adalah yang pertama keluar.

## Kode Program

```python
queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontelement = queue[0]
print("Peek: ", frontelement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
```

## Penjelasan

1. **Inisialisasi Queue**
Membuat list kosong yang digunakan sebagai struktur data antrian.

```python
queue = []
```

2. **Enqueue (Menambahkan Elemen ke Antrian)**
Menambahkan Elemen kebagian belakang antrian menggunakan `append()`:

```python
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)
```

Setelah bagian ini, isi antrian: `['A', 'B', 'C']`.

3. **Dequeue (Mengeluarkan Elemen dari Antrian)**
menghapus dan mengambil elemen pertama pada antrian:

```python
element = queue.pop(0)
print("Dequeue: ", element)
```

Karena antrian mengikuti prinsip FIFO (First In, First Out), maka elemen pertama yang masuk adalah yang keluar lebih dulu.

4. **Peek (Melihat Elemen Depan Tanpa Menghapus)**
mengambil elemen pertama tanpa menghapusnya, hanya untuk dilihat saja:

```python
frontelement = queue[0]
print("Peek: ", frontelement)
```

5. **isEmpty (Memeriksa Apakah Queue Kosong)**
Mengecek apakah list Queue kosong:

```python
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)
```
6. **Size (Menghitung Jumlah Elemen pada Stack)**
menghitung berapa banyak elemen yang tersisa dalam antrian:

```python
print("Size: ", len(queue))
```

## Output

```python
Queue:  ['A', 'B', 'C']
Dequeue:  A
Peek:  B
isEmpty:  False
Size:  2
```

## Kesimpulan

Dari kode di atas, dapat simpulkan bahwa struktur data queue dapat mudah diimplementasikan menggunakan list pada Python. Seperti yang telah dijelaskan sebelumnya, operasi yang perlu di implementasikan adalah enqueue, dequeue, peek atau head, is_empty, dan panjang dari queue. Semua operasi tersebut dapat dilakukan menggunakan fungsi bawaan list yakni append, pop, dan operator index. Dengan kode di atas, dapat dilihat juga sudah sesuai dengan karakteristik queue yaitu FIFO atau First-In-First-out. Ini artinya, elemen pertama yang sudah diceplok akan jadi elemen yang pertama di pop atau dequeue. Implementasi di atas menunjukkan bahwa Python menyediakan cara yang sangat mudah dan efektif untuk memodelkan proses queue yang sering digunakan di berbagai aplikasi komputasi, pengolahan data, dan simulasi sistem.
