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
