# Tokenization
Fitur ini digunakan untuk membuat token dari kata yang dimasukan. Token artinya pemenggalan per kata dari tipe data `string` menjadi `list`. Tujuan proses tokenization ini adalah untuk memenggal sebuah kalimat menjadi kata per kata sehingga memudahkan kita dalam memproses kata yang ada di dalam kalimat tersebut.

## Contoh proses
Misalnya kita memiliki kata seperti di bawah ini
```
"Hari ini adalah hari yang indah"
```
Setelah proses tokenization, hasilnya seperti di bawah ini
```
["Hari", "ini", "adalah", "hari", "yang", "indah"]
``` 

## Proses dengan Sastrapy
Untuk menjalankan fungsi tokenization, ikuti kode di bawah ini.
```python
# Import fungsi tokenize dari sastrapy

from Sastrapy.WordTokenize.Tokenize import tokenize

result = tokenize("Hari ini adalah hari yang indah")
print(result) 

# Hasilnya seperti di bawah ini
# ["Hari", "ini", "adalah", "hari", "yang", "indah"]
```