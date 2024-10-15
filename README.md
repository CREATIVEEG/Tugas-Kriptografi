# Tugas-Kriptografi
Nama: Rhendy Diki Nugraha<br>
Nim: 312210150<br>
Kelas: TI.22.A1<br><br>
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
Aturan Enkripsi:
<br>
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).<br>
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kanannya (dengan wrap-around).<br>
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris.<br>

<br><br>
Langkah-langkah Dekripsi<br>
Kebalikan proses enkripsi:<br>
• Jika pasangan huruf berada dalam baris yang sama, gantikan dengan huruf di kirinya (dengan wrap-around).<br>
• Jika pasangan huruf berada dalam kolom yang sama, gantikan dengan huruf di atasnya (dengan wrap-around). <br>
• Jika tidak dalam baris/kolom yang sama, buat persegi panjang dan gantikan dengan huruf di sudut yang sama baris. <br>
<br>
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

# Fungsi untuk dekripsi pasangan huruf
def decrypt_pairs(pairs, matrix):
    def find_position(c):
        for i in range(5):
            for j in range(5):
                if matrix[i][j] == c:
                    return i, j
        return -1, -1

    plaintext = []
    for pair in pairs:
        a, b = pair
        row_a, col_a = find_position(a)
        row_b, col_b = find_position(b)

        if row_a == row_b:
            plaintext.append(matrix[row_a][(col_a - 1) % 5] + matrix[row_b][(col_b - 1) % 5])
        elif col_a == col_b:
            plaintext.append(matrix[(row_a - 1) % 5][col_a] + matrix[(row_b - 1) % 5][col_b])
        else:
            plaintext.append(matrix[row_a][col_b] + matrix[row_b][col_a])

    return "".join(plaintext)

# Fungsi utama
def playfair_cipher(text, key, decrypt=False):
    matrix = generate_key_matrix(key)
    pairs = separate_pairs(text)
    if decrypt:
        result = decrypt_pairs(pairs, matrix)
    else:
        result = encrypt_pairs(pairs, matrix)
    return result

# Contoh penggunaan
key = "TEKNIKINFORMATIKA"
plaintexts = [
    "GOOD BROOM SWEEP CLEAN",
    "REDWOOD NATIONAL STATE PARK",
    "JUNK FOOD AND HEALTH PROBLEMS"
]

for plaintext in plaintexts:
    encrypted_text = playfair_cipher(plaintext, key)
    decrypted_text = playfair_cipher(encrypted_text, key, decrypt=True)
    print(f"Plaintext: {plaintext}")
    print(f"Ciphertext: {encrypted_text}")
    print(f"Decrypted text: {decrypted_text}\n")
```
<br>
Hasil Run:<br>


![Cuplikan layar 2024-10-15 090658](https://github.com/user-attachments/assets/42e0611c-91db-41c5-980b-c1d68a32db44)

<br>

## Penjelasan
Hasil Dekripsi tersebut tinggal menghapus huruf X yang terdapat pada kalimat, maka jadi kalimat asli. Dan juga ganti huruf I menjadi Huruf J jika memungkinkan untuk diganti.
