# Tugas-Kriptografi
Langkah-langkah Enkripsi
Buat Matriks Kunci:

Kunci: "TEKNIK INFORMATIKA" -> Hilangkan huruf berulang.

Matriks:

Copy
``` T E K N I
F O R M A
B C D G H
L P Q S U
V W X Y Z ```
Pisahkan Teks:

Contoh: "GOOD BROOM SWEEP CLEAN"

Jadikan pasangan: GO OD BR OM SW EE PC LE AN

Aturan Enkripsi:

• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kanannya (dengan wrap-around).
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris.

Contoh: "GO" -> G di (3,4) dan O di (2,2) jadi "CD".

Langkah-langkah Dekripsi
Kebalikan proses enkripsi:
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).
• Jika pasangan huruf berada dalam kolom yang sama, gantikan dengan huruf di atasnya (dengan wrap-around).
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris.

Contoh Enkripsi dan Dekripsi
GOOD BROOM SWEEP CLEAN:
Enkripsi: GO OD BR OM SW EE PC LE AN -> CT DR FM CO VW HH QC NM RN

Dekripsi: CT DR FM CO VW HH QC NM RN -> GO OD BR OM SW EE PC LE AN
