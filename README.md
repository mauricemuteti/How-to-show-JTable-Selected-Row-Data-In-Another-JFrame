# How-to-show-JTable-Selected-Row-Data-In-Another-JFrame
How to show JTable Selected Row Data In Another JFrame
For more details - http://mauricemuteti.info/how-to-show-jtable-selected-row-data-in-another-jframe/
Video tutorial - https://www.youtube.com/watch?v=fSQQMlrdmzc

<pre>
private void jButton5ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
        viewSelectedRow.setVisible(true);
        //prevent the frame from closing the parent frame
        viewSelectedRow.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
         
//        Get selected row
        int selectedRowForNewJframe = jTable1.getSelectedRow();
         
//        check if the row is selected
        if (selectedRowForNewJframe == -1) {
            //display error message
            viewSelectedRow.jLabel1NoselectedRowMessage.setText("No Row Selected !!..");
        } else {
        //Clear error message first
            viewSelectedRow.jLabel1NoselectedRowMessage.setText(null);
            System.out.println("selected row value  " + selectedRowForNewJframe);
             
             
             
            //Retrieving jtable selected row
             
            String newName = model.getValueAt(selectedRowForNewJframe, 0).toString();
            String newGender = model.getValueAt(selectedRowForNewJframe, 1).toString();
            String newProgrammingLanguage = model.getValueAt(selectedRowForNewJframe, 2).toString();
            String newsubject = model.getValueAt(selectedRowForNewJframe, 3).toString();
             
            JLabel newImageJL = (JLabel) model.getValueAt(selectedRowForNewJframe, 4);
            ImageIcon newImageIcon = (ImageIcon) newImageJL.getIcon();
             
            //Resize image to fit new Jlabel
            Image newImage = newImageIcon.getImage().getScaledInstance(viewSelectedRow.jLabelImageNewJframe.getWidth(), viewSelectedRow.jLabelImageNewJframe.getHeight(), Image.SCALE_SMOOTH);
                     
            //Displaying selected row on new jframe input fields
            viewSelectedRow.jTextFieldNameNewJframe.setText(newName);
            viewSelectedRow.jTextFieldGenderNewJframe.setText(newGender);
            viewSelectedRow.jTextFieldPLanguageNewJframe.setText(newProgrammingLanguage);
            viewSelectedRow.jTextFieldSubjectNewJframe.setText(newsubject);
            viewSelectedRow.jLabelImageNewJframe.setIcon(new ImageIcon(newImage));
             
         
        }
    }        

</pre>
