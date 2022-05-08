# ContextMenu

Компонент `ContextMenu` представлений класом
`javafx.scene.control.ContextMenu`, екземпляр якого може бути створений за допомогою класу-фабрики `ContextMenuBuilder`
або за допомогою одного з конструкторів:

- `ContextMenu contextMenu = new ContextMenu();`
- `ContextMenu contextMenu = new ContextMenu(MenuItem... items);`

Клас `ContextMenu` представляє контекстне меню GUI-компонентів `Control`, що відкривається при натисканні правою кнопкою
миші, і має такі властивості:

- успадковані від класу `javafx.stage.Window` властивості:
  eventDispatcher
    * focused
    * height
    * onCloseRequest
    * onHidden
    * onHiding
    * onShowing
    * onShown
    * opacity
    * scene
    * showing
    * width
    * x
    * y
- успадковані від класу `javafx.stage.PopupWindow` властивості:
    * autoFix
    * autoHide
    * hideOnEscape
    * onAutoHide
    * ownerNode
    * ownerWindow
- успадковані від класу `javafx.scene.control.PopupControl` властивості:
    * id
    * maxHeight
    * maxWidth
    * minHeight
    * minWidth
    * prefHeight
    * prefWidth
    * skin
    * style
- власну властивість `onAction`.

Елементи контекстного меню `ContextMenu` представлені класом `javafx.scene.control.MenuItem` і складають
набір `javafx.collections.ObservableList<MenuItem>`, який можна поповнити за допомогою методу `getItems().addAll()`
класу `javafx.scene.control.ContextMenu`.

Примірники класу `MenuItem` можуть бути створені за допомогою класу-фабрики `MenuItemBuilder` або за допомогою одного з
конструкторів:

- `MenuItem menuItem = new MenuItem();`
- `MenuItem menuItem = new MenuItem("[текст]");`
- `MenuItem menuItem = new MenuItem("[текст]", [вузол значка]);`

Клас `MenuItem` має властивості `accelerator`, `disabled`, `graphic`, `id`,
`mnemonicParsing`, `onAction`, `parentMenu`, `parentPopup`, `style`, `text` і `visible` і підкласи `CheckMenuItem`
, `CustomMenuItem`, `Menu`, `RadioMenuItem`. Тому в контекстне меню ContextMenu можна додавати не тільки
елементи `MenuItem`, але й прапорці `CheckMenuItem` та перемикачі `RadioMenuItem`, а також
роздільники `SeparatorMenuItem`, представлені класом `SeparatorMenuItem`, що розширює клас `CustomMenuItem`, і вкладені
меню `Menu`.

Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить контекстне меню `ContextMenu`, скористайтесь проектом `JavaFXApplicationTreeView`. У вікні Проекти клацніть
   правою клавішею миші на проекті `JavaFXApplicationTreeView`, виберіть `Копіювати` та змініть назву проекту на
   `JavaFXApplicationContextMenu`.
2. Змініть код методу `start()` класу `JavaFXApplicationTreeView`. Під час створення дерева `TreeView` створіть
   екземпляр контекстного меню `ContextMenu`, для нього встановіть стиль та набір компонентів
   `MenuItem`. Для елементів меню `Видалити`, `Копіювати` та `Вставити`
   визначте швидкі клавіші, а для елемента `Видалити` встановіть обробник подій, який видалятиме вибраний вузол
   дерева `TreeView`. Створене контекстне меню `ContextMenu` приєднайте до дерева
   `TreeView` методом `setContextMenu()`:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTreeViewContextMenu extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        Image rootimg = new Image(this.getClass().getResource("rootimg.png").toString());
        final ImageView rootimv = new ImageView(rootimg);
        rootimv.setFitHeight(20);
        rootimv.setFitWidth(20);

        Image packageimg = new Image(this.getClass().getResource("packageimg.png").toString());
        final ImageView packageimv = new ImageView(packageimg);
        packageimv.setFitHeight(20);
        packageimv.setFitWidth(20);

        Image packagesimg = new Image(this.getClass().getResource("packagesimg.png").toString());
        final ImageView packagesimv = new ImageView(packagesimg);
        packagesimv.setFitHeight(20);
        packagesimv.setFitWidth(20);

        Image sourceimg = new Image(this.getClass().getResource("sourceimg.png").toString());
        final ImageView sourceimv = new ImageView(sourceimg);
        sourceimv.setFitHeight(20);

        sourceimv.setFitWidth(20);

        TreeItem<String> rootTree = new TreeItem<>("JavaFXApplicationTreeView");
        rootTree.setExpanded(true);
        rootTree.setGraphic(rootimv);

        TreeItem<String> itemPS = new TreeItem<>("Пакети вихідних файлів");
        itemPS.setExpanded(true);
        itemPS.setGraphic(packagesimv);

        TreeItem<String> itemP = new TreeItem<>("javafxapplication");
        itemP.setExpanded(true);
        itemP.setGraphic(packageimv);

        final TreeItem<String> itemS = new TreeItem<>("JavaFXApplication.java");
        itemS.setGraphic(sourceimv);
        itemP.getChildren().addAll(itemS);
        itemPS.getChildren().addAll(itemP);
        rootTree.getChildren().addAll(itemPS);

        TreeView<String> treeView = new TreeView<>(rootTree);
        treeView.setLayoutX(10);
        treeView.setLayoutY(10);
        treeView.setCursor(Cursor.CLOSED_HAND);
        treeView.setStyle("-fx-border-width:3pt;-fx-border-color:#f0e68c;-fx-font:12pt Georgia;");
        treeView.setPrefSize(300, 200);
        treeView.getSelectionModel().selectedItemProperty().addListener(
                (ObservableValue<? extends TreeItem<String>> ov, TreeItem<String>
                        old_val, TreeItem<String> new_val) -> {
                    if (new_val == itemS) {
                        System.out.println("Редагування вихідного коду");
                    }
                });

        ContextMenu contextMenu = new ContextMenu();
        contextMenu.setStyle("-fx-text-fill:#808000;-fx-font:bold italic 11pt Georgia;");
        MenuItem menuItemDel = new MenuItem("Видалити");
        menuItemDel.setAccelerator(KeyCombination.keyCombination("Ctrl+D"));
        menuItemDel.setOnAction((ActionEvent e) -> {
            TreeItem<String>
                    item = treeView.getSelectionModel().getSelectedItem();
            if (item != treeView.getRoot()) {
                treeView.getSelectionModel().getSelectedItem().getParent().
                        getChildren().remove(item);
                System.out.println("Вузол " + item.getValue() + " видалений");
            }
        });

        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+C"));

        MenuItem menuItemPaste = new MenuItem("Вставити");
        menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        SeparatorMenuItem sep = new SeparatorMenuItem();
        contextMenu.getItems().addAll(menuItemDel, menuItemCopy, menuItemPaste, sep);
        treeView.setContextMenu(contextMenu);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: TreeView");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

3. Змініть заголовок основного вікна JavaFX-додатку на
   `“Тестування GUI-компонентів: TreeView, ContextMenu”`:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTreeViewContextMenu extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        Image rootimg = new Image(this.getClass().getResource("rootimg.png").toString());
        final ImageView rootimv = new ImageView(rootimg);
        rootimv.setFitHeight(20);
        rootimv.setFitWidth(20);

        Image packageimg = new Image(this.getClass().getResource("packageimg.png").toString());
        final ImageView packageimv = new ImageView(packageimg);
        packageimv.setFitHeight(20);
        packageimv.setFitWidth(20);

        Image packagesimg = new Image(this.getClass().getResource("packagesimg.png").toString());
        final ImageView packagesimv = new ImageView(packagesimg);
        packagesimv.setFitHeight(20);
        packagesimv.setFitWidth(20);

        Image sourceimg = new Image(this.getClass().getResource("sourceimg.png").toString());
        final ImageView sourceimv = new ImageView(sourceimg);
        sourceimv.setFitHeight(20);

        sourceimv.setFitWidth(20);

        TreeItem<String> rootTree = new TreeItem<>("JavaFXApplicationTreeView");
        rootTree.setExpanded(true);
        rootTree.setGraphic(rootimv);

        TreeItem<String> itemPS = new TreeItem<>("Пакети вихідних файлів");
        itemPS.setExpanded(true);
        itemPS.setGraphic(packagesimv);

        TreeItem<String> itemP = new TreeItem<>("javafxapplication");
        itemP.setExpanded(true);
        itemP.setGraphic(packageimv);

        final TreeItem<String> itemS = new TreeItem<>("JavaFXApplication.java");
        itemS.setGraphic(sourceimv);
        itemP.getChildren().addAll(itemS);
        itemPS.getChildren().addAll(itemP);
        rootTree.getChildren().addAll(itemPS);

        TreeView<String> treeView = new TreeView<>(rootTree);
        treeView.setLayoutX(10);
        treeView.setLayoutY(10);
        treeView.setCursor(Cursor.CLOSED_HAND);
        treeView.setStyle("-fx-border-width:3pt;-fx-border-color:#f0e68c;-fx-font:12pt Georgia;");
        treeView.setPrefSize(300, 200);
        treeView.getSelectionModel().selectedItemProperty().addListener(
                (ObservableValue<? extends TreeItem<String>> ov, TreeItem<String>
                        old_val, TreeItem<String> new_val) -> {
                    if (new_val == itemS) {
                        System.out.println("Редагування вихідного коду");
                    }
                });

        ContextMenu contextMenu = new ContextMenu();
        contextMenu.setStyle("-fx-text-fill:#808000;-fx-font:bold italic 11pt Georgia;");
        MenuItem menuItemDel = new MenuItem("Видалити");
        menuItemDel.setAccelerator(KeyCombination.keyCombination("Ctrl+D"));
        menuItemDel.setOnAction((ActionEvent e) -> {
            TreeItem<String>
                    item = treeView.getSelectionModel().getSelectedItem();
            if (item != treeView.getRoot()) {
                treeView.getSelectionModel().getSelectedItem().getParent().
                        getChildren().remove(item);
                System.out.println("Вузол " + item.getValue() + " видалений");
            }
        });

        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+C"));

        MenuItem menuItemPaste = new MenuItem("Вставити");
        menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        SeparatorMenuItem sep = new SeparatorMenuItem();
        contextMenu.getItems().addAll(menuItemDel, menuItemCopy, menuItemPaste, sep);
        treeView.setContextMenu(contextMenu);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: TreeView, ContextMenu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі `Очистити та побудувати проект
   (Shift+F11)`, а потім – `Виконати проект (F6)`.
