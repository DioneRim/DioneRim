// UAS ALGORITMA DAN PEMROGRAMAN
// DIONE RAISSA IVANA MATANY

#include <stdio.h>
#include <string.h>

int main() {
    char Username[50], Password[50];
    int kesempatan = 0;

    printf("Akses kedalam akun \n");
    while (kesempatan < 3) {
        printf("Masukkan Username : ");
        scanf("%s", Username);
        printf("Masukkan Password : ");
        scanf("%s", Password);
        
        
        if (strcmp(Username, "dionerim") == 0 && strcmp(Password, "112233") == 0) {
            printf("Selamat! Anda berhasil login \n");
            printf("Selamat Datang %s \n", Username);
            printf("------------------------------- \n\n");
            break;
        } else {
            printf("Username atau Password anda salah!! \n");
            kesempatan++;
            if (kesempatan < 3) {
                printf("Anda memiliki %d kesempatan lagi\n", 3 - kesempatan);
            } else {
                printf("Anda telah menggunakan semua kesempatan, Akses Ditolak!\n");
                return 1;  
            }
        }
    }
    
    char yn, tambah, belanjaLagi;
    char namaObat[100];
    int jumlahObat, kodeObat;
    float total, hargaObat, totalPembelian, totalSetelahPajak, uang, kembalian;

    printf("SELAMAT DATANG DI APOTEK MATANY \n \n");
    printf("------------------------------- \n");
        
    do {
        totalPembelian = 0; 

        printf("Apakah anda memiliki resep dokter? (y/n): ");
        scanf(" %c", &yn);

        if (yn == 'y' || yn == 'Y') {
            do {
                while (1) {
                    printf("List Obat Harus Dengan Resep Dokter :\n");
                    printf("%-3s %-20s %10s\n", "No", "Nama Obat", "Harga");
                    printf("%-3d %-20s Rp. %6.f \n", 1, "Omeprazole", 5800.0);
                    printf("%-3d %-20s Rp. %6.f \n", 2, "Paratusin", 17800.0);
                    printf("%-3d %-20s Rp. %6.f \n", 3, "Amoxicillin", 8300.0);
                    printf("%-3d %-20s Rp. %6.f \n", 4, "Acyclovir", 4200.0);
                    printf("%-3d %-20s Rp. %6.f \n", 5, "Rhinos", 23500.0);

                    printf("Masukkan kode obat sesuai dengan resep dokter (1-5): ");
                    scanf("%d", &kodeObat);

                    switch (kodeObat) {
                        case 1:
                            hargaObat = 5800;
                            strcpy(namaObat, "Omeprazole");
                            break;
                        case 2:
                            hargaObat = 17800;
                            strcpy(namaObat, "Paratusin");
                            break;
                        case 3:
                            hargaObat = 8300;
                            strcpy(namaObat, "Amoxicillin");
                            break;
                        case 4:
                            hargaObat = 4200;
                            strcpy(namaObat, "Acyclovir");
                            break;
                        case 5:
                            hargaObat = 23500;
                            strcpy(namaObat, "Rhinos");
                            break;
                        default:
                            printf("Kode obat tidak valid.\n");
                            continue;
                    }
                    break; 
                }

                printf("Banyak Pesanan: ");
                scanf("%d", &jumlahObat);

                total = hargaObat * jumlahObat;
                totalPembelian += total;

                printf("Apakah ingin menambah pesanan? (y/n): ");
                scanf(" %c", &tambah);

            } while (tambah == 'y' || tambah == 'Y');

        } else if (yn == 'n' || yn == 'N') {
            do {
                while (1) {
                    printf("List Obat Bebas :\n");
                    printf("%-3s %-20s %10s\n", "No", "Nama Obat", "Harga");
                    printf("%-3d %-20s Rp. %6.1f \n", 1, "Imboost Force", 23000.0);
                    printf("%-3d %-20s Rp. %6.1f \n", 2, "Paracetamol", 4100.0);
                    printf("%-3d %-20s Rp. %6.1f \n", 3, "Ibuprofen", 3800.0);
                    printf("%-3d %-20s Rp. %6.1f \n", 4, "Cetirizin", 6500.0);
                    printf("%-3d %-20s Rp. %6.1f \n", 5, "Antasidadoen", 3100.0);

                    printf("Obat apa yang anda ingin beli (1-5): ");
                    scanf("%d", &kodeObat);

                    switch (kodeObat) {
                        case 1:
                            hargaObat = 23000;
                            strcpy(namaObat, "Imboost Force");
                            break;
                        case 2:
                            hargaObat = 4100;
                            strcpy(namaObat, "Paracetamol");
                            break;
                        case 3:
                            hargaObat = 3800;
                            strcpy(namaObat, "Ibuprofen");
                            break;
                        case 4:
                            hargaObat = 6500;
                            strcpy(namaObat, "Cetirizin");
                            break;
                        case 5:
                            hargaObat = 3100;
                            strcpy(namaObat, "Antasidadoen");
                            break;
                        default:
                            printf("Kode obat tidak valid.\n");
                            continue;
                    }
                    break; 
                }

                printf("Banyak Pesanan: ");
                scanf("%d", &jumlahObat);

                total = hargaObat * jumlahObat;
                totalPembelian += total;

                printf("Apakah ingin menambah pesanan? (y/n): ");
                scanf(" %c", &tambah);

            } while (tambah == 'y' || tambah == 'Y');
        }

        totalSetelahPajak = totalPembelian * 1.10;

        printf("\n===PEMBAYARAN ===\n");
        printf("------------------------------- \n");
        printf("Jumlah bayar    : %.f\n", totalPembelian);
        printf("Pajak 10%%      : %.f\n", totalPembelian * 0.10);
        printf("TOTAL BAYAR: %.f\n", totalSetelahPajak);
        printf("------------------------------- \n");

        printf("Uang Pembayaran    : ");
        scanf("%f", &uang);

        kembalian = uang - totalSetelahPajak;
        printf("Uang Kembalian     : Rp. %.f\n", kembalian);

        printf("Apakah Anda ingin belanja lagi? (y/n): ");
        scanf(" %c", &belanjaLagi);

    } while (belanjaLagi == 'y' || belanjaLagi == 'Y');
    
    printf("TERIMAKASIH TELAH BELANJA\n");
    return 0;
}

