# TableView

Компонент TableView представлений класом `javafx.scene.control.TableView<S>`, екземпляр якого може бути створений за
допомогою класу-фабрики `TableViewBuilder` або за допомогою одного з конструкторів:
`TableView<S> table = new TableView<S>(); TableView<S> table = new TableView<S>(ObservableList<S> list);`

Набір даних `javafx.collections.ObservableList` для рядків таблиці TableView може бути створений за допомогою статичного
методу `observableArrayList()` класу `javafx.collections.FXCollections`. Клас `TableView<S>` представляє таблицю елементів і
має такі властивості:
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
  * layoutBounds,
  * layoutX
  * layoutY
  * managed
  * mouseTransparent
  * onDragDetected
  * onDragDone
  * onDragDropped
  * onDragEntered
  * onDragExited,
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
  * onMousePressed,
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
  * columnResizePolicy
  * editable
  * editingCell
  * focusModel
  * items
  * placeholder
  * rowFactory
  * selectionModel
  * tableMenuButtonVisible

Таблиця `TableView<S>` складається з набору стовпців `javafx.collections.ObservableList <TableColumn<S,?>>`, який можна
поповнити за допомогою методу `getColumns().addAll()`
класу `javafx.scene.control.TableView<S>`. 

За допомогою властивості `items` класу `TableView<S>` набір стовпців
таблиці `ObservableList<TableColumn<S,?>>` пов'язується з набором даних для рядків таблиці `ObservableList<S>`.

Властивість `tableMenuButtonVisible` забезпечує опцію контекстного меню, що дозволяє регулювати відображення стовпців
таблиці.

Властивість `placeholder` дає можливість встановити вузол `Node`, що відображається у разі відсутності даних таблиці.

Властивість `rowFactory` дозволяє наповнити таблицю компонентами користувача `javafx.scene.control.TableRow<S>`. Клас
`TableRow<S>` розширює клас `javafx.scene.control.IndexedCell<S>` і представляє рядки таблиці `TableView<S>`.

Властивість `selectionModel` дає можливість визначити виділені елементи таблиці та встановити множинність вибору.

Стовпці таблиці `TableView` представляє клас
`javafx.scene.control.TableColumn<S,T>`, екземпляр якого може бути
створений за допомогою класу-фабрики `TableColumnBuilder` або за
допомогою конструкторів:
- `TableColumn column = New TableColumn();`
- `TableColumn column = new TableColumn("[текст]");`

Клас `TableColumn<S,T>` має властивості: 
- cellFactory,
- cellValueFactory
- comparator
- contextMenu
- editable
- maxWidth,
- minWidth
- onEditCancel
- onEditCommit
- onEditStart
- parentColumn,
- prefWidth
- resizable
- sortable
- sortType
- tableView
- text
- visible
- width

Властивість `cellFactory` класу `TableColumn` дає можливість наповнити стовпець користувальницькими компонентами,
представленими класом `javafx.scene.control.TableCell<S,T>`, який розширює клас `javafx.scene.control.IndexedCell<T>`.

Властивості `maxWidth`, `minWidth`, `prefWidth` та `width`забезпечують визначення ширини стовпця.

Властивості `sortable`,`sortType` та `comparator` регулюють сортування даних стовпця.

Властивість `text` дозволяє визначити шапку стовпця, а властивість `resizable` – можливість зміни ширини стовпця користувачем.

За допомогою властивості `cellValueFactory` можна заповнити даними осередку стовпця таблиці. Для цього можна використати
клас `javafx.scene.control.cell.PropertyValueFactory<S,T>`, що реалізує
інтерфейси `Callback<TableColumn.CellDataFeatures<S,T>` і `ObservableValue<T>>`. Клас `PropertyValueFactory<S,T>` має
методи public `ObservableValue<T> call(TableColumn.CellDataFeatures<S,T> param)`
та `public final java.lang.String getProperty()`. Екземпляр класу `PropertyValueFactory<S,T>` може бути створений за
допомогою класу-фабрики `PropertyValueFactoryBuilder` або за допомогою конструктора:

- `PropertyValueFactory<S, T> pvf = new PropertyValueFactory<S, T>([java.lang.String property]);`

Стовпець `TableColumn<S,T>` може містити набір `javafx.collections.ObservableList<TableColumn<S,?>>` вкладених стовпців,
поповнити який можна за допомогою методу
`getColumns().addAll()` класу `javafx.scene.control.TableColumn<S,T>`. Для створення стовпця з редагованими елементами
необхідно створити клас, що розширює клас `TableCell<S,T>`, в якому перевизначаються методи `startEdit()`
, `cancelEdit()`, `commitEdit()` і `updateItem()` з використанням текстових полів, що редагуються, і наповнити стовпець
його екземплярами використовуючи властивість `cellFactory`.

Властивості `onEditCancel`, `onEditCommit` і `onEditStart` забезпечать обробку подій редагування. Властивість `editable`
класів `TableColumn<S,T>` і `TableView<S>` визначає редагування стовпця та таблиці.

## Завдання

1. Відкрийте середовище NetBeans з підтримкою платформи JavaFX 2.0. Для створення JavaFX-додатку з GUI-інтерфейсом, що
   містить таблицю `TableView`, в меню `Файл` оберіть `Створити проект`
   | `Java with Ant` | `JavaFX` | `JavaFX Application`, натисніть кнопку `Далі`, введіть ім’я
   проекту `JavaFXApplicationTableView`, залишивши прапорець `Create Main Class`, та натисніть кнопку `Готово`.

У вікні редактора середовища NetBeans з’явиться код згенерованого класу `JavaFXApplicationTableView`, який розширює
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

2. Попередньо створіть клас `Hotel`, який представляє дані
   таблиці. Для цього в меню `Файл` оберіть `Створити Файл` | `Java` | `Java
   Class`, натисніть кнопку `Далі`, введіть ім’я класу `Hotel` та натисніть
   кнопку `Готово`.

```java
public class Hotel {
    private final StringProperty name;
    private final StringProperty resort;
    private final StringProperty category;
    private final DoubleProperty rate;

    public Hotel(String name, String resort, String category, double rate) {
        this.name = new SimpleStringProperty(name);
        this.resort = new SimpleStringProperty(resort);
        this.category = new SimpleStringProperty(category);
        this.rate = new SimpleDoubleProperty(rate);
    }

    public StringProperty nameProperty() {
        return name;
    }

    public String getName() {
        return name.getValue();
    }

    public StringProperty resortProperty() {
        return resort;
    }

    public String getResort() {
        return resort.getValue();
    }

    public StringProperty categoryProperty() {
        return category;
    }

    public String getCategory() {
        return category.getValue();
    }

    public DoubleProperty rateProperty() {
        return rate;
    }

    public Double getRate() {
        return rate.getValue();
    }
}
```
   
3. У класі `JavaFXApplicationTableView` у методі start вилучіть весь код.

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
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

4. Створіть кореневий вузол графа сцени та на його основі екземпляр сцени, який встановлюється для об’єкта `Stage`.
   Установіть заголовок основного вікна JavaFX-додатку `“Тестування GUI-компонентів: TableView”` та зробіть видимим
   об’єкт `Stage`:

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
        Scene scene = new Scene(root, 600, 400, Color.BEIGE);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: TableView");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```


5. Створіть заголовок `Label` таблиці. Помістіть його в лівий
   верхній кут основного вікна JavaFX-додатку і для нього встановіть
   текст, бажані розміри, стиль та вирівнювання:

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
        Scene scene = new Scene(root, 600, 400, Color.BEIGE);
        
        Label label=new Label("ТОР20 готелів Туреччини");
        label.setLayoutX(10);
        label.setLayoutY(10);
        label.setPrefSize(500, 30);

        label.setStyle("-fx-font: bold italic 16pt Georgia;-fx-text-fill:#000066;-fxbackground-color:lightgrey;");
        label.setAlignment(Pos.CENTER);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: TableView");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

6. Створіть набір даних таблиці та екземпляр таблиці `TableView`, який міститься під заголовком `Label` таблиці і для
   якого визначаються такі властивості, як контекстне меню відображення стовпців, курсор миші, підказка, стиль, краща
   ширина і множинність вибору. Створіть стовпці таблиці, які пов'язуються з властивостями класу даних `Hotel` та
   додаються до таблиці `TableView`:

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
        Scene scene = new Scene(root, 600, 400, Color.BEIGE);
        
        Label label=new Label("ТОР20 готелів Туреччини");
        label.setLayoutX(10);
        label.setLayoutY(10);
        label.setPrefSize(500, 30);

        label.setStyle("-fx-font: bold italic 16pt Georgia;-fx-text-fill:#000066;-fxbackground-color:lightgrey;");
        label.setAlignment(Pos.CENTER);

        ObservableList<Hotel> hotels = FXCollections.observableArrayList(
                new Hotel("Amara Dolce Vita", "Кемер", "HV1", 4.5),
                new Hotel("Club Boran Mare Beach", "Кемер", "HV1", 4.7),
                new Hotel("Delphin Botanik World of Paradise", "Аланія", "5*", 4.4),
                new Hotel("Kamelya World Hotel Fulya", "Сіде", "5*", 4.8),
                new Hotel("Delphin Deluxe Resort", "Алания", "5*", 4.7)
        );
        
        TableView<Hotel> table = new TableView<>();
        table.setLayoutX(10);
        table.setLayoutY(50);
        table.setTableMenuButtonVisible(true);
        table.setCursor(Cursor.TEXT);
        table.setTooltip(new Tooltip("Популярні готелі Туреччини"));
        table.setStyle("-fx-font: 12pt Arial;");
        table.setPrefWidth(500);
        table.setPrefHeight(200);
        table.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        
        TableColumn nameCol = new TableColumn("Готель");
        nameCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("name"));
        nameCol.setPrefWidth(250);
        nameCol.setResizable(false);
        nameCol.setSortable(true);
        
        TableColumn resortCol = new TableColumn("Курорт");
        resortCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("resort"));
        
        TableColumn categoryCol = new TableColumn("Категорія");
        categoryCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("category"));
        
        TableColumn rateCol = new TableColumn("Рейтинг");
        rateCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("rate"));
        
        table.setItems(hotels);
        table.getColumns().addAll(nameCol, resortCol, categoryCol, rateCol);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: TableView");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

7. Створені заголовок `Label` та таблицю `TableView` додайте до кореневого вузла графа сцени:

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
        Scene scene = new Scene(root, 600, 400, Color.BEIGE);
        
        Label label=new Label("ТОР20 готелів Туреччини");
        label.setLayoutX(10);
        label.setLayoutY(10);
        label.setPrefSize(500, 30);

        label.setStyle("-fx-font: bold italic 16pt Georgia;-fx-text-fill:#000066;-fxbackground-color:lightgrey;");
        label.setAlignment(Pos.CENTER);

        ObservableList<Hotel> hotels = FXCollections.observableArrayList(
                new Hotel("Amara Dolce Vita", "Кемер", "HV1", 4.5),
                new Hotel("Club Boran Mare Beach", "Кемер", "HV1", 4.7),
                new Hotel("Delphin Botanik World of Paradise", "Аланія", "5*", 4.4),
                new Hotel("Kamelya World Hotel Fulya", "Сіде", "5*", 4.8),
                new Hotel("Delphin Deluxe Resort", "Алания", "5*", 4.7)
        );
        
        TableView<Hotel> table = new TableView<>();
        table.setLayoutX(10);
        table.setLayoutY(50);
        table.setTableMenuButtonVisible(true);
        table.setCursor(Cursor.TEXT);
        table.setTooltip(new Tooltip("Популярні готелі Туреччини"));
        table.setStyle("-fx-font: 12pt Arial;");
        table.setPrefWidth(500);
        table.setPrefHeight(200);
        table.getSelectionModel().setSelectionMode(SelectionMode.MULTIPLE);
        
        TableColumn nameCol = new TableColumn("Готель");
        nameCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("name"));
        nameCol.setPrefWidth(250);
        nameCol.setResizable(false);
        nameCol.setSortable(true);
        
        TableColumn resortCol = new TableColumn("Курорт");
        resortCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("resort"));
        
        TableColumn categoryCol = new TableColumn("Категорія");
        categoryCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("category"));
        
        TableColumn rateCol = new TableColumn("Рейтинг");
        rateCol.setCellValueFactory(new PropertyValueFactory<Hotel, String>("rate"));
        
        table.setItems(hotels);
        table.getColumns().addAll(nameCol, resortCol, categoryCol, rateCol);

        root.getChildren().add(label);
        root.getChildren().add(table);
        
        primaryStage.setScene(scene);
        primaryStage.setTitle("Тестування GUI-компонентів: TableView");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

8. Запустіть створений JavaFX-додаток, клацнувши правою кнопкою миші на
   піктограмі `Очистити та побудувати проект (Shift+F11)`, а потім – `Виконати проект (F6)`.
