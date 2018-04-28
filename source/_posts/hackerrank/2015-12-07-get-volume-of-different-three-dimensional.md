---
layout: post
title: Get Volume of different three dimensional
category: 算法
keywords: http://jeff-chung.com/blog_accessary/blog_images/hackerrank/open.png
---

**Object orientated style.**

```java
 class Calculate {
    public Outputer output;
    public Scanner scanner = new Scanner(System.in);

    public int getINTVal() throws IOException {
        int input = readInt();
        if (input <= 0) {
            throw new NumberFormatException("All the values must be positive");
        }
        return input;
    }

    public int readInt() {
        return scanner.nextInt();
    }

    public static Volume get_Vol() {
        return new Volume();
    }

    public double getDoubleVal() throws IOException {
        double input = scanner.nextDouble();
        if (input <= 0) {
            throw new NumberFormatException("All the values must be positive");
        }
        return input;
    }
}

class Volume {
    ThreeDimensional threeDimensional;

    public double main(int a) {
        threeDimensional = new Cube(a);
        return threeDimensional.getVolume();
    }

    public double main(int l, int b, int h) {
        threeDimensional = new Cuboid(l, b, h);
        return threeDimensional.getVolume();
    }

    public double main(double r) {
        threeDimensional = new Hemisphere(r);
        return threeDimensional.getVolume();
    }

    public double main(double r, double h) {
        threeDimensional = new Cylinder(r,h);
        return threeDimensional.getVolume();
    }
}

abstract class ThreeDimensional {
    public abstract double getVolume();
}

class Cube extends ThreeDimensional {
    private double length;

    Cube(double length) {
        this.length = length;
    }

    @Override
    public double getVolume() {
        return Math.pow(this.length, 3);
    }
}

class Cuboid extends ThreeDimensional {
    private double length;
    private double breath;
    private double height;

    Cuboid(double length, double breath, double height) {
        this.length = length;
        this.breath = breath;
        this.height = height;
    }

    @Override
    public double getVolume() {
        return length * breath * height;
    }
}

class Hemisphere extends ThreeDimensional {
    private double radius;

    Hemisphere(double radius) {
        this.radius = radius;
    }

    @Override
    public double getVolume() {
        return Math.PI * Math.pow(radius, 3) * 4 / 3 / 2;
    }
}

class Cylinder extends ThreeDimensional {
    private double radius;
    private double height;

    Cylinder(double radius, double height) {
        this.radius = radius;
        this.height = height;
    }

    @Override
    public double getVolume() {
        return Math.PI * this.radius * this.radius * this.height;
    }
}

class Outputer {
    public static void display(double number) {
        //System.out.println(number);
        System.out.println(String.format("%.3f", number));
    }
}
```

**Procedure orientated style**

```java
class Calculate {
    public Outputer output;
    public Scanner scanner = new Scanner(System.in);
    public int getINTVal() throws IOException {
        int input = readInt();
        if(input <= 0){
            throw  new NumberFormatException("All the values must be positive");
        }
        return input;
    }

    public int readInt() {
        return scanner.nextInt();
    }

    public static Volume get_Vol() {
        return new Volume();
    }

    public double getDoubleVal() throws IOException{
        double input = scanner.nextDouble();
        if(input <= 0){
            throw  new NumberFormatException("All the values must be positive");
        }
        return input;
    }
}
class Volume{

    public double main(int a) {
        return a*a*a;
    }

    public double main(int l, int b, int h) {
        return l*b*h;
    }

    public double main(double r) {
        return Math.PI * Math.pow(r,3)*4/3 /2;
    }

    public double main(double r, double h) {
        return Math.PI * r * r *h;
    }
}
class Outputer {
    public static void display(double number) {
        //System.out.println(number);
       System.out.println(String.format("%.3f", number));
    }
}
```

**Difference of object orientated style and procedure orientate**

1.  Object orientated style should have encapsulation.In here,only the `getVolume()` function exposed.

2.  Object orientated style should be add class easily.
    In this case,a new class of ThreeDimensional can be created easily.
    The main program construct related new class and call getVolume function.(**_Still has a room of improvement_**)

3.  (OCP principle,there is very likely to have new type ThreeDimensional rather than new Operation so I think it should adopt OCP style when you developing this program)
