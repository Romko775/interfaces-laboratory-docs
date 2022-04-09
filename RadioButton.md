#RadioButton

Компонент `RadioButton` представлений класом `javafx.scene.control.RadioButton`, екземпляр якого може бути створений за
допомогою класу-фабрики `RadioButtonBuilder` або за допомогою одного з конструкторів:
- `RadioButton btn = New RadioButton();`
- `RadioButton btn = new RadioButton("[текст]");`

Клас `RadioButton` має:
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
- успадковані від класу javafx.scene.control.Control властивості:
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
  
- успадковані від класу javafx.scene.control.Labeled властивості: 
  * alignment
  * contentDisplay
  * font
  * graphic
  * graphicTextGap,
  * labelPadding
  * mnemonicParsing
  * textAlignment
  * textFill
  * textOverrun,
  * text
  * underline
  * wrapText
  
- успадковані від класу `javafx.scene.control.ButtonBase` властивості `armed` та `onAction`
- успадковані від класу `javafx.scene.control.ToggleButton` властивості `selected` та `toggleGroup`

Властивості компонента `RadioButton` аналогічні властивостям компонента `ToggleButton`

Об'єднання перемикачів `RadioButton` у групу `ToggleGroup` відрізняється від об'єднання кнопок `ToggleButton` у групу
`ToggleGroup`.

У групі перемикачів `RadioButton` щонайменше один елемент повинен бути у вибраному стані, і вибір іншого перемикача
скасовує вибір решти. Таким чином, у групі перемикачів `RadioButton`постійно вибрано лише один елемент, і його не можна 
перевести у невибраний стан.

У групі кнопок `ToggleButton` при натисканні однієї з кнопок решта всіх кнопок групи автоматично віджимається, однак
натиснуту кнопку можна віджати.

Екземпляр класу `ToggleGroup` можна створити за допомогою класу-фабрики ToggleGroupBuilder або за допомогою конструктора:
`ToggleGroup tgroup = New ToggleGroup(); `
Клас `ToggleGroup` має властивість `selectedToggle`, що вказує на обраний в даний момент елемент групи.

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить перемикач `RadioButton`, в меню Файл оберіть` Створити проект | Java with Ant | JavaFX | JavaFX Application`,
   натисніть кнопку `Далі`, введіть ім’я проекту `JavaFXApplicationRadioButton`, залишивши прапорець `Create Main Class`, та
   натисніть кнопку `Готово`.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу JavaFXApplicationRadioButton, який розширює клас Application.

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationRadioButton extends Application {
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
Установіть заголовок основного вікна JavaFX-додатку “Тестування GUI- компонентів: RadioButton” та зробіть видимим об’єкт Stage:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationRadioButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: RadioButton");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Створіть групу `ToggleGroup` та перший екземпляр кнопки RadioButton з текстом. Кнопку помістіть у лівий верхній кут
   основного вікна JavaFX-програми. Для неї визначте такі властивості, як режим накладання, курсор миші, переважні
   розміри, спливаюча підказка, значок, стиль, вирівнювання, перенесення рядків, групу, фокус та обробник зміни значення
   selected кнопки, в якому змінюється загальний колір сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationRadioButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: RadioButton");

        // new code
        ToggleGroup tgroup = new ToggleGroup();
        RadioButton btnOn;
        btnOn = new RadioButton("Mozilla Firefox");

        btnOn.setLayoutX(20);
        btnOn.setLayoutY(20);
        btnOn.setBlendMode(BlendMode.MULTIPLY);
        btnOn.setCursor(Cursor.CLOSED_HAND);
        btnOn.setPrefSize(200, 80);
        btnOn.setTooltip(new Tooltip("Це кнопка вибору Mozilla Firefox"));
        Image imOn = new Image(this.getClass().getResource("imageOn.jpg").toString());
        ImageView imvOn = new ImageView(imOn);
        imvOn.setFitHeight(50);
        imvOn.setFitWidth(50);
        btnOn.setGraphic(imvOn);
        btnOn.setStyle("-fx-font: bold italic 12pt Georgia;");
        btnOn.setAlignment(Pos.CENTER);
        btnOn.setContentDisplay(ContentDisplay.RIGHT);
        btnOn.setTextAlignment(TextAlignment.CENTER);
        btnOn.setGraphicTextGap(10);
        btnOn.setWrapText(true);
        btnOn.setToggleGroup(tgroup);
        btnOn.requestFocus();
        btnOn.selectedProperty().addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) ->
        {
            if (new_val.equals(Boolean.TRUE)) scene.setFill(Color.web("#fff8dc"));
        });

        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

5. Створіть другий екземпляр кнопки `RadioButton` із текстом. Другу кнопку помістіть під першою кнопкою, і для неї
   визначте також такі властивості, як режим накладання, курсор миші, переважні розміри, підказка, значок, стиль,
   вирівнювання, перенесення рядків, група та обробник зміни значення властивості selected кнопки, в якому змінюється
   загальний колір сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationRadioButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: RadioButton");

        // new code
        ToggleGroup tgroup = new ToggleGroup();
        RadioButton btnOn;
        btnOn = new RadioButton("Mozilla Firefox");

        btnOn.setLayoutX(20);
        btnOn.setLayoutY(20);
        btnOn.setBlendMode(BlendMode.MULTIPLY);
        btnOn.setCursor(Cursor.CLOSED_HAND);
        btnOn.setPrefSize(200, 80);
        btnOn.setTooltip(new Tooltip("Це кнопка вибору Mozilla Firefox"));
        Image imOn = new Image(this.getClass().getResource("imageOn.jpg").toString());
        ImageView imvOn = new ImageView(imOn);
        imvOn.setFitHeight(50);
        imvOn.setFitWidth(50);
        btnOn.setGraphic(imvOn);
        btnOn.setStyle("-fx-font: bold italic 12pt Georgia;");
        btnOn.setAlignment(Pos.CENTER);
        btnOn.setContentDisplay(ContentDisplay.RIGHT);
        btnOn.setTextAlignment(TextAlignment.CENTER);
        btnOn.setGraphicTextGap(10);
        btnOn.setWrapText(true);
        btnOn.setToggleGroup(tgroup);
        btnOn.requestFocus();
        btnOn.selectedProperty().addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) ->
        {
            if (new_val.equals(Boolean.TRUE)) scene.setFill(Color.web("#fff8dc"));
        });

        // new code 2
        RadioButton btnOf;
        btnOf = new RadioButton("Internet Explorer");
        btnOf.setLayoutX(20);
        btnOf.setLayoutY(100);
        btnOf.setBlendMode(BlendMode.MULTIPLY);
        btnOf.setCursor(Cursor.CLOSED_HAND);

        btnOf.setPrefSize(200, 80);
        btnOf.setTooltip(new Tooltip("Це кнопка вибору Internet Explorer"));
        Image imOf = new Image(this.getClass().getResource("imageOf.jpg").toString());
        ImageView imvOf = new ImageView(imOf);
        imvOf.setFitHeight(50);
        imvOf.setFitWidth(50);
        btnOf.setGraphic(imvOf);
        btnOf.setStyle("-fx-font: bold italic 12pt Georgia;");
        btnOf.setAlignment(Pos.CENTER);
        btnOf.setContentDisplay(ContentDisplay.RIGHT);
        btnOf.setTextAlignment(TextAlignment.CENTER);
        btnOf.setGraphicTextGap(10);
        btnOf.setWrapText(true);
        btnOf.setToggleGroup(tgroup);
        btnOf.selectedProperty().addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) ->
        {
            if (new_val.equals(Boolean.TRUE)) scene.setFill(Color.web("#99ffff"));
        });
        
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

6. Скачайте з інтернету рисунки, назвавши як `imageOn.jpg` та `imageOf.jpg` і збережіть їх у папці, де розміщений файл
   `JavaFXApplicationRadioButton.java`.
7. Створені кнопки додайте в кореневий вузол графа сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationRadioButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: RadioButton");

        // new code
        ToggleGroup tgroup = new ToggleGroup();
        RadioButton btnOn;
        btnOn = new RadioButton("Mozilla Firefox");

        btnOn.setLayoutX(20);
        btnOn.setLayoutY(20);
        btnOn.setBlendMode(BlendMode.MULTIPLY);
        btnOn.setCursor(Cursor.CLOSED_HAND);
        btnOn.setPrefSize(200, 80);
        btnOn.setTooltip(new Tooltip("Це кнопка вибору Mozilla Firefox"));
        Image imOn = new Image(this.getClass().getResource("imageOn.jpg").toString());
        ImageView imvOn = new ImageView(imOn);
        imvOn.setFitHeight(50);
        imvOn.setFitWidth(50);
        btnOn.setGraphic(imvOn);
        btnOn.setStyle("-fx-font: bold italic 12pt Georgia;");
        btnOn.setAlignment(Pos.CENTER);
        btnOn.setContentDisplay(ContentDisplay.RIGHT);
        btnOn.setTextAlignment(TextAlignment.CENTER);
        btnOn.setGraphicTextGap(10);
        btnOn.setWrapText(true);
        btnOn.setToggleGroup(tgroup);
        btnOn.requestFocus();
        btnOn.selectedProperty().addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) ->
        {
            if (new_val.equals(Boolean.TRUE)) scene.setFill(Color.web("#fff8dc"));
        });

        // new code 2
        RadioButton btnOf;
        btnOf = new RadioButton("Internet Explorer");
        btnOf.setLayoutX(20);
        btnOf.setLayoutY(100);
        btnOf.setBlendMode(BlendMode.MULTIPLY);
        btnOf.setCursor(Cursor.CLOSED_HAND);

        btnOf.setPrefSize(200, 80);
        btnOf.setTooltip(new Tooltip("Це кнопка вибору Internet Explorer"));
        Image imOf = new Image(this.getClass().getResource("imageOf.jpg").toString());
        ImageView imvOf = new ImageView(imOf);
        imvOf.setFitHeight(50);
        imvOf.setFitWidth(50);
        btnOf.setGraphic(imvOf);
        btnOf.setStyle("-fx-font: bold italic 12pt Georgia;");
        btnOf.setAlignment(Pos.CENTER);
        btnOf.setContentDisplay(ContentDisplay.RIGHT);
        btnOf.setTextAlignment(TextAlignment.CENTER);
        btnOf.setGraphicTextGap(10);
        btnOf.setWrapText(true);
        btnOf.setToggleGroup(tgroup);
        btnOf.selectedProperty().addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) ->
        {
            if (new_val.equals(Boolean.TRUE)) scene.setFill(Color.web("#99ffff"));
        });
        
        // new code 3
        root.getChildren().add(btnOn);
        root.getChildren().add(btnOf);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

8. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі Очистити та побудувати проект
   (Shift+F11), а потім – Виконати проект (F6).
