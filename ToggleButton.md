# ToggleButton

Компонент `ToggleButton` представлений класом
`javafx.scene.control.ToggleButton`, екземпляр якого може бути створений за допомогою
класу-фабрики `ToggleButtonBuilder` або за допомогою одного з конструкторів:

- `ToggleButton btn = New ToggleButton();`
- `ToggleButton btn = New ToggleButton("[текст]");`
- `ToggleButton btn = New ToggleButton("[текст]", [вузол значка]);`

Клас `ToggleButton` представляє кнопку, яка може перебувати в натиснутому та відтисненому станах, і має наступні
властивості:

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
- успадковані від класу `javafx.scene.control.ButtonBase` властивості `armed` та `onAction`; 
- власні властивості `selected` і `toggleGroup`.

Властивості компонента `ToggleButton`, успадковані від класів `ButtonBase`, `Labeled`, `Control`,
`Parent` та `Node`, аналогічні тим самим властивостям, які має і компонент `Button`. Відмінність набору властивостей
компонента `ToggleButton` від набору властивостей компонента Button полягає в наявності властивостей selected та
toggleGroup самого класу`javafx.scene.control.ToggleButton`. 

Властивість `selected` приймає значення `true`, якщо кнопка `ToggleButton` знаходиться в натиснутому стані, а значення `false` – якщо кнопка `ToggleButton` віджата. Властивість
toggleGroup вказує групу `javafx.scene.control.ToggleGroup`, до якої належить кнопка `ToggleButton`. Об’єднання
кнопок `ToggleButton` у групу `ToggleGroup` відрізняється від об’єднання перемикачів `RadioButton` у групу
`ToggleGroup` – у групі перемикачів `RadioButton` щонайменше один елемент повинен перебувати у вибраному стані. У групі
кнопок `ToggleButton` такої функціональності немає. Об’єднання кнопок `ToggleButton` у групу забезпечує ефект натискання
лише єдиної кнопки у групі. При натисканні іншої кнопки групи всі інші кнопки автоматично віджимаються. Екземпляр
класу `ToggleGroup` можна створити за допомогою класу-фабрики або за допомогою конструктора:
`ToggleGroup tgroup = New ToggleGroup();`

Клас `ToggleGroup` має властивість `selectedToggle`, що вказує на обраний в даний момент елемент групи.

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи `JavaFX 2.0`. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить об’єднання кнопок `ToggleButton`, в меню `Файл` оберіть `Створити проект` | `Java with Ant` | `JavaFX` | `JavaFX
   Application`, натисніть кнопку Далі, введіть ім’я проекту `JavaFXApplicationToggleButton`, залишивши прапорець `Create
   Main Class`, та натисніть кнопку `Готово`.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationToggleButton`, який розширює
клас `Application`. 

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationToggleButton extends Application {
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

Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI-компонентів: ToggleButton”` та зробіть видимим об’єкт `Stage`:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationToggleButton extends Application {

   @Override
   public void start(Stage primaryStage) {
      // New code
      Group root = new Group();
      Scene scene = new Scene(root, 430, 400, Color.LIGHTGREEN);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: ToggleButton");
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

4. Створіть групу `ToggleGroup`, перший та другий екземпляр кнопки `ToggleButton` з текстом.

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationToggleButton extends Application {

   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 430, 400, Color.LIGHTGREEN);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: ToggleButton");

      // New code
      ToggleGroup tgroup = new ToggleGroup();
      ToggleButton btnOn = new ToggleButton("JavaFX");
      ToggleButton btnOf = new ToggleButton("Silverlight");

      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

5. Перший екземпляр кнопки помістіть у лівий верхній кут основного вікна JavaFX-програми, і для неї визначте такі
   властивості, як курсор миші, візуальний ефект, кращі розміри, підказка, значок, стиль, вирівнювання, перенесення
   рядків, група та обробник подій кнопки. При визначенні стилю кнопки встановіть початковий стиль та обробник зміни
   значення властивості selected кнопки, в якому стиль кнопки та розмір значка змінюються залежно від того, кнопка
   натиснута або віджата. При цьому змінюється загальний колір сцени. Встановіть обробник подій кнопки, який виводить у
   консоль значення властивості `selected` кнопки:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationToggleButton extends Application {

   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 430, 400, Color.LIGHTGREEN);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: ToggleButton");

      ToggleGroup tgroup = new ToggleGroup();
      ToggleButton btnOn = new ToggleButton("JavaFX");
      ToggleButton btnOf = new ToggleButton("Silverlight");

      // New code
      btnOn.setLayoutX(10);
      btnOn.setLayoutY(10);
      btnOn.setCursor(Cursor.CLOSED_HAND);

      DropShadow effect = new DropShadow();
      effect.setOffsetX(5);
      effect.setOffsetY(5);
      btnOn.setEffect(effect);

      btnOn.setPrefSize(200, 80);
      btnOn.setTooltip(new Tooltip("Це кнопка вибору платформи JavaFX"));

      Image imOn = new
              Image(this.getClass().getResource("imageOn.jpg").toString());
      ImageView imvOn;
      imvOn = new ImageView(imOn);
      imvOn.setFitHeight(50);
      imvOn.setFitWidth(50);
      btnOn.setGraphic(imvOn);

      btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 16pt Georgia; -fx-textfill:white;");

      btnOn
              .selectedProperty()
              .addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) -> {
                 if (new_val.equals(Boolean.TRUE)) {
                    btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 16pt Georgia; -fx-text-fill:white;");
                    imvOn.setFitHeight(40);
                    imvOn.setFitWidth(40);
                    scene.setFill(Color.web("#ffff00"));
                    System.out.println("Використовую JavaFX");
                 }
                 if (new_val.equals(Boolean.FALSE)) {
                    btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 18pt Georgia; -fx-text-fill:white;");
                    imvOn.setFitHeight(50);
                    imvOn.setFitWidth(50);
                    scene.setFill(Color.LIGHTGREEN);
                 }
              });


      btnOn.setAlignment(Pos.CENTER);
      btnOn.setContentDisplay(ContentDisplay.LEFT);
      btnOn.setTextAlignment(TextAlignment.CENTER);
      btnOn.setGraphicTextGap(20);
      btnOn.setWrapText(true);
      btnOn.setToggleGroup(tgroup);
      btnOn.setOnAction((ActionEvent e) -> {
         System.out.println("JavaFX:" + btnOn.selectedProperty().getValue());
         System.out.println("Silverlight:" + btnOf.selectedProperty().getValue());
      });

      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

5. Другий екземпляр кнопки помістіть поруч з першою кнопкою, і для неї визначте такі властивості, як курсор миші,
   візуальний ефект, переважні розміри, підказка, значок, стиль, вирівнювання, перенесення рядків, група і обробник
   подій кнопки. При визначенні стилю другої кнопки також встановіть початковий стиль та обробник зміни значення
   властивості selected кнопки, в якому стиль кнопки та розмір значка змінюються залежно від того, кнопка натиснута або
   віджата. При цьому змінюється загальний колір сцени. Встановіть обробник подій кнопки, який виводить у консоль
   значення властивості `selected` кнопки:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationToggleButton extends Application {

   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 430, 400, Color.LIGHTGREEN);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: ToggleButton");

      ToggleGroup tgroup = new ToggleGroup();
      ToggleButton btnOn = new ToggleButton("JavaFX");
      ToggleButton btnOf = new ToggleButton("Silverlight");

      btnOn.setLayoutX(10);
      btnOn.setLayoutY(10);
      btnOn.setCursor(Cursor.CLOSED_HAND);

      DropShadow effect = new DropShadow();
      effect.setOffsetX(5);
      effect.setOffsetY(5);
      btnOn.setEffect(effect);

      btnOn.setPrefSize(200, 80);
      btnOn.setTooltip(new Tooltip("Це кнопка вибору платформи JavaFX"));

      Image imOn = new Image(this.getClass().getResource("imageOn.jpg").toString());
      ImageView imvOn;
      imvOn = new ImageView(imOn);
      imvOn.setFitHeight(50);
      imvOn.setFitWidth(50);
      btnOn.setGraphic(imvOn);

      btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 16pt Georgia; -fx-textfill:white;");

      btnOn
              .selectedProperty()
              .addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) -> {
                 if (new_val.equals(Boolean.TRUE)) {
                    btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 16pt Georgia; -fx-text-fill:white;");
                    imvOn.setFitHeight(40);
                    imvOn.setFitWidth(40);
                    scene.setFill(Color.web("#ffff00"));
                    System.out.println("Використовую JavaFX");
                 }
                 if (new_val.equals(Boolean.FALSE)) {
                    btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 18pt Georgia; -fx-text-fill:white;");
                    imvOn.setFitHeight(50);
                    imvOn.setFitWidth(50);
                    scene.setFill(Color.LIGHTGREEN);
                 }
              });


      btnOn.setAlignment(Pos.CENTER);
      btnOn.setContentDisplay(ContentDisplay.LEFT);
      btnOn.setTextAlignment(TextAlignment.CENTER);
      btnOn.setGraphicTextGap(20);
      btnOn.setWrapText(true);
      btnOn.setToggleGroup(tgroup);
      btnOn.setOnAction((ActionEvent e) -> {
         System.out.println("JavaFX:" + btnOn.selectedProperty().getValue());
         System.out.println("Silverlight:" + btnOf.selectedProperty().getValue());
      });
      
      // New code
      btnOf.setLayoutX(220);
      btnOf.setLayoutY(10);
      btnOf.setCursor(Cursor.CLOSED_HAND);
      btnOf.setEffect(effect);

      btnOf.setPrefSize(200, 80);
      btnOf.setTooltip(new Tooltip("Це кнопка вибору платформи Silverlight"));

      Image imOf = new Image(this.getClass().getResource("imageOf.jpg").toString());
      ImageView imvOf;
      imvOf = new ImageView(imOf);
      imvOf.setFitHeight(50);
      imvOf.setFitWidth(50);
      btnOf.setGraphic(imvOf);

      btnOf.setStyle("-fx-base:#ff0000; -fx-font: bold italic 14pt Georgia; -fx-text-fill:white;");

      btnOf
              .selectedProperty()
              .addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) -> {
                 if (new_val.equals(Boolean.TRUE)) {
                    btnOf.setStyle("-fx-base:#ff0000; -fx-font: bold italic 12pt Georgia;-fxtext-fill:white;");
                    imvOf.setFitHeight(40);
                    imvOf.setFitWidth(40);
                    scene.setFill(Color.web("#660000"));
                    System.out.println("Використовую Silverlight");
                 }
                 if (new_val.equals(Boolean.FALSE)) {
                    btnOf.setStyle("-fx-base:#ff0000; -fx-font: bold italic 14pt Georgia; -fxtext-fill:white;");
                    imvOf.setFitHeight(50);
                    imvOf.setFitWidth(50);
                    scene.setFill(Color.LIGHTGREEN);
                 }
              });

      btnOf.setAlignment(Pos.CENTER);
      btnOf.setContentDisplay(ContentDisplay.LEFT);
      btnOf.setTextAlignment(TextAlignment.CENTER);
      btnOf.setGraphicTextGap(20);
      btnOf.setWrapText(true);
      btnOf.setToggleGroup(tgroup);
      btnOf.setOnAction((ActionEvent e) -> {
         System.out.println("JavaFX:" + btnOn.selectedProperty().getValue());
         System.out.println("Silverlight:" + btnOf.selectedProperty().getValue());
      });

      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

6. Скачайте з інтернету рисунки, назвавши як `imageOn.jpg` та `imageOf.jpg` і збережіть їх у папці, де розміщений файл
   `JavaFXApplicationToggleButton.java`.
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

public class JavaFXApplicationToggleButton extends Application {

   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 430, 400, Color.LIGHTGREEN);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: ToggleButton");

      ToggleGroup tgroup = new ToggleGroup();
      ToggleButton btnOn = new ToggleButton("JavaFX");
      ToggleButton btnOf = new ToggleButton("Silverlight");

      btnOn.setLayoutX(10);
      btnOn.setLayoutY(10);
      btnOn.setCursor(Cursor.CLOSED_HAND);

      DropShadow effect = new DropShadow();
      effect.setOffsetX(5);
      effect.setOffsetY(5);
      btnOn.setEffect(effect);

      btnOn.setPrefSize(200, 80);
      btnOn.setTooltip(new Tooltip("Це кнопка вибору платформи JavaFX"));

      Image imOn = new Image(this.getClass().getResource("imageOn.jpg").toString());
      ImageView imvOn;
      imvOn = new ImageView(imOn);
      imvOn.setFitHeight(50);
      imvOn.setFitWidth(50);
      btnOn.setGraphic(imvOn);

      btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 16pt Georgia; -fx-textfill:white;");

      btnOn
              .selectedProperty()
              .addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) -> {
                 if (new_val.equals(Boolean.TRUE)) {
                    btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 16pt Georgia; -fx-text-fill:white;");
                    imvOn.setFitHeight(40);
                    imvOn.setFitWidth(40);
                    scene.setFill(Color.web("#ffff00"));
                    System.out.println("Використовую JavaFX");
                 }
                 if (new_val.equals(Boolean.FALSE)) {
                    btnOn.setStyle("-fx-base:#9900ff; -fx-font: bold italic 18pt Georgia; -fx-text-fill:white;");
                    imvOn.setFitHeight(50);
                    imvOn.setFitWidth(50);
                    scene.setFill(Color.LIGHTGREEN);
                 }
              });


      btnOn.setAlignment(Pos.CENTER);
      btnOn.setContentDisplay(ContentDisplay.LEFT);
      btnOn.setTextAlignment(TextAlignment.CENTER);
      btnOn.setGraphicTextGap(20);
      btnOn.setWrapText(true);
      btnOn.setToggleGroup(tgroup);
      btnOn.setOnAction((ActionEvent e) -> {
         System.out.println("JavaFX:" + btnOn.selectedProperty().getValue());
         System.out.println("Silverlight:" + btnOf.selectedProperty().getValue());
      });
      
      btnOf.setLayoutX(220);
      btnOf.setLayoutY(10);
      btnOf.setCursor(Cursor.CLOSED_HAND);
      btnOf.setEffect(effect);

      btnOf.setPrefSize(200, 80);
      btnOf.setTooltip(new Tooltip("Це кнопка вибору платформи Silverlight"));

      Image imOf = new Image(this.getClass().getResource("imageOf.jpg").toString());
      ImageView imvOf;
      imvOf = new ImageView(imOf);
      imvOf.setFitHeight(50);
      imvOf.setFitWidth(50);
      btnOf.setGraphic(imvOf);

      btnOf.setStyle("-fx-base:#ff0000; -fx-font: bold italic 14pt Georgia; -fx-text-fill:white;");

      btnOf
              .selectedProperty()
              .addListener((javafx.beans.value.ObservableValue<? extends Boolean> ov, Boolean old_val, Boolean new_val) -> {
                 if (new_val.equals(Boolean.TRUE)) {
                    btnOf.setStyle("-fx-base:#ff0000; -fx-font: bold italic 12pt Georgia;-fxtext-fill:white;");
                    imvOf.setFitHeight(40);
                    imvOf.setFitWidth(40);
                    scene.setFill(Color.web("#660000"));
                    System.out.println("Використовую Silverlight");
                 }
                 if (new_val.equals(Boolean.FALSE)) {
                    btnOf.setStyle("-fx-base:#ff0000; -fx-font: bold italic 14pt Georgia; -fxtext-fill:white;");
                    imvOf.setFitHeight(50);
                    imvOf.setFitWidth(50);
                    scene.setFill(Color.LIGHTGREEN);
                 }
              });

      btnOf.setAlignment(Pos.CENTER);
      btnOf.setContentDisplay(ContentDisplay.LEFT);
      btnOf.setTextAlignment(TextAlignment.CENTER);
      btnOf.setGraphicTextGap(20);
      btnOf.setWrapText(true);
      btnOf.setToggleGroup(tgroup);
      btnOf.setOnAction((ActionEvent e) -> {
         System.out.println("JavaFX:" + btnOn.selectedProperty().getValue());
         System.out.println("Silverlight:" + btnOf.selectedProperty().getValue());
      });

      // New code
      root.getChildren().add(btnOn);
      root.getChildren().add(btnOf);

      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

8. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі `Очистити` та побудувати проект
   `(Shift+F11)`, а потім – `Виконати проект (F6)`.
