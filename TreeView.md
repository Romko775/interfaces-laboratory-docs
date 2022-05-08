# TreeView

Компонент `TreeView` представлений класом `javafx.scene.control.TreeView<T>`, екземпляр якого може бути створений за
допомогою класу-фабрики `TreeViewBuilder` або за допомогою одного з конструкторів:

- `TreeView<String> treeView = new TreeView<String>();`
- `TreeView<String> treeView = new TreeView<String>(TreeItem<String> root);`

Клас `TreeView<T>` представляє відображення дерева
елементів, що прокручується, і має наступні властивості:
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
  * onKeyPressed,
  * onKeyReleased
  * onKeyTyped
  * onMouseClicked
  * onMouseDragged
  * onMouseEntered
  * onMouseExited
  * onMouseMoved
  * onMousePressed,
  * onMouseReleased
  * opacity
  * parent
  * pickOnBounds
  * pressed
  * rotate,
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
- успадковану від класу `javafx.scene.Parent` властивість needsLayout;
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
  * editingItem,
  * focusModel
  * onEditCancel
  * onEditCommit
  * onEditStart
  * root
  * selectionModel
  * showRoot

Відображення дерева елементів `TreeView` створюється на основі кореневого вузла, який визначається властивістю root та
представлений класом `javafx.scene.control.TreeItem<T>`. Примірники класу `TreeItem<T>` можуть бути створені за
допомогою класу-фабрики `TreeItemBuilder` або за допомогою одного з конструкторів:

- `TreeItem<String> treeItem=new TreeItem<String>();`
- `TreeItem<String> treeItem=new TreeItem<String>("[текст]");`
- `TreeItem<String> treeItem = new TreeItem<String>("[текст]", [вузол значка]);`

Клас `TreeItem` представляє вузол дерева і має властивості `expanded`, `graphic`, `leaf`, `parent` і `value`. Якщо
вузол `TreeItem` не є листом дерева, метод `getChildren().addAll()` класу `TreeItem<T>` дозволяє додати у вузол
`TreeItem` набір дочірніх вузлів.

Властивість `cellFactory` класу `TreeView<T>` дозволяє заповнити дерево `TreeView` компонентами користувача
`javafx.scene.control.TreeCell<T>`.

Примірник класу `TreeCell<T>` можна створити за допомогою класу-фабрики `TreeCellBuilder` або за допомогою конструктора:
- `TreeCell<String> cell = new TreeCell<String>();`

Клас `TreeCell<T>` представляє елемент дерева `TreeView<T>` і має такі властивості:
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
- успадковану від класу `javafx.scene.Parent` властивість `needsLayout`;
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
-успадковані від класу `javafx.scene.control.Labeled` властивості: 
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
- успадковану від класу `javafx.scene.control.IndexedCell<T>` властивість `index`;
- власні властивості `disclosureNode`, `treeItem` і `treeView`.

Властивість `selectionModel` класу `TreeView<T>` дає можливість визначити множинність вибору та обробку події вибору
вузла дерева.

Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить дерево `TreeView`, в меню `Файл` оберіть `Створити проект` | `Java with Ant` | `JavaFX` | `JavaFX Application`, натисніть
   кнопку `Далі`, введіть ім’я проекту `JavaFXApplicationTreeView`, залишивши прапорець `Create Main Class`, та натисніть
   кнопку `Готово`. У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationTreeView`,
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

public class JavaFXApplicationTreeView extends Application {
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
2. У методі start() вилучіть весь код.
3. Створіть кореневий вузол графа сцени та на його основі екземпляр сцени, який встановлюється для об’єкта `Stage`.
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI-компонентів: TreeView”` та зробіть видимим об’єкт
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

public class JavaFXApplicationTreeView extends Application {
   @Override
   public void start(Stage primaryStage) {
      Group root = new Group();
      Scene scene = new Scene(root, 400, 300, Color.BEIGE);
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: TreeView");
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```
4. Створіть значки для вузлів дерева:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTreeView extends Application {
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
      
      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: TreeView");
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```
5. Створіть вузли `TreeItem` дерева `TreeView`:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTreeView extends Application {
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

      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: TreeView");
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```

6. На основі кореневого вузла створіть дерево `TreeView`. Дерево помістіть у лівий верхній кут основного вікна
   JavaFX-додатку, і для нього визначте такі властивості, як курсор миші, стиль, переважні розміри та обробник вибору
   вузла дерева:

```java
package javafxapplicationbutton;

import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class JavaFXApplicationTreeView extends Application {
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

      primaryStage.setScene(scene);
      primaryStage.setTitle("Тестування GUI-компонентів: TreeView");
      primaryStage.show();
   }

   public static void main(String[] args) {
      launch(args);
   }
}
```
7. Скачайте з інтернету піктограми, назвавши як `rootimg.png`,
   `packageimg.png`, `packagesimg.png` та `sourceimg.png`, і збережіть їх у
   папці, де розміщений файл `JavaFXApplicationTreeView.java`.
8. Створене дерево додайте в кореневий вузол графа сцени: `root.getChildren().add(treeView)`;
9. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на піктограмі `Очистити та побудувати проект
   (Shift+F11)`, а потім – `Виконати проект (F6)`.
