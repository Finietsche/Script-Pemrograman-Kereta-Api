#include <iostream>
using namespace std;

int main() {
    // List destinasi, tanggal keberangkatan, dan harga tiket
    string destinasi[3] = {"Bandung - Surabaya", "Bandung - Jakarta", "Bandung - Yogyakarta"};
    string tanggal_keberangkatan[2] = {"13 September 2023", "14 September 2023"};
    int harga_tiket[3] = {500000, 300000, 400000};

    // Variabel untuk menyimpan inputan user
    string destinasi_terpilih;
    string tanggal_keberangkatan_terpilih;
    int jumlah_tiket;

    // Looping utama
    char pilihan;
    do {
        // Meminta user untuk memilih destinasi, tanggal, dan jumlah tiket
        cout << "== Sistem Pemesanan Tiket Kereta Api ==" << endl;
        cout << "Daftar Destinasi:" << endl;
        for (int i = 0; i < 3; ++i) {
            cout << i + 1 << ". " << destinasi[i] << endl;
        }

        cout << "Tanggal Keberangkatan Kereta" << endl;
        for (int i = 0; i < 2; ++i) {
            cout << i + 1 << ". " << tanggal_keberangkatan[i] << endl;
        }

        cout << "Pilih Destinasi (1-3): ";
        int pilihan_destinasi;
        cin >> pilihan_destinasi;

        // Validasi pilihan destinasi
        if (pilihan_destinasi < 1 || pilihan_destinasi > 3) {
            cout << "Pilihan destinasi tidak valid. Program berhenti." << endl;
            return 1;
        }

        destinasi_terpilih = destinasi[pilihan_destinasi - 1];

        cout << "Pilih Tanggal Keberangkatan (1-2): ";
        int pilihan_tanggal;
        cin >> pilihan_tanggal;

        // Validasi pilihan tanggal keberangkatan
        if (pilihan_tanggal < 1 || pilihan_tanggal > 2) {
            cout << "Pilihan tanggal keberangkatan tidak valid. Program berhenti." << endl;
            return 1;
        }

        tanggal_keberangkatan_terpilih = tanggal_keberangkatan[pilihan_tanggal - 1];

        cout << "Masukkan Jumlah Tiket Yang Akan Dipesan: ";
        cin >> jumlah_tiket;

        // Menghitung total biaya tiket
        int total_biaya = jumlah_tiket * harga_tiket[pilihan_destinasi - 1];

        // Menampilkan pesan konfirmasi pemesanan
        cout << "== Pesan Konfirmasi Pemesanan ==" << endl;
        cout << "Destinasi: " << destinasi_terpilih << endl;
        cout << "Tanggal Keberangkatan: " << tanggal_keberangkatan_terpilih << endl;
        cout << "Jumlah Tiket: " << jumlah_tiket << endl;
        cout << "Total Biaya: Rp " << total_biaya << endl;
        cout << "Terima kasih telah menggunakan jasa layanan kami!" << endl;

        // Meminta input untuk melanjutkan atau keluar dari program
        cout << "Apakah Anda ingin memesan tiket lagi? (y/n): ";
        cin >> pilihan;
    } while (pilihan == 'y' || pilihan == 'Y');

    return 0;
}
