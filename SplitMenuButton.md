# SplitMenuButton

Компонент `SplitMenuButton` представлений класом `javafx.scene.control.SplitMenuButton`, екземпляр якого може бути
створений за допомогою класу-фабрики `SplitMenuButtonBuilder` або за допомогою одного з конструкторів:

- `SplitMenuButton btn = New SplitMenuButton();`
- `SplitMenuButton btn = New SplitMenuButton(MenuItem... items);`

Клас `SplitMenuButton` представляє кнопку, розділену на дві частини, одна з яких відіграє роль звичайної кнопки, а при
натисканні на іншу з’являється меню, і має такі властивості:

- успадковані від `класу javafx.scene.Node` властивості:
    * blendMode
    * boundsInLocal
    * boundsInParent
    * cacheHint
    * cache
    * cli
    * cursor
    * depthTest
    * disabled
    * disable
    * effect
    * eventDispatcher
    * focuse
    * focusTraversable
    * hover
    * id
    * inputMethodRequests
    * layoutBound
    * layoutX
    * layoutY
    * managed
    * mouseTransparent
    * onDragDetecte
    * onDragDone
    * onDragDropped
    * onDragEntered
    * onDragExite
    * onDragOver
    * onInputMethodTextChanged
    * onKeyPresse
    * onKeyReleased
    * onKeyTyped
    * onMouseClicked
    * onMouseDragge
    * onMouseEntered
    * onMouseExited
    * onMouseMoved
    * onMousePresse
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
- успадкована від класу `javafx.scene.Parent` властивість `needsLayout`; ‒ успадковані від
  класу `javafx.scene.control.Control` властивості:
    * contextMenu
    * height
    * maxHeight
    * maxWidth
    * minHeight
    * minWidt
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
    * textOverru
    * text
    * underline
    * wrapText
- успадковані від класу `javafx.scene.control.ButtonBase` властивості `armed` та `onAction`
- успадковані від класу `javafx.scene.control.MenuButton` властивості `popupSide` та `showing`

Компонент `SplitMenuButton` за своєю функціональністю аналогічний до компоненту `MenuButton`. Відмінність полягає в
тому, що компонент `SplitMenuButton` складається з двох частин, одна з яких може працювати як звичайна кнопка і для неї
можна визначити окремий обробник подій `onAction`, а інша частина виконує основну функцію компонента `MenuButton`, тобто
відкриває контекстне меню. Меню компонента `SplitMenuButton` складається з набору компонентів, представлених
класом `javafx.scene.control.MenuItem`, поповнювати який можна за допомогою методу `getItems().addAll()`
класу `javafx.scene.control.MenuButton`.

Екземпляр класу `MenuItem` можна створити за допомогою класу-фабрики `MenuItemBuilder` або за допомогою одного з
конструкторів:

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
тексту, обробник подій , батьківське контекстне меню, стиль, текст та видимість.

Клас `MenuItem` має підкласи `CheckMenuItem`, `CustomMenuItem`,`Menu` і `RadioMenuItem`, тому в меню компонента
`SplitMenuButton`можна додавати не тільки елементи `MenuItem`, але й перемикачі`CheckMenuItem` і `RadioMenuItem`, а
також роздільники `SeparatorMenuItem`, представлені класом `SeparatorMenuItem`, представлені класом `SeparatorMenuItem`,
що розширює клас `CustomMenuItem`, та вкладені меню `Menu`.

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить кнопку SplitMenuButton, в меню Файл оберіть Створити проект | Java with Ant | JavaFX | JavaFX Application,
   натисніть кнопку Далі, введіть ім’я проекту JavaFXApplicationSplitMenuButton, залишивши прапорець Create Main Class,
   та натисніть кнопку Готово.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу JavaFXApplicationSplitMenuButton, який розширює
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

public class JavaFXApplicationSplitMenuButton extends Application {
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
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI- компонентів: SplitMenuButton”` та зробіть
   видимим об’єкт `Stage`:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationSplitMenuButton extends Application {

    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: SplitMenuButton");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Створіть екземпляр кнопки `SplitMenuButton`.

Кнопку помістіть у лівий верхній кут основного вікна JavaFX-додатка, і для неї визначте такі властивості, як текст,
режим накладання, курсор миші, візуальний ефект, переважні розміри, підказка, значок, стиль, вирівнювання, перенесення
рядків, розташування меню щодо кнопки та обробник подій. Створіть елементи меню Вирізати, Копіювати та Вставити. Для них
встановіть текст, стиль, швидкі клавіші та обробники подій:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationSplitMenuButton extends Application {

    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: SplitMenuButton");

        // New code
        SplitMenuButton btn = new SplitMenuButton();
        btn.setText("Правка");
        btn.setLayoutX(20);
        btn.setLayoutY(20);
        btn.setBlendMode(BlendMode.HARD_LIGHT);
        btn.setCursor(Cursor.CLOSED_HAND);
        
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        btn.setEffect(effect);
        
        btn.setPrefSize(200, 80);
        btn.setTooltip(new Tooltip(" Кнопка редагування")); 
        
        Image im = new Image(this.getClass().getResource(" image.png").toString()); 
        ImageView imv = new ImageView(im); imv.setFitHeight(50);
        imv.setFitWidth(50);
        btn.setGraphic(imv);
        
        btn.setStyle("-fx-font: bold italic 14pt Georgia;"); 
        btn.setAlignment(Pos.CENTER); 
        btn.setContentDisplay(ContentDisplay.LEFT); 
        btn.setTextAlignment(TextAlignment.CENTER);
        
        btn.setGraphicTextGap(5);
        btn.setWrapText(true);
        btn.setPopupSide(Side.BOTTOM);

        btn.setOnAction(e -> System.out.println("Обробка натиснення кнопки"));
        
        MenuItem menuItemCut = new MenuItem(" Вирізати"); 
        menuItemCut.setStyle("-fx-text-fill:green; -fx-font:bold italic 12 pt Times;"); 
        menuItemCut.setAccelerator(KeyCombination.keyCombination("Ctrl+U")); 
        menuItemCut.setOnAction(e1 -> System.out.println("Вирізаю")); 
        
        MenuItem menuItemCopy = new MenuItem("Копіювати"); 
        menuItemCopy.setStyle("-fx-text-fill:green; -fx-font:bold italic 12 pt Times;"); 
        menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+O"));
        menuItemCopy.setOnAction(e2 -> System.out.println("Копіюю"));
        
        MenuItem menuItemPaste = new MenuItem("Вставити"); 
        menuItemPaste.setStyle("-fx-text-fill:green; -fx-font:bold italic 12 pt Times;");
        menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        menuItemPaste.setOnAction(e3 -> System.out.println("Вставляю"));

        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

5. Скачайте з інтернету рисунок із зображенням смайлика та збережіть його як image.png у папці, де розміщений файл `JavaFXApplicationSplitMenuButton.java`.
6. У меню кнопки додайте елементи меню, додайте кнопку в кореневий вузол графа сцени:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationSplitMenuButton extends Application {

    @Override
    public void start(Stage primaryStage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: SplitMenuButton");

        SplitMenuButton btn = new SplitMenuButton();
        btn.setText("Правка");
        btn.setLayoutX(20);
        btn.setLayoutY(20);
        btn.setBlendMode(BlendMode.HARD_LIGHT);
        btn.setCursor(Cursor.CLOSED_HAND);
        
        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        btn.setEffect(effect);
        
        btn.setPrefSize(200, 80);
        btn.setTooltip(new Tooltip(" Кнопка редагування")); 
        
        Image im = new Image(this.getClass().getResource(" image.png").toString()); 
        ImageView imv = new ImageView(im); imv.setFitHeight(50);
        imv.setFitWidth(50);
        btn.setGraphic(imv);
        
        btn.setStyle("-fx-font: bold italic 14pt Georgia;"); 
        btn.setAlignment(Pos.CENTER); 
        btn.setContentDisplay(ContentDisplay.LEFT); 
        btn.setTextAlignment(TextAlignment.CENTER);
        
        btn.setGraphicTextGap(5);
        btn.setWrapText(true);
        btn.setPopupSide(Side.BOTTOM);

        btn.setOnAction(e -> System.out.println("Обробка натиснення кнопки"));
        
        MenuItem menuItemCut = new MenuItem(" Вирізати"); 
        menuItemCut.setStyle("-fx-text-fill:green; -fx-font:bold italic 12 pt Times;"); 
        menuItemCut.setAccelerator(KeyCombination.keyCombination("Ctrl+U")); 
        menuItemCut.setOnAction(e1 -> System.out.println("Вирізаю")); 
        
        MenuItem menuItemCopy = new MenuItem("Копіювати"); 
        menuItemCopy.setStyle("-fx-text-fill:green; -fx-font:bold italic 12 pt Times;"); 
        menuItemCopy.setAccelerator(KeyCombination.keyCombination("Ctrl+O"));
        menuItemCopy.setOnAction(e2 -> System.out.println("Копіюю"));
        
        MenuItem menuItemPaste = new MenuItem("Вставити"); 
        menuItemPaste.setStyle("-fx-text-fill:green; -fx-font:bold italic 12 pt Times;");
        menuItemPaste.setAccelerator(KeyCombination.keyCombination("Ctrl+P"));
        menuItemPaste.setOnAction(e3 -> System.out.println("Вставляю"));

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

## Робочий результат

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.geometry.Pos;
import javafx.geometry.Side;
import javafx.scene.Cursor;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.effect.BlendMode;
import javafx.scene.effect.DropShadow;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.input.KeyCombination;
import javafx.scene.paint.Color;
import javafx.scene.text.TextAlignment;
import javafx.stage.Stage;

public class SplitMenuButtonApplication extends Application {

    private final String MenuItemFontStyle = "-fx-text-fill:green; -fx-font:bold italic 12pt Times;";
    
    @Override
    public void start(Stage stage) {
        Group root = new Group();
        Scene scene = new Scene(root, 400, 400, Color.LIGHTGREEN);

        stage.setScene(scene);
        stage.setTitle("Тестування GUI-компонентів: SplitMenuButton");

        SplitMenuButton btn = createSplitMenuBtn();
        btn.getItems().addAll(createMenuItemCut(), createMenuItemCopy(), createMenuItemPaste());

        root.getChildren().add(btn);
        stage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }

    private SplitMenuButton createSplitMenuBtn() {
        SplitMenuButton _btn = new SplitMenuButton();
        _btn.setText("Правка");
        _btn.setLayoutX(20);
        _btn.setLayoutY(20);
        _btn.setBlendMode(BlendMode.HARD_LIGHT);
        _btn.setCursor(Cursor.CLOSED_HAND);

        DropShadow effect = new DropShadow();
        effect.setOffsetX(8);
        effect.setOffsetY(8);
        _btn.setEffect(effect);

        _btn.setPrefSize(200, 80);
        _btn.setTooltip(new Tooltip(" Кнопка редагування"));

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
        _btn.setGraphicTextGap(5);
        _btn.setWrapText(true);
        _btn.setPopupSide(Side.BOTTOM);
        _btn.setOnAction(e -> System.out.println("Обробка натиснення кнопки"));
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
