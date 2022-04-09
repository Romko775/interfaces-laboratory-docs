# Label

Компонент `Label` представлений класом `javafx.scene.control.Label`, екземпляр якого може бути створений за допомогою
класу-фабрики `LabelBuilder` або за допомогою одного з конструкторів:
- `Label label = new Label();`
- `Label label = new Label("[текст]");`
- `Label label = new Label("[текст]", [вузол значка]);`

Клас Label забезпечує відображення текстового підпису, зображення, текстового підпису та зображення одночасно і має такі
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
- успадкована від класу `javafx.scene.Parent `властивість `needsLayout`;
- успадковані від класу `javafx.scene.control.Control` властивості:
  * contextMenu
  * height
  * maxHeight
  * maxWidth
  * minHeight
  * minWidth,
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
  * graphicTextGap,
  * labelPadding
  * mnemonicParsing
  * textAlignment
  * textFill
  * textOverrun,
  * text
  * underline
  * wrapText
- власна властивість labelFor, що визначає компонент, з яким зв'язується мітка.

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить мітку `Label`, в меню `Файл` оберіть `Створити проект | Java with Ant | JavaFX | JavaFX Application`, натисніть
   кнопку `Далі`, введіть ім’я проекту `JavaFXApplicationLabel`, залишивши прапорець `Create Main Class`, та натисніть кнопку
   `Готово`.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationLabel`, який розширює клас
`Application`.

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationLabel extends Application {
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
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI- компонентів: Label”` та зробіть видимим об’єкт
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

public class JavaFXApplicationLabel extends Application {
   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 400, 400, Color.BEIGE);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: Label");
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

4. Створіть перший екземпляр мітки Label. Мітку помістіть у лівий верхній кут основного вікна JavaFX-програми, і для неї
   визначте такі властивості, як курсор миші, візуальний ефект, переважні розміри, підказка, значок і вирівнювання:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationLabel extends Application {
   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 400, 400, Color.BEIGE);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: Label");
      
      // new code 
      Label limg = new Label();
      limg.setLayoutX(10);
      limg.setLayoutY(10);
      limg.setCursor(Cursor.CROSSHAIR);
      
      DropShadow effect = new DropShadow();
      effect.setOffsetX(10);
      effect.setOffsetY(10);
      
      limg.setEffect(effect);
      limg.setPrefSize(200, 200);
      limg.setTooltip(new Tooltip("Це ті гори, де я не бував"));
      
      Image im = new Image(this.getClass().getResource("image.jpg").toString());
      ImageView imv = new ImageView(im);
      
      imv.setPreserveRatio(true);
      imv.setFitHeight(200);
      imv.setFitWidth(200);
      
      limg.setGraphic(imv);
      limg.setAlignment(Pos.TOP_LEFT);
      
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

5. Створіть другий екземпляр мітки Label із текстом. Другу мітку помістіть під першою міткою, і для неї визначте такі
   властивості, як масштабування, курсор миші, переважні розміри, стиль, вирівнювання та перенесення рядків:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationLabel extends Application {
   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 400, 400, Color.BEIGE);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: Label");

      Label limg = new Label();
      limg.setLayoutX(10);
      limg.setLayoutY(10);
      limg.setCursor(Cursor.CROSSHAIR);
      
      DropShadow effect = new DropShadow();
      effect.setOffsetX(10);
      effect.setOffsetY(10);
      
      limg.setEffect(effect);
      limg.setPrefSize(200, 200);
      limg.setTooltip(new Tooltip("Це ті гори, де я не бував"));
      
      Image im = new Image(this.getClass().getResource("image.jpg").toString());
      ImageView imv = new ImageView(im);
      
      imv.setPreserveRatio(true);
      imv.setFitHeight(200);
      imv.setFitWidth(200);
      
      limg.setGraphic(imv);
      limg.setAlignment(Pos.TOP_LEFT);
      
      // new code 2

      Label label = new Label("Гори");
      label.setLayoutX(45);
      label.setLayoutY(155);
      label.setScaleX(1.5);
      label.setCursor(Cursor.TEXT);
      label.setPrefSize(133,30);

      label.setStyle("-fx-font: bold italic 14pt Georgia;-fx-text-fill:#000066;-fx-background-color: lightgrey;");

      label.setGraphic(null);
      label.setAlignment(Pos.CENTER);
      label.setWrapText(true);
      
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

6. Скачайте з інтернету рисунок із зображенням гір та збережіть його як image.png у папці, де розміщений файл
   JavaFXApplicationLabel.java.
7. Створені мітки додайте в кореневий вузол графа сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationLabel extends Application {
   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 400, 400, Color.BEIGE);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: Label");

      Label limg = new Label();
      limg.setLayoutX(10);
      limg.setLayoutY(10);
      limg.setCursor(Cursor.CROSSHAIR);
      
      DropShadow effect = new DropShadow();
      effect.setOffsetX(10);
      effect.setOffsetY(10);
      
      limg.setEffect(effect);
      limg.setPrefSize(200, 200);
      limg.setTooltip(new Tooltip("Це ті гори, де я не бував"));
      
      Image im = new Image(this.getClass().getResource("image.jpg").toString());
      ImageView imv = new ImageView(im);
      
      imv.setPreserveRatio(true);
      imv.setFitHeight(200);
      imv.setFitWidth(200);
      
      limg.setGraphic(imv);
      limg.setAlignment(Pos.TOP_LEFT);
      
      // new code 2

      Label label = new Label("Гори");
      label.setLayoutX(45);
      label.setLayoutY(155);
      label.setScaleX(1.5);
      label.setCursor(Cursor.TEXT);
      label.setPrefSize(133,30);

      label.setStyle("-fx-font: bold italic 14pt Georgia;-fx-text-fill:#000066;-fx-background-color: lightgrey;");

      label.setGraphic(null);
      label.setAlignment(Pos.CENTER);
      label.setWrapText(true);

      root.getChildren().add(label);
      root.getChildren().add(limg);
      
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

8. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі Очистити та побудувати проект
   `(Shift+F11)`, а потім – `Виконати проект (F6)`.
