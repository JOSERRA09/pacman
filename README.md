# pacman
/*NOMBRE COMPLETO :FLORES SANCHEZ JOSE RAMON
 * CARRERA : INGENIERIA EN DESARROLLO DE SFTWARE
 * TURNO : VESPERTINO
 * CARRERA : PROGRAMACION III
 */
package pacman;

import java.awt.EventQueue;
import java.awt.Graphics;
import java.awt.Graphics2D;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.text.TableView.TableRow;
import org.w3c.dom.Node;
import java.awt.BorderLayout;
import javax.swing.JButton;
import javax.swing.JComponent;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.SystemColor;
import java.awt.EventQueue;
import java.awt.Graphics;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.text.TableView.TableRow;
import java.awt.BorderLayout;
import javax.swing.JButton;
import javax.swing.JComponent;
import java.awt.Color;
import java.awt.Dimension;
import java.awt.SystemColor;


public class pacman {

	private JFrame frame;
	public int speed = 10;
	public int pac_x = 225, pac_y = 310;
	public elemet pacman = new elemet(pac_x, pac_y, 30, 30, Color.yellow);
	public elemet pared1 = new elemet(4, 0, 190, 10, Color.decode("#002AFA"));
	public elemet pared2 = new elemet(465, 0, 190, 10, Color.decode("#002AFA"));
	public elemet pared3 = new elemet(15, 0, 10, 450, Color.decode("#002AFA"));
	public elemet pared4 = new elemet(15, 380, 10, 450, Color.decode("#002AFA"));
	public elemet pared5 = new elemet(465, 250, 140, 10, Color.decode("#002AFA"));
	public elemet pared6 = new elemet(4, 250, 140, 10, Color.decode("#002AFA"));
	public elemet pared7 = new elemet(50, 40, 30, 60, Color.decode("#002AFA"));
	public elemet pared8 = new elemet(150, 40, 30, 60, Color.decode("#002AFA"));
	public elemet pared9 = new elemet(250, 10, 70, 20, Color.decode("#002AFA"));
	public elemet pared10 = new elemet(310, 40, 20, 40, Color.decode("#002AFA"));
	public elemet pared11 = new elemet(390, 40, 20, 40, Color.decode("#002AFA"));
	public elemet pared12 = new elemet(50, 140, 10, 40, Color.decode("#002AFA"));
	public elemet pared13 = new elemet(190, 120, 10, 100, Color.decode("#002AFA"));
	public elemet pared14 = new elemet(390, 140, 10, 40, Color.decode("#002AFA"));
	public elemet pared15 = new elemet(120, 120, 100, 10, Color.decode("#002AFA"));
	public elemet pared16 = new elemet(340, 120, 100, 10, Color.decode("#002AFA"));
	public elemet pared17 = new elemet(120, 170, 10, 40, Color.decode("#002AFA"));
	public elemet pared18 = new elemet(300, 170, 10, 40, Color.decode("#002AFA"));
	public elemet pared19 = new elemet(230, 130, 20, 10, Color.decode("#002AFA"));
	public elemet pared20 = new elemet(120, 260, 40, 10, Color.decode("#002AFA"));
	public elemet pared21 = new elemet(340, 260, 40, 10, Color.decode("#002AFA"));
	public elemet pared22 = new elemet(180, 260, 10, 120, Color.decode("#002AFA"));
	public elemet pared23 = new elemet(235, 260, 40, 10, Color.decode("#002AFA"));
	public elemet pared24 = new elemet(10, 250, 10, 40, Color.decode("#002AFA"));
	public elemet pared25 = new elemet(430, 250, 10, 40, Color.decode("#002AFA"));
	public elemet pared26 = new elemet(10, 180, 10, 40, Color.decode("#002AFA"));
	public elemet pared27 = new elemet(430, 180, 10, 40, Color.decode("#002AFA"));
	public elemet pared28 = new elemet(390, 310, 10, 30, Color.decode("#002AFA"));
	public elemet pared29 = new elemet(50, 310, 10, 30, Color.decode("#002AFA"));
	public elemet pared30 = new elemet(220, 340, 10, 40, Color.decode("#002AFA"));
	public elemet pared31 = new elemet(210, 180, 40, 10, Color.decode("#002AFA"));
	public elemet pared32 = new elemet(210, 210, 10, 50, Color.decode("#002AFA"));
	public elemet pared33 = new elemet(250, 180, 40, 10, Color.decode("#002AFA"));
	
	public elemet limEje_x = new elemet(-10, 90, 190, 10, Color.decode("#000000"));
	public elemet limEje_x2 = new elemet(480, 90, 190, 10, Color.decode("#000000"));

	
	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					pacman window = new pacman();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the application.
	 */
	public pacman() {
		initialize();
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		frame = new JFrame();
		frame.setBounds(100, 100, 500, 472);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		JPanel tablero = new JPanel();

		frame.addKeyListener(new KeyListener() {

			@Override
			public void keyTyped(KeyEvent e) {
				// TODO Auto-generated method stub

			}

			@Override
			public void keyReleased(KeyEvent e) {
				// TODO Auto-generated method stub

			}

			@Override
			public void keyPressed(KeyEvent e) {
				// TODO Auto-generated method stub
				System.out.println(e.getKeyCode());
				if (e.getKeyCode() == 38) {
					pacman.y -= speed;
				}
				if (e.getKeyCode() == 37) {
					pacman.y += speed;
				}
				if (e.getKeyCode() == 40) {
					pacman.x -= speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x += speed;
				}

				if (pacman.tocando(pared1)) {
					System.out.println("hola");

					if (e.getKeyCode() == 38) {
						pacman.y += speed;
					}

					if (e.getKeyCode() == 37) {
						pacman.x += speed;
					}

					if (e.getKeyCode() == 40) {
						pacman.x += speed;
					}

					if (e.getKeyCode() == 39) {
						pacman.x -= speed;
					}

				}
				if (pacman.tocando(pared2)) {

					if (e.getKeyCode() == 39) {
						pacman.x -= speed;
					}

					if (e.getKeyCode() == 38) {
						pacman.y += speed;
					}

				}

				if (pacman.tocando(limEje_x)) {
					if (e.getKeyCode() == 37) {
						pacman.x = 450;
					}
				}
				if (pacman.tocando(limEje_x2)) {
					System.out.println("hola");

					if (e.getKeyCode() == 39) {
						pacman.x = 0;
					}
				}
				if (pacman.tocando(pared3)) {

					if (e.getKeyCode() == 37) {
						pacman.y -= speed;
					}

					if (e.getKeyCode() == 38) {
						pacman.y += speed;
					}

				}
					if (pacman.tocando(pared4)) {

						if (e.getKeyCode() == 37) {
							pacman.y -= speed;
						}

						if (e.getKeyCode() == 38) {
							pacman.x += speed;
						}
					}
					
			
			if (pacman.tocando(pared5)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
				}
			}
			
			if (pacman.tocando(pared6)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
			}
			
			if (pacman.tocando(pared7)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}

			if (pacman.tocando(pared8)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared9)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}

			if (pacman.tocando(pared10)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			

			if (pacman.tocando(pared11)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared12)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared13)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared14)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared15)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared16)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared17)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared18)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared19)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared20)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared21)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared22)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared23)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared24)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared25)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared26)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared27)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared28)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared29)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared30)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared31)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
			if (pacman.tocando(pared32)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			if (pacman.tocando(pared33)) {

				if (e.getKeyCode() == 38) {
					pacman.y += speed;
				}

				if (e.getKeyCode() == 40) {
					pacman.x += speed;
				}
				if (e.getKeyCode() == 39) {
					pacman.x -= speed;
			
			}
				
				if (e.getKeyCode() == 37) {
					pacman.y -= speed;	
			}
			
			}
			
				tablero.repaint();
			}
		});
		frame.setFocusable(true);
		frame.requestFocus();

		JPanel panel = new JPanel();
		panel.setBackground(SystemColor.controlHighlight);
		frame.getContentPane().add(panel, BorderLayout.SOUTH);

		JButton btnNewButton = new JButton("New button");
		panel.add(btnNewButton);

		
		tablero.setBackground(Color.BLACK);
		frame.getContentPane().add(tablero, BorderLayout.CENTER);

		tablero.add(new MyGraphics());
	
	
	
}
   

public class MyGraphics extends JComponent {

	private static final long serialVersionUID = 1L;

	MyGraphics() {
		setPreferredSize(new Dimension(480, 420));
	}

	@Override
	public void paintComponent(Graphics g) {
		super.paintComponent(g);

		// fondo
		g.fillRect(0, 0, 480, 420);

		// Pacman
		g.setColor(pacman.c);
		g.fillArc(pacman.x, pacman.y, pacman.w, pacman.h, 0, 360);

		// pared
		g.setColor(pared1.c);
		g.fillRect(pared1.x, pared1.y, pared1.w, pared1.h);

		g.setColor(pared2.c);
		g.fillRect(pared2.x, pared2.y, pared2.w, pared2.h);

		g.setColor(pared3.c);
		g.fillRect(pared3.x, pared3.y, pared3.w, pared3.h);

		g.setColor(pared4.c);
		g.fillRect(pared4.x, pared4.y, pared4.w, pared4.h);

		g.setColor(pared5.c);
		g.fillRect(pared5.x, pared5.y, pared5.w, pared5.h);

		g.setColor(pared6.c);
		g.fillRect(pared6.x, pared6.y, pared6.w, pared6.h);

		g.setColor(pared7.c);
		g.fillRect(pared7.x, pared7.y, pared7.w, pared7.h);

		g.setColor(pared8.c);
		g.fillRect(pared8.x, pared8.y, pared8.w, pared8.h);

		g.setColor(pared9.c);
		g.fillRect(pared9.x, pared9.y, pared9.w, pared9.h);

		g.setColor(pared10.c);
		g.fillRect(pared10.x, pared10.y, pared10.w, pared10.h);

		g.setColor(pared11.c);
		g.fillRect(pared11.x, pared11.y, pared11.w, pared11.h);

		g.setColor(pared12.c);
		g.fillRect(pared12.x, pared12.y, pared12.w, pared12.h);

		g.setColor(pared13.c);
		g.fillRect(pared13.x, pared13.y, pared13.w, pared13.h);

		g.setColor(pared14.c);
		g.fillRect(pared14.x, pared14.y, pared14.w, pared14.h);

		g.setColor(pared15.c);
		g.fillRect(pared15.x, pared15.y, pared15.w, pared15.h);

		g.setColor(pared16.c);
		g.fillRect(pared16.x, pared16.y, pared16.w, pared16.h);

		g.setColor(pared17.c);
		g.fillRect(pared17.x, pared17.y, pared17.w, pared17.h);

		g.setColor(pared18.c);
		g.fillRect(pared18.x, pared18.y, pared18.w, pared18.h);

		g.setColor(pared19.c);
		g.fillRect(pared19.x, pared19.y, pared19.w, pared19.h);

		g.setColor(pared20.c);
		g.fillRect(pared20.x, pared20.y, pared20.w, pared20.h);

		g.setColor(pared21.c);
		g.fillRect(pared21.x, pared21.y, pared21.w, pared21.h);

		g.setColor(pared22.c);
		g.fillRect(pared22.x, pared22.y, pared22.w, pared22.h);

		g.setColor(pared23.c);
		g.fillRect(pared23.x, pared23.y, pared23.w, pared23.h);

		g.setColor(pared24.c);
		g.fillRect(pared24.x, pared24.y, pared24.w, pared24.h);

		g.setColor(pared25.c);
		g.fillRect(pared25.x, pared25.y, pared25.w, pared25.h);

		g.setColor(pared26.c);
		g.fillRect(pared26.x, pared26.y, pared26.w, pared26.h);

		g.setColor(pared27.c);
		g.fillRect(pared27.x, pared27.y, pared27.w, pared27.h);

		g.setColor(pared28.c);
		g.fillRect(pared28.x, pared28.y, pared28.w, pared28.h);

		g.setColor(pared29.c);
		g.fillRect(pared29.x, pared29.y, pared29.w, pared29.h);

		g.setColor(pared30.c);
		g.fillRect(pared30.x, pared30.y, pared30.w, pared30.h);

		g.setColor(pared31.c);
		g.fillRect(pared31.x, pared31.y, pared31.w, pared31.h);

		g.setColor(pared32.c);
		g.fillRect(pared32.x, pared32.y, pared32.w, pared32.h);

		g.setColor(pared33.c);
		g.fillRect(pared33.x, pared33.y, pared33.w, pared33.h);

		g.setColor(limEje_x.c);
		g.drawRect(limEje_x.x, limEje_x.y, limEje_x.w, limEje_x.h);

		g.setColor(limEje_x2.c);
		g.drawRect(limEje_x2.x, limEje_x2.y, limEje_x2.w, limEje_x2.h);

	}
}

public class elemet {

	int x, y, h, w;
	Color c;

	public elemet(int x, int y, int h, int w, Color c) {
		this.x = x;
		this.y = y;
		this.h = h;
		this.w = w;
		this.c = c;
	}

	public boolean tocando(elemet e) {

		// ss
		if (this.x < e.x + e.w && this.x + this.w > e.x &&

				this.y < e.y + e.h && this.y + this.h > e.y) {
			return true;
		} else {

		}
		return false;
	}

	
	}



}


