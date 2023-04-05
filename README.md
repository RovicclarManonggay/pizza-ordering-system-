# pizza-ordering-system-
import 	   java.swing.*;
import    java.aw.event.*;
import    java.swing.border*;

public class Pizza extends JFrame
{
	public static void main(String [ ] args)
	{
		new Pizza();
	}

	private JButton buttonOk;
	private JRadioButton small, medium, large;
	private JCheckBox pepporoni, mushrooms, anchovies;

	public Pizza()
	{
		this.setSize(320,200);
		this.setTitle("Order Your Pizza);
		set.DefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

                ButtonListener b1 = new ButtonListener();
		JPanel mainPanel = new JPanel();
		JPanel sizePanel = new JPanel();

		Border b1 = BorderFactory.createTitledBorder("Size");
		sizePanel.setBorder(b1);

		ButtonGroup sizeGroup = new ButtonGroup();

		small = new JRadioButton("Small");
		small.setSelected(true);
		sizePanel.add(small);
		sizeGroup.add(small);

	   medium = new JRadioButton("Medium");
		sizePanel.add(medium);
		sizeGroup.add(large);

		mainPanel.add(sizePanel);

		JPanel topPanel = new JPanel();
		Border b2 = BorderFactory.createTitleBorder("toppings*);
		topPanel.setBorder(b2)
               
mushrooms = new JCheckBox("Mushrooms");
		topPanel.add(mushrooms);


		anchovies = new JCheckBox("Anchovies");
		topPanel.add(anchovies);

		pepperoni = new JCheckBox("Pepperoni");
		topPanel.add(pepperoni);

		mainPanel.add(topPanel);

		buttonOk  = new JButton("OK");
		buttonOK.addActionListener(b1);
		mainPanel.add(buttonOK);

		this.add(mainPanel);
		this.setVisible(true);
	}
		
		private class ButtonListener implements ActionListener
	{
		public void actionPerformed(ActionEvent e)
			if (e.getSource() == buttonOK)
			{
				String tops = "";
				if (pepporoni.isSelected())
				tops += "Pepperoni \n";
				if (mushrooms.isSelected())
				tops += "Mushrooms \n";
				if(anchovies.isSelected())
				tops +="Anchovies \n";

			String msg = "You ordered a ";
			if (small.isSelected())
			msg += "small pizza with";
			if(medium.isSelected())
			msg+= "medium pizza with";
			if(large.isSelected())
			msg+="small pizza with";

			if(tops.equals(""))
			msg += "no toppings.";
			else
			msg += "the following toppings: \n" + tops;


                 JOptionPane.showMessageDialog(buttonOk, msg, "Your Order", JOptionsPane.INFORMATION_MESSAGE);
 
		pepperoni.setSelected(false);		
		mushrooms.setSelected(false);		
		anchovies.setSelected(false);
		small.setSelected(true)

