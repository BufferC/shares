# JavaFaker

## 背景

Java的单元测试经常需要构造各种测试数据，其中一项就是构造测试的字符串。

如果手动创建非常麻烦，也有一些框架支持创建指定长度的随机字符串，但是并不是我们想要的效果，我们想要的是人名、地名等。那么有一个库叫java-fake可以实现这个功能。

## 一、官网

```
https://github.com/DiUS/java-faker
```

## 二、maven依赖

我们Java是有可以生成仿真数据的框架的，这里我安利一个Javafaker的框架，你只需要在项目中引入：

```xml
<dependency>
    <groupId>com.github.javafaker</groupId>
    <artifactId>javafaker</artifactId>
    <version>1.0.0</version>
</dependency>
```

## 三、包含的领域

在包：com.github.javafaker 下面有包含的领域
金融 - faker.finance()
书籍 - faker.book()
商务 - faker.business()
地址 - faker.address()
姓名 - faker.name()
等等...

## 四、编码

默认是英文编码，如果想使用中文可以使用:

```java
Faker faker = new Faker(new Locale("zh-CN"));
```



## 五、实例

忘记说了它主要的使用场景就是为了制造仿真测试数据，而并不是用来造假。

然后演示一下它的用法，先定义一个Java Bean :

/**

* User info.

*

* @author felord.cn

* @since 10 :50

*/

@Data

public class UserInfo {undefined

/**

* 真实姓名

*/

private String realName;

/**

* 手机

*/

private String cellPhone;

/**

* 大学

*/

private String universityName;

/**

* 城市

*/

private String city;

/**

* 地址

*/

private String street;

}

然后声明一个Faker对象，你可以根据需要进行本地化声明，如果是使用中国的：

Faker fakerWithCN = new Faker(Locale.CHINA);

你要是想造点美帝的数据就改成这样：

Faker fakerWithUS = new Faker(Locale.US);

这里我们使用中国来生成模拟10条仿真数据：

for (int i = 0; i < 10; i++) {undefined

UserInfo userInfo = new UserInfo();

userInfo.setRealName(fakerWithCN.name().fullName());

userInfo.setCellPhone(fakerWithCN.phoneNumber().cellPhone());

userInfo.setCity(fakerWithCN.address().city());

userInfo.setStreet(fakerWithCN.address().streetAddress());

userInfo.setUniversityName(fakerWithCN.university().name());

System.out.println("userInfo = " + userInfo);

}

我们来看下结果：

![img](https://img-blog.csdnimg.cn/img_convert/ac12cb1b703090c0bbba2cdb8cff5092.png)

随机生成一百个学生及考生分数

>
>
>```
>/**
>* 测试model 学生
>* @author szhu
>*/
>public class Student implements Comparable<Student>{
>
>/**
>* 姓名
>*/
>private String name;
>
>
>/**
>* 分数
>*/
>private double score;
>
>public Student(String name, double score) {
>this.name = name;
>this.score = score;
>}
>
>public String getName() {
>return name;
>}
>
>public void setName(String name) {
>this.name = name;
>}
>
>public double getScore() {
>return score;
>}
>
>public void setScore(double score) {
>this.score = score;
>}
>
>@Override
>public int compareTo(Student o) {
>return Double.compare(this.score, o.score);
>}
>
>@Override
>public String toString() {
>return "Student{" +
>"name='" + name + '\'' +
>", score=" + score +
>'}';
>}
>} 
>```

指定汉语

>
>
>```
>Faker FAKER = new Faker(Locale.CHINA);
>中文姓名
>FAKER.name().fullName();
>1~100之间两位小数数字
>FAKER.number().randomDouble(2, 1, 100)
>```

具体如下

>
>
>```
>import com.github.javafaker.Faker;
>
>import java.util.List;
>import java.util.Locale;
>import java.util.stream.Collectors;
>import java.util.stream.Stream;
>
>/**
>* 模型生成工厂
>*
>* @author szhu
>*/
>public class ModelFactory {
>/**
>* faker 指定汉语，默认英语
>*/
>private static Faker FAKER = new Faker(Locale.CHINA);
>
>
>/**
>* 随机生成一定数量学生
>*
>* @param number 数量
>* @return 学生
>*/
>public static List<Student> listStudentList(final int number) {
>return Stream.generate(() -> new Student(FAKER.name().fullName(), FAKER.number().randomDouble(2, 1, number))).limit(number).collect(Collectors.toList());
>}
>
>
>/**
>* main函数
>*/
>public static void main(String[] args) throws Exception {
>listStudentList(100).forEach(System.out::println);
>}
>
>} 
>```
