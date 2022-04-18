# Kamus slang
Kamus slang atau kamus singkatan merupakan dataset yang berisi kata singkatan beserta arti yang sudah ditentukan. Kalian bisa melihatnya pada folder `src/Sastrapy/Corpus/Dictionary` yang ada pada repository Sastrapy. Kalian juga bisa mengganti kamus sesuai dengan kamus kalian dan mengikuti format berikut
### Pastikan dalam bentuk .txt
Saat ini belum ada validasi apakah format `.txt` atau bukan. Akan tetapi, untuk meminimalisasi error, gunakan format `.txt`
### Format isi dataset
Format isi dataset adalah sebagai berikut
```
# Yang dibolehkan
katasingkatan;kataasli
katasingkatan;kata asli

# Yang tidak dibolehkan
kata singkatan;kata asli
```
Kata singkatan tidak boleh ada yang menggunakan spasi. Kata singkatan bisa ditulis beberapa kali. Pemisah menggunakan simbol titik koma `;`. Tidak ada spasi setelah simbol `;`. Contoh
```
tdk;tidak
km;kamu
sy;saya
nder;sender
askrl;ask real life
btw;by the way
```
Import dengan fungsi `importDictionary()`