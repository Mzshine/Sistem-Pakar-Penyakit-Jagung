# Sistem-Pakar-Penyakit-Jagung
#Sistem Pakar Pendeteksi Gejala Penyakit Jagung

penyakit = {
    "bulai": [
        "Daun Berwarna Klorotik",
        "Mengalami retardasi pertumbuhan",
        "Warna putih seperti tepung pada permukaan atas dan bawah daun yang mengalami klorosis",
        "Daun melengkung dan bengkok",
        "Formasi bonggol yang terganggu"
    ],
    "hawar": [
        "Formasi bongkol yang terganggu",
        "Daun yang terkena terlihat layu",
        "Beberapa bercak kecil bersatu untuk membentuk titik yang lebih besar",
        "Bercak cokelat muda memanjang berbentuk kumparan atau perahu",
        "Bintik-bintik cokelat berbentuk seperti elips",
        "Daun terlihat kering"
    ],
    "karat daun": [
        "Daun terlihat kering",
        "Bintik-bintik kecil berwarna coklat atau kuning pada permukaan daun",
        "Bintik merah pada pelepah daun",
        "Ada benang berbentuk tidak beraturan yang berwarna putih dan kemudian cokelat",
        "Keluar bubuk seperti tepung berwarna coklat kekuningan"
    ],
    "terbakar": [
        "Pembengkakan pada bonggol",
        "Terdapat jamur berwarna putih hingga hitam pada bijinya",
        "Biji bengkak",
        "Kelenjar terbentuk di dalam biji",
        "bonggol terbuka dan muncul banyak jamur berwarna putih sampai hitam"
    ],
    "penggerek batang": [
        "Terdapat lubang kecil pada daun",
        "Celah di batang",
        "Batang dan rumbai-rumbai (bunga jantan) yang mudah patah",
        "Tumpukan jumbai yang rusak",
        "Bunga jantan tidak terbentuk",
        "Ada tepung/kotoran di sekitar kerekan",
        "Daun agak kuning"
    ],
    "penggerek bonggol": [
        "Lubang melintang pada daun dalam tahap vegetatif",
        "Rambut tongkol jagung dipotong / dikurangi / dikeringkan",
        "Ujung bongkolnya memiliki kerekan",
        "Seringkali ada larva"
    ]    
}

def deteksi_penyakit(pilihan_penyakit):
    gejala_terdeteksi = 0
    print(f"\nAnda memilih untuk mendeteksi {pilihan_penyakit}.")
    print(f"Berikut adalah daftar gejala {pilihan_penyakit}:")

    # Tampilkan gejala penyakit yang dipilih
    for index, gejala in enumerate(penyakit[pilihan_penyakit], start=1):
        print(f"{index}. {gejala}")

    print("\nJawab 'yes' atau 'no' untuk tiap gejala yang Anda alami.")

    # Periksa gejala satu per satu
    for gejala in penyakit[pilihan_penyakit]:
        jawaban = input(f"Apakah Anda mengalami {gejala}? ").lower()
        if jawaban == 'yes':
            gejala_terdeteksi += 1

        # Jika sudah terdeteksi 2 gejala, berhenti dan diagnosis
        if gejala_terdeteksi >= 2:
            print(f"\nHasil: Anda dipastikan terkena {pilihan_penyakit}.")
            return True

    # Jika gejala yang terdeteksi kurang dari 2
    print(f"\nHasil: Anda tidak terdeteksi terkena {pilihan_penyakit}.")
    return False

def main():
    while True:
        print("\nSelamat datang di sistem pakar deteksi penyakit!")
        print("Penyakit yang tersedia untuk dideteksi:")
        print("1. bulai")
        print("2. hawar")
        print("3. karat daun")
        print("4. terbakar")
        print("5. penggerek batang")
        print("6. penggerek bonggol")
        print("7. keluar")

        # Meminta pengguna memilih penyakit yang akan dideteksi
        pilihan = input("Masukkan nomor penyakit yang ingin Anda deteksi: ")

        if pilihan == '1':
            deteksi_penyakit("bulai")
        elif pilihan == '2':
            deteksi_penyakit("hawar")
        elif pilihan == '3':
            deteksi_penyakit("karat daun")
        elif pilihan == '4':
            deteksi_penyakit("terbakar")
        elif pilihan == '5':
            deteksi_penyakit("penggerek batang")
        elif pilihan == '6':
            deteksi_penyakit("penggerek bonggol")  
        elif pilihan == '7':
            print("Terima kasih telah menggunakan sistem ini. Sampai jumpa!")
            break
        else:
            print("Pilihan tidak valid, harap masukkan nomor yang benar.")
            continue

        # Menanyakan apakah pengguna ingin melanjutkan atau keluar
        lanjut = input("\nApakah Anda ingin mendeteksi penyakit lain? (yes/no): ").lower()
        if lanjut != 'yes':
            print("Terima kasih telah menggunakan sistem ini. Sampai jumpa!")
            break

if __name__ == "__main__":
    main()
