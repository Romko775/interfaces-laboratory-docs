# ListView

Компонент `ListView` представлений класом `javafx.scene.control.ListView<T>`, екземпляр якого може бути створений за
допомогою класу-фабрики `ListViewBuilder` або за допомогою одного з конструкторів:
- `ListView<String> listView = New ListView<String>();`
- `ListView<String> listView = new ListView<String>(ObservableList<String> list);`

Набір елементів `javafx.collections.ObservableList` списку `ListView` може бути створений за допомогою статичного методу
`observableArrayList()` класу `javafx.collections.FXCollections`. Клас `ListView<T>` представляє список елементів, що
прокручується, і має наступні властивості:
- успадковані від класу `javafx.scene.Node` властивості:
  * blendMode
  * boundsInLocal
  * boundsInParent
  * cacheHint
  * cache
  * clip
  * cursor
  * depthTest
  * disabled
  * disable
  * effect
  * eventDispatcher
  * focused
  * focusTraversable
  * hover
  * id
  * inputMethodRequests
  * layoutBounds
  * layoutX
  * layoutY
  * managed
  * mouseTransparent
  * onDragDetected
  * onDragDone
  * onDragDropped
  * onDragEntered
  * onDragExited
  * onDragOver
  * onInputMethodTextChanged
  * onKeyPressed
  * onKeyReleased
  * onKeyTyped
  * onMouseClicked
  * onMouseDragged
  * onMouseEntered
  * onMouseExited
  * onMouseMoved
  * onMousePressed
  * onMouseReleased
  * opacity
  * parent
  * pickOnBounds
  * pressed
  * rotate
  * rotationAxis
  * scaleX
  * scaleY
  * scaleZ
  * scene
  * style
  * translateX
  * translateY
  * translateZ
  * visible
- успадкована від класу `javafx.scene.Parent` властивість `needsLayout`;
- успадковані від класу `javafx.scene.control.Control` властивості:
  * contextMenu
  * height
  * maxHeight
  * maxWidth
  * minHeight
  * minWidth
  * prefHeight
  * prefWidth
  * skin
  * tooltip
  * width
- власні властивості: 
  * cellFactory
  * editable
  * editingIndex
  * focusModel
  * items
  * onEditCancel
  * onEditCommit
  * onEditStart
  * orientation
  * selectionModel

За допомогою властивості: orientation класу `ListView<T> `можна встановити, чи список буде вертикальним або горизонтальним списком елементів.

Властивість `cellFactory` класу `ListView<T>` дозволяє заповнити список `ListView` користувачами компонентами
`javafx.scene.control.ListCell<T>`. Примірник класу `ListCell<T>` можна створити за допомогою класу-фабрики `ListCellBuilder`
або за допомогою конструктора: `ListCell<String> cell=new ListCell<String>();` 
Клас `ListCell<T>` представляє елемент списку `ListView<T>` і має такі властивості:
- успадковані від класу javafx.scene.Node властивості:
  * blendMode
  * boundsInLocal
  * boundsInParent
  * cacheHint
  * cache
  * clip
  * cursor
  * depthTest
  * disabled
  * disable
  * effect
  * eventDispatcher
  * focused
  * focusTraversable
  * hover
  * id
  * inputMethodRequests
  * layoutBounds
  * layoutX
  * layoutY
  * managed
  * mouseTransparent
  * onDragDetected
  * onDragDone
  * onDragDropped
  * onDragEntered
  * onDragExited
  * onDragOver
  * onInputMethodTextChanged
  * onKeyPressed
  * onKeyReleased
  * onKeyTyped
  * onMouseClicked
  * onMouseDragged
  * onMouseEntered
  * onMouseExited
  * onMouseMoved
  * onMousePressed
  * onMouseReleased
  * opacity
  * parent
  * pickOnBounds
  * pressed
  * rotate
  * rotationAxis
  * scaleX
  * scaleY
  * scaleZ
  * scene
  * style
  * translateX
  * translateY
  * translateZ
  * visible
- успадкована від класу `javafx.scene.Parent` властивість `needsLayout`;
- успадковані від класу `javafx.scene.control.Control` властивості:
  * contextMenu
  * height
  * maxHeight
  * maxWidth
  * minHeight
  * minWidth
  * prefHeight
  * prefWidth
  * skin
  * tooltip
  * width
- успадковані від класу `javafx.scene.control.Labeled` властивості: 
  * alignment
  * contentDisplay
  * font
  * graphic
  * graphicTextGap
  * labelPadding
  * mnemonicParsing
  * textAlignment
  * textFill
  * textOverrun
  * text
  * underline
  * wrapText
- успадковані від класу `javafx.scene.control.Cell<T>` властивості: 
  * editable
  * editing
  * empty
  * item
  * selected
- успадкована від класу `javafx.scene.control.IndexedCell<T>` властивість `index`;
- власну властивість `listView`.

Властивість `selectionModel` класу `ListView<T>` дозволяє визначити множинність вибору та обробку події вибору елемента
списку.

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить список `ListView`, в меню `Файл` оберіть `Створити проект | Java with Ant | JavaFX | JavaFX Application`, натисніть
   кнопку `Далі`, введіть ім’я проекту `JavaFXApplicationListView`, залишивши прапорець `Create Main Class`, та натисніть
   кнопку `Готово`. У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationListView`,
   який розширює клас `Application`.

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Button btn = new Button();
        btn.setText("Say ‘Hello World’");
        btn.setOnAction(new EventHandler<ActionEvent>() {
            @Override
            public void handle(ActionEvent event) {
                System.out.println("Hello World!");
            }
        });
        StackPane root = new StackPane();
        root.getChildren().add(btn);
        Scene scene = new Scene(root, 300, 250);
        primaryStage.setTitle("Hello World!");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

2. У методі start вилучіть весь код.
3. Створіть кореневий вузол графа сцени та на його основі екземпляр сцени, який встановлюється для об’єкта `Stage`.
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI- компонентів: ListView”` та зробіть видимим об’єкт
   `Stage`:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Створіть перший екземпляр списку та відповідний екземпляр набору елементів списку. Список помістіть в лівий верхній
   кут основного вікна JavaFX-додатка, і для нього визначте такі властивості, як курсор миші, візуальний ефект, стиль,
   кращі розміри, підказка, орієнтація, фабрика елементів списку, яка заповнює список осередками, що містять кнопки:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");

        // new code
        ObservableList<String> categories = FXCollections.observableArrayList("Побутова техніка", "Посуд", "Госптовари");
        ListView<String> listViewC = new ListView<>(categories);
        listViewC.setLayoutX(10);
        listViewC.setLayoutY(10);
        listViewC.setCursor(Cursor.OPEN_HAND);
        final DropShadow effect = new DropShadow();
        effect.setOffsetX(10);
        effect.setOffsetY(10);
        listViewC.setEffect(effect);
        listViewC.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewC.setPrefSize(470, 170);
        listViewC.setTooltip(new Tooltip("Виберіть категорію товару"));
        listViewC.setOrientation(Orientation.HORIZONTAL);
        listViewC.setCellFactory((ListView<String> p) -> {
            Button btn = new Button();
            btn.setEffect(effect);
            btn.setStyle("-fx-background-color:#66ccff;");
            btn.setPrefSize(130, 50);
            btn.setCursor(Cursor.NONE);
            btn.setWrapText(true);

            final ListCell<String> cell = new ListCell<String>(){
                @Override
                public void updateItem(String item, boolean empty) {
                    super.updateItem(item, empty);
                    if (item != null) {
                        btn.setText(item);
                        this.setGraphic(btn);
                    }
                }
            };
            return cell;
        });
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

5. Створіть другий екземпляр списку та відповідний йому екземпляр набору елементів списку. Другий список помістіть під
   першим списком, і для нього визначте такі властивості, як курсор миші, візуальний ефект, стиль, переважні розміри,
   орієнтація, множинність вибору та видимість:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");

        // new code
        ObservableList<String> categories = FXCollections.observableArrayList("Побутова техніка", "Посуд", "Госптовари");
        ListView<String> listViewC = new ListView<>(categories);
        listViewC.setLayoutX(10);
        listViewC.setLayoutY(10);
        listViewC.setCursor(Cursor.OPEN_HAND);
        final DropShadow effect = new DropShadow();
        effect.setOffsetX(10);
        effect.setOffsetY(10);
        listViewC.setEffect(effect);
        listViewC.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewC.setPrefSize(470, 170);
        listViewC.setTooltip(new Tooltip("Виберіть категорію товару"));
        listViewC.setOrientation(Orientation.HORIZONTAL);
        listViewC.setCellFactory((ListView<String> p) -> {
            Button btn = new Button();
            btn.setEffect(effect);
            btn.setStyle("-fx-background-color:#66ccff;");
            btn.setPrefSize(130, 50);
            btn.setCursor(Cursor.NONE);
            btn.setWrapText(true);

            final ListCell<String> cell = new ListCell<String>(){
                @Override
                public void updateItem(String item, boolean empty) {
                    super.updateItem(item, empty);
                    if (item != null) {
                        btn.setText(item);
                        this.setGraphic(btn);
                    }
                }
            };
            return cell;
        });
        
        // new code 2
        ObservableList<String> goodsH = FXCollections.observableArrayList("Вентилятор", "М’ясорубка", "Насос");
        ListView<String> listViewH;
        listViewH = new ListView<>(goodsH);
        listViewH.setLayoutX(10);
        listViewH.setLayoutY(220);
        listViewH.setCursor(Cursor.CROSSHAIR);
        listViewH.setEffect(effect);
        listViewH.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewH.setPrefSize(200, 150);
        listViewH.setOrientation(Orientation.VERTICAL);
        listViewH.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewH.setVisible(false);
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

6. Створіть третій екземпляр списку та відповідний екземпляр набору елементів списку. Третій список помістіть під першим
   списком, і для нього визначте такі властивості, як курсор миші, візуальний ефект, стиль, переважні розміри,
   орієнтація, множинність вибору та видимість:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");

        // new code
        ObservableList<String> categories = FXCollections.observableArrayList("Побутова техніка", "Посуд", "Госптовари");
        ListView<String> listViewC = new ListView<>(categories);
        listViewC.setLayoutX(10);
        listViewC.setLayoutY(10);
        listViewC.setCursor(Cursor.OPEN_HAND);
        final DropShadow effect = new DropShadow();
        effect.setOffsetX(10);
        effect.setOffsetY(10);
        listViewC.setEffect(effect);
        listViewC.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewC.setPrefSize(470, 170);
        listViewC.setTooltip(new Tooltip("Виберіть категорію товару"));
        listViewC.setOrientation(Orientation.HORIZONTAL);
        listViewC.setCellFactory((ListView<String> p) -> {
            Button btn = new Button();
            btn.setEffect(effect);
            btn.setStyle("-fx-background-color:#66ccff;");
            btn.setPrefSize(130, 50);
            btn.setCursor(Cursor.NONE);
            btn.setWrapText(true);

            final ListCell<String> cell = new ListCell<String>(){
                @Override
                public void updateItem(String item, boolean empty) {
                    super.updateItem(item, empty);
                    if (item != null) {
                        btn.setText(item);
                        this.setGraphic(btn);
                    }
                }
            };
            return cell;
        });
        
        // new code 2
        ObservableList<String> goodsH = FXCollections.observableArrayList("Вентилятор", "М’ясорубка", "Насос");
        ListView<String> listViewH;
        listViewH = new ListView<>(goodsH);
        listViewH.setLayoutX(10);
        listViewH.setLayoutY(220);
        listViewH.setCursor(Cursor.CROSSHAIR);
        listViewH.setEffect(effect);
        listViewH.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewH.setPrefSize(200, 150);
        listViewH.setOrientation(Orientation.VERTICAL);
        listViewH.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewH.setVisible(false);

        // new code 3
        ObservableList<String> goodsU = FXCollections.observableArrayList("Чайник", "Каструля", "Пательня");
        ListView<String> listViewU;
        listViewU = new ListView<>(goodsU);
        listViewU.setLayoutX(10);
        listViewU.setLayoutY(220);
        listViewU.setCursor(Cursor.CROSSHAIR);
        listViewU.setEffect(effect);
        listViewU.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewU.setPrefSize(200, 150);
        listViewU.setOrientation(Orientation.VERTICAL);
        listViewU.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewU.setVisible(false);
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

7. Створіть четвертий екземпляр списку та відповідний екземпляр набору елементів списку. Четвертий список помістіть під
   першим списком і для нього визначте такі властивості, як курсор миші, візуальний ефект, стиль, переважні розміри,
   орієнтація, множинність вибору та видимість:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");

        // new code
        ObservableList<String> categories = FXCollections.observableArrayList("Побутова техніка", "Посуд", "Госптовари");
        ListView<String> listViewC = new ListView<>(categories);
        listViewC.setLayoutX(10);
        listViewC.setLayoutY(10);
        listViewC.setCursor(Cursor.OPEN_HAND);
        final DropShadow effect = new DropShadow();
        effect.setOffsetX(10);
        effect.setOffsetY(10);
        listViewC.setEffect(effect);
        listViewC.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewC.setPrefSize(470, 170);
        listViewC.setTooltip(new Tooltip("Виберіть категорію товару"));
        listViewC.setOrientation(Orientation.HORIZONTAL);
        listViewC.setCellFactory((ListView<String> p) -> {
            Button btn = new Button();
            btn.setEffect(effect);
            btn.setStyle("-fx-background-color:#66ccff;");
            btn.setPrefSize(130, 50);
            btn.setCursor(Cursor.NONE);
            btn.setWrapText(true);

            final ListCell<String> cell = new ListCell<String>(){
                @Override
                public void updateItem(String item, boolean empty) {
                    super.updateItem(item, empty);
                    if (item != null) {
                        btn.setText(item);
                        this.setGraphic(btn);
                    }
                }
            };
            return cell;
        });
        
        // new code 2
        ObservableList<String> goodsH = FXCollections.observableArrayList("Вентилятор", "М’ясорубка", "Насос");
        ListView<String> listViewH;
        listViewH = new ListView<>(goodsH);
        listViewH.setLayoutX(10);
        listViewH.setLayoutY(220);
        listViewH.setCursor(Cursor.CROSSHAIR);
        listViewH.setEffect(effect);
        listViewH.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewH.setPrefSize(200, 150);
        listViewH.setOrientation(Orientation.VERTICAL);
        listViewH.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewH.setVisible(false);

        // new code 3
        ObservableList<String> goodsU = FXCollections.observableArrayList("Чайник", "Каструля", "Пательня");
        ListView<String> listViewU;
        listViewU = new ListView<>(goodsU);
        listViewU.setLayoutX(10);
        listViewU.setLayoutY(220);
        listViewU.setCursor(Cursor.CROSSHAIR);
        listViewU.setEffect(effect);
        listViewU.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewU.setPrefSize(200, 150);
        listViewU.setOrientation(Orientation.VERTICAL);
        listViewU.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewU.setVisible(false);
        
        // new code 3
        ObservableList<String> goodsW = FhXCollections.observableArrayList("Шланг", "Лопата", "Ваги");
        ListView<String> listViewW;
        listViewW = new ListView<>(goodsW);
        listViewW.setLayoutX(10);
        listViewW.setLayoutY(220);
        listViewW.setCursor(Cursor.CROSSHAIR);
        listViewW.setEffect(effect);
        listViewW.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewW.setPrefSize(200, 150);
        listViewW.setOrientation(Orientation.VERTICAL);
        listViewW.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewW.setVisible(false);
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

8. Створіть обробник вибору елемента списку, який візуалізує ще один список, що відповідає обраному елементу:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");

        // new code
        ObservableList<String> categories = FXCollections.observableArrayList("Побутова техніка", "Посуд", "Госптовари");
        ListView<String> listViewC = new ListView<>(categories);
        listViewC.setLayoutX(10);
        listViewC.setLayoutY(10);
        listViewC.setCursor(Cursor.OPEN_HAND);
        final DropShadow effect = new DropShadow();
        effect.setOffsetX(10);
        effect.setOffsetY(10);
        listViewC.setEffect(effect);
        listViewC.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewC.setPrefSize(470, 170);
        listViewC.setTooltip(new Tooltip("Виберіть категорію товару"));
        listViewC.setOrientation(Orientation.HORIZONTAL);
        listViewC.setCellFactory((ListView<String> p) -> {
            Button btn = new Button();
            btn.setEffect(effect);
            btn.setStyle("-fx-background-color:#66ccff;");
            btn.setPrefSize(130, 50);
            btn.setCursor(Cursor.NONE);
            btn.setWrapText(true);

            final ListCell<String> cell = new ListCell<String>(){
                @Override
                public void updateItem(String item, boolean empty) {
                    super.updateItem(item, empty);
                    if (item != null) {
                        btn.setText(item);
                        this.setGraphic(btn);
                    }
                }
            };
            return cell;
        });
        
        // new code 2
        ObservableList<String> goodsH = FXCollections.observableArrayList("Вентилятор", "М’ясорубка", "Насос");
        ListView<String> listViewH;
        listViewH = new ListView<>(goodsH);
        listViewH.setLayoutX(10);
        listViewH.setLayoutY(220);
        listViewH.setCursor(Cursor.CROSSHAIR);
        listViewH.setEffect(effect);
        listViewH.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewH.setPrefSize(200, 150);
        listViewH.setOrientation(Orientation.VERTICAL);
        listViewH.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewH.setVisible(false);

        // new code 3
        ObservableList<String> goodsU = FXCollections.observableArrayList("Чайник", "Каструля", "Пательня");
        ListView<String> listViewU;
        listViewU = new ListView<>(goodsU);
        listViewU.setLayoutX(10);
        listViewU.setLayoutY(220);
        listViewU.setCursor(Cursor.CROSSHAIR);
        listViewU.setEffect(effect);
        listViewU.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewU.setPrefSize(200, 150);
        listViewU.setOrientation(Orientation.VERTICAL);
        listViewU.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewU.setVisible(false);
        
        // new code 3
        ObservableList<String> goodsW = FhXCollections.observableArrayList("Шланг", "Лопата", "Ваги");
        ListView<String> listViewW;
        listViewW = new ListView<>(goodsW);
        listViewW.setLayoutX(10);
        listViewW.setLayoutY(220);
        listViewW.setCursor(Cursor.CROSSHAIR);
        listViewW.setEffect(effect);
        listViewW.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewW.setPrefSize(200, 150);
        listViewW.setOrientation(Orientation.VERTICAL);
        listViewW.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewW.setVisible(false);

        // new code 4
        listViewC.getSelectionModel().selectedItemProperty().addListener
                ((ObservableValue<? extends String> ov, String old_val, String new_val)
                        -> {
                    if(new_val.equals("Побутова техніка")){
                        listViewH.setVisible(true);
                        listViewU.setVisible(false);
                        listViewW.setVisible(false);
                    }
                    if(new_val.equals("Посуд")){
                        listViewU.setVisible(true);
                        listViewH.setVisible(false);
                        listViewW.setVisible(false);
                    }
                    if(new_val.equals("Госптовари")){
                        listViewW.setVisible(true);
                        listViewH.setVisible(false);
                        listViewU.setVisible(false);
                    }
                });
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

9. Створені списки додайте до кореневого вузла графа сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationListView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 500, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ListView");

        // new code
        ObservableList<String> categories = FXCollections.observableArrayList("Побутова техніка", "Посуд", "Госптовари");
        ListView<String> listViewC = new ListView<>(categories);
        listViewC.setLayoutX(10);
        listViewC.setLayoutY(10);
        listViewC.setCursor(Cursor.OPEN_HAND);
        final DropShadow effect = new DropShadow();
        effect.setOffsetX(10);
        effect.setOffsetY(10);
        listViewC.setEffect(effect);
        listViewC.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewC.setPrefSize(470, 170);
        listViewC.setTooltip(new Tooltip("Виберіть категорію товару"));
        listViewC.setOrientation(Orientation.HORIZONTAL);
        listViewC.setCellFactory((ListView<String> p) -> {
            Button btn = new Button();
            btn.setEffect(effect);
            btn.setStyle("-fx-background-color:#66ccff;");
            btn.setPrefSize(130, 50);
            btn.setCursor(Cursor.NONE);
            btn.setWrapText(true);

            final ListCell<String> cell = new ListCell<String>(){
                @Override
                public void updateItem(String item, boolean empty) {
                    super.updateItem(item, empty);
                    if (item != null) {
                        btn.setText(item);
                        this.setGraphic(btn);
                    }
                }
            };
            return cell;
        });
        
        // new code 2
        ObservableList<String> goodsH = FXCollections.observableArrayList("Вентилятор", "М’ясорубка", "Насос");
        ListView<String> listViewH;
        listViewH = new ListView<>(goodsH);
        listViewH.setLayoutX(10);
        listViewH.setLayoutY(220);
        listViewH.setCursor(Cursor.CROSSHAIR);
        listViewH.setEffect(effect);
        listViewH.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewH.setPrefSize(200, 150);
        listViewH.setOrientation(Orientation.VERTICAL);
        listViewH.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewH.setVisible(false);

        // new code 3
        ObservableList<String> goodsU = FXCollections.observableArrayList("Чайник", "Каструля", "Пательня");
        ListView<String> listViewU;
        listViewU = new ListView<>(goodsU);
        listViewU.setLayoutX(10);
        listViewU.setLayoutY(220);
        listViewU.setCursor(Cursor.CROSSHAIR);
        listViewU.setEffect(effect);
        listViewU.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewU.setPrefSize(200, 150);
        listViewU.setOrientation(Orientation.VERTICAL);
        listViewU.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewU.setVisible(false);
        
        // new code 3
        ObservableList<String> goodsW = FhXCollections.observableArrayList("Шланг", "Лопата", "Ваги");
        ListView<String> listViewW;
        listViewW = new ListView<>(goodsW);
        listViewW.setLayoutX(10);
        listViewW.setLayoutY(220);
        listViewW.setCursor(Cursor.CROSSHAIR);
        listViewW.setEffect(effect);
        listViewW.setStyle("-fx-border-width:3pt;-fx-border-color:navy;-fx-font:bold 12pt Georgia;");
        listViewW.setPrefSize(200, 150);
        listViewW.setOrientation(Orientation.VERTICAL);
        listViewW.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        listViewW.setVisible(false);

        // new code 4
        listViewC.getSelectionModel().selectedItemProperty().addListener
                ((ObservableValue<? extends String> ov, String old_val, String new_val)
                        -> {
                    if(new_val.equals("Побутова техніка")){
                        listViewH.setVisible(true);
                        listViewU.setVisible(false);
                        listViewW.setVisible(false);
                    }
                    if(new_val.equals("Посуд")){
                        listViewU.setVisible(true);
                        listViewH.setVisible(false);
                        listViewW.setVisible(false);
                    }
                    if(new_val.equals("Госптовари")){
                        listViewW.setVisible(true);
                        listViewH.setVisible(false);
                        listViewU.setVisible(false);
                    }
                });

        // new code 5
        root.getChildren().add(listViewC);
        root.getChildren().add(listViewH);
        root.getChildren().add(listViewU);
        root.getChildren().add(listViewW);
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

10. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі Очистити та побудувати проект
    `(Shift+F11)`, а потім – `Виконати проект (F6)`.
