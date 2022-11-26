# Pertemuan10-Praktikum5

***Repositiry ini dibuat untuk memenuhi tugas Pertemuan 10 - Bahasa Pemrograman (Module Praktikum 5)***

Nama : Ghamma Pramana Putra Setyadin

Kelas : TI.22.B1

Nim : 312210247

Dosen : Agung Nugroho, M.Kom

Matkul : Bahasa Pemograman

Pada halaman ini (Tugas Pertemuan-9-Module Praktikum 5) Dosen memberi tugas sebagai berikut :

- ***Soal Latihan yang ada pada module praktikum 5***

  ![image](https://user-images.githubusercontent.com/115474950/204111864-f2fc35fd-b6be-465d-bba8-33449b1bbc20.png)

  ***Berikut adalah program syntax yang saya buat untuk memenuhi latihan module 5***
```  
print("===================================================================")
print("Nama         :   Ghamma Pramana Putra Setyadin")
print("NIM          :   312210247")
print("Kelas        :   TI.22.B1")
print("Mata Kuliah  :   Bahasa Pemrograman")
print("===================================================================")

# Buat dictionary daftar kontak
print("Buat dictionary nama sebagai key, dan nomor sebagai value")

isi = {'Ari': '081267888', 'Dina': '087677776'}
print("Nama | Nomor kontak")
print(isi)

print("Tampilkan Kontaknya Ari")
print(isi['Ari'])

print("Tambah kontak baru dengan nama Riko, nomor 087654544")
isi['Riko']= '087654544'
print(isi)

print("Ubah kontak Dina dengan nomor baru 088999776")
isi['Dina']= '088999777'
print(isi)

print("Tampilkan semua Nama")
print(isi.keys())

print("Tampilkan semua Nomor")
print(isi.values())

print("Tampilkan daftar Nama dan nomornya")
print(isi.items())

print("Hapus kontak Dina")
del isi['Dina']
print(isi)

print("===================================================================")
```
![Screenshot (103)](https://user-images.githubusercontent.com/115474950/204112131-66239972-c529-4c2d-bf5c-d203b61adfdc.png)

![Screenshot (104)](https://user-images.githubusercontent.com/115474950/204112142-b6370c76-3f37-4c70-800c-b0690c924d6b.png)

   ***Ini adalah hasil run dari syntax latihan module 5 yang saya buat***
  
  ![Screenshot (103)](https://user-images.githubusercontent.com/115474950/204112231-67e05ad4-2172-4eb9-bc67-af699d249b44.png)

- ***Soal Tugas Praktikum yang ada pada module praktikum 5 adalah sebagai berikut***

  ![image](https://user-images.githubusercontent.com/115474950/204112345-aac920b7-5fea-40df-989c-97215964c5d6.png)
  
  ***Berikut hasil yang diinginkan pada soal praktikum 5***
  
  ![image](https://user-images.githubusercontent.com/115474950/204112375-88ed55b7-7af9-4dd3-8548-70e3cc413306.png)
  
  ![image](https://user-images.githubusercontent.com/115474950/204112387-727d950b-815d-476c-b758-ef67f7e1f996.png)

- ***Setelah memahami materi saya membuat syntax sebagai berikut untuk memenuhi tugas praktikum module 5 :***
```  
from prettytable import PrettyTable

print("===================================================================")
print("Nama         :   Ghamma Pramana Putra Setyadin")
print("NIM          :   312210247")
print("Kelas        :   TI.22.B1")
print("Mata Kuliah  :   Bahasa Pemrograman")
print("===================================================================")

baris = []
x = PrettyTable()

while True:
    print("[ (L)ihat , (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar ]")
    tanya = input("Masukkan Pilihan : ")
    if tanya == "L":
        print("==== Daftar Nilai ====")
        no = 0
        no += 1
        x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
        if not baris:
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            print("Not Data")
        else:
            for data in baris:
                x.add_row([no, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
            print(x)
    elif tanya == "T":
        print("Tambah Data ")
        nim_v = input("NIM : ")
        nama_v = input("Nama Lengkap : ")
        uts_v = input("Nilai UTS : ")
        uas_v = input("Nilai UAS : ")
        tugas_v = input("Nilai Tugas : ")
        akhir_v = 0.3 * float(tugas_v) + 0.35 * float(uts_v) + 0.35 * float(uas_v)
        baris.append({"nim": nim_v, "nama": nama_v, "tugas": tugas_v, "uts": uts_v, "uas": uas_v, "akhir": akhir_v})
        print()
        print("==== Daftar Nilai ====")
        i = 0
        for data in baris:
            i += 1
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
        print(x)
    elif tanya == "U":
        print("Edit File")
        print("Data siapa yang akan diubah ?")
        siapa = input("Masukkan NIM Mahasiswa yang akan diubah : ")

        print("Data apa yang akan diubah ? : ")
        mhs = input(" 1. Nama \n 2. Nilai Tugas \n 3. Nilai UTS \n 4. Nilai UAS\n Pilih dengan angka (1/2/3/4) : ")
        if mhs == "1":
            ubahnama = input("Silahkan masukan nama yang benar : ")
            i = 0
            d = next(item for item in baris if item['nim'] == siapa)
            d['nama'] = ubahnama
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            i += 1
            x.add_row([i, d["nim"], d["nama"], d["tugas"], d["uts"], d["uas"], d["akhir"]])
            print(x)
        elif mhs == "2":
            ubahtugas = input("Masukkan Nilai Tugas yang benar : ")
            i = 0
            d = next(item for item in baris if item['nim'] == siapa)
            d['tugas'] = ubahtugas
            lihatuts = d['uts']
            lihatuas = d['uas']
            lihatakhir = 0.3 * float(ubahtugas) + 0.35 * float(lihatuts) + 0.35 * float(lihatuas)
            d['akhir'] = lihatakhir
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            for data in baris:
                i += 1
                x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
            print(x)
        elif mhs == "3":
            ubahuts = input("Masukkan Nilai UTS yang benar : ")
            i = 0
            d = next(item for item in baris if item['nim'] == siapa)
            d['uts'] = ubahuts
            lihattugas = d['tugas']
            lihatuas = d['uas']
            lihatakhir = 0.3 * float(lihattugas) + 0.35 * float(ubahuts) + 0.35 * float(lihatuas)
            d['akhir'] = lihatakhir
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            for data in baris:
                i += 1
                x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
            print(x)
        elif mhs == "4":
            ubahuas = input("Masukkan Nilai UAS yang benar : ")
            i = 0
            d = next(item for item in baris if item['nim'] == siapa)
            d['uas'] = ubahuas
            lihattugas = d['tugas']
            lihatuts = d['uts']
            lihatakhir = 0.3 * float(lihattugas) + 0.35 * float(lihatuts) + 0.35 * float(ubahuas)
            d['akhir'] = lihatakhir
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            for data in baris:
                i += 1
                x.add_row([i, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
            print(x)
        else:
            print("Pilihan Salah")

    elif tanya == "C":
        print(" ========== Pencarian Data ==========")
        print(" Pencarian berdasarkan NIM ")
        carinim = input("Masukkan NIM yang akan dicari : ")
        xdata = next(item for item in baris if item['nim'] == carinim)
        print("NIM : ", carinim)
        print("Nama : ", xdata['nama'])
        print("Nilai Tugas : ", xdata['tugas'])
        print("Nilai UTS : ", xdata['uts'])
        print("Nilai UAS : ", xdata['uas'])
        print("Nilai Akhir : ", xdata['akhir'])
    elif tanya == "H":
        print("Hapus Data Berdasarkan NIM")
        datahapus = input("Masukkan NIM data yang akan dihapus : ")
        xhapus = next(item for item in baris if item['nim'] == datahapus)
        del xhapus['nim']
        del xhapus['nama']
        del xhapus['tugas']
        del xhapus['uts']
        del xhapus['uas']
        del xhapus['akhir']
        print("Data Berhasil Dihapus")
        no = 0
        no += 1
        x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
        if not baris:
            x.field_names = ["No", "NIM", " NAMA", "TUGAS", "UTS", "UAS", "AKHIR"]
            print("Not Data")
        else:
            for data in baris:
                x.add_row([no, data["nim"], data["nama"], data["tugas"], data["uts"], data["uas"], data["akhir"]])
            print(x)

    elif tanya == "K":
        print("Anda Keluar Dari Aplikasi")
        break
    else:
        print("Anda Memilih Pilihan Yang Salah")
```
- ***Berikut ini adalah hasil run dari syntax diatas akan diuraikan satu persatu***

- **Lihat data sebelum data ditambahkan**
  
  ![Screenshot (109)](https://user-images.githubusercontent.com/115474950/204112870-2283e946-c2fd-4cbe-ad81-36a5bb160136.png)

- **Tambah data**
  
  ![Screenshot (110)](https://user-images.githubusercontent.com/115474950/204112884-3dfc50af-f3d6-4af5-8bc5-a115466c4bd6.png)

- **Lihat setelah tambah data**
  
  ![Screenshot (111)](https://user-images.githubusercontent.com/115474950/204112934-2288acb6-0096-4f60-b74e-345edb21195a.png)

- **Ubah data, dan pada gambar dibawah adalah hasil dari perubahan data**
  
  ![Screenshot (112)](https://user-images.githubusercontent.com/115474950/204112966-970b2ab7-6345-4590-a452-271b12b2e155.png)

- **Mencari data yang diinputkan**
  
  ![Screenshot (113)](https://user-images.githubusercontent.com/115474950/204112990-1fb654bd-4e57-4c40-83e6-5628a06cf2b8.png)
  
- **Menghapus data yang diinputkan**

  ![Screenshot (110)](https://user-images.githubusercontent.com/115474950/204113107-cfbf24eb-c819-4c9c-b729-d951d1779c9a.png)

- **Keluar dari program aplikasi**
  
  ![20411-65e93cf6-6825-4c28-b29b-a3c3420b894d (2)](https://user-images.githubusercontent.com/115474950/204113242-89e84366-e488-44b8-a061-0ffec9ea8da4.png)

**Berikut langkah langkah untuk tugas Pertemuan10 Module pratikum5, Bila ada kesalahan mohon di maafkan**

# SEKIAN TERIMA KASIH









