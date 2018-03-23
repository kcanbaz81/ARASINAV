# ARASINAV
package org.eclipse.wb.swing;
import java.util.Random;

import java.awt.BorderLayout;
import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JButton;
import java.awt.List;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import java.awt.Color;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
public class say extends JFrame {

	private JPanel contentPane;

	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					say frame = new say();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	
	public say() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 420, 420);
		contentPane = new JPanel();
		contentPane.setBackground(Color.BLACK);
		contentPane.setForeground(Color.GREEN);
		contentPane.setBorder(new EmptyBorder(3, 3, 3, 3));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		List list = new List();
		list.setBounds(55, 135, 115, 200);
		contentPane.add(list);
		
		List list_1 = new List();
		list_1.setBounds(230, 135, 115, 200);
		contentPane.add(list_1);
		
		JButton btnNewButton = new JButton("RANDOM DEĞER");
		btnNewButton.setBounds(110, 5, 180, 50);
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				Random random = new Random();
				int deger = random.nextInt(100);
				String sayi = Integer.toString(deger);
				if(deger > 50) {
					list.add(sayi);
						
				}
				else if (deger<50) {
					list_1.add(sayi);
				}
				if(deger==50) {
					JOptionPane.showMessageDialog(null,"SAYI 50 YE EŞİT");
				}
			}
		});
		
		
		contentPane.add(btnNewButton);
		
		JLabel lblX = new JLabel("50Den Büyük");
		lblX.setBounds(95, 100, 75, 30);
		contentPane.add(lblX);
		
		JLabel lblX_1 = new JLabel("50Den Küçük");
		lblX_1.setBounds(255, 105, 85, 15);
		contentPane.add(lblX_1);
		
	}
}
