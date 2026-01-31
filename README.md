# java-hesapmakinesi
Bu proje kullanıcıdan veri alarak ,basit bir konsol tabanlı hesap makinesidir.

import java.util.Scanner;

class HesapMakinesi {

    public double toplama(double a, double b) {
        return a + b;
    }

    public double cikarma(double a, double b) {
        return a - b;
    }

    public double carpma(double a, double b) {
        return a * b;
    }

    public double bolme(double a, double b) {
        if (b == 0) {
            System.out.println("Bir sayı 0'a bölünemez!");
            return 0;
        }
        return a / b;
    }
}

public class HesapMakinesiUygulamasi {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        HesapMakinesi hesapMakinesi = new HesapMakinesi();

        int secim;

        do {
            System.out.println("\n--- HESAP MAKİNESİ ---");
            System.out.println("1 - Toplama");
            System.out.println("2 - Çıkarma");
            System.out.println("3 - Çarpma");
            System.out.println("4 - Bölme");
            System.out.println("0 - Çıkış");
            System.out.print("Seçiminiz: ");

            secim = scanner.nextInt();

            if (secim >= 1 && secim <= 4) {
                System.out.print("Birinci sayıyı girin: ");
                double sayi1 = scanner.nextDouble();

                System.out.print("İkinci sayıyı girin: ");
                double sayi2 = scanner.nextDouble();

                switch (secim) {
                    case 1:
                        System.out.println("Sonuç: " + hesapMakinesi.toplama(sayi1, sayi2));
                        break;
                    case 2:
                        System.out.println("Sonuç: " + hesapMakinesi.cikarma(sayi1, sayi2));
                        break;
                    case 3:
                        System.out.println("Sonuç: " + hesapMakinesi.carpma(sayi1, sayi2));
                        break;
                    case 4:
                        System.out.println("Sonuç: " + hesapMakinesi.bolme(sayi1, sayi2));
                        break;
                }
            } else if (secim != 0) {
                System.out.println("Geçersiz seçim!");
            }

        } while (secim != 0);

        System.out.println("Programdan çıkılıyor...");
        scanner.close();
    }
}
