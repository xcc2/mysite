# 面向对象知识整理

> 构造方法


``` java
// 构造方法调用其他构造方法
class Person {
    private String name;
    private int age;
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public Person(String name) {
        this(name, 18); // 调用另一个构造方法Person(String, int)
    }
    public Person() {
        this("Unnamed"); // 调用另一个构造方法Person(String)
    }
}

```


``` java
// 一个class多个构造方法
class Person {
    private String name;
    private int age;
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public Person(String name) {
        this.name = name;
        this.age = 12;
    }
    public Person() {
    }
}
```
> 如果调用new Person("Xiao Ming", 20);，会自动匹配到构造方法public Person(String, int)。 <br/>

如果调用new Person("Xiao Ming");，会自动匹配到构造方法public Person(String)。<br/>

如果调用new Person();，会自动匹配到构造方法public Person()。<br/>



> 继承

``` java
class Person {   //student的爸爸，别名为 超类（super class），父类（parent class），基类（base class）
    private String name;
    private int age;  
    public String getName() {...}
    public void setName(String name) {...} 
    public int getAge() {...}
    public void setAge(int age) {...}
}
class Student extends Person {  //使用extends让student继承来自person，person的子类（subclass），扩展类（extended class）
    private int score;
    public String getName(){
      return this.name;     //会报错，因为name是private属性，如果需要在这里使用，需要将属性修改为protected 
    }
    public int getScore() { … }
    public void setScore(int score) { … }
}

```


  > super必须显示调用的情况，当超类下没有不带参数的构造方法，此时子类自动调用超类构造方法时报错，需要显示调用super(**args)




> 多态

复写
调用super


** final关键字 **
  1. class内的方法定义，不允许被复写
  2. class的修饰，不允许被继承
  3. 字段的修饰，初始化后不允许修改