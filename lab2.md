# Lab Report 2:
## Part 1
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Type in '/add-message?s=<string>' in URL to add messages!");
        } else {
            System.out.println("Path: " + url.getPath()); // What does this line do?
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    str += parameters[1];
                    str += "\n";
                    return String.format(str);
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

![Image](lab2Screenshot2.jpg)
<br>
1. My code called the method url.getPath() and url.getQuery(). (It also called the method .contains, . equals and .split but they are just basic string methods.)
2. The argument of url.getPath() is the Path of the URL, and its value is */add-message?s=What is today's date?* <br> The arguement of url.getQuery() is the Query of the URL , and its value is *s=What is today's date?*
3. The value of the String str is updated to *What is today's date \n*

![Image](lab2Screenshot3.jpg)
<br>
1. My code called the method url.getPath() and url.getQuery(). 
2. The argument of url.getPath() is the Path of the URL, and its value is */add-message?s=Saturday, April 22, 2023* <br> The arguement of url.getQuery() is the Query of the URL , and its value is *s=Saturday, April 22, 2023*
3. The value of the String str is updated to *What is today's date \n Saturday, April 22, 2023 \n*
<br>
<br>
<br>

## Part 2
<br>
I chose the bug of method ReverseInPlace in java file ArrayExamples
<br>
1. Failure-inducing input

```
public void testReverseInPlace() {
    int[] input1 = {1,2,3,4,5,6,7 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(input1,new int[]{1,2,3,4,3,2,1});
}
```

<br>
2. Positive Input

```
public void testReverseInPlace() {
    int[] input1 = {1,2,3,4,3,2,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(input1,new int[]{1,2,3,4,3,2,1});
}
```

<br>
3. <br>
Symptoms of both inputs <br>
<br>

![Image](Input1symptom.jpg)

![Image](Input2symptom.jpg)

4. <br>
Original Code:

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```

Fixed Code:

```
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1){
      temp[i] = arr[i];
    } 
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = temp[arr.length - i - 1];
    }
}
```

The issue with the original code is that it uses the value of the second half of the array to replace the first half. However, once the second half is reached during the loop, the first half has already been updated with the values from its counterpart in the second half. This means that when applying reverseInPlace to the second half, we are simply reassigning the value of itself.
<br>
In the fixed code, I made a temporary copy of the array and used this copy to assign values when reversing. Thus, during the for loop, the values of the passed-in array are successfully swapped without modifying the original array. 
<br>
<br>
<br>
## Part 3(Something I learned from lab 2 or 3):
There are the four parts that form the URL. They are:
* **Domain** <br>
The part of the URL after *http://*
* **Path** <br>
The part of URl after *domain* and before *?*
* **Query** <br>
The part of the URL after *?* and before *anchor*
* **Anchor** <br>
The part of the URL after the *#*

In example *https://www.google.com/search?q=cse15l*

*" www.google.com "* is the **domain** <br>
*" /search "* is the **path** <br>
*" q=cse15l "* is the **query** <br>

In example *https://ucsd-cse15l-s23.github.io/week/week1/#week1-lab-report*

*" ucsd-cse15l-s23.github.io "* is the **domain** <br>
*" /week/week1/ "* is the **path** <br>
*" week1-lab-report "* is the **anchor** <br>

In example *https://map.concept3d.com/?id=1005#!m/576556*

*" map.concept3d.com "* is the **domain** <br>
*" /search "* is the **path** <br>
*" id=1005 "* is the **query** <br>
*" !m/576556 "* is the **anchor** <br>

