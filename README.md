import java.util.ArrayList;
import java.util.List;

// Kelas utama untuk merepresentasikan Kambing
class Kambing {
    private String nama;
    private double berat;
    private double tinggi;
    private double panjang;

    // Constructor untuk inisialisasi objek Kambing
    public Kambing(String nama, double berat, double tinggi, double panjang) {
        this.nama = nama;
        this.berat = berat;
        this.tinggi = tinggi;
        this.panjang = panjang;
    }

    // Getter untuk mendapatkan informasi Kambing
    public String getInformasiKambing() {
        return "Nama: " + nama + "\nBerat: " + berat + " kg\nTinggi: " + tinggi + " cm\nPanjang: " + panjang + " cm";
    }

    // Metode untuk mengupdate informasi perkembangan Kambing
    public void updatePerkembangan(double beratBaru, double tinggiBaru, double panjangBaru) {
        this.berat = beratBaru;
        this.tinggi = tinggiBaru;
        this.panjang = panjangBaru;
    }

    // Metode untuk menandai Kambing sebagai terjual atau mati
    public void kambingTerjual() {
        System.out.println("Kambing " + nama + " telah terjual atau mati.");
    }
}

// Kelas untuk merepresentasikan data perkembangan Kambing secara bulanan
class PerkembanganBulanan {
    private int bulan;
    private List<Kambing> daftarKambing;

    // Constructor untuk inisialisasi objek PerkembanganBulanan
    public PerkembanganBulanan(int bulan) {
        this.bulan = bulan;
        this.daftarKambing = new ArrayList<>();
    }

    // Metode untuk menambahkan Kambing ke dalam daftar perkembangan bulanan
    public void tambahKambing(Kambing kambing) {
        daftarKambing.add(kambing);
    }

    // Metode untuk mendapatkan informasi perkembangan bulanan
    public void cetakInformasiPerkembangan() {
        System.out.println("\nPerkembangan pada Bulan ke-" + bulan);
        for (Kambing kambing : daftarKambing) {
            System.out.println(kambing.getInformasiKambing());
        }
    }
}

public class ProgramKambing {
    public static void main(String[] args) {
        // Membuat objek Kambing menggunakan constructor
        Kambing kambing1 = new Kambing("Kambing A", 20, 70, 90);
        Kambing kambing2 = new Kambing("Kambing B", 25, 80, 95);

        // Membuat objek PerkembanganBulanan menggunakan constructor
        PerkembanganBulanan bulan1 = new PerkembanganBulanan(1);
        bulan1.tambahKambing(kambing1);
        bulan1.tambahKambing(kambing2);

        // Menampilkan informasi perkembangan bulanan
        bulan1.cetakInformasiPerkembangan();

        // Mengupdate informasi perkembangan Kambing pada bulan berikutnya
        kambing1.updatePerkembangan(22, 75, 92);
        kambing2.updatePerkembangan(27, 85, 97);

        // Menampilkan informasi perkembangan bulanan setelah update
        bulan1.cetakInformasiPerkembangan();

        // Menandai kambing sebagai terjual atau mati
        kambing1.kambingTerjual();

        // Menambahkan perkembangan Kambing baru pada bulan berikutnya
        Kambing kambing3 = new Kambing("Kambing C", 30, 90, 100);
        bulan1.tambahKambing(kambing3);

        // Menampilkan informasi perkembangan bulanan setelah penambahan baru
        bulan1.cetakInformasiPerkembangan();
    }
}
