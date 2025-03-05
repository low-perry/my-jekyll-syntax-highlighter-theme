## Tutorial on how to create your own syntax highlighter theme

The following java code displays [my theme](https://github.com/low-perry/my-jekyll-syntax-highlighter-theme) of choice, and I am going to use that snippet to show you how to create your own theme.

```java

public class GenericClassExample<T, V> {
    private T first;
    private V second;
    private static final int LOW = 123;

    public GenericClassExample(T first, V second) {
        this.first = first;
        this.second = second;
    }

    public T getFirst() {
        return first;
    }

    public void setFirst(T first) {
        this.first = first;
    }

    public V getSecond() {
        return second;
    }

    public void setSecond(V second) {
        this.second = second;
    }

    @Override
    public String toString() {
        return "GenericClassExample{" +
                "first=" + first +
                ", second=" + second +
                '}';
    }

    public static void main(String[] args) {
        GenericClassExample<String, Integer> example = new GenericClassExample<>("Hello", 123);
        System.out.println(example);

        example.setFirst("World");
        example.setSecond(456);
        System.out.println(example);

        // This demonstrates the primitives
        byte a = 1;
        short b = 2;
        int c = 3;
        boolean d = true;
        boolean e = (a < 3) ? true : false;

        //Reference types
        Integer ab = 4;

        /* Create an ArrayList with positive and negative numbers */
        List<Integer> arr = new ArrayList<>();
        arr.add(-10);
        arr.add(20);
        arr.add(-30);
        arr.add(40);
        arr.add(-50);
        arr.add(60);

        // Print the ArrayList
        System.out.println("ArrayList: " + arr);

        // Check for positive numbers in the ArrayList
        for (Integer n : arr) {
            if (n > 0) {
                System.out.println(n + " is positive.");
            } else {
                System.out.println(n + " is negative.");
            }
        }
    }
    
}

```

1. **Access modifiers** like `public`, `private` etc., **non-access modifiers** like `final`, `abstract`, `static` etc., and the `class` and `interface` keywords are rendered on the HTML as `<span>` elements with the class `class="kd"`, who are children of a `<pre>` element with the class `class="highlight"`. To change their color do the following:

    ```css
    .highlight .kd {
        color: #f38ba8; /* color of your choosing */
    }
    ```

2. **Operators** like `new`, `+`, `?`, `.`, `=` etc, and **punctuation** like `{}`, `()`, `,`, `;` etc., are rendered on the HTML as `<span>` elements with the class `class="o"`. (This is only in Java's case, in other languages like C# the punctuation has the class `class=`p`). To change their color do the following:

    ```css
        .highlight .o {
            color: #f38ba8; /* color of your choosing */
        }
    ```

3. **Class names** or **Reference types** are rendered on the HTML as `<span>` elements with the class `class="nc"`. To change their color do the following:

    ```css
        .highlight .kd {
            color: #89b4fa; /* color of your choosing */
        }
    ```

4. **Primitive types** and **void** are rendered on the HTML as `<span>` elements with the class `class="kt"`. To change their color do the following:

    ```css
        .highlight .kt {
            color: #74c7ec; /* color of your choosing */
        }
    ```

5. **Reserved keywords** for looping (`while`, `for`), branching (`if`, `else`, `switch`), skipping or breaking form loops or branches (`break`, `continue`), `this` and the `new` operator, are rendered on the HTML as `<span>` elements with the class `class="k"`. To change their color do the following:

    ```css
        .highlight .k {
            color: #f38ba8; /* color of your choosing */
        }
    ```

6. **Functions** and **methods** are rendered on the HTML as `<span>` elements with the class `class="nf"`. Be careful, the method calls on an object are rendered with the `class="na"` (This happens only in the pattern `object.method()` where `object` has `class="n"` and `.` operator has `class="o"`). To change their color do the following:

    ```css
        .highlight .nf, .n + .o + .na, .na + .o + .na {
            color: #a6e3a1; /* color of your choosing */
        }
    ```

7. **Arguments**, **variables** and **instance fields** are rendered on the HTML as `<span>` elements with the class `class="n"`. When we refer to a class member with the `this` keyword then it is rendered with the `class="na"`. To change their color do the following:

    ```css
        .highlight .n, .highlight .na  {
            color: #ced6f5; /* color of your choosing */
        }
    ```

8. **String literals** are rendered on the HTML as `<span>` elements with the class `class="s"`.To change their color do the following:

    ```css
        .highlight .s {
            color:  #f9e2af; /* color of your choosing */
        }
    ```

9. **Number literals** are rendered on the HTML as `<span>` elements with the class `class="mi"`. **Boolean literals** are rendered on the HTML as `<span>` elements with the class `class="kc"`. To change their color do the following:

    ```css
        .highlight .kc, .highlight .mi {
        color: #cba6f7; /* color of your choosing */
        }
    ```

10. **Single line comments** are rendered on the HTML as `<span>` elements with the class `class="c1"`. **Multi line comments** are rendered on the HTML as `<span>` elements with the class `class="cm"`. To change their color do the following:

    ```css
        .highlight .c1, .highlight .cm {
            color: #505050; /* color of your choosing */
        }
    ```

> **Note:** This is an example based on Java, to be more careful please inspect the HTML elements on your browser's dev tools.
