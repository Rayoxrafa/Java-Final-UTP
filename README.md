# Java-Final-UTP
package principal;

import servicios.GestionEstudiantes;
import java.util.Scanner;

/**
 * Clase principal con el menú de la aplicación.
 */
public class Main {
    public static void main(String[] args) {
        GestionEstudiantes gestor = new GestionEstudiantes();
        Scanner scanner = new Scanner(System.in);
        int opcion;

        do {
            System.out.println("\n--- Menú Principal ---");
            System.out.println("1. Gestionar Estudiantes");
            System.out.println("2. Ver Reportes");
            System.out.println("3. Salir");
            System.out.print("Seleccione opción: ");
            opcion = scanner.nextInt();

            switch (opcion) {
                case 1:
                    menuGestion(gestor, scanner);
                    break;
                case 2:
                    gestor.listarEstudiantes();
                    break;
                case 3:
                    System.out.println("Programa finalizado.");
                    break;
                default:
                    System.out.println("Opción inválida.");
            }
        } while (opcion != 3);
        scanner.close();
    }

    private static void menuGestion(GestionEstudiantes gestor, Scanner scanner) {
        int opcion;
        do {
            System.out.println("\n--- Gestionar Estudiantes ---");
            System.out.println("1. Registrar");
            System.out.println("2. Buscar por ID");
            System.out.println("3. Buscar por Nombre");
            System.out.println("4. Actualizar");
            System.out.println("5. Volver al menú principal");
            System.out.print("Seleccione opción: ");
            opcion = scanner.nextInt();

            switch (opcion) {
                case 1:
                    gestor.registrarEstudiante();
                    break;
                case 2:
                    gestor.buscarPorID();
                    break;
                case 3:
                    gestor.buscarPorNombre();
                    break;
                case 4:
                    gestor.actualizarEstudiante();
                    break;
                case 5:
                    System.out.println("Regresando al menú principal...");
                    break;
                default:
                    System.out.println("Opción inválida.");
            }
        } while (opcion != 5);
    }
}
