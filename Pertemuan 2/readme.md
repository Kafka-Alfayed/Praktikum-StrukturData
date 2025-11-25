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
