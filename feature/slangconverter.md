# Slang Converter
Terkadang dalam proses pengolahan kata kita menemukan istilah baru yang tidak bisa diolah sebelum kita konversi terlebih dahulu. Istilah tersebut bisa sebuah singkatan, bahasa gaul, dan lain sebagainya. Untuk itulah Sastrapy menyediakan fitur untuk mengkonversi kata singkatan, atau bahasa slang ke dalam bahasa asli yang sudah ditentukan.

## Contoh proses
Misalnya ketika kita melakukan pengolahan kata terdapat kalimat seperti di bawah ini
```
"Aku mmg sngt rindu km
```
Tentu kalimat di atas terlalu sukar jika kita olah. Dengan demikian kita harus ubah terlebih dahulu ke dalam bentuk seperti ini
```
"saya memang sangat rindu kamu"
```
Kalimat di atas terlihat lebih mudah diolah bukan?

## Penggunaannya dengan Sastrapy
Seperti biasa, kita harus import fitur slang converter terlebih dahulu dan menginisialisasinya seperti di bawah ini
```python
# Import fitur slang converter dari Sastrapy
from Sastrapy.Corpus.SlangConverter import SlangConverterMachine

# Inisialisasi fitur slang converter
machine = SlangConverterMachine()
```
Jika sudah diinisialisasi, kalian bisa menggunakan fitur slang converter seperti di bawah ini

### Mengubah kata dari bentuk string
Berikut adalah cara mengubah kata dari bentuk string
```python
result = machine.convertSlang('Aku mmg sngt rindu km')
print(result) 

# Hasilnya
# saya memang sangat rindu kamu
```

### Mengubah kata dari bentuk list
Kalian juga bisa mengubah kata dari bentuk list, caranya sama dengan yang bentuk string
```python
result = machine.convertSlang(['Aku', 'mmg', 'sngt', 'rindu', 'km'])
print(result) 

# Hasilnya
# ['saya', 'memang', 'sangat', 'rindu', 'kamu']
```

### Gunakan kamus sendiri
Kalian bisa menggunakan kamus bahasa sendiri dengan menuliskan kode di bawah ini setelah proses inisialisasi
```python
machine.importDictionary('path/to/slang_dictionary.txt')
```
Kamus yang ada harus berformat `.txt` dan struktur nya bisa dilihat di halaman [Kamus Slang](/dictionary/slang.md)

### Menambahkan data kamus
Kode import di atas akan me-replace kamus default dari Sastrapy. Jika kalian ingin menambahkan data kamus tanpa me-replace nya, gunakan kode di bawah ini
```python
machine.addDictionary('path/to/more_slang_dictionary.txt')
```
Atau bisa juga kalian masukan dalam bentuk `dict`
```python
newData = {
  'cnt': 'cinta', 
  'rnd': 'rindu'
}
machine.addDictionary(newData)
```
!> **Important** tipe data kamus slang converter adalah dict bukan list. Jadi pastikan yang diinputkan adalah dict atau file `.txt` seperti pada halaman [Kamus Slang](/dictionary/slang.md)


### Mendapatkan data kamus
Jika kalian ingin melihat kamus yang ada di dalam Sastrapy, gunakan kode di bawah ini
```python
dictionary = machine.getDictionary()
```
### Reset kamus
Jika ingin mengembalikan kamus ke bentuk semula, tulis kode di bawah ini sebelum proses pengolahan kata nya
```python
machine.resetDictionary()
```