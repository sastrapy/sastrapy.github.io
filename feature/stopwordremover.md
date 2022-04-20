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

### Menambahkan data kamus
Kode import di atas akan me-replace kamus default dari Sastrapy. Jika kalian ingin menambahkan data kamus tanpa me-replace nya, gunakan kode di bawah ini
```python
machine.addDictionary('path/to/more_stopword_dictionary.txt')
```
Atau bisa juga kalian masukan dalam bentuk `list`
```python
machine.addDictionary(['list', 'stopword', 'baru'])
```
!> **Important** tipe data kamus stopword  adalah list. Jadi pastikan yang diinputkan adalah list atau file `.txt` seperti pada halaman [Kamus Stopword](/dictionary/stopword.md)

### Mendapatkan data kamus
Jika kalian ingin melihat kamus yang ada di dalam Sastrapy, gunakan kode di bawah ini
```python
dictionary = machine.getDictionary()
```

### Reset kamus
Jika kalian ingin mereset kamus kembali ke pengaturan semula (kamus yang digunakan Sastrapy secara default) silahkan tambahkan kode di bawah ini sebelum proses pengolahan teks dilakukan.
```python
machine.resetDictionary()
```