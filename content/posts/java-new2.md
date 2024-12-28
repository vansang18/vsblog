---
title: "Các tính chất của ngôn ngữ Java"
date: 2024-12-26
author: "Nguyễn Văn Sang"
tags: ["Java", "Lập trình", "Người mới bắt đầu"]
categories: ["Java", "Hướng dẫn"]
description: "Các đặc điểm của ngôn ngữ Java"
---

# Tính Đóng Gói, Kế Thừa, Trừu Tượng, và Đa Hình trong Lập Trình Hướng Đối Tượng

Lập trình hướng đối tượng (OOP - Object-Oriented Programming) là một mô hình lập trình phổ biến với bốn nguyên lý cơ bản: **Tính đóng gói**, **Kế thừa**, **Trừu tượng**, và **Đa hình**. Các nguyên lý này giúp tổ chức mã nguồn một cách logic, dễ bảo trì và tái sử dụng.

---

## 1. Tính Đóng Gói (Encapsulation)
### Định nghĩa
Tính đóng gói là khả năng che giấu dữ liệu và cung cấp quyền truy cập thông qua các phương thức (methods). Nó bảo vệ dữ liệu bên trong đối tượng khỏi sự truy cập trực tiếp từ bên ngoài.

### Đặc điểm chính
- Sử dụng **các thuộc tính (fields)** để lưu trữ dữ liệu.
- Quyền truy cập dữ liệu được kiểm soát qua **getter** và **setter**.
- Sử dụng các từ khóa như `private`, `protected` để hạn chế truy cập.

### Ví dụ
```java
public class Person {
    private String name;
    private int age;

    // Getter và Setter
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        } else {
            System.out.println("Tuổi phải lớn hơn 0.");
        }
    }
}
```

---

## 2. Tính Kế Thừa (Inheritance)
### Định nghĩa
Tính kế thừa cho phép một lớp (class) con sử dụng lại các thuộc tính và phương thức của một lớp cha. Điều này giúp giảm thiểu sự lặp lại mã và hỗ trợ mở rộng chức năng dễ dàng.

### Đặc điểm chính
- Kế thừa sử dụng từ khóa `extends` trong Java.
- Lớp con có thể **ghi đè (override)** các phương thức của lớp cha.
- Kế thừa hỗ trợ **tái sử dụng mã nguồn**.

### Ví dụ
```java
class Animal {
    public void eat() {
        System.out.println("Động vật đang ăn.");
    }
}

class Dog extends Animal {
    @Override
    public void eat() {
        System.out.println("Chó đang ăn xương.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // Output: Chó đang ăn xương.
    }
}
```

---

## 3. Tính Trừu Tượng (Abstraction)
### Định nghĩa
Tính trừu tượng là khả năng ẩn đi các chi tiết cài đặt và chỉ hiển thị các chức năng cần thiết. Điều này được thực hiện thông qua **lớp trừu tượng (abstract class)** và **giao diện (interface)**.

### Đặc điểm chính
- Lớp trừu tượng sử dụng từ khóa `abstract`.
- Phương thức trừu tượng không có phần thân (body), được lớp con triển khai.
- Giao diện (interface) chứa các phương thức mà các lớp phải tuân thủ.

### Ví dụ
#### Lớp trừu tượng
```java
abstract class Shape {
    abstract void draw(); // Phương thức trừu tượng
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Vẽ hình tròn.");
    }
}

class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Vẽ hình chữ nhật.");
    }
}
```

#### Giao diện
```java
interface Animal {
    void sound();
}

class Cat implements Animal {
    @Override
    public void sound() {
        System.out.println("Mèo kêu meo meo.");
    }
}
```

---

## 4. Tính Đa Hình (Polymorphism)
### Định nghĩa
Tính đa hình cho phép một đối tượng thực hiện các hành vi khác nhau tùy thuộc vào ngữ cảnh. Nó có hai dạng chính:
- **Đa hình tại thời điểm biên dịch (Compile-time polymorphism)**: Thường được thực hiện qua **nạp chồng phương thức (method overloading)**.
- **Đa hình tại thời điểm chạy (Runtime polymorphism)**: Thường được thực hiện qua **ghi đè phương thức (method overriding)**.

### Ví dụ
#### Nạp chồng phương thức
```java
class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}
```

#### Ghi đè phương thức
```java
class Animal {
    public void sound() {
        System.out.println("Động vật tạo ra âm thanh.");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Chó sủa gâu gâu.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound();  // Output: Chó sủa gâu gâu.
    }
}
```

---

## Kết Luận
Bốn nguyên lý OOP - **Tính đóng gói**, **Kế thừa**, **Trừu tượng**, và **Đa hình** - là nền tảng quan trọng trong lập trình hướng đối tượng. Hiểu và áp dụng tốt các nguyên lý này sẽ giúp bạn thiết kế hệ thống phần mềm linh hoạt, dễ bảo trì và mở rộng.
