# CODINGGANBIODATA
/*  * To change this license header, choose License Headers in Project Properties.  * To change this template file, choose Tools | Templates  * and open the template in the editor.  */ package mhsapp; import java.sql.*; import java.text.Format; import javax.swing.*; import javax.swing.table.*; import java.text.SimpleDateFormat; import java.util.Date;  import javax.swing.JOptionPane; import java.awt.HeadlessException; import java.sql.Connection; import java.sql.SQLException;  /**  *  * @author AZWAR  */ public class mhs extends javax.swing.JFrame {      public String tgl_lahir;      /**      * Creates new form mhs      */     public mhs() {         initComponents();     }      /**      * This method is called from within the constructor to initialize the form.      * WARNING: Do NOT modify this code. The content of this method is always      * regenerated by the Form Editor.      */     @SuppressWarnings("unchecked")     // &lt;editor-fold defaultstate="collapsed" desc="Generated Code">                               private void initComponents() {          jLabel1 = new javax.swing.JLabel();         jPanel1 = new javax.swing.JPanel();         jLabel2 = new javax.swing.JLabel();         jLabel3 = new javax.swing.JLabel();         jLabel4 = new javax.swing.JLabel();         jLabel5 = new javax.swing.JLabel();         nim = new javax.swing.JTextField();         nama = new javax.swing.JTextField();         jurusan = new javax.swing.JTextField();         tgl = new com.toedter.calendar.JDateChooser();         jPanel2 = new javax.swing.JPanel();         bt_tambah = new javax.swing.JButton();         bt_ubah = new javax.swing.JButton();         bt_hapus = new javax.swing.JButton();         jScrollPane1 = new javax.swing.JScrollPane();         jTable1 = new javax.swing.JTable();          setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);          jLabel1.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N         jLabel1.setText("DATA MAHASISWA");         jLabel1.setVerifyInputWhenFocusTarget(false);          jLabel2.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N         jLabel2.setText("NIM");          jLabel3.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N         jLabel3.setText("Nama");          jLabel4.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N         jLabel4.setText("tgl_lahir");          jLabel5.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N         jLabel5.setText("Jurusan");          tgl.addPropertyChangeListener(new java.beans.PropertyChangeListener() {             public void propertyChange(java.beans.PropertyChangeEvent evt) {                 tglPropertyChange(evt);             }         });          javax.swing.GroupLayout jPanel1Layout = new javax.swing.GroupLayout(jPanel1);         jPanel1.setLayout(jPanel1Layout);         jPanel1Layout.setHorizontalGroup(             jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)             .addGroup(jPanel1Layout.createSequentialGroup()                 .addGap(28, 28, 28)                 .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)                     .addComponent(jLabel2)                     .addComponent(jLabel3)                     .addComponent(jLabel4)                     .addComponent(jLabel5))                 .addGap(68, 68, 68)                 .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)                     .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)                         .addComponent(nim, javax.swing.GroupLayout.DEFAULT_SIZE, 155, Short.MAX_VALUE)                         .addComponent(jurusan)                         .addComponent(nama))                     .addComponent(tgl, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))                 .addContainerGap(89, Short.MAX_VALUE))         );         jPanel1Layout.setVerticalGroup(             jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)             .addGroup(jPanel1Layout.createSequentialGroup()                 .addContainerGap()                 .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)                     .addComponent(jLabel2)                     .addComponent(nim, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))                 .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)                 .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)                     .addComponent(jLabel3)                     .addComponent(nama, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))                 .addGap(18, 18, 18)                 .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)                     .addComponent(jLabel4)                     .addComponent(tgl, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))                 .addGap(18, 18, 18)                 .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)                     .addComponent(jLabel5)                     .addComponent(jurusan, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))                 .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))         );          bt_tambah.setText("tambah");         bt_tambah.addActionListener(new java.awt.event.ActionListener() {             public void actionPerformed(java.awt.event.ActionEvent evt) {                 bt_tambahActionPerformed(evt);             }         });          bt_ubah.setText("ubah");          bt_hapus.setText("Hapus");          jTable1.setModel(new javax.swing.table.DefaultTableModel(             new Object [][] {                 {null, null, null, null},                 {null, null, null, null},                 {null, null, null, null},                 {null, null, null, null}             },             new String [] {                 "Title 1", "Title 2", "Title 3", "Title 4"             }         ));         jScrollPane1.setViewportView(jTable1);          javax.swing.GroupLayout jPanel2Layout = new javax.swing.GroupLayout(jPanel2);         jPanel2.setLayout(jPanel2Layout);         jPanel2Layout.setHorizontalGroup(             jPanel2Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)             .addGroup(jPanel2Layout.createSequentialGroup()                 .addGap(27, 27, 27)                 .addGroup(jPanel2Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)                     .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)                     .addGroup(jPanel2Layout.createSequentialGroup()                         .addComponent(bt_tambah)                         .addGap(18, 18, 18)                         .addComponent(bt_ubah)                         .addGap(18, 18, 18)                         .addComponent(bt_hapus)))                 .addContainerGap(28, Short.MAX_VALUE))         );         jPanel2Layout.setVerticalGroup(             jPanel2Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)             .addGroup(jPanel2Layout.createSequentialGroup()                 .addContainerGap()                 .addGroup(jPanel2Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)                     .addComponent(bt_tambah)                     .addComponent(bt_ubah)                     .addComponent(bt_hapus))                 .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)                 .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, 130, javax.swing.GroupLayout.PREFERRED_SIZE)                 .addContainerGap(323, Short.MAX_VALUE))         );          javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());         getContentPane().setLayout(layout);         layout.setHorizontalGroup(             layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)             .addGroup(layout.createSequentialGroup()                 .addGap(28, 28, 28)                 .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)                     .addComponent(jPanel2, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)                     .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)                         .addComponent(jPanel1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)                         .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 183, javax.swing.GroupLayout.PREFERRED_SIZE)))                 .addContainerGap(391, Short.MAX_VALUE))         );         layout.setVerticalGroup(             layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)             .addGroup(layout.createSequentialGroup()                 .addGap(27, 27, 27)                 .addComponent(jLabel1)                 .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)                 .addComponent(jPanel1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)                 .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)                 .addComponent(jPanel2, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)                 .addGap(446, 446, 446))         );          pack();     }// &lt;/editor-fold>                              private void tglPropertyChange(java.beans.PropertyChangeEvent evt) {                                            // TODO add your handling code here:         if (tgl.getDate()!=null){             SimpleDateFormat format=new SimpleDateFormat("yyyy-MM-dd");                  }     }                                        private void bt_tambahActionPerformed(java.awt.event.ActionEvent evt) {                                                   // TODO add your handling code here:           //===tombol tambah===         try{             String sql="insert into mhs values('"                     +nim.getText()+"','"                     +nama.getText()+"','"                     +tgl_lahir+"','"                     +.getText()+"','"             java.sql.Connection conn=(java.sql.Connection)mhsAPP.koneksi.koneksiDB();             java.sql.PreparedStatement pst=conn.prepareStatement(sql);             pst.execute();             JOptionPane.showMessageDialog(null, "Berhasil disimpan");             tampil_data();         }         catch (Exception e){             JOptionPane.showMessageDialog(null, "Gagal disimpan");             System.out.println(e.getMessage());         }     }                                               /**      * @param args the command line arguments      */     public static void main(String args[]) {         /* Set the Nimbus look and feel */         //&lt;editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">         /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.          * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html           */         try {             for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {                 if ("Nimbus".equals(info.getName())) {                     javax.swing.UIManager.setLookAndFeel(info.getClassName());                     break;                 }             }         } catch (ClassNotFoundException ex) {             java.util.logging.Logger.getLogger(mhs.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);         } catch (InstantiationException ex) {             java.util.logging.Logger.getLogger(mhs.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);         } catch (IllegalAccessException ex) {             java.util.logging.Logger.getLogger(mhs.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);         } catch (javax.swing.UnsupportedLookAndFeelException ex) {             java.util.logging.Logger.getLogger(mhs.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);         }         //&lt;/editor-fold>          /* Create and display the form */         java.awt.EventQueue.invokeLater(new Runnable() {             public void run() {                 new mhs().setVisible(true);             }         });     }      // Variables declaration - do not modify                          private javax.swing.JButton bt_hapus;     private javax.swing.JButton bt_tambah;     private javax.swing.JButton bt_ubah;     private javax.swing.JLabel jLabel1;     private javax.swing.JLabel jLabel2;     private javax.swing.JLabel jLabel3;     private javax.swing.JLabel jLabel4;     private javax.swing.JLabel jLabel5;     private javax.swing.JPanel jPanel1;     private javax.swing.JPanel jPanel2;     private javax.swing.JScrollPane jScrollPane1;     private javax.swing.JTable jTable1;     private javax.swing.JTextField jurusan;     private javax.swing.JTextField nama;     private javax.swing.JTextField nim;     private com.toedter.calendar.JDateChooser tgl;     // End of variables declaration                         private void tampil_data() {         throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.     } }
