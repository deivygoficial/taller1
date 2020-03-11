# taller1
import java.util.Scanner;

public class Ramdomizer {
	public static void main (String [] args){
		Scanner sc = new Scanner (System.in);
		int numPlayers=0; 
		int difNevel=0;
		int i=30;
		int cont=0;
		boolean nP=true;
		boolean dN=true;
		boolean winGame=false;

		while (nP==true){
			System.out.println("===========================================");
			System.out.println("  > Dijite el numero de jugadores (2-4): ");numPlayers=sc.nextInt();
			if (numPlayers<2){
				System.out.println("===========================================");
				System.out.println("===========================================");
				System.out.println("  X NO PUEDEN JUGAR MENOS DE 2 PERSONAS  X ");
				System.out.println("===========================================");
				try{
				Thread.sleep(3000);
				}catch(InterruptedException e ) {}
			while (cont<=i){
				System.out.println("");
				cont=cont+1;
			}
				cont=0;
			}
			
			else
				if (numPlayers>4){
					System.out.println("===========================================");
					System.out.println("===========================================");
					System.out.println("  X  NO PUEDEN JUGAR MAS DE 4 PERSONAS  X ");
					System.out.println("===========================================");
					try{
						Thread.sleep(3000);
						}catch(InterruptedException e ) {}
					while (cont<=i){
						System.out.println("");
						cont=cont+1;
					}
						cont=0;
			}else nP=false;
			System.out.println("===========================================");  //ciclo para el numero de jugadores
		}

		while (cont<=i){
				System.out.println("");
				cont=cont+1;
			}
				cont=0;

		while (dN==true){
				System.out.println("===========================================");
				System.out.print("      >> Numero de Jugadores: ");System.out.println(numPlayers);
				System.out.println("===========================================");
				System.out.println("  > Elija el nivel que desean jugar:): ");
				System.out.println("   (1) Nivel basico: 20 Puntos.  ");
				System.out.println("   (2) Nivel intermedio: 30 Puntos.  ");
				System.out.println("   (3) Nivel avanzado: 50 Puntos.  ");
				System.out.println("");
				difNevel=sc.nextInt();
				if (difNevel>3){
					System.out.println("===========================================");
					System.out.println("   X ELIJA UN NIVEL DE JUEGO VALIDO  X ");
					System.out.println("===========================================");
					try{
						Thread.sleep(3000);
						}catch(InterruptedException e ) {}
					while (cont<=i){
						System.out.println("");
						cont=cont+1;
					}
						cont=0;
				}else if (difNevel<1){
					System.out.println("===========================================");
					System.out.println("   X ELIJA UN NIVEL DE JUEGO VALIDO  X ");
					System.out.println("===========================================");
					try{
						Thread.sleep(3000);
						}catch(InterruptedException e ) {}
					while (cont<=i){
						System.out.println("");
						cont=cont+1;
					}
						cont=0;
				} else dN=false;		  //ciclo para la dificultad del nivel
		}

		while (cont<=i){
				System.out.println("");
				cont=cont+1;
			}
				cont=0;

		int[] playerPoints = new int[numPlayers];

		int pointsWin=0;
		int turno=0;
		int dado1=0;
		int dado2=0;
		int parCont=0;
		int comboWin=0;
		int winner=0;
		int pointTurno=0;
		int reasonWin=0;
		int playerWinner=0;

		if (difNevel==1){pointsWin=20;}
		if (difNevel==2){pointsWin=30;}
		if (difNevel==3){pointsWin=50;}
		//playerPoints[2]=difNevel;

		while (winGame==false){
			turno=turno+1;

			if (turno==1){
				while (cont<=i){
					System.out.println("");
					cont=cont+1;
				}
					cont=0;

				dado1= (int) Math.floor(Math.random()*6+1);
				dado2= (int) Math.floor(Math.random()*6+1);
				System.out.println("===========================================");
				System.out.print("            PLAYER ");	System.out.println(turno);
				System.out.print("  Puntuacion: ");System.out.println(playerPoints[0]);
				System.out.println("===========================================");
				System.out.print(" DADO 1: "); System.out.println(dado1);
				System.out.print(" DADO 2: "); System.out.println(dado2);
				System.out.println("===========================================");

				pointTurno=dado1+dado2;
				playerPoints[0]=playerPoints[0]+pointTurno;

				System.out.print("  Nueva Puntuacion: ");System.out.println(playerPoints[0]);
				System.out.println("===========================================");

				if (dado1==dado2){
					parCont=parCont+1;
					System.out.println(" Felicidades saco par, tiene otra tirada.");
					System.out.println("===========================================");
					try{
						Thread.sleep(2000);
							}catch(InterruptedException e ) {}
				} else if (dado1!=dado2) {comboWin=0; parCont=0;}
					try{
						Thread.sleep(4000);
							}catch(InterruptedException e ) {}
				if (parCont>=1){comboWin=comboWin+1; turno=turno-1;}
				if (comboWin==3){ winGame= true; winner=turno+1; reasonWin=1;}

				if (playerPoints[0]>=pointsWin){winGame=true; reasonWin=2;playerWinner=1;}		

			}
			if (turno==2){
				while (cont<=i){
					System.out.println("");
					cont=cont+1;
				}
					cont=0;

				dado1= (int) Math.floor(Math.random()*6+1);
				dado2= (int) Math.floor(Math.random()*6+1);
				System.out.println("===========================================");
				System.out.print("            PLAYER ");	System.out.println(turno);
				System.out.print("  Puntuacion: ");System.out.println(playerPoints[1]);
				System.out.println("===========================================");
				System.out.print(" DADO 1: "); System.out.println(dado1);
				System.out.print(" DADO 2: "); System.out.println(dado2);
				System.out.println("===========================================");

				pointTurno=dado1+dado2;
				playerPoints[1]=playerPoints[1]+pointTurno;
				System.out.print("  Nueva Puntuacion: ");System.out.println(playerPoints[1]);
				System.out.println("===========================================");

				if (dado1==dado2){
					parCont=parCont+1;
					System.out.println(" Felicidades saco par, tiene otra tirada.");
					System.out.println("===========================================");
					try{
						Thread.sleep(2000);
							}catch(InterruptedException e ) {}
				} else if (dado1!=dado2) {comboWin=0; parCont=0;}
					try{
						Thread.sleep(4000);
							}catch(InterruptedException e ) {}
				if (parCont>=1){comboWin=comboWin+1; turno=turno-1;}
				if (comboWin==3){ winGame= true; winner=turno+1; reasonWin=1;}		
				if (playerPoints[1]>=pointsWin){winGame=true; reasonWin=2;playerWinner=2;}			

			}
			if (turno==3){
				while (cont<=i){
					System.out.println("");
					cont=cont+1;
				}
					cont=0;

				dado1= (int) Math.floor(Math.random()*6+1);
				dado2= (int) Math.floor(Math.random()*6+1);
				System.out.println("===========================================");
				System.out.print("            PLAYER ");	System.out.println(turno);
				System.out.print("  Puntuacion: ");System.out.println(playerPoints[2]);
				System.out.println("===========================================");
				System.out.print(" DADO 1: "); System.out.println(dado1);
				System.out.print(" DADO 2: "); System.out.println(dado2);
				System.out.println("===========================================");

				pointTurno=dado1+dado2;
				playerPoints[2]=playerPoints[2]+pointTurno;
				System.out.print("  Nueva Puntuacion: ");System.out.println(playerPoints[2]);
				System.out.println("===========================================");

				if (dado1==dado2){
					parCont=parCont+1;
					System.out.println(" Felicidades saco par, tiene otra tirada.");
					System.out.println("===========================================");
					try{
						Thread.sleep(2000);
							}catch(InterruptedException e ) {}
				} else if (dado1!=dado2) {comboWin=0; parCont=0;}
						try{
						Thread.sleep(4000);
							}catch(InterruptedException e ) {}
				if (parCont>=1){comboWin=comboWin+1; turno=turno-1;}
				if (comboWin==3){ winGame= true; winner=turno+1; reasonWin=1;}	
				if (playerPoints[2]>=pointsWin){winGame=true; reasonWin=2;playerWinner=3;}				

			}
			if (turno==4){
				while (cont<=i){
					System.out.println("");
					cont=cont+1;
				}
					cont=0;

				dado1= (int) Math.floor(Math.random()*6+1);
				dado2= (int) Math.floor(Math.random()*6+1);
				System.out.println("===========================================");
				System.out.print("            PLAYER ");	System.out.println(turno);
				System.out.print("  Puntuacion: ");System.out.println(playerPoints[3]);
				System.out.println("===========================================");
				System.out.print(" DADO 1: "); System.out.println(dado1);
				System.out.print(" DADO 2: "); System.out.println(dado2);
				System.out.println("===========================================");

				pointTurno=dado1+dado2;
				playerPoints[3]=playerPoints[3]+pointTurno;
				System.out.print("  Nueva Puntuacion: ");System.out.println(playerPoints[3]);
				System.out.println("===========================================");

				if (dado1==dado2){
					parCont=parCont+1;
					System.out.println(" Felicidades saco par, tiene otra tirada.");
					System.out.println("===========================================");
					try{
						Thread.sleep(2000);
							}catch(InterruptedException e ) {}
				} else if (dado1!=dado2) {comboWin=0; parCont=0;}
					try{
						Thread.sleep(4000);
							}catch(InterruptedException e ) {}
				if (parCont>=1){comboWin=comboWin+1; turno=turno-1;}
				if (comboWin==3){ winGame= true; winner=turno+1; reasonWin=1;}		
				if (playerPoints[3]>=pointsWin){winGame=true; reasonWin=2;playerWinner=4;}			

			}

			if (turno==numPlayers){turno=0;}	
		}

		while (cont<=i){
					System.out.println("");
					cont=cont+1;
				}
					cont=0;

		System.out.println("==============================================");
		System.out.print("    	FELICITACIONES HA GANADO PLAYER ");System.out.println(playerWinner);
		System.out.println("==============================================");
		System.out.println("              HA GANADO POR");
		if (reasonWin==1){
		System.out.println("             COMBO DE PARES");
		} else if (reasonWin==2){
		System.out.println("   SUPERAR O IGUALAR LA PUNTUACION DE JUEGO");
		}
		System.out.println("==============================================");

		if (playerWinner==1){
			System.out.print("	Puntuacion Final: ");System.out.println(playerPoints[0]);
		}else if (playerWinner==2){
			System.out.print("	Puntuacion Final: ");System.out.println(playerPoints[1]);
		}else if (playerWinner==3){
			System.out.print("	Puntuacion Final: ");System.out.println(playerPoints[2]);
		}else if (playerWinner==4){
			System.out.print("	Puntuacion Final: ");System.out.println(playerPoints[3]);
		}
		System.out.println("==============================================");




		//System.out.println(playerPoints[2]);
		//int valorEntero = (int) Math.floor(Math.random()*6+1);
		System.out.println("		FIN DEL JUEGO");
		System.out.println("==============================================");
	}
} 
