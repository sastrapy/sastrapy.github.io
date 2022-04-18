# Stopword Remover
Stopword merupakan sebuah kata yang tidak memiliki arti signifikan di dalam kalimat seperti kata sambung, kata ganti, dan lainnya. Biasanya stopword akan dihapus dari kalimat untuk memfilter kata yang memang digunakan saja. 

## Penggunaannya dengan Sastrapy
Untuk menggunakan fitur stopword ini, kita harus import fungsinya terlebih dahulu dan menginisialisasinya. Di dalam projek kalian, silahkan import dan inisialisasi dengan kode di bawah ini
```python
# Import fungsi stopword remover
from Sastrapy.Corpus.StopwordRemover import StopwordRemoverMachine

# Inisialisasi terlebih dahulu
machine = StopwordRemoverMachine()
```
Selanjutnya kita sudah bisa menggunakan fungsi stopword remover seperti di bawah ini

### Proses menghapus stopword dari string
Berikut adalah contoh proses menghapus stopword dari string
```python
result = machine.removeStopword('Aku sangat merindukan dirimu')
print(result) 

# Hasilnya adalah
# merindukan
```

### Proses menghapus stopword dari list
Berikut adalah contoh proses menghapus stopword dari list
```python
result = machine.removeStopword(['Aku', 'sangat', 'merindukan', 'dirimu'])
print(result) 

# Hasilnya adalah
# ['merindukan']
```

### Gunakan kamus stopword sendiri
Jika kalian ingin menggunakan kamus stopword sendiri, silahkan tambahkan kode di bawah setelah proses inisialisasi
```python
machine.importDictionary('path/to/stopword_dictionary.txt')
```
Kamus stopword harus dalam format `.txt` dengan format mengikuti panduan yang ada di dalam halaman [Kamus Stopword](/dictionary/stopword.md)

### Reset kamus
Jika kalian ingin mereset kamus kembali ke pengaturan semula (kamus yang digunakan Sastrapy secara default) silahkan tambahkan kode di bawah ini sebelum proses pengolahan teks dilakukan.
```python
machine.resetDictionary()
```