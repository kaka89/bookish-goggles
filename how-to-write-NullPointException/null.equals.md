# null equals with others

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("value");
        String nullValue = null;
        try {
            if (nullValue.equals("value")) {
                System.out.println("you will not see this.");
            }
        } catch (NullPointerException npe) {
            System.out.println("you got NullPointException");
        }
    }
}

```

**Right way for this bug**

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("value");
        String nullValue = null;
        try {
            if (!"value".equals(nullValue)) {
                System.out.println("you will see this.");
            }
        } catch (NullPointerException npe) {
            System.out.println("you got NullPointException");
        }
    }
}

```