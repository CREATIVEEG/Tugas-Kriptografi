# Tugas-Kriptografi
Langkah-langkah Enkripsi <br>
Buat Matriks Kunci:
<br>
Kunci: "TEKNIK INFORMATIKA" -> Hilangkan huruf berulang.
<br>
Matriks:
```
T E K N I
F O R M A
B C D G H
L P Q S U
V W X Y Z
```
Pisahkan Teks:
<br>
Contoh: "GOOD BROOM SWEEP CLEAN"
<br>
Jadikan pasangan: GO OD BR OM SW EE PC LE AN
<br>
Aturan Enkripsi:
<br>
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kanannya (dengan wrap-around).
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris.
<br>
Contoh: "GO" -> G di (3,4) dan O di (2,2) jadi "CD".
<br>
Langkah-langkah Dekripsi
Kebalikan proses enkripsi:
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).
• Jika pasangan huruf berada dalam kolom yang sama, gantikan dengan huruf di atasnya (dengan wrap-around).
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris.

Enkripsi <br>
1. GOOD BROOM SWEEP CLEAN <br>
Pasangan huruf: GO OD BR OM SW EE PC LE AN <br>
Enkripsi: RN NS OG NP CX ZI KD NA KO <br>
<br>
2. REDWOOD NATIONAL STATE PARK <br>
Pasangan huruf: RE DW OO DN AT IO NA LS TA TE PA RK <br>
Enkripsi: SK GO PX GO FN MO LK IE FN UN NM XA KL <br>
<br>
3.JUNK FOOD AND HEALTH PROBLEMS <br>
Pasangan huruf: JU NK FO OD AN DH EA LT HP RO BL EM S <br>
Enkripsi: KT LO NR NN FN ID HM ND HP ZJ NF CM Q <br>
<br> 
Dekripsi <br> 
1. GOOD BROOM SWEEP CLEAN <br>
Enkripsi: RN NS OG NP CX ZI KD NA KO <br>
Dekripsi: GO OD BR OM SW EE PC LE AN <br>
<br>
2. REDWOOD NATIONAL STATE PARK <br>
Enkripsi: SK GO PX GO FN MO LK IE FN UN NM XA KL <br>
Dekripsi: RE DW OO DN AT IO NA LS TA TE PA RK <br>
<br>
3. JUNK FOOD AND HEALTH PROBLEMS <br>
Enkripsi: KT LO NR NN FN ID HM ND HP ZJ NF CM Q <br>
Dekripsi: JU NK FO OD AN DH EA LT HP RO BL EM S <br>
