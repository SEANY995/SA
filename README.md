# Conversión de Fechas


import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

public class ConversiónFechas {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Ingrese una fecha (YYYY-MM-DD): ");
        String fecha = scanner.nextLine();

        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd");
        LocalDate fechaLocal = LocalDate.parse(fecha, formatter);

        LocalDate fechaSemanaDespués = fechaLocal.plusWeeks(1);
        LocalDate fechaMesAntes = fechaLocal.minusMonths(1);

        System.out.println("Fecha una semana después: " + fechaSemanaDespués);
        System.out.println("Fecha un mes antes: " + fechaMesAntes);
    }
}


Comparación de Cadenas


import java.util.Scanner;

public class ComparaciónCadenas {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Ingrese la primera cadena: ");
        String cadena1 = scanner.nextLine();
        System.out.println("Ingrese la segunda cadena: ");
        String cadena2 = scanner.nextLine();

        if (cadena1.length() == cadena2.length()) {
            System.out.println("Las cadenas tienen la misma longitud.");
        } else {
            System.out.println("Las cadenas no tienen la misma longitud.");
        }

        if (cadena1.equals(cadena2)) {
            System.out.println("Las cadenas son iguales.");
        } else {
            System.out.println("Las cadenas no son iguales.");
        }
    }
}


Manipulación de Texto


import java.util.Scanner;

public class ManipulaciónTexto {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Ingrese un texto largo: ");
        String texto = scanner.nextLine();

        int conteo = 0;
        String[] palabras = texto.split("\\s+");

        for (String palabra : palabras) {
            if (palabra.equalsIgnoreCase("ingeniería")) {
                conteo++;
            }
        }

        System.out.println("La palabra 'ingeniería' aparece " + conteo + " veces en el texto.");
    }
}


Convertir Nombres


import java.util.Scanner;

public class ConvertirNombres {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("Ingrese el nombre completo de una persona en minúsculas (o 'salir' para terminar): ");
            String nombre = scanner.nextLine();

            if (nombre.equalsIgnoreCase("salir")) {
                break;
            }

            String[] palabras = nombre.split("\\s+");
            StringBuilder nombreConvertido = new StringBuilder();

            for (String palabra : palabras) {
                nombreConvertido.append(Character.toUpperCase(palabra.charAt(0)));
                nombreConvertido.append(palabra.substring(1).toLowerCase());
                nombreConvertido.append(" ");
            }

            System.out.println("Nombre convertido: " + nombreConvertido.toString().trim());
        }
    }
}
