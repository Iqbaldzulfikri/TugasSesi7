import java.util.Scanner;

public class HitungGajiLembur {

    public static void main(String[] args) {
    
        Scanner Scanner = new Scanner(System.in);

        System.out.print("Masukkan gaji bulanan: ");
        double gajiBulanan = Scanner.nextDouble();

        System.out.print("Masukkan jam lembur: ");
        int jamLembur = Scanner.nextInt();

        int upahLemburPerJam = (int) Math.ceil(gajiBulanan / 173);

        double upahLembur;
        if (jamLembur > 4) {

            upahLembur = 4 * upahLemburPerJam + (jamLembur - 4) * 2 * upahLemburPerJam;
        } else {
            upahLembur = jamLembur * upahLemburPerJam;
        }

        double totalGaji = gajiBulanan + upahLembur;

        System.out.println("Upah lembur per jam: " + upahLemburPerJam);
        System.out.println("Total gaji dengan lembur: " + totalGaji);
    }
}


public class PolaLoop {

    public static void main(String[] args) {
    
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                if (j < 3 - i) {
                    System.out.print("S ");
                } else {
                    System.out.print("O ");
                }
            }
            System.out.println(); 
        }
    }
}


import java.util.ArrayList;

class MataKuliah {

    String namaMataKuliah;
    int sks;
    double nilai;

    MataKuliah(String namaMataKuliah, int sks, double nilai) {
        this.namaMataKuliah = namaMataKuliah;
        this.sks = sks;
        this.nilai = nilai;
    }

    @Override
    public String toString() {
        return "Mata Kuliah: " + namaMataKuliah + ", SKS: " + sks + ", Nilai: " + nilai;
    }

    double getBobot() {
        if (nilai >= 85) {
            return 4.0;
        } else if (nilai >= 80) {
            return 3.5;
        } else if (nilai >= 75) {
            return 3.0;
        } else if (nilai >= 70) {
            return 2.5;
        } else if (nilai >= 65) {
            return 2.0;
        } else if (nilai >= 60) {
            return 1.5;
        } else if (nilai >= 55) {
            return 1.0;
        } else {
            return 0.0;
        }
    }
}

public class DataMahasiswa {
    public static void main(String[] args) {
        String namaMahasiswa = "Iqbal";
        int semester = 3;

        ArrayList<MataKuliah> daftarMataKuliah = new ArrayList<>();

        daftarMataKuliah.add(new MataKuliah("Nilai Dasar Shalih Akram", 2, 70.00));
        daftarMataKuliah.add(new MataKuliah("Teologi Aswaja", 2, 83.10));
        daftarMataKuliah.add(new MataKuliah("Civic Education", 2, 88.00));
        daftarMataKuliah.add(new MataKuliah("Ulumul Qur'an", 2, 80.60));
        daftarMataKuliah.add(new MataKuliah("Sejarah Pemikiran Dan Keuangan Perbankan", 2, 79.50));
        daftarMataKuliah.add(new MataKuliah("Bahasa Arab I", 2, 68.00));
        daftarMataKuliah.add(new MataKuliah("Bahasa Inggris I", 2, 72.45));
        daftarMataKuliah.add(new MataKuliah("Pengantar Ekonomi Mikro", 3, 82.00));
        daftarMataKuliah.add(new MataKuliah("Manajemen Syariah", 2, 84.50));
        daftarMataKuliah.add(new MataKuliah("Pengantar Filsafat", 2, 83.80));
        daftarMataKuliah.add(new MataKuliah("Bahasa Indonesia", 2, 80.00));

        int totalSKS = 0;
        double totalBobot = 0.0;
        for (MataKuliah mk : daftarMataKuliah) {
            totalSKS += mk.sks;
            totalBobot += mk.getBobot() * mk.sks;
        }
        double ipSemester = totalBobot / totalSKS;

        System.out.println("Nama Mahasiswa: " + namaMahasiswa);
        System.out.println("Semester: " + semester);
        System.out.println("\nDaftar Mata Kuliah:");
        for (MataKuliah mk : daftarMataKuliah) {
            System.out.println(mk);
        }

        System.out.println("\nJumlah SKS: " + totalSKS);
        System.out.printf("IP Semester: %.2f%n", ipSemester);
    }
}

