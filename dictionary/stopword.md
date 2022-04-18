# Kamus stopword
Kamus stopword  merupakan dataset yang berisi list kata stopword. Kalian bisa melihatnya pada folder `src/Sastrapy/Corpus/Dictionary` yang ada pada repository Sastrapy. Kalian juga bisa mengganti kamus sesuai dengan kamus kalian dan mengikuti format berikut
### Pastikan dalam bentuk .txt
Saat ini belum ada validasi apakah format `.txt` atau bukan. Akan tetapi, untuk meminimalisasi error, gunakan format `.txt`
### Format isi dataset
Format isi dataset adalah sebagai berikut
```
stopword1
stopword2
stopword3
```
Kata stopword ditulis satu baris satu kata. Contoh
```
aku
kamu
adalah
meskipun
```
Import dengan fungsi `importDictionary()`