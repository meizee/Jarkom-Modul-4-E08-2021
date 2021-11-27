# Jarkom-Modul-4-E08-2021

**Lapres Praktikum Jaringan Komputer Modul 4**

- Fais Rafii Akbar Hidiya (05111940000026)
- Zahra Dyah Meilani (05111940000069)
- Aji Rindra Fakhrezi Putra Faisal (05111940000205)

## **1. VLSM dengan CPT**

Berikut topologi pada soal

![topologi](./images/topologi.png)

### **a. Subnetting**

Berdasarkan topologi tersebut, didapatkan 15 pembagian subnet seperti yang terlihat pada gambar di bawah ini:

![subnet_vlsm](./images/subnet_vlsm.png)

Detail dari setiap subnet ada pada tabel di bawah:

![tabel_subnet_vlsm](./images/tabel_subnet_vlsm.png)

Dari tabel di atas diketahui bahwa subnet besar yang dibentuk mempunyai NID 10.33.0.0 dengan netmask /19. Pembagian IP berdasarkan NID dan netmask didapatkan dari hasil penghitungan menggunakan tree di bawah:

![tree_vlsm](./images/tree_vlsm.jpg)

Dari tree tersebut didapatkan pembagian IP untuk setiap node menjadi seperti berikut:

![tabel_ip_vlsm](./images/tabel_ip_vlsm.png)

Setelah itu ubah konfigurasi setiap node dengan IP serta netmask yang sesuai pada tabel dan topologi.

### **b. Routing**

Untuk melakukan routing, tambahkan static route ke semua router yang ada. Berikut merupakan route yang ditambahkan:

FOOSHA

```
10.33.12.0/22 via 10.33.27.149      #water7
10.33.24.0/23 via 10.33.27.154      #gunhao
10.33.27.0/25 via 10.33.27.149
10.33.16.0/22 via 10.33.27.154
10.33.27.128/28 via 10.33.27.154
10.33.27.160/28 via 10.33.27.162    #doriki
10.33.0.0/21 via 10.33.27.149
10.33.26.0/24 via 10.33.27.154
10.33.27.164/30 via 10.33.27.154
10.33.20.0/22 via 10.33.27.154
10.33.27.156/30 via 10.33.27.154
```

WATER7

```
0.0.0.0/0 via 10.33.27.150          #foosha
10.33.27.0/25 via 10.33.27.145      #pucci
10.33.0.0/21 via 10.33.27.145
```

PUCCI
```
0.0.0.0/0 via 10.33.27.146          #water7
```

GUANHAO

```
0.0.0.0/0 via 10.33.27.153          #foosha
10.33.27.128/28 via 10.33.24.2      #alabasta
10.33.26.0/24 via 10.33.27.158      #oimo
10.33.27.164/30 via 10.33.27.158
10.33.20.0/22 via 10.33.27.158
```

ALABASTA

```
0.0.0.0/0 via 10.33.24.1            #guanhao
```

OIMO

```
0.0.0.0/0 via 10.33.27.157          #guanhao
10.33.20.0/22 via 10.33.26.2        #seastone
```

SEASTONE

```
0.0.0.0/0 via 10.33.26.1        #oimo
```

### **c. Testing**

Untuk melakukan testing, kita bisa mencoba melakukan ping antar node, berikut merupakan contoh ping dengan source dan destination node yang sudah dicoba:

![testing_1](./images/testing_1.png)

![testing_2](./images/testing_2.png)

## **2. CIDR dengan GNS3**


### **a. Subnetting**
Pembagian subnet di CIDR dimulai dari yang terjauh dari cloud untuk mempermudah routing sehingga didapatkan subnet sebagai berikut : 

![CIDR](./images/CIDR.png)

Dan didapat tree dari subnet VLSM seperti berikut : 

![testing_3](https://github.com/meizee/Jarkom-Modul-4-E08-2021/blob/e8e48f2e9315d3e76296f6d9b145ecf94cda65db/images/Tree%20VLSM.jpeg)


### **b. Routing**
### **c. Testing**
