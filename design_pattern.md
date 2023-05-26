### Factory

当client不知道要创建哪个具体类的实例，或者不想在client代码中指明要具体 创建的实例时，用工厂方法。

**客户端代码**

```java
public class Client {
    public static void main(String[] args) {
        Phone huawei = new HuaweiFactory().createPhone();
        huawei.call();
        huawei.message();
        Phone iphone = new IphoneFactory().createPhone();
        iphone.call();
        iphone.message();
    }
}
```
**手机接口，用于组织手机**

```java
public interface Phone {
    public void call();
    public void message();
}
```

```java
public class Huawei implements Phone{
    private final String name = "Huawei";

    public Huawei() {
        System.out.println("Huawei is created");
    }
    
    @Override
    public void call() {
        System.out.println("Calling from " + name);
    }
    @Override
    public void message() {
        System.out.println("Messaging from " + name);
    }
}
```

```java
public class Iphone implements Phone{
    private final String name = "Iphone";

    public Iphone() {
        System.out.println("Iphone is created");
    }

    @Override
    public void call() {
        System.out.println("Calling from " + name);
    }
    @Override
    public void message() {
        System.out.println("Messaging from " + name);
    }
}
```
**工厂接口，用于组织工厂**

```java
public interface Factory {
    public Phone createPhone();
}
```

```java
public class IphoneFactory implements Factory{
    @Override
    public Phone createPhone() {
        return new Iphone();
    }
}
```

```java
public class HuaweiFactory implements Factory{
    @Override
    public Phone createPhone() {
        return new Huawei();
    }
}
```

如果不用工厂设计模式，客户端代码为

```java
public class Client {
    public static void main(String[] args) {
        Phone huawei = new Huawei();
        huawei.call();
        huawei.message();
        Phone iphone = new Iphone();
        iphone.call();
        iphone.message();
    }
}
```

这样的话客户端需要知道所需类的构造函数，这样的话客户端与实际的源代码关联就比较紧密，耦合性比较大

比如说如果又多了pad接口，并且有两个实现类：Ipad，HuaweiPad。利用工厂设计模式时只需要在Factory接口中加上createPad方法，并且再在IphoneFactory和HuaweiFactory中override就行了，客户端行为不变。如果不用的话客户端还要专门调用pad的构造方法，比较麻烦。

### Adaptor

  Adaptor设计模式是一种结构型设计模式，用于将一个类的接口转换成客户端所期望的另一个接口。这种模式可以让原本由于接口不兼容而无法一起工作的类能够协同工作。

**原方法**

```java
public class LegacyRectangle {
    public void display(int x1, int y1, int w, int h) {
        System.out.println("标准矩形");
    }
}
```
**用户期望接口**

```java
public interface Shape {
    void display(int x1, int y1, int x2, int y2);
}
```

**“转接头”**

```java
public class Rectangle implements Shape{
    @Override
    public void display(int x1, int y1, int x2, int y2) {
        new LegacyRectangle().display(x1, y1, x2 - x1, y2 - y1);
    }
}
```

就是起到一个转接头的作用，主要是处理用户端参数输入和已有方法参数列表不同的方法

### Decorator

```java
// 定义组件接口
public interface Shape {
    void draw();
}

// 定义组件实现类
public class Rectangle implements Shape {
    @Override
    public void draw() {
        System.out.println("画一个矩形");
    }
}

// 定义装饰器抽象类
public abstract class ShapeDecorator implements Shape {
    protected Shape decoratedShape;

    public ShapeDecorator(Shape decoratedShape) {
        this.decoratedShape = decoratedShape;
    }

    public void draw() {
        decoratedShape.draw();
    }
}

// 定义具体装饰器类
public class RedShapeDecorator extends ShapeDecorator {
    public RedShapeDecorator(Shape decoratedShape) {
        super(decoratedShape);
    }

    @Override
    public void draw() {
        decoratedShape.draw();
        setRedBorder(decoratedShape);
    }

    private void setRedBorder(Shape decoratedShape) {
        System.out.println("添加红色边框");
    }
}
```

**注意：**

1. 基本装饰类是一个抽象类
2. 其中的属性是protected（为了它的子类能够直接调用该属性的方法）

```java
public class Client {
    public static void main(String[] args) {
        // 使用普通的
        Shape s1 = new Rectangle();
        // 使用装饰的
        Shape s2 = new RedShapeDecorator(new Rectangle);
    }
}
```

### Strategy

感觉就是用接口管理函数的调用，然后再用委托来调用函数

```java
// 策略接口
public interface SortStrategy {
    void sort();
}

// 具体策略
public class QiuckSort implements SortStrategy{
    @Override
    public void sort() {
        System.out.println("快速排序");
    }
}

public class MergeSort implements SortStrategy{
    @Override
    public void sort() {
        System.out.println("归并排序");
    }
}

// 使用算法的类
public class Student {
    public void sort(SortStrategy s) {
        s.sort;
    }
}
```

### Template Method

