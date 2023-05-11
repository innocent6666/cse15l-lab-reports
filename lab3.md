
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
<br> <br>

**2. find -iname "partial name of the file"**


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


**3. find -type (f/d/l/...)**

```
$ find -type d 
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

<br>
This command searches for the type directories inside the technical folder. We can use it when we only want to search for directories. 
<br>
<br>

```
$ find 911report/ -type f
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
This command goes into the 911report folder and searches for the type file. We can use it when we only want to search for files. 
<br>
<br>

**4.find -maxdepth n**

```
$ find -maxdepth 1
.
./911report
./biomed
./government
./plos
```

<br>
This limit the maximum search depth to be 1. We can use it when we don't want to go deep into subfolders.
<br>
<br>

```
$ find  -maxdepth 2 -name "*chapter*"
./911report/chapter-1.txt
./911report/chapter-10.txt
./911report/chapter-11.txt
./911report/chapter-12.txt
./911report/chapter-13.1.txt
./911report/chapter-13.2.txt
./911report/chapter-13.3.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-2.txt
./911report/chapter-3.txt
./911report/chapter-5.txt
./911report/chapter-6.txt
./911report/chapter-7.txt
./911report/chapter-8.txt
./911report/chapter-9.txt
```

This limit the maximum search depth to be 2 and search for any fiel containing the word "chapter". We can use it when we don't want to go deeper into subfolders and want the file contains the name "chapter".


Source https://www.redhat.com/sysadmin/linux-find-command

