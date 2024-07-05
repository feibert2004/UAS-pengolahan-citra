# UAS-pengolahan-citra


Nama      : Feibert Sianturi

Kelas     : TI.22.a5

NIM       : 312210578

Teknik Informatika

Dosen Pengajar Muhammad Fatchan, S.kom, M.kom, MTCNA



# source kode

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Baca tiga gambar dari file
image1 = cv2.imread('images/Sepatu.jpeg')
image2 = cv2.imread('images/Sepatu 2.jpeg')
image3 = cv2.imread('images/Sepatu 3.jpeg')

# Periksa apakah semua gambar berhasil dibaca
if image1 is None or image2 is None or image3 is None:
    print("Salah satu atau lebih gambar tidak ditemukan")
else:
    # Ubah warna dari BGR ke RGB untuk ketiga gambar
    image1_rgb = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
    image2_rgb = cv2.cvtColor(image2, cv2.COLOR_BGR2RGB)
    image3_rgb = cv2.cvtColor(image3, cv2.COLOR_BGR2RGB)

    # Sesuaikan ukuran gambar jika diperlukan agar memiliki tinggi yang sama
    height = min(image1.shape[0], image2.shape[0], image3.shape[0])
    image1_rgb = cv2.resize(image1_rgb, (int(image1.shape[1] * height / image1.shape[0]), height))
    image2_rgb = cv2.resize(image2_rgb, (int(image2.shape[1] * height / image2.shape[0]), height))
    image3_rgb = cv2.resize(image3_rgb, (int(image3.shape[1] * height / image3.shape[0]), height))

    # Gabungkan ketiga gambar secara horizontal
    combined_image = cv2.hconcat([image1_rgb, image2_rgb, image3_rgb])

    # Tampilkan gambar gabungan
    plt.imshow(combined_image)
    plt.axis('off')  # Menyembunyikan sumbu
    plt.show()



    # Output

    
    
    
    
    ![Sepatu](https://github.com/feibert2004/UAS-pengolahan-citra/assets/123952371/7b5a148c-350a-4482-ae9c-2fe487b48399)




    # Mentahan Data Gambar


    
    
    
    ![DATA](https://github.com/feibert2004/UAS-pengolahan-citra/assets/123952371/aad64b40-b481-4f17-be94-9fc29f49e61f)


