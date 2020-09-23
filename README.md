<div align="center">

## SOFTWARE REBOOT UNDER  MS\-DOS


</div>

### Description

Writing a program in C/C++ for Rebooting Under MS-DOS. PLEASE PROVIDE YOUR FEEDBACK OR VOTE ABOUT THIS ARTICLE.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mohit Aggarwal](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mohit-aggarwal.md)
**Level**          |Advanced
**User Rating**    |4.6 (32 globes from 7 users)
**Compatibility**  |C, C\+\+ \(general\), Borland C\+\+, UNIX C\+\+
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__3-23.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mohit-aggarwal-software-reboot-under-ms-dos__3-3138/archive/master.zip)





### Source Code

<b>PLEASE PROVIDE YOUR FEEDBACK OR VOTE ABOUT THIS ARTICLE SO I MAY DECIDE TO WRITE ANY FURTHER ARTICLES.</b><br><br>
<font color="red">Why this article?</font><br>
<font color="blue">Most of us have to work under MS-DOS for various reasons like troubleshooting windows, installing sub-operating system, altering windows default settings and many more. But didn't you miss something there??? Yes, you are right RESTART. We always have to use hardware reset while working under MS-DOS. This article will solve your problem.</font><br>
<br><center><b><font color="green">*****ARTICLE*****</font></b></center><br>
<br>
<font color="blue">So, in here we will write a program in C/C++ to make our system reboot when executed. Before the code i would like to explain some topics which we have to consider before writing. These are:<br><br>
1)Pointers to Functions<br>
2)ROM BIOS Routine Addresses<br><br>
So, Here we go:<br><br>
<b><u><i>POINTERS TO FUNCTIONS:-</i></u></b><br><br>
For many of us this can be a strange topics as we all have dedicated some part of our programming
carrier in understanding pointers but never(or very few) came across pointers to functions. So, before going further note that functions do occupies memory and therefore we can assign pointers to those memory locations from which functions get start.<br>
<b><u><i>DECLAREING A POINTER TO a FUNCTION:-</i></u></b><br><br>
int (*function_ptr)() is a pointer to a function whose return type is integer. Mind you, we always have to look for memory usage while dealing with pointers.<br><br>
<b><u><i>ROM BIOS ROUTINE ADDRESSES:-</i></u></b><br><br>
Now we all know, ROM Chips consitutes Read Only Memory which contains programs which cannot be altered. But have you ever thought that the ROM Chips contains those programs which loads into memory before anything else and these gets loaded into memory(RAM) unless we turn off our computer. Therefore to write a program which reboot our computer we just need the memory address of first ROM BIOS Routine which get executed the moment we boot our computer. This address is 0xFFFF0000.<br>
I think, now we are in the position of writing requires code.<br><br></font>
<font color="#FF234C">#include"dos.h"<br><br>
void main()<br>
{<br>
void far(*p)(); //we need 32 bit pointer<br>
p=0xFFFF0000; //this is the location we are pointing to<br>
(*p)(); 	//calling<br>
}<br>
</font><br>
<font color="blue">
I dont know, why Microsoft put DOS reboot by themselves. But you can do so by the .exe file of above code.</font><br><br>
<font color="red">Why this code is not working under windows?</font><br>
<font color="blue">This code cannot work under windows as window work above DOS's 1MB memory. If you run this code under Window, the window you are working under will get closed.</font><br>
<font color="red">Why didn't i provide just the source code?</font><br>
<font color="blue"> I dont think every person out there is able to understand this code. Also begginers like to have many lines of code. They do not see the power behind the code.</font><br><br>
<font color="black"><b>Mohit Aggarwal</b></font>

