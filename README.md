# SMT2-Logika-Informatika-Pert2
# DWI YANUAR PRASETIA
# TI.24.A1
# 312410107
# SOAL


# INPUT PROGRAM
'''python
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
