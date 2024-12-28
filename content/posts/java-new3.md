---
title: "Cấu Trúc Chương Trình Java: Giới Thiệu Về Lớp, Phương Thức, Và Cách Java Tổ Chức Mã Nguồn"
date: 2024-12-26
author: "Nguyễn Văn Sang"
tags: ["Java", "Lập trình", "Người mới bắt đầu"]
categories: ["Java", "Hướng dẫn"]
description: "Tìm hiểu cách Java tổ chức chương trình, từ lớp, phương thức đến cấu trúc mã nguồn."
---

# **Cấu trúc Chương trình Java: Giới thiệu về Lớp, Phương thức và Tổ chức Mã nguồn**

Java là một ngôn ngữ lập trình hướng đối tượng, nổi bật với cấu trúc mã nguồn rõ ràng và dễ tổ chức. Hiểu rõ cách Java tổ chức chương trình sẽ giúp bạn viết mã dễ hiểu, dễ bảo trì, và chuẩn mực hơn.

---

## **1. Cấu trúc cơ bản của một chương trình Java**

Một chương trình Java điển hình bao gồm:
1. **Gói (Package)**: Dùng để nhóm các lớp liên quan.
2. **Lớp (Class)**: Thành phần cơ bản nhất chứa các thuộc tính (fields) và phương thức (methods).
3. **Phương thức (Method)**: Các chức năng hoặc hành động mà lớp có thể thực hiện.
4. **Hàm `main`**: Điểm bắt đầu của mọi chương trình Java.

### **Ví dụ cơ bản**
```java
// 1. Khai báo gói
package com.example;

// 2. Khai báo lớp
public class HelloWorld {

    // 3. Phương thức main - Điểm bắt đầu của chương trình
    public static void main(String[] args) {
        System.out.println("Hello, World!"); // In ra màn hình
    }
}
```

---

## **2. Gói (Package)**

**Gói** được sử dụng để tổ chức các lớp và giao diện, giúp mã nguồn gọn gàng hơn.  
- Gói mặc định: Nếu không khai báo, các lớp sẽ thuộc gói mặc định.  
- Cách sử dụng:  
  ```java
  package com.example.utils;
  ```

### **Lợi ích của gói**
- Nhóm các lớp liên quan để dễ quản lý.
- Tránh xung đột tên lớp trong các dự án lớn.

---

## **3. Lớp (Class)**

**Lớp** là đơn vị cơ bản trong lập trình Java. Nó mô tả các thuộc tính (dữ liệu) và hành vi (phương thức) của đối tượng.

### **Cấu trúc một lớp**
```java
public class Person {
    // Thuộc tính (fields)
    private String name;
    private int age;

    // Constructor (Hàm khởi tạo)
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Phương thức
    public void introduce() {
        System.out.println("Tôi tên là " + name + ", " + age + " tuổi.");
    }
}
```

### **Giải thích**
- **Thuộc tính (Fields)**: Biến lưu trữ thông tin của đối tượng.
- **Constructor**: Hàm khởi tạo được gọi khi đối tượng được tạo.
- **Phương thức (Methods)**: Hành vi hoặc chức năng của đối tượng.

---

## **4. Phương thức (Method)**

**Phương thức** là các khối mã thực hiện một chức năng cụ thể.  
Chúng có thể nhận tham số và trả về giá trị.

### **Cấu trúc một phương thức**
```java
public int add(int a, int b) {
    return a + b; // Trả về tổng của a và b
}
```

### **Loại phương thức**
1. **Phương thức tĩnh (Static)**: Gọi trực tiếp từ lớp, không cần tạo đối tượng.
   ```java
   public static void greet() {
       System.out.println("Xin chào!");
   }
   ```
2. **Phương thức không tĩnh**: Gọi từ một đối tượng.
   ```java
   public void sayHello() {
       System.out.println("Hello từ đối tượng!");
   }
   ```

---

## **5. Hàm `main`**

Hàm `main` là điểm bắt đầu thực thi của mọi chương trình Java.  
Cấu trúc:
```java
public static void main(String[] args) {
    // Code sẽ được thực thi từ đây
    System.out.println("Chương trình Java của tôi!");
}
```

### **Giải thích**
- **`public`**: Cho phép JVM truy cập từ bất kỳ đâu.
- **`static`**: Không cần tạo đối tượng để gọi.
- **`void`**: Không trả về giá trị.
- **`String[] args`**: Tham số dòng lệnh (nếu có).

---

## **6. Tổ chức mã nguồn**

### **Cấu trúc thư mục**
Java thường tổ chức mã nguồn theo cấu trúc chuẩn:
```
src/
  └── main/
      ├── java/
      │   └── com/
      │       └── example/
      │           └── HelloWorld.java
      └── resources/
```

- **`src/main/java`**: Chứa mã nguồn Java.
- **`src/main/resources`**: Chứa file cấu hình hoặc tài nguyên.

### **Cách biên dịch và chạy chương trình**
1. **Biên dịch**:  
   ```bash
   javac HelloWorld.java
   ```
2. **Chạy chương trình**:  
   ```bash
   java HelloWorld
   ```

---

## **Kết luận**

Cấu trúc chương trình Java được thiết kế logic, giúp dễ tổ chức và quản lý mã nguồn. Việc hiểu rõ lớp, phương thức và cách tổ chức mã nguồn sẽ giúp bạn xây dựng các chương trình từ cơ bản đến phức tạp một cách hiệu quả.
