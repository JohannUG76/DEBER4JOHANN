package application;

import javafx.application.Application; import javafx.scene.Scene; import javafx.scene.control.*; import javafx.scene.layout.BorderPane; import javafx.stage.Stage;

public class Main extends Application { @Override public void start(Stage primaryStage) { try { // Crear la barra de menú MenuBar menuBar = new MenuBar(); menuBar.getStyleClass().add("menu-bar");

        // Menú Archivo
        Menu fileMenu = new Menu("Archivo");
        fileMenu.getStyleClass().add("menu-file");
        MenuItem newFile = new MenuItem("Nuevo");
        MenuItem openFile = new MenuItem("Abrir");
        MenuItem saveFile = new MenuItem("Guardar");
        MenuItem exitFile = new MenuItem("Salir");

        // Acciones del menú Archivo
        newFile.setOnAction(e -> System.out.println("Nuevo archivo seleccionado"));
        openFile.setOnAction(e -> System.out.println("Abrir archivo seleccionado"));
        saveFile.setOnAction(e -> System.out.println("Guardar archivo seleccionado"));
        exitFile.setOnAction(e -> primaryStage.close());

        fileMenu.getItems().addAll(newFile, openFile, saveFile, new SeparatorMenuItem(), exitFile);

        // Menú Editar
        Menu editMenu = new Menu("Editar");
        editMenu.getStyleClass().add("menu-edit");
        MenuItem cut = new MenuItem("Cortar");
        MenuItem copy = new MenuItem("Copiar");
        MenuItem paste = new MenuItem("Pegar");

        // Acciones del menú Editar
        cut.setOnAction(e -> System.out.println("Cortar seleccionado"));
        copy.setOnAction(e -> System.out.println("Copiar seleccionado"));
        paste.setOnAction(e -> System.out.println("Pegar seleccionado"));

        editMenu.getItems().addAll(cut, copy, paste);

        // Menú Ayuda
        Menu helpMenu = new Menu("Ayuda");
        helpMenu.getStyleClass().add("menu-help");
        MenuItem about = new MenuItem("Acerca de");

        about.setOnAction(e -> System.out.println("Acerca de seleccionado"));

        helpMenu.getItems().add(about);

        // Agregar menús a la barra de menú
        menuBar.getMenus().addAll(fileMenu, editMenu, helpMenu);

        // Crear el BorderPane y agregar la barra de menú
        BorderPane root = new BorderPane();
        root.setTop(menuBar);

        // Crear la escena
        Scene scene = new Scene(root, 400, 300);

        // Agregar la hoja de estilos
        scene.getStylesheets().add(getClass().getResource("application.css").toExternalForm());

        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Barra");
        primaryStage.show();
    } catch (Exception e) {
        e.printStackTrace();
    }
}

public static void main(String[] args) {
    launch(args);
}

![Captura de pantalla 2024-06-11 204209](https://github.com/JohannUG76/DEBER4JOHANN/assets/169223501/7dc8a2c3-aede-45dc-82a7-6fcdfc063deb)
