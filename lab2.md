# Lab Report 2:
## Part 1
```
# code block
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



1. My code called the method url.getPath() and url.getQuery(). (It also called the method .contains, . equals and .split but they are just basic string methods.)
2. The argument for url.getPath() is the Path of the URL, and its value is */add-message?s=What is today's date?* <br> The arguement for url.getQuery() is the query of the URL , and its value is *s=What is today's date?*
3. The value of the String str then changed to *What is today's date \n*
    








<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
## Handout 3:
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

