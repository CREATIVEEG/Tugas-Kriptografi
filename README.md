# Tugas-Kriptografi
<b>Nama: Rhendy Diki Nugraha<b><br>
<b>Nim: 312210150<b><br>
<b>Kelas: TI.22.A1<b><br><br>
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
<br><br>
Langkah-langkah Dekripsi
Kebalikan proses enkripsi:
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).
• Jika pasangan huruf berada dalam kolom yang sama, gantikan dengan huruf di atasnya (dengan wrap-around).
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris.

Berikut dikerjakan dalam code Python:
```
# Fungsi untuk membuat matriks kunci
def generate_key_matrix(key):
    key = "".join(sorted(set(key), key=key.index))
    alphabet = "ABCDEFGHIKLMNOPQRSTUVWXYZ"
    key += "".join([c for c in alphabet if c not in key])
    matrix = [list(key[i:i + 5]) for i in range(0, 25, 5)]
    return matrix

# Fungsi untuk memisahkan plaintext
def separate_pairs(plaintext):
    plaintext = plaintext.replace(" ", "").upper().replace("J", "I")
    pairs = []
    i = 0
    while i < len(plaintext):
        a = plaintext[i]
        if i + 1 < len(plaintext):
            b = plaintext[i + 1]
            if a != b:
                pairs.append(a + b)
                i += 2
            else:
                pairs.append(a + "X")
                i += 1
        else:
            pairs.append(a + "X")
            i += 1
    return pairs

# Fungsi untuk enkripsi pasangan huruf
def encrypt_pairs(pairs, matrix):
    def find_position(c):
        for i in range(5):
            for j in range(5):
                if matrix[i][j] == c:
                    return i, j
        return -1, -1

    ciphertext = []
    for pair in pairs:
        a, b = pair
        row_a, col_a = find_position(a)
        row_b, col_b = find_position(b)

        if row_a == row_b:
            ciphertext.append(matrix[row_a][(col_a + 1) % 5] + matrix[row_b][(col_b + 1) % 5])
        elif col_a == col_b:
            ciphertext.append(matrix[(row_a + 1) % 5][col_a] + matrix[(row_b + 1) % 5][col_b])
        else:
            ciphertext.append(matrix[row_a][col_b] + matrix[row_b][col_a])

    return "".join(ciphertext)

# Fungsi utama
def playfair_cipher(text, key):
    matrix = generate_key_matrix(key)
    pairs = separate_pairs(text)
    ciphertext = encrypt_pairs(pairs, matrix)
    return ciphertext

# Contoh penggunaan
key = "TEKNIKINFORMATIKA"
plaintexts = [
    "GOOD BROOM SWEEP CLEAN",
    "REDWOOD NATIONAL STATE PARK",
    "JUNK FOOD AND HEALTH PROBLEMS"
]

for plaintext in plaintexts:
    encrypted_text = playfair_cipher(plaintext, key)
    print(f"Plaintext: {plaintext}\nCiphertext: {encrypted_text}\n")
```
<br>
Hasil Run:<br>

![Cuplikan layar 2024-10-15 085931](https://github.com/user-attachments/assets/faea23f8-a8c5-4cb2-9d9b-529966cb7fe7)

