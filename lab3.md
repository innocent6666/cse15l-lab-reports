
**1. find -name "file extension"**

``` 
$ find 911report/ -name "*.txt"
911report/chapter-1.txt
911report/chapter-10.txt
911report/chapter-11.txt
911report/chapter-12.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-2.txt
911report/chapter-3.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-8.txt
911report/chapter-9.txt
911report/preface.txt
```

<br>
This commans goes into the 911report folder and searches for every file that has ".txt" in its name. We can use this command to locate any file with a specific extension.
<br>
<br>


``` 
$ find government/Alcohol_Problems/ -name "*.txt"
government/Alcohol_Problems/DraftRecom-PDF.txt
government/Alcohol_Problems/Session2-PDF.txt
government/Alcohol_Problems/Session3-PDF.txt
government/Alcohol_Problems/Session4-PDF.txt
``` 

<br>
This commans goes into the Alcohol_Problems folder inside the government folder and searches for every file that has ".txt" in its name. We can use this command to locate any file with a specific extension.
<br>
<br>

**2. find -iname "partial name of the file" ** 

``` 
$ find government/Alcohol_Problems/ -iname "*draft*txt"
government/Alcohol_Problems/DraftRecom-PDF.txt
``` 

<br>
This commands goes into the Alcohol_Problems folder inside the government folder and searchs (case insensitive) for any file that contains "draft" and "txt" in its file name. We can use it when we do not remember the exact name of a file (or whether we capitalized some letters).
<br><br>

```
$ find government/Env_Prot_Agen/ -iname "*tech*txt"
government/Env_Prot_Agen/tech_adden.txt
government/Env_Prot_Agen/tech_sectiong.txt
```
<br>

This commands goes into the Env_Prot_Agen inside the government folder and searchs (case insensitive) for any file that contains "tech" and "txt" in its file name. We can use it when we do not remember the exact name of a file (or whether we capitalized some letters).
<br><br>


**3. find -type 
























Source https://www.redhat.com/sysadmin/linux-find-command

