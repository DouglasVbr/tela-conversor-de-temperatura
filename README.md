# tela-conversor-de-temperatura


import javax.swing.JOptionPane;

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

/**
 *
 * @author aluno.saolucas
 */
public class Comversor extends javax.swing.JFrame {

    /**
     * Creates new form Comversor
     */
    public Comversor() {
        initComponents();
    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        btngrupo = new javax.swing.ButtonGroup();
        lblTitulo = new javax.swing.JLabel();
        lblValor = new javax.swing.JLabel();
        btnCalcular = new javax.swing.JButton();
        btnRCparaF = new javax.swing.JRadioButton();
        btnRFparaC = new javax.swing.JRadioButton();
        txtTemperatura = new javax.swing.JTextField();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);
        setBackground(new java.awt.Color(51, 0, 255));
        setCursor(new java.awt.Cursor(java.awt.Cursor.DEFAULT_CURSOR));

        lblTitulo.setFont(new java.awt.Font("Tahoma", 1, 18)); // NOI18N
        lblTitulo.setText("CONVERSOR DE TEMPERATURA");

        lblValor.setFont(new java.awt.Font("Tahoma", 1, 12)); // NOI18N
        lblValor.setText("TEMPERATURA:");

        btnCalcular.setFont(new java.awt.Font("Tahoma", 1, 12)); // NOI18N
        btnCalcular.setText("CALCULAR");
        btnCalcular.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                btnCalcularActionPerformed(evt);
            }
        });

        btngrupo.add(btnRCparaF);
        btnRCparaF.setFont(new java.awt.Font("Tahoma", 1, 12)); // NOI18N
        btnRCparaF.setSelected(true);
        btnRCparaF.setText(" C° /  F °");

        btngrupo.add(btnRFparaC);
        btnRFparaC.setFont(new java.awt.Font("Tahoma", 1, 12)); // NOI18N
        btnRFparaC.setText(" F ° / C °");

        txtTemperatura.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                txtTemperaturaActionPerformed(evt);
            }
        });

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(121, 121, 121)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addComponent(btnRCparaF)
                            .addComponent(btnRFparaC)))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(103, 103, 103)
                        .addComponent(lblValor)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(txtTemperatura, javax.swing.GroupLayout.PREFERRED_SIZE, 96, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                .addGap(0, 64, Short.MAX_VALUE)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                        .addComponent(lblTitulo)
                        .addGap(56, 56, 56))
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                        .addComponent(btnCalcular)
                        .addGap(145, 145, 145))))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(lblTitulo)
                .addGap(39, 39, 39)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(lblValor)
                    .addComponent(txtTemperatura, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 27, Short.MAX_VALUE)
                .addComponent(btnRCparaF)
                .addGap(26, 26, 26)
                .addComponent(btnRFparaC)
                .addGap(40, 40, 40)
                .addComponent(btnCalcular)
                .addGap(54, 54, 54))
        );

        pack();
        setLocationRelativeTo(null);
    }// </editor-fold>                        

    private void btnCalcularActionPerformed(java.awt.event.ActionEvent evt) {                                            
        try {
        double res = Double.valueOf(txtTemperatura.getText());
        Temperatura objT = new Temperatura(res);
       
        
        if (btnRCparaF.isSelected()){
            JOptionPane.showMessageDialog(null, " TEMPERATURA EM °F É : " + String.format("%.2f", objT.ConverteTemF(res)));
        }else if (btnRFparaC.isSelected()){
            JOptionPane.showMessageDialog(null, " TEMPERATURA EM °C É : " + String.format("%.2f", objT.ConverteTemC(res)));
        }
   } catch (NumberFormatException e) {
        JOptionPane.showMessageDialog(null, "Por favor, insira um valor numérico válido.");
    }
          // Limpar o campo de texto
    txtTemperatura.setText("");
    }                                           

    private void txtTemperaturaActionPerformed(java.awt.event.ActionEvent evt) {                                               
        // TODO add your handling code here:
    }                                              

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ClassNotFoundException ex) {
            java.util.logging.Logger.getLogger(Comversor.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (InstantiationException ex) {
            java.util.logging.Logger.getLogger(Comversor.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (IllegalAccessException ex) {
            java.util.logging.Logger.getLogger(Comversor.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        } catch (javax.swing.UnsupportedLookAndFeelException ex) {
            java.util.logging.Logger.getLogger(Comversor.class.getName()).log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new Comversor().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JButton btnCalcular;
    private javax.swing.JRadioButton btnRCparaF;
    private javax.swing.JRadioButton btnRFparaC;
    private javax.swing.ButtonGroup btngrupo;
    private javax.swing.JLabel lblTitulo;
    private javax.swing.JLabel lblValor;
    private javax.swing.JTextField txtTemperatura;
    // End of variables declaration                   
}


import javax.swing.JOptionPane;


public class Temperatura {

    private double Temperatura;

    public Temperatura(double Temperatura) {
        this.Temperatura = Temperatura;
    }

    public void setTemperatura(double Temperatura) {
        this.Temperatura = Temperatura;

    }

    public double getTemperatura() {

        return Temperatura;
    }
    
    public void exibir(){
        JOptionPane.showMessageDialog(null, "TEMPERATURA" + getTemperatura());
        
        
    }
    
    public double ConverteTemF(double Temperatura){
    this.Temperatura = Temperatura;
    double Temp = (Temperatura * 9/5 + 32);
    return Temp;
    }
    
     public double ConverteTemC(double Temperatura){
    this.Temperatura = Temperatura;
    double Temp = (Temperatura - 32) * 5 / 9;
    return Temp;
    }

    void exibir(double res) {
        throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.
    }
    
    

}
