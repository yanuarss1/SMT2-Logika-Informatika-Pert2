# SMT2-Logika-Informatika-Pert2
# DWI YANUAR PRASETIA
# TI.24.A1
# 312410107
# SOAL
-Sebuah jasa pengiriman memiliki aturan biaya yang bergantung pada beberapa faktor. Biaya dasar pengiriman ditetapkan sebesar Rp 10.000.
-Jika berat paket melebihi 5 kg, maka akan dikenakan tambahan biaya sebesar Rp 5.000. Selain itu, jika jarak pengiriman lebih dari 10 km, maka ada tambahan biaya sebesar Rp 8.000. 
-Jika pelanggan memilih layanan pengiriman express, maka akan dikenakan tambahan biaya sebesar Rp 20.000. Namun, jika pelanggan merupakan member, mereka akan mendapatkan diskon 10% dari total biaya pengiriman yang dihitung sebelum diskon. 
-Buatlah sebuah fungsi dalam Python yang dapat menghitung total biaya pengiriman berdasarkan aturan tersebut, dengan parameter berat paket, jarak pengiriman, jenis pengiriman (biasa atau express), serta status keanggotaan pelanggan (member atau non-member).

# INPUT PROGRAM
```python
def hitung_biaya_pengiriman(berat, jarak, ekspres=False, member=False):
    # Biaya dasar
    biaya = 10000
    biaya_dasar = biaya
    
    # Biaya tambahan berdasarkan berat
    biaya_berat = 5000 if berat > 5 else 0
    biaya += biaya_berat
    
    # Biaya tambahan berdasarkan jarak
    biaya_jarak = 8000 if jarak > 10 else 0
    biaya += biaya_jarak
    
    # Biaya tambahan untuk layanan ekspres
    biaya_ekspres = 20000 if ekspres else 0
    biaya += biaya_ekspres
    
    # Diskon untuk member
    diskon = 0.1 * biaya if member else 0
    biaya -= diskon
    
    return int(biaya), biaya_dasar, biaya_berat, biaya_jarak, biaya_ekspres, diskon

# Input dari pengguna
berat = float(input("Masukkan berat paket (kg): "))
jarak = float(input("Masukkan jarak pengiriman (km): "))

# Validasi input jenis pengiriman
while True:
    jenis_pengiriman = input("Masukkan jenis pengiriman (biasa/ekspres): ").strip().lower()
    if jenis_pengiriman in ["biasa", "ekspres", "express"]:
        break
    print("Input tidak valid! Harap masukkan 'biasa' atau 'ekspres'.")

# Validasi input status member
while True:
    status_member = input("Apakah Anda member? (member/non-member): ").strip().lower()
    if status_member in ["member", "non-member"]:
        break
    print("Input tidak valid! Harap masukkan 'member' atau 'non-member'.")

# Konversi input ke parameter fungsi
ekspres = jenis_pengiriman in ["ekspres", "express"]
member = status_member == "member"

# Hitung biaya pengiriman
total_biaya, biaya_dasar, biaya_berat, biaya_jarak, biaya_ekspres, diskon = hitung_biaya_pengiriman(berat, jarak, ekspres, member)

# Cetak struk
print("\n========== STRUK PENGIRIMAN ==========")
print(f"Berat Paket          : {berat} kg")
print(f"Jarak Pengiriman     : {jarak} km")
print(f"Jenis Pengiriman     : {'Ekspres' if ekspres else 'Biasa'}")
print(f"Status Member        : {'Member' if member else 'Non-Member'}")
print("--------------------------------------")
print(f"Biaya Dasar          : Rp {biaya_dasar}")
print(f"Biaya Tambahan Berat : Rp {biaya_berat}")
print(f"Biaya Tambahan Jarak : Rp {biaya_jarak}")
print(f"Biaya Layanan Ekspres: Rp {biaya_ekspres}")
print(f"Diskon Member        : Rp {int(diskon)}")
print("--------------------------------------")
print(f"Total Biaya          : Rp {total_biaya}")
print("======================================")

# OUTPUT PROGRAM
Masukkan jarak pengiriman (km): 50
Masukkan jenis pengiriman (biasa/ekspres): ekspres
Apakah Anda member? (member/non-member): member

========== STRUK PENGIRIMAN ==========
Berat Paket          : 50.0 kg
Jarak Pengiriman     : 50.0 km
Jenis Pengiriman     : Ekspres
Status Member        : Member
--------------------------------------
Biaya Dasar          : Rp 10000
Biaya Tambahan Berat : Rp 5000
Biaya Tambahan Jarak : Rp 8000
Biaya Layanan Ekspres: Rp 20000
Diskon Member        : Rp 4300
--------------------------------------
Total Biaya          : Rp 38700
======================================
PS C:\MATAKULIAH\LOGIKA INFORMATIKA> 
