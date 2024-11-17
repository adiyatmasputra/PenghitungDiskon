# PenghitungDiskon
 latihan 3 (Adiyatma saputra 2210010115)

Berikut adalah README.md yang mencakup penjelasan aplikasi dan kode sumbernya

Aplikasi Perhitungan Diskon
Deskripsi Proyek

Aplikasi Perhitungan Diskon adalah program berbasis Java Swing yang dibuat untuk menghitung harga akhir setelah diskon dan menampilkan jumlah penghematan. Aplikasi ini dibangun menggunakan NetBeans dan memanfaatkan komponen GUI seperti JFrame, JPanel, JLabel, JTextField, JComboBox, dan JButton.
Fitur Utama

    Input Harga Asli: Pengguna dapat memasukkan harga asli barang.
    Pilihan Persentase Diskon: Pengguna dapat memilih persentase diskon dari daftar yang disediakan.
    Perhitungan Otomatis: Aplikasi menghitung penghematan dan harga akhir setelah diskon.
    Tampilan Hasil: Menampilkan hasil penghitungan harga akhir dan penghematan di antarmuka pengguna.
    Penanganan Kesalahan: Menampilkan pesan kesalahan jika input tidak valid (misalnya, input bukan angka).

Kode Sumber Aplikasi

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
import javax.swing.JOptionPane;
/**
 *
 * @author User
 */
public class PerhitunganDiskonForm extends javax.swing.JFrame {

    /**
     * Creates new form PerhitunganDiskonForm
     */
    public PerhitunganDiskonForm() {
        initComponents();
    }

    @SuppressWarnings("unchecked")
    private void initComponents() {
        jPanel1 = new javax.swing.JPanel();
        txtHargaAsli = new javax.swing.JLabel();
        jLabel2 = new javax.swing.JLabel();
        txtHargaAkhir = new javax.swing.JLabel();
        jLabel4 = new javax.swing.JLabel();
        jTextField1 = new javax.swing.JTextField();
        jTextField2 = new javax.swing.JTextField();
        comboDiskon = new javax.swing.JComboBox<>();
        jLabel5 = new javax.swing.JLabel();
        lblPenghematan = new javax.swing.JLabel();
        jButton1 = new javax.swing.JButton();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        txtHargaAsli.setText("Harga Asli");
        jLabel2.setText("Persentase Diskon");
        txtHargaAkhir.setText("Harga Akhir");
        jLabel4.setText("Penghematan");
        comboDiskon.setModel(new javax.swing.DefaultComboBoxModel<>(new String[] { "10", "20", "30", "40", "50" }));

        jButton1.setText("HITUNG");
        jButton1.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                jButton1ActionPerformed(evt);
            }
        });

        // Layout configuration is omitted for brevity

        pack();
    }

    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {
        try {
            double hargaAsli = Double.parseDouble(jTextField1.getText());
            double persentaseDiskon = Double.parseDouble(comboDiskon.getSelectedItem().toString());
            double penghematan = hargaAsli * (persentaseDiskon / 100);
            double hargaAkhir = hargaAsli - penghematan;

            // Debug output
            System.out.println("Harga Asli: " + hargaAsli);
            System.out.println("Persentase Diskon: " + persentaseDiskon);
            System.out.println("Harga Akhir: " + hargaAkhir);

            jTextField2.setText(String.format("%.2f", hargaAkhir));
            lblPenghematan.setText("Penghematan: " + String.format("%.2f", penghematan));
        } catch (NumberFormatException ex) {
            JOptionPane.showMessageDialog(this, "Masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
        }
    }

    public static void main(String args[]) {
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new PerhitunganDiskonForm().setVisible(true);
            }
        });
    }

    // Variables declaration
    private javax.swing.JComboBox<String> comboDiskon;
    private javax.swing.JButton jButton1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JLabel jLabel4;
    private javax.swing.JLabel jLabel5;
    private javax.swing.JPanel jPanel1;
    private javax.swing.JTextField jTextField1;
    private javax.swing.JTextField jTextField2;
    private javax.swing.JLabel lblPenghematan;
    private javax.swing.JLabel txtHargaAkhir;
    private javax.swing.JLabel txtHargaAsli;
    // End of variables declaration
}

Cara Menjalankan Aplikasi

    Buka proyek di NetBeans atau IDE lain yang mendukung Java Swing.
    Jalankan file PerhitunganDiskonForm.java.
    Masukkan harga asli di kolom input.
    Pilih persentase diskon dari JComboBox.
    Klik tombol "HITUNG" untuk melihat hasil perhitungan di kolom hasil.

Penanganan Kesalahan

Aplikasi menangani input non-numerik dengan menampilkan pesan kesalahan menggunakan JOptionPane.showMessageDialog() agar pengguna mengetahui bahwa input harus berupa angka.
Contoh Penggunaan

    Masukkan harga asli, misalnya 100000.
    Pilih diskon 20%.
    Klik tombol "HITUNG", dan aplikasi akan menampilkan harga akhir (80000) serta jumlah penghematan (20000).

Lisensi
Proyek ini dibuat untuk tujuan pembelajaran dan bebas digunakan.
