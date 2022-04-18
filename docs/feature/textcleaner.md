# Text Cleaner
Dalam kasus yang sesungguhnya, kalimat yang didapatkan dalam proses pengolahan teks masih terbilang kotor, seperti banyaknya simbol yang tidak penting, adanya link, simbol hashtag, atau penyebutan username, dan lain sebagainya. Untuk itulah kita harus membersihkannya. Sastrapy memiliki fitur untuk membersihkan teks dari beberapa hal di tadi.

## Penggunaannya dengan Sastrapy
Jangan lupa import dan inisialisasi terlebih dahulu dengan kode di bawah ini
```python
# Import fitur text cleaner dari Sastrapy
from Sastrapy.Cleaner.TextCleaner import CleanerTextMachine

# Inisialisasi fiturnya
machine = CleanerTextMachine()
```
### Fungsi penghapusan yang tersedia
Berikut ini adalah beberapa fungsi penghapusan yang tersedia
```python
machine.cleanNumber(data)     # Akan membersihkan semua angka
machine.cleanUrl(data)        # Akan membersihkan link
machine.cleanHashtag(data)    # Akan membersihkan hashtag #text
machine.cleanMention(data)    # Akan membersihkan mention @nama
machine.cleanSymbol(data)     # Akan membersihkan symbol
```
### Menghapus kata pendek
Fitur ini digunakan ketika ada kata yang pendek dan tidak bermakna, misalnya `s` atau `sa` dan lain sebagainya.
```python
# Akan membersihkan huruf yang panjangnya satu karakter saja
machine.cleanSingleChar(dara) 

# Akan membersihkan huruf yang panjangnya lebih kecil 
# dari yang telah ditetapkan
machine.cleanMinChar(data, length)
```

### Mode penghapusan custom
Jika ingin menggunakan mode penghapusan custom, gunakan kode di bawah ini. Akan tetapi, pastikan kalian sudah memahami regex.
```python
# Akan membersihkan data sesuai pattern regex yang ditentukan
machine.cleanCustom(pattern, data)
```

### Mode Deep Clean
Jika ingin membersihkan kalimat dari angka, simbol, url, dan lainnya
```python
# Akan membersihkan semua url, angka, 
# mention, hashtag, dan symbol
machine.deepClean(data)

```