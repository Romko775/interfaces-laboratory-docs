# ChoiceBox

Компонент `ChoiceBox` представлений класом `javafx.scene.control.ChoiceBox<T>`, екземпляр якого може бути створений за
допомогою класу-фабрики `ChoiceBoxBuilder`
або за допомогою одного з конструкторів:
- `ChoiceBox<String> choice=new ChoiceBox<String>();`
- `ChoiceBox<String> choice = new ChoiceBox<String>(ObservableList<String> list);`

Набір елементів `javafx.collections.ObservableList` списку `ChoiceBox` може бути створений за допомогою статичного
методу `observableArrayList()` класу `javafx.collections.FXCollections`. Клас `ChoiceBox<T>` представляє список
елементів, що випадає, і має наступні властивості:
- успадковані від класу `javafx.scene.Node` властивості:
  * blendMode
  * boundsInLocal
  * boundsInParent
  * cacheHint
  * cache
  * clip,
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
  * visible;
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
- власні властивості `items`, `selectionModel` і `showing`.

За допомогою властивості `items` класу C`hoiceBox<T>` можна встановити набір `ObservableList<T>` елементів списку.

Властивість `selectionModel` класу `ChoiceBox<T>` дає можливість визначити вибір елемента та обробку події вибору елемента списку.

Властивість `showing` класу `ChoiceBox<T>` приймає значення `true`, якщо відображається список, що випадає.

Завдання

1. Відкрийте середовище `NetBeans` з підтримкою платформи `JavaFX 2.0`. Для створення JavaFX-додатку з GUI-інтерфейсом,
   що містить список `ChoiceBox`, в меню `Файл оберіть Створити проект` | `Java with Ant` | `JavaFX`
   | `JavaFX Application`, натисніть кнопку `Далі`, введіть ім’я проекту `JavaFXApplicationChoiceBox`, залишивши
   прапорець `Create Main Class`, та натисніть кнопку `Готово`.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationChoiceBox`, який розширює клас `Application`.
   
```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
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

2. У методі `start` вилучіть весь код.
3. Створіть кореневий вузол графа сцени та на його основі екземпляр сцени, який встановлюється для об’єкта `Stage`.
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI-компонентів: ChoiceBox”` та зробіть видимим об’єкт
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

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Створіть екземпляр списку та відповідний екземпляр набору елементів списку. Список помістіть у лівому верхньому куті
   основного вікна JavaFX-додатка, і для нього визначте такі властивості, як режим накладання, курсор миші, візуальний
   ефект, стиль, переважні розміри, підказка, початковий вибір першого елемента списку:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        ObservableList<String> country = FXCollections.observableArrayList("Україна", "США", "Великобританія");
        ChoiceBox<String> choice = new ChoiceBox<>(country);
        choice.setLayoutX(10);
        choice.setLayoutY(10);
        choice.setBlendMode(BlendMode.HARD_LIGHT);
        choice.setCursor(Cursor.CLOSED_HAND);
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        choice.setEffect(effect);

        choice.setStyle("-fx-text-fill:#000000;-fx-border-width:5pt;-fx-bordercolor:#d2691e;-fx-font:bold italic 12pt Georgia;");

        choice.setPrefSize(200, 50);
        choice.setTooltip(new Tooltip("Виберіть країну"));
        choice.getSelectionModel().selectFirst();
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

5. Створіть перший екземпляр вузла зображення `ImageView`, помістіть під списком і для нього визначте такі властивості,
   як розміри та збереження пропорцій вихідного зображення:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        ObservableList<String> country = FXCollections.observableArrayList("Україна", "США", "Великобританія");
        ChoiceBox<String> choice = new ChoiceBox<>(country);
        choice.setLayoutX(10);
        choice.setLayoutY(10);
        choice.setBlendMode(BlendMode.HARD_LIGHT);
        choice.setCursor(Cursor.CLOSED_HAND);
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        choice.setEffect(effect);

        choice.setStyle("-fx-text-fill:#000000;-fx-border-width:5pt;-fx-bordercolor:#d2691e;-fx-font:bold italic 12pt Georgia;");

        choice.setPrefSize(200, 50);
        choice.setTooltip(new Tooltip("Виберіть країну"));
        choice.getSelectionModel().selectFirst();

        Image imR = new Image(this.getClass().getResource("imageR.jpg").toString());
        ImageView imvR;
        imvR = new ImageView(imR);
        imvR.setPreserveRatio(true);
        imvR.setFitHeight(200);
        imvR.setFitWidth(200);
        imvR.setLayoutX(10);
        imvR.setLayoutY(100);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

6. Створіть другий екземпляр вузла зображення `ImageView`, помістіть під списком і для нього визначте такі властивості,
   як розміри, збереження пропорцій вихідного зображення та видимість:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        ObservableList<String> country = FXCollections.observableArrayList("Україна", "США", "Великобританія");
        ChoiceBox<String> choice = new ChoiceBox<>(country);
        choice.setLayoutX(10);
        choice.setLayoutY(10);
        choice.setBlendMode(BlendMode.HARD_LIGHT);
        choice.setCursor(Cursor.CLOSED_HAND);
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        choice.setEffect(effect);

        choice.setStyle("-fx-text-fill:#000000;-fx-border-width:5pt;-fx-bordercolor:#d2691e;-fx-font:bold italic 12pt Georgia;");

        choice.setPrefSize(200, 50);
        choice.setTooltip(new Tooltip("Виберіть країну"));
        choice.getSelectionModel().selectFirst();

        Image imR = new Image(this.getClass().getResource("imageR.jpg").toString());
        ImageView imvR;
        imvR = new ImageView(imR);
        imvR.setPreserveRatio(true);
        imvR.setFitHeight(200);
        imvR.setFitWidth(200);
        imvR.setLayoutX(10);
        imvR.setLayoutY(100);

        Image imU = new Image(this.getClass().getResource("imageU.jpg").toString());
        ImageView imvU;
        imvU = new ImageView(imU);
        imvU.setPreserveRatio(true);
        imvU.setFitHeight(200);
        imvU.setFitWidth(200);
        imvU.setLayoutX(10);
        imvU.setLayoutY(100);
        imvU.setVisible(false);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

7. Створіть третій екземпляр вузла зображення `ImageView`, помістіть під списком і для нього визначте такі властивості,
   як розміри, збереження пропорцій вихідного зображення та видимість:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        ObservableList<String> country = FXCollections.observableArrayList("Україна", "США", "Великобританія");
        ChoiceBox<String> choice = new ChoiceBox<>(country);
        choice.setLayoutX(10);
        choice.setLayoutY(10);
        choice.setBlendMode(BlendMode.HARD_LIGHT);
        choice.setCursor(Cursor.CLOSED_HAND);
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        choice.setEffect(effect);

        choice.setStyle("-fx-text-fill:#000000;-fx-border-width:5pt;-fx-bordercolor:#d2691e;-fx-font:bold italic 12pt Georgia;");

        choice.setPrefSize(200, 50);
        choice.setTooltip(new Tooltip("Виберіть країну"));
        choice.getSelectionModel().selectFirst();

        Image imR = new Image(this.getClass().getResource("imageR.jpg").toString());
        ImageView imvR;
        imvR = new ImageView(imR);
        imvR.setPreserveRatio(true);
        imvR.setFitHeight(200);
        imvR.setFitWidth(200);
        imvR.setLayoutX(10);
        imvR.setLayoutY(100);

        Image imU = new Image(this.getClass().getResource("imageU.jpg").toString());
        ImageView imvU;
        imvU = new ImageView(imU);
        imvU.setPreserveRatio(true);
        imvU.setFitHeight(200);
        imvU.setFitWidth(200);
        imvU.setLayoutX(10);
        imvU.setLayoutY(100);
        imvU.setVisible(false);

        Image imG = new Image(this.getClass().getResource("imageG.jpg").toString());
        ImageView imvG;
        imvG = new ImageView(imG);
        imvG.setPreserveRatio(true);
        imvG.setFitHeight(200);
        imvG.setFitWidth(200);
        imvG.setLayoutX(10);
        imvG.setLayoutY(100);
        imvG.setVisible(false);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

8. Створіть обробник вибору елемента списку, який візуалізує
   зображення, що відповідає вибраному елементу:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        ObservableList<String> country = FXCollections.observableArrayList("Україна", "США", "Великобританія");
        ChoiceBox<String> choice = new ChoiceBox<>(country);
        choice.setLayoutX(10);
        choice.setLayoutY(10);
        choice.setBlendMode(BlendMode.HARD_LIGHT);
        choice.setCursor(Cursor.CLOSED_HAND);
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        choice.setEffect(effect);

        choice.setStyle("-fx-text-fill:#000000;-fx-border-width:5pt;-fx-bordercolor:#d2691e;-fx-font:bold italic 12pt Georgia;");

        choice.setPrefSize(200, 50);
        choice.setTooltip(new Tooltip("Виберіть країну"));
        choice.getSelectionModel().selectFirst();

        Image imR = new Image(this.getClass().getResource("imageR.jpg").toString());
        ImageView imvR;
        imvR = new ImageView(imR);
        imvR.setPreserveRatio(true);
        imvR.setFitHeight(200);
        imvR.setFitWidth(200);
        imvR.setLayoutX(10);
        imvR.setLayoutY(100);

        Image imU = new Image(this.getClass().getResource("imageU.jpg").toString());
        ImageView imvU;
        imvU = new ImageView(imU);
        imvU.setPreserveRatio(true);
        imvU.setFitHeight(200);
        imvU.setFitWidth(200);
        imvU.setLayoutX(10);
        imvU.setLayoutY(100);
        imvU.setVisible(false);

        Image imG = new Image(this.getClass().getResource("imageG.jpg").toString());
        ImageView imvG;
        imvG = new ImageView(imG);
        imvG.setPreserveRatio(true);
        imvG.setFitHeight(200);
        imvG.setFitWidth(200);
        imvG.setLayoutX(10);
        imvG.setLayoutY(100);
        imvG.setVisible(false);

        choice.getSelectionModel()
                .selectedItemProperty()
                .addListener((ObservableValue<? extends String> ov, String old_val, String new_val) ->
                {
                    if (new_val.equals("Україна")) {
                        imvR.setVisible(true);
                        imvU.setVisible(false);
                        imvG.setVisible(false);
                    }
                    if (new_val.equals("США")) {
                        imvU.setVisible(true);
                        imvR.setVisible(false);
                        imvG.setVisible(false);
                    }
                    if (new_val.equals("Великобританія")) {
                        imvG.setVisible(true);
                        imvR.setVisible(false);
                        imvU.setVisible(false);
                    }
                });
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

9. Скачайте з інтернету рисунки із зображенням України, США та Великобританії, назвавши як `imageR.jpg`, `imageU.jpg` та
   `imageG.jpg`, і збережіть їх у папці, де розміщений файл
   `JavaFXApplicationChoiceBox.java`.
10. Створений список та вузли зображень додайте до
    кореневого вузла графа сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTableView extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 300, Color.BEIGE);

        ObservableList<String> country = FXCollections.observableArrayList("Україна", "США", "Великобританія");
        ChoiceBox<String> choice = new ChoiceBox<>(country);
        choice.setLayoutX(10);
        choice.setLayoutY(10);
        choice.setBlendMode(BlendMode.HARD_LIGHT);
        choice.setCursor(Cursor.CLOSED_HAND);
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        choice.setEffect(effect);

        choice.setStyle("-fx-text-fill:#000000;-fx-border-width:5pt;-fx-bordercolor:#d2691e;-fx-font:bold italic 12pt Georgia;");

        choice.setPrefSize(200, 50);
        choice.setTooltip(new Tooltip("Виберіть країну"));
        choice.getSelectionModel().selectFirst();

        Image imR = new Image(this.getClass().getResource("imageR.jpg").toString());
        ImageView imvR;
        imvR = new ImageView(imR);
        imvR.setPreserveRatio(true);
        imvR.setFitHeight(200);
        imvR.setFitWidth(200);
        imvR.setLayoutX(10);
        imvR.setLayoutY(100);

        Image imU = new Image(this.getClass().getResource("imageU.jpg").toString());
        ImageView imvU;
        imvU = new ImageView(imU);
        imvU.setPreserveRatio(true);
        imvU.setFitHeight(200);
        imvU.setFitWidth(200);
        imvU.setLayoutX(10);
        imvU.setLayoutY(100);
        imvU.setVisible(false);

        Image imG = new Image(this.getClass().getResource("imageG.jpg").toString());
        ImageView imvG;
        imvG = new ImageView(imG);
        imvG.setPreserveRatio(true);
        imvG.setFitHeight(200);
        imvG.setFitWidth(200);
        imvG.setLayoutX(10);
        imvG.setLayoutY(100);
        imvG.setVisible(false);

        choice.getSelectionModel()
                .selectedItemProperty()
                .addListener((ObservableValue<? extends String> ov, String old_val, String new_val) ->
                {
                    if (new_val.equals("Україна")) {
                        imvR.setVisible(true);
                        imvU.setVisible(false);
                        imvG.setVisible(false);
                    }
                    if (new_val.equals("США")) {
                        imvU.setVisible(true);
                        imvR.setVisible(false);
                        imvG.setVisible(false);
                    }
                    if (new_val.equals("Великобританія")) {
                        imvG.setVisible(true);
                        imvR.setVisible(false);
                        imvU.setVisible(false);
                    }
                });

        root.getChildren().add(choice);
        root.getChildren().add(imvR);
        root.getChildren().add(imvU);
        root.getChildren().add(imvG);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: ChoiceBox");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

11. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі `Очистити та побудувати проект
    (Shift+F11)`, а потім – `Виконати проект (F6).`
