package test;

import java.awt.Color;
import java.sql.Statement;
import javax.swing.ImageIcon;
import java.sql.*;
import javax.swing.JOptionPane;

       
/**
 *
 * @author 18029040
 */

public class Game extends javax.swing.JFrame {
    
    public int QuestionID = 0;
    
    //Used for database connection
    Connection con = null;
    String url = "jdbc:derby://localhost:1527/Assignment";
    String username = "abc";
    String password = "abc";
    Statement state;
    ResultSet rs;
    
    public int money = 0;
    public int safemoney = 0;
    public int questionID = 0;
    public String answer = "";
    public int correct = 0;
    public String fifty1 = "";
    public String fifty2 = "";
    public String Question = "";
    public String AnswerA = "";
    public String AnswerB = "";
    public String AnswerC = "";
    public String AnswerD = "";
    public int clicked = 0;
    public int clicked2 = 0;
    public String name = "";
    public static int open = 0;
    
    //Imported images for both 5050 logos
    int Usefifty = 0;
    String[] imageUsefifty = {"Used5050.png"};
    int Usedfifty2 = 0;
    String[] imageUsedfifty2 = {"Used5050.png"};
    
    public void CreateTables()
    {
        try
        {
            con = DriverManager.getConnection(url, username, password);
            state = con.createStatement();
            state.executeUpdate("DROP TABLE Usernames");//Deletes any previous tables
            state.executeUpdate("CREATE TABLE Usernames(username VARCHAR(100))");// Creates the user table
            
        }
        catch(SQLException ex)
        {
            System.out.println(ex);
        }
    }
    
    public void set()
    {
        QuestionID = 0;
    }
    public Game() {
        initComponents();
        //diables button for later
        jButton1.setEnabled(false);
        
        //intial set question
        try {
            con = DriverManager.getConnection(url, username, password);
            state = con.createStatement();
            String query = "SELECT * FROM QUESTIONS WHERE questionsID ="+ questionID;
            rs = state.executeQuery(query);
            while(rs.next())
            {
                Question = rs.getString("Question");
                jTextField1.setText(Question);
                AnswerA = rs.getString("AnswerA");
                jRadioButton1.setText(AnswerA);
                AnswerB = rs.getString("AnswerB");
                jRadioButton2.setText(AnswerB);
                AnswerC = rs.getString("AnswerC");
                jRadioButton3.setText(AnswerC);
                AnswerD = rs.getString("AnswerD");
                jRadioButton4.setText(AnswerD);
                answer = rs.getString("Correct");
                fifty1 = rs.getString("FiftyFifty");
                fifty2 = rs.getString("FiftyFifty2");
                
            }
                
        } catch (SQLException ex) {
            System.out.println(ex);
        } 
    }
    
    public void Answercheck()
    {
        //Checks if user selected answer is correct
        String selectedAns = "";
        if(jRadioButton1.isSelected())
        {
            selectedAns = jRadioButton1.getText();
        }
        else if(jRadioButton2.isSelected())
        {
            selectedAns = jRadioButton2.getText();
        }
        else if(jRadioButton3.isSelected())
        {
            selectedAns = jRadioButton3.getText();
        }
        else
        {
            selectedAns = jRadioButton4.getText();
        }
        
        if(questionID >= 1)
        {    
            if(selectedAns.equals(answer))
            {
                correct = correct + 1;

            }
            else if(!selectedAns.equals(answer))
            {
                Lose();
            }
        }
        
        //sets money after questions are answered correctly
        switch (correct) {
            case 1:
                money = 100;
                break;
            case 2:
                money = 200;
                break;
            case 3:
                money = 300;
                break;
            case 4:
                money = 500;
                break;
            case 5:
                money = 1000;
                safemoney = 1000;
                break;
            case 6:
                money = 2000;
                break;
            case 7:
                money = 5000;
                break;
            case 8:
                money = 10000;
                break;
            case 9:
                money = 25000;
                break;
            case 10:
                money = 50000;
                safemoney = 50000;
                break;
            case 11:
                money = 100000;
                break;
            case 12:
                money = 250000;
                break;
            case 13:
                money = 500000;
                break;
            case 14:
                money = 1000000;
                safemoney = 1000000;
                break;
            default:
                money = 0;
                break;
        }
        
        //Change Question
        questionID = questionID + 1;
        
        //Clear selection and resets for next question
        jRadioButton1.setSelected(false);
        jRadioButton2.setSelected(false);
        jRadioButton3.setSelected(false);
        jRadioButton4.setSelected(false);
        jButton1.setEnabled(false);
        jRadioButton1.setEnabled(true);
        jRadioButton2.setEnabled(true);
        jRadioButton3.setEnabled(true);
        jRadioButton4.setEnabled(true);
        jRadioButton1.setForeground(Color.WHITE);
        jRadioButton2.setForeground(Color.WHITE);
        jRadioButton3.setForeground(Color.WHITE);
        jRadioButton4.setForeground(Color.WHITE);
        
    }
    
    public void question()
    {
        //Sets Questions
        try {
            con = DriverManager.getConnection(url, username, password);
            state = con.createStatement();
            String query = "SELECT * FROM QUESTIONS WHERE questionsID ="+ questionID;
            rs = state.executeQuery(query);
            while(rs.next())
            {
                Question = rs.getString("Question");
                jTextField1.setText(Question);
                AnswerA = rs.getString("AnswerA");
                jRadioButton1.setText(AnswerA);
                AnswerB = rs.getString("AnswerB");
                jRadioButton2.setText(AnswerB);
                AnswerC = rs.getString("AnswerC");
                jRadioButton3.setText(AnswerC);
                AnswerD = rs.getString("AnswerD");
                jRadioButton4.setText(AnswerD);
                answer = rs.getString("Correct");
                fifty1 = rs.getString("FiftyFifty");
                fifty2 = rs.getString("FiftyFifty2");
                
            }
                
        } catch (SQLException ex) {
            System.out.println(ex);
        } 
        
        //Changing Money playing for
        switch (questionID) {
            case 1:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st1.PNG")));
                break;
            case 2:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st2.PNG")));
                break;
            case 3:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st3.PNG")));
                break;
            case 4:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st4.PNG")));
                break;
            case 5:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st5.PNG")));
                break;
            case 6:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st6.PNG")));
                break;
            case 7:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st7.PNG")));
                break;
            case 8:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st8.PNG")));
                break;
            case 9:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st9.PNG")));
                break;
            case 10:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st10.PNG")));
                break;
            case 11:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st11.PNG")));
                break;
            case 12:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st12.PNG")));
                break;
            case 13:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st13.PNG")));
                break;
            case 14:
                jLabel5.setIcon(new ImageIcon(getClass().getResource("/test/Image/st14.PNG")));
                break;
            default:
                break;
        }
        
        if(questionID >= 15)
        {
            Exit(); 
        }
    }
    
    //Passes name and money to the exit screen
    public void Exit()
    {
        setVisible(false);
        new ExitScreen(name, money).setVisible(true);
    }
    
    //Passes name and safemoney to the lose screen
    public void Lose()
    {
        setVisible(false);
        new LoseFrame(name, safemoney).setVisible(true);
    }
    
    //diables jradiobuttons for the 5050
    public void Fiftyfifty()
    {
            if(jLabel6.isEnabled())
            {
                if(fifty1.equals(AnswerA))
                {
                    jRadioButton1.setEnabled(false);
                    jRadioButton1.setForeground(Color.BLACK);
                }
                else if(fifty1.equals(AnswerB))
                {
                    jRadioButton2.setEnabled(false);
                    jRadioButton2.setForeground(Color.BLACK);
                }
                else if(fifty1.equals(AnswerC))
                {
                    jRadioButton3.setEnabled(false);
                    jRadioButton3.setForeground(Color.BLACK);
                }
                else if(fifty1.equals(AnswerD))
                {
                    jRadioButton4.setEnabled(false);
                    jRadioButton4.setForeground(Color.BLACK);
                }

                if(fifty2.equals(AnswerA))
                {
                    jRadioButton1.setEnabled(false);
                    jRadioButton1.setForeground(Color.BLACK);
                }
                else if(fifty2.equals(AnswerB))
                {
                    jRadioButton2.setEnabled(false);
                    jRadioButton2.setForeground(Color.BLACK);
                }
                else if(fifty2.equals(AnswerC))
                {
                    jRadioButton3.setEnabled(false);
                    jRadioButton3.setForeground(Color.BLACK);
                }
                else if(fifty2.equals(AnswerD))
                {
                    jRadioButton4.setEnabled(false);
                    jRadioButton4.setForeground(Color.BLACK);
                }
            } 
    }
    
    //diables jradiobuttons for the second 5050
    public void Fiftyfifty2()
    {
        if(jLabel3.isEnabled())
            {
                if(fifty1.equals(AnswerA))
                {
                    jRadioButton1.setEnabled(false);
                    jRadioButton1.setForeground(Color.BLACK);
                }
                else if(fifty1.equals(AnswerB))
                {
                    jRadioButton2.setEnabled(false);
                    jRadioButton2.setForeground(Color.BLACK);
                }
                else if(fifty1.equals(AnswerC))
                {
                    jRadioButton3.setEnabled(false);
                    jRadioButton3.setForeground(Color.BLACK);
                }
                else if(fifty1.equals(AnswerD))
                {
                    jRadioButton4.setEnabled(false);
                    jRadioButton4.setForeground(Color.BLACK);
                }

                if(fifty2.equals(AnswerA))
                {
                    jRadioButton1.setEnabled(false);
                    jRadioButton1.setForeground(Color.BLACK);
                }
                else if(fifty2.equals(AnswerB))
                {
                    jRadioButton2.setEnabled(false);
                    jRadioButton2.setForeground(Color.BLACK);
                }
                else if(fifty2.equals(AnswerC))
                {
                    jRadioButton3.setEnabled(false);
                    jRadioButton3.setForeground(Color.BLACK);
                }
                else if(fifty2.equals(AnswerD))
                {
                    jRadioButton4.setEnabled(false);
                    jRadioButton4.setForeground(Color.BLACK);
                }
            } 
    }

    @SuppressWarnings("unchecked")
    
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        buttonGroup1 = new javax.swing.ButtonGroup();
        jLabel3 = new javax.swing.JLabel();
        jLabel4 = new javax.swing.JLabel();
        jLabel1 = new javax.swing.JLabel();
        jLabel2 = new javax.swing.JLabel();
        jLabel5 = new javax.swing.JLabel();
        jTextField1 = new javax.swing.JTextField();
        jButton1 = new javax.swing.JButton();
        jTextField6 = new javax.swing.JTextField();
        jRadioButton1 = new javax.swing.JRadioButton();
        jRadioButton2 = new javax.swing.JRadioButton();
        jRadioButton3 = new javax.swing.JRadioButton();
        jRadioButton4 = new javax.swing.JRadioButton();
        jLabel6 = new javax.swing.JLabel();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);
        setBackground(new java.awt.Color(0, 0, 0));
        addWindowListener(new java.awt.event.WindowAdapter() {
            public void windowActivated(java.awt.event.WindowEvent evt) {
                formWindowActivated(evt);
            }
        });

        jLabel3.addMouseListener(new java.awt.event.MouseAdapter() {
            public void mouseClicked(java.awt.event.MouseEvent evt) {
                jLabel3MouseClicked(evt);
            }
        });

        jLabel4.setIcon(new javax.swing.ImageIcon("C:\\Users\\Gorilla Rig\\Documents\\NetBeansProjects\\Assignment 1\\5050.png")); // NOI18N
        jLabel4.addMouseListener(new java.awt.event.MouseAdapter() {
            public void mouseClicked(java.awt.event.MouseEvent evt) {
                jLabel4MouseClicked(evt);
            }
        });

        jLabel1.setIcon(new javax.swing.ImageIcon("C:\\Users\\Gorilla Rig\\Documents\\NetBeansProjects\\Assignment 1\\Logo-1.jpg")); // NOI18N

        jLabel2.setIcon(new javax.swing.ImageIcon("C:\\Users\\Gorilla Rig\\Documents\\NetBeansProjects\\Assignment 1\\exit.png")); // NOI18N
        jLabel2.addMouseListener(new java.awt.event.MouseAdapter() {
            public void mouseClicked(java.awt.event.MouseEvent evt) {
                jLabel2MouseClicked(evt);
            }
        });

        jLabel5.setIcon(new javax.swing.ImageIcon("C:\\Users\\Gorilla Rig\\Documents\\NetBeansProjects\\Assignment 1\\money.PNG")); // NOI18N

        jTextField1.setEditable(false);
        jTextField1.setBackground(new java.awt.Color(0, 0, 0));
        jTextField1.setFont(new java.awt.Font("Tw Cen MT Condensed", 1, 14)); // NOI18N
        jTextField1.setForeground(new java.awt.Color(255, 255, 255));
        jTextField1.setHorizontalAlignment(javax.swing.JTextField.CENTER);
        jTextField1.setText("jTextField1");
        jTextField1.setBorder(javax.swing.BorderFactory.createLineBorder(new java.awt.Color(0, 153, 255), 3));

        jButton1.setBackground(new java.awt.Color(0, 0, 0));
        jButton1.setIcon(new javax.swing.ImageIcon(getClass().getResource("/test/Image/button.PNG"))); // NOI18N
        jButton1.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                jButton1ActionPerformed(evt);
            }
        });

        jTextField6.setBackground(new java.awt.Color(0, 0, 0));
        jTextField6.setFont(new java.awt.Font("Tw Cen MT Condensed", 1, 18)); // NOI18N
        jTextField6.setForeground(new java.awt.Color(255, 255, 255));
        jTextField6.setText("Enter User name");
        jTextField6.setBorder(javax.swing.BorderFactory.createLineBorder(new java.awt.Color(0, 153, 204), 3));
        jTextField6.addKeyListener(new java.awt.event.KeyAdapter() {
            public void keyReleased(java.awt.event.KeyEvent evt) {
                jTextField6KeyReleased(evt);
            }
        });

        jRadioButton1.setBackground(new java.awt.Color(0, 0, 0));
        jRadioButton1.setFont(new java.awt.Font("Tw Cen MT Condensed", 1, 14)); // NOI18N
        jRadioButton1.setForeground(new java.awt.Color(255, 255, 255));
        jRadioButton1.setText("jRadioButton1");
        jRadioButton1.setBorder(javax.swing.BorderFactory.createLineBorder(new java.awt.Color(0, 153, 204), 3));
        jRadioButton1.setBorderPainted(true);
        jRadioButton1.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                jRadioButton1ActionPerformed(evt);
            }
        });

        jRadioButton2.setBackground(new java.awt.Color(0, 0, 0));
        jRadioButton2.setFont(new java.awt.Font("Tw Cen MT Condensed", 1, 14)); // NOI18N
        jRadioButton2.setForeground(new java.awt.Color(255, 255, 255));
        jRadioButton2.setText("jRadioButton2");
        jRadioButton2.setBorder(javax.swing.BorderFactory.createLineBorder(new java.awt.Color(0, 153, 204), 3));
        jRadioButton2.setBorderPainted(true);
        jRadioButton2.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                jRadioButton2ActionPerformed(evt);
            }
        });

        jRadioButton3.setBackground(new java.awt.Color(0, 0, 0));
        jRadioButton3.setFont(new java.awt.Font("Tw Cen MT Condensed", 1, 14)); // NOI18N
        jRadioButton3.setForeground(new java.awt.Color(255, 255, 255));
        jRadioButton3.setText("jRadioButton3");
        jRadioButton3.setBorder(javax.swing.BorderFactory.createLineBorder(new java.awt.Color(0, 153, 204), 3));
        jRadioButton3.setBorderPainted(true);
        jRadioButton3.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                jRadioButton3ActionPerformed(evt);
            }
        });

        jRadioButton4.setBackground(new java.awt.Color(0, 0, 0));
        jRadioButton4.setFont(new java.awt.Font("Tw Cen MT Condensed", 1, 14)); // NOI18N
        jRadioButton4.setForeground(new java.awt.Color(255, 255, 255));
        jRadioButton4.setText("jRadioButton4");
        jRadioButton4.setBorder(javax.swing.BorderFactory.createLineBorder(new java.awt.Color(0, 153, 204), 3));
        jRadioButton4.setBorderPainted(true);
        jRadioButton4.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                jRadioButton4ActionPerformed(evt);
            }
        });

        jLabel6.setIcon(new javax.swing.ImageIcon("C:\\Users\\Gorilla Rig\\Documents\\NetBeansProjects\\Assignment 1\\5050.png")); // NOI18N
        jLabel6.addMouseListener(new java.awt.event.MouseAdapter() {
            public void mouseClicked(java.awt.event.MouseEvent evt) {
                jLabel6MouseClicked(evt);
            }
        });

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                .addContainerGap(26, Short.MAX_VALUE)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING, false)
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jRadioButton3, javax.swing.GroupLayout.PREFERRED_SIZE, 225, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                        .addComponent(jRadioButton4, javax.swing.GroupLayout.PREFERRED_SIZE, 225, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addComponent(jLabel1, javax.swing.GroupLayout.Alignment.LEADING, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                    .addComponent(jTextField1, javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jRadioButton1, javax.swing.GroupLayout.PREFERRED_SIZE, 225, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                        .addComponent(jRadioButton2, javax.swing.GroupLayout.PREFERRED_SIZE, 225, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addGroup(layout.createSequentialGroup()
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                                .addComponent(jLabel3)
                                .addGap(207, 207, 207))
                            .addGroup(layout.createSequentialGroup()
                                .addComponent(jLabel6)
                                .addGap(32, 32, 32)
                                .addComponent(jLabel2)
                                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)))
                        .addComponent(jLabel4)))
                .addGap(18, 18, 18)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addComponent(jTextField6, javax.swing.GroupLayout.PREFERRED_SIZE, 163, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(jLabel5)
                    .addComponent(jButton1, javax.swing.GroupLayout.PREFERRED_SIZE, 163, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(23, 23, 23))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGap(22, 22, 22)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(9, 9, 9)
                        .addComponent(jTextField6, javax.swing.GroupLayout.PREFERRED_SIZE, 30, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                        .addComponent(jLabel5))
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jLabel3)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING)
                            .addComponent(jLabel6, javax.swing.GroupLayout.PREFERRED_SIZE, 97, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(jLabel2)
                            .addComponent(jLabel4, javax.swing.GroupLayout.PREFERRED_SIZE, 97, javax.swing.GroupLayout.PREFERRED_SIZE))
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                        .addComponent(jLabel1)
                        .addGap(18, 18, 18)
                        .addComponent(jTextField1, javax.swing.GroupLayout.PREFERRED_SIZE, 51, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                            .addComponent(jRadioButton1, javax.swing.GroupLayout.PREFERRED_SIZE, 47, javax.swing.GroupLayout.PREFERRED_SIZE)
                            .addComponent(jRadioButton2, javax.swing.GroupLayout.PREFERRED_SIZE, 47, javax.swing.GroupLayout.PREFERRED_SIZE))))
                .addGap(5, 5, 5)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                        .addComponent(jRadioButton4, javax.swing.GroupLayout.PREFERRED_SIZE, 45, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addComponent(jRadioButton3, javax.swing.GroupLayout.PREFERRED_SIZE, 45, javax.swing.GroupLayout.PREFERRED_SIZE))
                    .addComponent(jButton1, javax.swing.GroupLayout.PREFERRED_SIZE, 55, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addContainerGap(27, Short.MAX_VALUE))
        );

        pack();
    }// </editor-fold>                        

    private void formWindowActivated(java.awt.event.WindowEvent evt) {                                     
        
        this.getContentPane().setBackground(Color.BLACK);
        //calls Createtables
        CreateTables();
        
        //Sets the look of the program when its started
        if(QuestionID == 0)
        {    
            jTextField1.setText("Please Enter your name in the top right, Then click confirm");
            jRadioButton1.setText("          ");
            jRadioButton2.setText("          ");
            jRadioButton3.setText("          ");
            jRadioButton4.setText("          ");
        }
    }                                    

    private void jLabel4MouseClicked(java.awt.event.MouseEvent evt) {                                     
        
        //Changes to the second Used 5050 icon
        if(questionID >= 1)
        {
            ImageIcon[] images = new ImageIcon[1];
            for(int i = 0; i < images.length; i++)
            {
                images[i] = new ImageIcon(getClass().getResource("/test/Image/" + imageUsedfifty2[i]));
            }
            if (Usedfifty2 < 0) Usedfifty2 = 1;
            if(Usedfifty2 >= 0 && Usedfifty2 < imageUsedfifty2.length)
            {
                jLabel4.setIcon(images[Usedfifty2]);

                Usedfifty2 ++;
            }

            //diables jradiobuttons for the second 5050
            Fiftyfifty();

            clicked2 = clicked2 + 1;

            //Diables the second 5050 button after use
            if(clicked2 == 0)
            {
                jLabel4.setEnabled(true);
            }
            else
            {
                jLabel4.setEnabled(false);
            }
        }
    }                                    

    private void jLabel3MouseClicked(java.awt.event.MouseEvent evt) {                                     
        
        
    }                                    

    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        
        QuestionID = QuestionID + 1;
        
        Answercheck();
        question();
        
        //Used to Store username in Database
        if(1 == QuestionID)
        {
            try {
                con = DriverManager.getConnection(url, username, password);
                state = con.createStatement();
                String query = "INSERT INTO USERNAMES (USERNAME) VALUES('" + jTextField6.getText() + "')";
                state.execute(query);
                jTextField6.setEditable(false);
            } catch (SQLException ex) {
                System.out.println(ex);
            }
        }
        else 
        {
            jTextField6.setEditable(false);
        }
        
        //Gets the Users name
        try
        {
            con = DriverManager.getConnection(url, username, password);
            state = con.createStatement();
            String query = "SELECT * FROM Usernames";
            rs = state.executeQuery(query);
            while(rs.next())
            {
                name = rs.getString("Username");
            }
        }
        catch(SQLException ex)
        {
            System.out.println(ex);
        }
        
    }                                        

  
    private void jLabel2MouseClicked(java.awt.event.MouseEvent evt) {                                     

        //Sets a Option window for user to choose if they want to leave
        int a = JOptionPane.showConfirmDialog(null, "Safely exit with $" + money + "?\nIf you get the answer wrong you will leave with $" + safemoney, "Leaving?", JOptionPane.YES_NO_OPTION);
        if(a == 0)
        {
            Exit();
        }
    }                                    

    private void jRadioButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                              

        //Makes sure that only one jRadiobutton can be selected
        if(jRadioButton1.isSelected() && questionID >= 1)
        {
            jRadioButton2.setSelected(false);
            jRadioButton3.setSelected(false);
            jRadioButton4.setSelected(false);
            jButton1.setEnabled(true);//makes button avaliable after a jradiobutton is select
        }
    }                                             

    private void jRadioButton3ActionPerformed(java.awt.event.ActionEvent evt) {                                              
        
        //Makes sure that only one jRadiobutton can be selected
        if(jRadioButton3.isSelected() && questionID >= 1)
        {
            jRadioButton1.setSelected(false);
            jRadioButton2.setSelected(false);
            jRadioButton4.setSelected(false);
            jButton1.setEnabled(true);//makes button avaliable after a jradiobutton is select
        }
    }                                             

    private void jRadioButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                              
        
        //Makes sure that only one jRadiobutton can be selected
        if(jRadioButton2.isSelected() && questionID >= 1)
        {
            jRadioButton1.setSelected(false);
            jRadioButton3.setSelected(false);
            jRadioButton4.setSelected(false);
            jButton1.setEnabled(true);//makes button avaliable after a jradiobutton is select
        }
    }                                             

    private void jRadioButton4ActionPerformed(java.awt.event.ActionEvent evt) {                                              
        
        //Makes sure that only one jRadiobutton can be selected
        if(jRadioButton4.isSelected() && questionID >= 1)
        {
            jRadioButton1.setSelected(false);
            jRadioButton2.setSelected(false);
            jRadioButton3.setSelected(false);
            jButton1.setEnabled(true);//makes button avaliable after a jradiobutton is select
        }
    }                                             

    private void jTextField6KeyReleased(java.awt.event.KeyEvent evt) {                                        
        
        //Makes button avaliable after entering username
        jButton1.setEnabled(true);
    }                                       

    private void jLabel6MouseClicked(java.awt.event.MouseEvent evt) {                                     
        // TODO add your handling code here:
        //Changes to the Used 5050 icon
        if(questionID >= 1)
        {    
            ImageIcon[] images = new ImageIcon[1];
            for(int i = 0; i < images.length; i++)
            {
                images[i] = new ImageIcon(getClass().getResource("/test/Image/" + imageUsefifty[i]));
            }
            if (Usefifty < 0) Usefifty = 1;
            if(Usefifty >= 0 && Usefifty < imageUsefifty.length)
            {
                jLabel6.setIcon(images[Usefifty]);

                Usefifty ++;
            }
            
            //diables jradiobuttons for 5050
            Fiftyfifty2();


            clicked = clicked + 1;

            //Diables the 5050 button after use
            if(clicked == 0)
            {
                jLabel6.setEnabled(true);
            }
            else
            {
                jLabel6.setEnabled(false);
            }
        }
    }                                    

    
    /**
     * @param args the command line arguments
     */
    /*public static void main(String args[]) {
        
        java.awt.EventQueue.invokeLater(() -> {
            new Game().setVisible(true);
        });
    }*/

    // Variables declaration - do not modify                     
    private javax.swing.ButtonGroup buttonGroup1;
    private javax.swing.JButton jButton1;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JLabel jLabel3;
    private javax.swing.JLabel jLabel4;
    private javax.swing.JLabel jLabel5;
    private javax.swing.JLabel jLabel6;
    private javax.swing.JRadioButton jRadioButton1;
    private javax.swing.JRadioButton jRadioButton2;
    private javax.swing.JRadioButton jRadioButton3;
    private javax.swing.JRadioButton jRadioButton4;
    private javax.swing.JTextField jTextField1;
    private javax.swing.JTextField jTextField6;
    // End of variables declaration                   
}
