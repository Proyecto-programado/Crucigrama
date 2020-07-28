# Crucigrama
package com.company;
public class Main {

    public static void main(String[] args) {

        int tamanio = 9;

        char[][] matriz = new char[tamanio][tamanio];
        //Espacios negros de la matriz
        String[] vectorEspaciosNegro = {"0 0", "0 1", "0 3", "0 4", "0 5" , "0 6" ,"0 8" , "1 5" , "1 6" ,"1 8" , "2 0", "2 1", "2 3" , "3 0", "3 1", "3 3" , "3 5" , "3 6" , "3 7" ,"3 8" , "4 0", "4 1", "4 5" , "4 6" , "4 7" ,"4 8" , "5 0", "5 1", "5 3" , "5 8" , "6 0", "6 1", "6 3", "6 4", "6 5" , "6 6" , "6 7" ,"6 8" , "7 0", "7 1", "7 3", "7 4",  "7 5" , "7 6" , "7 7" ,"7 8" , "8 0", "8 1", "8 3", "8 4", "8 5" , "8 6" , "8 7" ,"8 8"};
        //Posición de cada palabra
        String[] vectorPosiciones = {"0 7 v", "1 0 h", "2 4 v" , "3 4 v", "4 3 h", "4 3 v" , "5 6 h"};
        //Pistas de las palabras
        String[] vectorPistas = {"Causa, motivo\n", "Persona que interpreta una acción o un papel\n", "Metal precioso\n"};
        //Palabras por adivinar
        String[] vectorPalabras = {"Razon", "Actor", "Oro"};


        for (int i = 0; i < vectorEspaciosNegro.length; i++) {
            String[] posiciones = vectorEspaciosNegro[i].split(" ");
            int fila = Integer.parseInt(posiciones[0]);
            int columna = Integer.parseInt(posiciones[1]);
            matriz[fila][columna] = '%';
        }


        agregarPalabra(vectorPalabras[0], vectorPosiciones[0], matriz);


        for (int i = 0; i < tamanio; i++) {
            for (int j = 0; j < tamanio; j++) {
                System.out.print(matriz[i][j] + "\t");
            }
            System.out.println();
        }

    }

    public static void agregarPalabra(String palabra, String posicion, char[][] matriz) {
        String[] vectorTemporal = posicion.split(" ");
        int filaInicial = Integer.parseInt(vectorTemporal[0]);
        int columna = Integer.parseInt(vectorTemporal[1]);

        char[] vectorPalabra = palabra.toCharArray();

        if (vectorTemporal[2].equals("v")) {
            for(int fila = filaInicial; fila < palabra.length(); fila++) {
                matriz[fila][columna] = vectorPalabra[fila];
            }
        } else {
            //Falta de implementar
        }
    }
}
