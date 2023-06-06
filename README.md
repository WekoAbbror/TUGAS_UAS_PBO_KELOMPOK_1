# TUGAS_UAS_PBO_KELOMPOK_1
Anggota :  Weko Abbror (G1A022025), Citra Azzahra Al-Fatihah (G1A022057), Ridho Herta Putra (G1A022061)

Source code:

import random  # Modul random digunakan untuk mengacak karakter dalam pembuatan password

import string  # Modul string digunakan untuk mendefinisikan karakter yang diperlukan dalam password

def Pembuat_password(length):
    # Mendefinisikan karakter yang diperlukan dalam password
    karakter = string.ascii_letters + string.digits
    
    # Memastikan setidaknya ada satu huruf besar, satu huruf kecil, dan satu angka dalam password
    huruf_kecil = False
    huruf_besar = False
    angka = False
    
    while True:
        # Mengacak karakter
        password = ''.join(random.choice(karakter) for _ in range(length))
        
        # Memeriksa apakah password memenuhi batasan
        for char in password:
            if char.isupper():
                huruf_kecil = True
            elif char.islower():
                huruf_besar = True
            elif char.isdigit():
                angka = True
        
        # Jika password memenuhi batasan, keluar dari perulangan
        if huruf_kecil and huruf_besar and angka:
            break
    
    return password

# Meminta pengguna untuk panjang password yang diinginkan
print("""UAS PEMROGRAMAN BERORIENTASI OBJEK : Membuat password dengan menggunakan phyton
======================================================================================== """)
length = int(input("\nMasukkan panjang password yang diinginkan: "))

# Membuat dan mencetak password
password = Pembuat_password(length)
print("Password yang dibuat:", password)
