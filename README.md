# Tugas-Kriptografi
Langkah-langkah Enkripsi
Buat Matriks Kunci:

Kunci: "TEKNIK INFORMATIKA" -> Hilangkan huruf berulang.

Matriks:
```
T E K N I
F O R M A
B C D G H
L P Q S U
V W X Y Z
```
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

Enkripsi
1. GOOD BROOM SWEEP CLEAN
Pasangan huruf: GO OD BR OM SW EE PC LE AN
Enkripsi: RN NS OG NP CX ZI KD NA KO

2. REDWOOD NATIONAL STATE PARK
Pasangan huruf: RE DW OO DN AT IO NA LS TA TE PA RK
Enkripsi: SK GO PX GO FN MO LK IE FN UN NM XA KL

3.JUNK FOOD AND HEALTH PROBLEMS
Pasangan huruf: JU NK FO OD AN DH EA LT HP RO BL EM S
Enkripsi: KT LO NR NN FN ID HM ND HP ZJ NF CM Q

Dekripsi
1. GOOD BROOM SWEEP CLEAN
Enkripsi: RN NS OG NP CX ZI KD NA KO
Dekripsi: GO OD BR OM SW EE PC LE AN

2. REDWOOD NATIONAL STATE PARK
Enkripsi: SK GO PX GO FN MO LK IE FN UN NM XA KL
Dekripsi: RE DW OO DN AT IO NA LS TA TE PA RK

3. JUNK FOOD AND HEALTH PROBLEMS
Enkripsi: KT LO NR NN FN ID HM ND HP ZJ NF CM Q
Dekripsi: JU NK FO OD AN DH EA LT HP RO BL EM S
