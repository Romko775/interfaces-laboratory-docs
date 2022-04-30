# MenuBar, Menu

- [MenuBar, Menu](#menubar--menu)
    * [MenuBar](#menubar)
    * [Menu](#menu)
        + [MenuItem](#menuitem)
        + [CheckMenuItem](#checkmenuitem)
        + [RadioMenuItem](#radiomenuitem)
        + [SeparatorMenuItem](#separatormenuitem)
    * [Завдання](#--------)

## MenuBar

Компонент `MenuBar` представлений класом `javafx.scene.control.MenuBar`, екземпляр якого може бути створений за
допомогою класу-фабрики `MenuBarBuilder` або за допомогою конструктора:

- `MenuBar MenuBar = New MenuBar();`

Клас `MenuBar` представляє панель меню і має такі властивості:

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
- успадкована від класу `javafx.scene.Parent` властивість
    * needsLayout
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

Компонент `MenuBar` містить список `javafx.collections.ObservableList<Menu>` компонентів меню `Menu`, який можна
поповнити за допомогою методу `getMenus().addAll()` класу `javafx.scene.control.MenuBar`.

## Menu

Компоненти меню `Menu`, що містяться в панелі `MenuBar`, представлені класом `javafx.scene.control.Menu`, екземпляр
якого може бути створений за допомогою класу-фабрики `MenuBuilder` або за допомогою одного з конструкторів:

- `Menu menu = new Menu("[текст]");`
- `Menu menu = new Menu("[текст]", [вузол значка]);`

Клас `Menu` має такі властивості:

- успадковані від класу `javafx.scene.control.MenuItem` властивості:
    * accelerator
    * disabled
    * graphic
    * id
    * mnemonicParsing
    * onAction
    * parentMenu
    * parentPopup
    * style
    * text
    * visible
- власні властивості:
    * onHidden
    * onHiding
    * onShowing
    * onShown,
    * showing

Компоненти меню `Menu` панелі `MenuBar` також містять свої набори `javafx.collections.ObservableList<MenuItem`>
компонентів `MenuItem`, які можна поповнити за допомогою методу `getItems().addAll()` класу `javafx.scene.control.Menu`.

Компоненти `MenuItem` представлені класом `javafx.scene.control.MenuItem`, екземпляр якого може бути створений за
допомогою класу-фабрики `MenuItemBuilder` або за допомогою одного з конструкторів:

- `MenuItem menuItem = new MenuItem();`
- `MenuItem menuItem = new MenuItem("[текст]");`
- `MenuItem menuItem = new MenuItem("[текст]", [вузол значка]);`

### MenuItem

Клас `MenuItem` має властивості

- accelerator
- disabled
- graphic
- id,
- mnemonicParsing
- onAction
- parentMenu
- parentPopup
- style
- text
- visible
- підкласи
    * `CheckMenuItem`
    * `CustomMenuItem`
    * `Menu`
    * `RadioMenuItem`

Тому до компоненту меню `Menu` панелі `MenuBar` можна додавати не тільки елементи `MenuItem`, але й
прапорці `CheckMenuItem` та перемикачі `RadioMenuItem`, а також роздільники `SeparatorMenuItem`, представлені
класом `SeparatorMenuItem`, що розширює клас `CustomMenuItem`, та вкладені меню `Menu`.

### CheckMenuItem

Прапорець `CheckMenuItem` представлений класом `javafx.scene.control.CheckMenuItem`, екземпляр якого може бути створений
за допомогою класу-фабрики `CheckMenuItemBuilder` або за допомогою одного з конструкторів:

- `CheckMenuItem сheckMenuItem = new CheckMenuItem();`
- `CheckMenuItem сheckMenuItem = new CheckMenuItem("[текст]");`
- `CheckMenuItem сheckMenuItem = new CheckMenuItem("[текст]", [вузол значка]);`

Клас `CheckMenuItem` має такі властивості:

- успадковані від класу `javafx.scene.control.MenuItem` властивості:
    * accelerator
    * disabled
    * graphic
    * id
    * mnemonicParsing
    * onAction
    * parentMenu
    * parentPopup
    * style
    * text
    * visible ‒ власну властивість selected.

### RadioMenuItem

Перемикач `RadioMenuItem` представлений класом `javafx.scene.control.RadioMenuItem`, екземпляр якого може бути створений
за допомогою класу-фабрики `RadioMenuItemBuilder` або за допомогою одного з конструкторів:

- `RadioMenuItem radioItem = new RadioMenuItem("[текст]");`
- `RadioMenuItem radioItem = new RadioMenuItem("[текст]", [вузол значка]);`

Клас `RadioMenuItem` має такі властивості:
‒ успадковані від класу `javafx.scene.control.MenuItem` властивості: accelerator, disabled, graphic, id,
mnemonicParsing, onAction, parentMenu, parentPopup, style, text, visible; ‒ власні властивості selected та toggleGroup (
дозволяє об'єднувати перемикачі у групу ToggleGroup).

### SeparatorMenuItem

Розділювач `SeparatorMenuItem` представлений класом `javafx.scene.control. SeparatorMenuItem`, екземпляр якого може бути
створений за допомогою класу-фабрики `SeparatorMenuItemBuilder` або за допомогою конструктора:

- `SeparatorMenuItem separatorMenuItem = new SeparatorMenuItem();`

Клас `SeparatorMenuItem` має такі властивості:

- успадковані від класу `javafx.scene.control.MenuItem` властивості:
    * accelerator
    * disabled
    * graphic
    * id
    * mnemonicParsing
    * onAction
    * parentMenu
    * parentPopup
    * style
    * text
    * visible
- успадковані від класу `javafx.scene.control.CustomMenuItem` властивості:
    * content
    * hideOnClick

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить панель `MenuBar`, в меню `Файл` оберіть `Створити проект` | `Java with Ant` | `JavaFX` | `JavaFX Application`
   , натисніть кнопку `Далі`, введіть ім’я проекту `JavaFXApplicationMenuBar`, залишивши прапорець `Create Main Class`,
   та натисніть кнопку `Готово`. У вікні редактора середовища NetBeans з’явиться код згенерованого
   класу `JavaFXApplicationMenuBar`, який розширює клас `Application`.

```java
package javafxapplicationbutton;

import javafx.application.Application;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuBar extends Application {
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
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI-компонентів: MenuBar”` та зробіть видимим об’єкт
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

public class JavaFXApplicationMenuBar extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 450, 300, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuBar, Menu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Створіть екземпляр панелі MenuBar. Панель меню помістіть у лівий верхній кут основного вікна JavaFX-додатка, і для
   неї визначте такі властивості, як режим накладання, курсор миші, візуальний ефект, стиль і бажані розміри:

```java
package javafxapplicationbutton;

import javafx.application.Application;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuBar extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 450, 300, Color.BEIGE);

        MenuBar menuBar = new MenuBar();
        menuBar.setLayoutX(10);
        menuBar.setLayoutY(10);
        menuBar.setBlendMode(BlendMode.HARD_LIGHT);
        menuBar.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect = new DropShadow();
        effect.setOffsetX(5);
        effect.setOffsetY(5);

        menuBar.setEffect(effect);
        menuBar.setStyle("-fx-base:skyblue;-fx-border-width:4pt;-fx-border-color:navy;-fx-font:bold 16pt Georgia;");
        menuBar.setPrefSize(350, 50);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuBar, Menu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

5. Створіть перший екземпляр компонента меню `Menu` з текстом, для якого створюється набір елементів меню, що
   складається з компонента `MenuItem`, роздільника `SeparatorMenuItem`, перемикачів `RadioMenuItem` та
   прапорця `CheckMenuItem`. Для компонента `MenuItem` визначте текст, стиль, швидкі клавіші та обробник вибору.
   Перемикачі `RadioMenuItem` об'єднайте в групу, і для них встановіть текст та стиль. Для прапорця `CheckMenuItem`
   визначте текст, стиль та вибір:

```java
package javafxapplicationbutton;

import javafx.application.Application;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuBar extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 450, 300, Color.BEIGE);

        MenuBar menuBar = new MenuBar();
        menuBar.setLayoutX(10);
        menuBar.setLayoutY(10);
        menuBar.setBlendMode(BlendMode.HARD_LIGHT);
        menuBar.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect = new DropShadow();
        effect.setOffsetX(5);
        effect.setOffsetY(5);

        menuBar.setEffect(effect);
        menuBar.setStyle("-fx-base:skyblue;-fx-border-width:4pt;-fx-border-color:navy;-fx-font:bold 16pt Georgia;");
        menuBar.setPrefSize(350, 50);

        Menu menuF = new Menu("Файл");
        MenuItem menuItemP = new MenuItem("Друк");
        menuItemP.setStyle("-fx-text-fill: navy;-fx-font:bold italic 14pt Georgia;");
        menuItemP.setAccelerator(KeyCombination.keyCombination("Ctr l+P"));
        menuItemP.setOnAction((ActionEvent e) -> {
            System.out.println("Триває друк...");
        });

        SeparatorMenuItem sep = new SeparatorMenuItem();
        RadioMenuItem radioItemY = new RadioMenuItem("З номерами сторінок");
        radioItemY.setStyle(" -fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");

        ToggleGroup tgroup = new ToggleGroup();

        radioItemY.setToggleGroup(tgroup);
        radioItemY.setSelected(true);
        RadioMenuItem radioItemN = new RadioMenuItem("Без номерів сторінок");
        radioItemN.setStyle("-fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");
        radioItemN.setToggleGroup(tgroup);
        CheckMenuItem checkMenuItem = new CheckMenuItem("Покращена якість");
        checkMenuItem.setSelected(true);
        checkMenuItem.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuF.getItems().addAll(menuItemP, radioItemY, radioItemN, sep, checkMenuItem);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuBar, Menu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

6. Створіть другий екземпляр компонента меню `Menu` з текстом, для якого формується набір елементів меню, що складається з
   компонентів `MenuItem`. Для компонентів MenuItem встановіть текст та стиль:

```java
package javafxapplicationbutton;

import javafx.application.Application;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuBar extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 450, 300, Color.BEIGE);

        MenuBar menuBar = new MenuBar();
        menuBar.setLayoutX(10);
        menuBar.setLayoutY(10);
        menuBar.setBlendMode(BlendMode.HARD_LIGHT);
        menuBar.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect = new DropShadow();
        effect.setOffsetX(5);
        effect.setOffsetY(5);

        menuBar.setEffect(effect);
        menuBar.setStyle("-fx-base:skyblue;-fx-border-width:4pt;-fx-border-color:navy;-fx-font:bold 16pt Georgia;");
        menuBar.setPrefSize(350, 50);

        Menu menuF = new Menu("Файл");
        MenuItem menuItemP = new MenuItem("Друк");
        menuItemP.setStyle("-fx-text-fill: navy;-fx-font:bold italic 14pt Georgia;");
        menuItemP.setAccelerator(KeyCombination.keyCombination("Ctr l+P"));
        menuItemP.setOnAction((ActionEvent e) -> {
            System.out.println("Триває друк...");
        });

        SeparatorMenuItem sep = new SeparatorMenuItem();
        RadioMenuItem radioItemY = new RadioMenuItem("З номерами сторінок");
        radioItemY.setStyle(" -fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");

        ToggleGroup tgroup = new ToggleGroup();

        radioItemY.setToggleGroup(tgroup);
        radioItemY.setSelected(true);
        RadioMenuItem radioItemN = new RadioMenuItem("Без номерів сторінок");
        radioItemN.setStyle("-fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");
        radioItemN.setToggleGroup(tgroup);
        CheckMenuItem checkMenuItem = new CheckMenuItem("Покращена якість");
        checkMenuItem.setSelected(true);
        checkMenuItem.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuF.getItems().addAll(menuItemP, radioItemY, radioItemN, sep, checkMenuItem);

        Menu menuE = new Menu("Правка"); 
        MenuItem menuItemCut = new MenuItem("Вирізати"); 
        menuItemCut.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;"); 
        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;"); 
        MenuItem menuItemPaste = new MenuItem("Вставити"); 
        menuItemPaste.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuE.getItems().addAll(menuItemCut, menuItemCopy, menuItemPaste);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuBar, Menu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

7. Створіть третій примірник компонента меню Menu з текстом, для якого створюється набір елементів меню, що складається
   з компонента MenuItem. Для компонента MenuItem встановіть текст та стиль:

```java
package javafxapplicationbutton;

import javafx.application.Application;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuBar extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 450, 300, Color.BEIGE);

        MenuBar menuBar = new MenuBar();
        menuBar.setLayoutX(10);
        menuBar.setLayoutY(10);
        menuBar.setBlendMode(BlendMode.HARD_LIGHT);
        menuBar.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect = new DropShadow();
        effect.setOffsetX(5);
        effect.setOffsetY(5);

        menuBar.setEffect(effect);
        menuBar.setStyle("-fx-base:skyblue;-fx-border-width:4pt;-fx-border-color:navy;-fx-font:bold 16pt Georgia;");
        menuBar.setPrefSize(350, 50);

        Menu menuF = new Menu("Файл");
        MenuItem menuItemP = new MenuItem("Друк");
        menuItemP.setStyle("-fx-text-fill: navy;-fx-font:bold italic 14pt Georgia;");
        menuItemP.setAccelerator(KeyCombination.keyCombination("Ctr l+P"));
        menuItemP.setOnAction((ActionEvent e) -> {
            System.out.println("Триває друк...");
        });

        SeparatorMenuItem sep = new SeparatorMenuItem();
        RadioMenuItem radioItemY = new RadioMenuItem("З номерами сторінок");
        radioItemY.setStyle(" -fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");

        ToggleGroup tgroup = new ToggleGroup();

        radioItemY.setToggleGroup(tgroup);
        radioItemY.setSelected(true);
        RadioMenuItem radioItemN = new RadioMenuItem("Без номерів сторінок");
        radioItemN.setStyle("-fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");
        radioItemN.setToggleGroup(tgroup);
        CheckMenuItem checkMenuItem = new CheckMenuItem("Покращена якість");
        checkMenuItem.setSelected(true);
        checkMenuItem.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuF.getItems().addAll(menuItemP, radioItemY, radioItemN, sep, checkMenuItem);

        Menu menuE = new Menu("Правка"); 
        MenuItem menuItemCut = new MenuItem("Вирізати"); 
        menuItemCut.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;"); 
        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;"); 
        MenuItem menuItemPaste = new MenuItem("Вставити"); 
        menuItemPaste.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuE.getItems().addAll(menuItemCut, menuItemCopy, menuItemPaste);

        Menu menuV = new Menu("Вид"); 
        MenuItem menuItemS = new MenuItem("Масштаб"); 
        menuItemS.setStyle("-fx-text-fill: navy;-fx-font:bold italic 14pt Georgia;"); 
        menuV.getItems().addAll(menuItemS);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuBar, Menu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

8. Створені екземпляри компонента меню Menu додайте в панель `MenuBar`, яка в свою чергу додається до кореневого вузла
   графа сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;

import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuBar extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 450, 300, Color.BEIGE);

        MenuBar menuBar = new MenuBar();
        menuBar.setLayoutX(10);
        menuBar.setLayoutY(10);
        menuBar.setBlendMode(BlendMode.HARD_LIGHT);
        menuBar.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect = new DropShadow();
        effect.setOffsetX(5);
        effect.setOffsetY(5);

        menuBar.setEffect(effect);
        menuBar.setStyle("-fx-base:skyblue;-fx-border-width:4pt;-fx-border-color:navy;-fx-font:bold 16pt Georgia;");
        menuBar.setPrefSize(350, 50);

        Menu menuF = new Menu("Файл");
        MenuItem menuItemP = new MenuItem("Друк");
        menuItemP.setStyle("-fx-text-fill: navy;-fx-font:bold italic 14pt Georgia;");
        menuItemP.setAccelerator(KeyCombination.keyCombination("Ctr l+P"));
        menuItemP.setOnAction((ActionEvent e) -> {
            System.out.println("Триває друк...");
        });

        SeparatorMenuItem sep = new SeparatorMenuItem();
        RadioMenuItem radioItemY = new RadioMenuItem("З номерами сторінок");
        radioItemY.setStyle(" -fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");

        ToggleGroup tgroup = new ToggleGroup();

        radioItemY.setToggleGroup(tgroup);
        radioItemY.setSelected(true);
        RadioMenuItem radioItemN = new RadioMenuItem("Без номерів сторінок");
        radioItemN.setStyle("-fx-text-fill:navy;-fx-font:bold italic 12pt Georgia;");
        radioItemN.setToggleGroup(tgroup);
        CheckMenuItem checkMenuItem = new CheckMenuItem("Покращена якість");
        checkMenuItem.setSelected(true);
        checkMenuItem.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuF.getItems().addAll(menuItemP, radioItemY, radioItemN, sep, checkMenuItem);

        Menu menuE = new Menu("Правка"); 
        MenuItem menuItemCut = new MenuItem("Вирізати"); 
        menuItemCut.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;"); 
        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;"); 
        MenuItem menuItemPaste = new MenuItem("Вставити"); 
        menuItemPaste.setStyle("-fx-text-fill:navy;-fx-font:bold italic 14pt Georgia;");
        menuE.getItems().addAll(menuItemCut, menuItemCopy, menuItemPaste);

        Menu menuV = new Menu("Вид"); 
        MenuItem menuItemS = new MenuItem("Масштаб"); 
        menuItemS.setStyle("-fx-text-fill: navy;-fx-font:bold italic 14pt Georgia;"); 
        menuV.getItems().addAll(menuItemS);

        menuBar.getMenus().addAll(menuF, menuE, menuV); 
        root.getChildren().add(menuBar);

        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuBar, Menu");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

9. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на
   піктограмі `Очистити та побудувати проект (Shift+F11)`, а потім – `Виконати проект (F6)`.
