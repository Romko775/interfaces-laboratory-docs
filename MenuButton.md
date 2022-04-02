# MenuButton

Компонент `MenuButton` представлений класом`javafx.scene.control.MenuButton`, екземпляр якого може бути створений за допомогою класу-фабрики або за допомогою одного з конструкторів:
- `MenuButton btn = New MenuButton();`
- `MenuButton btn = new MenuButton("[текст]");`
- `MenuButton btn = new MenuButton("[текст]", [вузол значка]);`

Клас `MenuButton` представляє кнопку, при натисканні якої з'являється меню, і має такі властивості:
- успадковані від класу `javafx.scene.Nodne` властивості:
  * blendMode, 
  * boundsInLocal, 
  * boundsInParent, 
  * cacheHint, 
  * cache, 
  * clip,
  * cursor, 
  * depthTest, 
  * disabled, 
  * disable, 
  * effect, 
  * eventDispatcher, 
  * focused,
  * focusTraversable, 
  * hover, 
  * id, 
  * inputMethodRequests, 
  * layoutBounds,
  * layoutX, 
  * layoutY, 
  * managed, 
  * mouseTransparent, 
  * onDragDetected,
  * onDragDone, 
  * onDragDropped, 
  * onDragEntered, 
  * onDragExited,
  * onDragOver, 
  * onInputMethodTextChanged, 
  * onKeyPressed,
  * onKeyReleased, 
  * onKeyTyped, 
  * onMouseClicked, 
  * onMouseDragged,
  * onMouseEntered, 
  * onMouseExited, 
  * onMouseMoved, 
  * onMousePressed,
  * onMouseReleased, 
  * opacity, 
  * parent, 
  * pickOnBounds, 
  * pressed, 
  * rotate,
  * rotationAxis, 
  * scaleX, 
  * scaleY, 
  * scaleZ, 
  * scene, 
  * style, 
  * translateX, 
  * translateY,
  * translateZ, 
  * visible;
- успадкована від класу `javafx.scene.Parent` властивість needsLayout;
- успадковані від класу `javafx.scene.control.Control` властивості:
  * contextMenu, 
  * height, 
  * maxHeight, 
  * maxWidth, 
  * minHeight, 
  * minWidth,
  * prefHeight, 
  * prefWidth, 
  * skin, 
  * tooltip, 
  * width;
- успадковані від класу `javafx.scene.control.Labeled` властивості: 
  * alignment, 
  * contentDisplay, 
  * font, 
  * graphic, 
  * graphicTextGap,
  * labelPadding, 
  * mnemonicParsing, 
  * textAlignment, 
  * textFill, 
  * textOverrun,
  * text, 
  * underline, 
  * wrapText;
- успадковані від класу `javafx.scene.control.ButtonBase` властивості armed та onAction;
- власні властивості `popupSide` і `showing`.

Властивості компонента `MenuButton`, успадковані від класів 
- ButtonBase
- Labeled
- Control
- Parent та Node

аналогічні тим самим властивостям, які має і компонент `Button`.

Відмінність набору властивостей компонента `MenuButton` від набору властивостей компонента `Button` полягає в наявності
властивостей `popupSide` та showing самого класу `javafx.scene.control.MenuButton`.
Властивість `popupSide` визначає розташування меню щодо кнопки, а властивість `showing` набуває значення true при 
відображенні меню. При створенні компонента `MenuButton` потрібно створити меню, що є невід'ємною частиною компонента. 
При цьому меню складається з набору компонентів, представлених класом `javafx.scene.control.MenuItem`, 
поповнювати який можна за допомогою методу `getItems().addAll()` класу`javafx.scene.control.MenuButton`.

Екземпляр класу `MenuItem` можна створити за допомогою класу-фабрики `MenuItemBuilder` або за допомогою одного з конструкторів:
- `MenuItem menuItem = new MenuItem();`
- `MenuItem menuItem = new MenuItem("[текст]");`
- `MenuItem menuItem = new MenuItem("[текст]", [вузол значка]);`

Клас `MenuItem` має властивості:
- accelerator
- disabled
- graphic
- id
- mnemonicParsing
- onAction
- parentMenu
- parentPopup
- style
- text
- visible

що дозволяють визначити для елемента меню швидкі клавіші, відключити його, визначити значок, ідентифікатор, розбір
тексту, обробка меню, батьківське контекстне меню, стиль, текст та видимість. Клас `MenuItem` має підкласи 
`CheckMenuItem`, `CustomMenuItem`, `Menu` і `RadioMenuItem`, тому в меню компонента `MenuButton` можна
додавати не тільки елементи `MenuItem`, але і прапорець`CheckMenuItem` і перемикач `RadioMenuItem`, а також 
роздільники `SeparatorMenuItem`, представлені класом `SeparatorMenuItem`, клас `CustomMenuItem`, та вкладені меню `Menu`.

## Завдання

1. Відкрийте середовище `NetBeans` з підтримкою платформи `JavaFX 2.0`. Для створення JavaFX-додатку з GUI-інтерфейсом, що
містить компонент `MenuButton`, в меню `Файл` оберіть `Створити проект` | `Java with Ant` | `JavaFX` | `JavaFX Application`, натисніть
кнопку Далі, введіть ім’я проекту `JavaFXApplicationMenuButton`, залишивши прапорець `Create Main Class`, та натисніть кнопку.
Готово.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationMenuButton`, який розширює клас `Application`.
```java
package javafxapplicationbutton;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        StackPane root = new StackPane();
        Scene scene = new Scene(root, 300, 250);
        Button btn = new Button();
        
        btn.setText("Say ‘Hello World’");
        btn.setOnAction(new EventHandler<ActionEvent>() {
            @Override
            public void handle(ActionEvent event) {
                System.out.println("Hello World!");
            }
        });
        
        
        root.getChildren().add(btn);
        primaryStage.setTitle("Hello World!");
        primaryStage.setScene(scene);
        primaryStage.show();
        
    }
    public static void main(String[] args) {
        launch(args);
    }
}
```

3. У методі `start` вилучіть весь код.
4. Створіть кореневий вузол графа сцени та на його основі екземпляр сцени, який встановлюється для об'єкта `Stage`. Установіть
заголовок основного вікна JavaFX-додатку `“Тестування GUI-компонентів: MenuButton”` та зробіть видимим об'єкт `Stage`:

```java
package javafxapplicationbutton;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        
        // New code 
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuButton");
        primaryStage.show();
    }
    public static void main(String[] args) {
        launch(args);
    }
}
```


4. Створіть екземпляр кнопки `MenuButton` із текстом. Кнопку помістіть у лівий верхній кут основного вікна JavaFX-програми, і
для неї визначте такі властивості, як режим накладання, курсор миші, візуальний ефект, переважні розміри, підказка, значок, стиль,
вирівнювання, перенесення рядків і розташування меню щодо кнопки. Створіть елементи меню `Вирізати`, `Копіювати` та `Вставити`.
Для них встановіть текст, стиль, швидкі клавіші та обробники подій:

```java
package javafxapplicationbutton;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuButton");

        // New code
        MenuButton btn = new MenuButton("Правка");
        btn.setLayoutX(20);
        btn.setLayoutY(20);
        btn.setBlendMode(BlendMode.HARD_LIGHT);
        btn.setCursor(Cursor.CLOSED_HAND);
        
        DropShadow effect=new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        
        btn.setEffect(effect);
        btn.setPrefSize(200,80);
        btn.setTooltip(new Tooltip("Це кнопка контекстного меню"));
        
        Image im = new Image(this.getClass().getResource("image.png").toString());
        ImageView imv = new ImageView(im);
        imv.setFitHeight(50);
        imv.setFitWidth(50);
        
        btn.setGraphic(imv);
        btn.setStyle("-fx-font: bold italic 14pt Georgia;");
        btn.setAlignment(Pos.CENTER);
        btn.setContentDisplay(ContentDisplay.LEFT);
        btn.setTextAlignment(TextAlignment.CENTER);
        btn.setGraphicTextGap(10);
        btn.setWrapText(true);
        btn.setPopupSide(Side.RIGHT);

        MenuItem menuItemCut = new MenuItem("Вирізати");
        menuItemCut.setStyle("-fx-font:bold italic 12pt Times;" );
        menuItemCut.setAccelerator(KeyCombination.keyCombination("Ctrl+U"));
        menuItemCut.setOnAction(e -> {
            System.out.println("Вирізаю");
        });
        
        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setStyle("-fx-font:bold italic 12pt Times;");
        menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+O"));
        menuItemCopy.setOnAction(e1 -> {
            System.out.println("Копіюю");
        });
        
        MenuItem menuItemPaste = new MenuItem("Вставити");
        menuItemPaste.setStyle("-fx-font:bold italic 12pt Times;" );
        menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        menuItemPaste.setOnAction(e2 -> {
            System.out.println("Вставляю");
        });
        
        // primaryStage.show();
    }
    public static void main(String[] args) {
        launch(args);
    }
}
```

5. Скачайте з інтернету рисунок із зображенням смайлика та збережіть його як image.png у папці, де розміщений файл `JavaFXApplicationMenuButton.java`.
6. Додайте в меню кнопки елементи меню, а кнопку додайте в кореневий вузол графа сцени:
```java
package javafxapplicationbutton;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationMenuButton extends Application {
    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: MenuButton");
        
        MenuButton btn = new MenuButton("Правка");
        btn.setLayoutX(20);
        btn.setLayoutY(20);
        btn.setBlendMode(BlendMode.HARD_LIGHT);
        btn.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect=new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);

        btn.setEffect(effect);
        btn.setPrefSize(200,80);
        btn.setTooltip(new Tooltip("Це кнопка контекстного меню"));

        Image im = new Image(this.getClass().getResource("image.png").toString());
        ImageView imv = new ImageView(im);
        imv.setFitHeight(50);
        imv.setFitWidth(50);

        btn.setGraphic(imv);
        btn.setStyle("-fx-font: bold italic 14pt Georgia;");
        btn.setAlignment(Pos.CENTER);
        btn.setContentDisplay(ContentDisplay.LEFT);
        btn.setTextAlignment(TextAlignment.CENTER);
        btn.setGraphicTextGap(10);
        btn.setWrapText(true);
        btn.setPopupSide(Side.RIGHT);

        MenuItem menuItemCut = new MenuItem("Вирізати");
        menuItemCut.setStyle("-fx-font:bold italic 12pt Times;" );
        menuItemCut.setAccelerator(KeyCombination.keyCombination("Ctrl+U"));
        menuItemCut.setOnAction(e -> {
            System.out.println("Вирізаю");
        });

        MenuItem menuItemCopy = new MenuItem("Копіювати");
        menuItemCopy.setStyle("-fx-font:bold italic 12pt Times;");
        menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+O"));
        menuItemCopy.setOnAction(e1 -> {
            System.out.println("Копіюю");
        });

        MenuItem menuItemPaste = new MenuItem("Вставити");
        menuItemPaste.setStyle("-fx-font:bold italic 12pt Times;" );
        menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        menuItemPaste.setOnAction(e2 -> {
            System.out.println("Вставляю");
        });

        // New code
        btn.getItems().addAll(menuItemCut, menuItemCopy, menuItemPaste);
        root.getChildren().add(btn);
        primaryStage.show();
    }
    public static void main(String[] args) {
        launch(args);
    }
}
```
7. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі Очистити та побудувати проект
`(Shift+F11)`, а потім – `Виконати проект (F6)`.
У результаті можна буде побачити кнопку при натисканні якої з'являється меню (рис. 1). Елементи меню кнопки відображаються 
своїм текстом та позначенням швидких клавіш, і при активації елемента меню спрацьовує його обробник подій.

## Робочий результат

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.geometry.Pos;
import javafx.geometry.Side;
import javafx.scene.Cursor;
import javafx.scene.Group;
import javafx.scene.control.ContentDisplay;
import javafx.scene.control.MenuButton;
import javafx.scene.control.MenuItem;
import javafx.scene.control.Tooltip;
import javafx.scene.effect.BlendMode;
import javafx.scene.effect.DropShadow;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.input.KeyCombination;
import javafx.scene.paint.Color;
import javafx.scene.text.TextAlignment;
import javafx.stage.Stage;
import javafx.scene.Scene;

import java.io.IOException;

public class MenuButtonApplication extends Application {
    private final String MenuItemFontStyle = "-fx-font:bold italic 12pt Times;";

    @Override
    public void start(Stage stage) throws IOException {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);

        stage.setScene(scene);
        stage.setTitle("Тестування GUI-компонентів: MenuButton");

        MenuButton btn = createMenuBtn();
        btn.getItems().addAll(createMenuItemCut(), createMenuItemCopy(), createMenuItemPaste());

        root.getChildren().add(btn);
        stage.show();
    }

    public static void main(String[] args) {
        launch();
    }

    private MenuButton createMenuBtn() {
        MenuButton _btn = new MenuButton("Правка");
        _btn.setLayoutX(20);
        _btn.setLayoutY(20);
        _btn.setBlendMode(BlendMode.HARD_LIGHT);
        _btn.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect=new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);

        _btn.setEffect(effect);
        _btn.setPrefSize(200,80);
        _btn.setTooltip(new Tooltip("Це кнопка контекстного меню"));

        Image img;
        ImageView imv;

        try {
            img = new Image("image.jpeg");
            imv = new ImageView(img);
            imv.setFitHeight(50);
            imv.setFitWidth(50);
            _btn.setGraphic(imv);
        } catch (Exception e) {
            e.printStackTrace();
        }

        _btn.setStyle("-fx-font: bold italic 14pt Georgia;");
        _btn.setAlignment(Pos.CENTER);
        _btn.setContentDisplay(ContentDisplay.LEFT);
        _btn.setTextAlignment(TextAlignment.CENTER);
        _btn.setGraphicTextGap(10);
        _btn.setWrapText(true);
        _btn.setPopupSide(Side.RIGHT);

        return _btn;
    }

    private MenuItem createMenuItemCut() {
        MenuItem _menuItemCut = new MenuItem("Вирізати");
        _menuItemCut.setStyle(MenuItemFontStyle);
        _menuItemCut.setAccelerator(KeyCombination.keyCombination("Ctrl+U"));
        _menuItemCut.setOnAction(e -> System.out.println("Вирізаю"));
        return _menuItemCut;
    }

    private MenuItem createMenuItemCopy() {
        MenuItem _menuItemCopy = new MenuItem("Копіювати");
        _menuItemCopy.setStyle(MenuItemFontStyle);
        _menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+O"));
        _menuItemCopy.setOnAction(e1 -> System.out.println("Копіюю"));
        return _menuItemCopy;
    }

    private MenuItem createMenuItemPaste() {
        MenuItem _menuItemPaste = new MenuItem("Вставити");
        _menuItemPaste.setStyle(MenuItemFontStyle);
        _menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        _menuItemPaste.setOnAction(e2 -> System.out.println("Вставляю"));
        return _menuItemPaste;
    }

}
```
