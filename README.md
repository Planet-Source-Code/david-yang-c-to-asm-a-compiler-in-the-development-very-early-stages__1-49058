<div align="center">

## C to ASM \- a compiler in the development \(very early stages\)


</div>

### Description

THis program translates a subset of C into asm, currently, it supports looping (for, while), conditions (if), maths (+,*,-,/), boolean operators (&&, ||), arrays(partly)

This outputs asm code that should work, the output is currently generic asm code, without conforming to the rules of any specific asm compiler, but that can be easily taken care of.

THis program is written in excel Visual basic, because my version of Visual basic was deleted, and i lost my visual basic installation cd. anyway, you can still run it. TO view the source code, press ALT+F11 to enter a editor, much like the normal VB editor (sorry about that...)

Sample Code Translation is below (in the "Windows API section" below):
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |2003-10-07 16:48:10
**By**             |[David Yang](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/david-yang.md)
**Level**          |Advanced
**User Rating**    |5.0 (20 globes from 4 users)
**Compatibility**  |VB 6\.0
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__1-27.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[C\_to\_ASM\_\-1655731082003\.zip](https://github.com/Planet-Source-Code/david-yang-c-to-asm-a-compiler-in-the-development-very-early-stages__1-49058/archive/master.zip)

### API Declarations

```
int main()
{
	msgbox(hitme(5,6));
};
int hitme(int a,int b)
{
	a=a*a+b*b;
	return a;
};
TRANSLATES TO::
const \\ --String Constants
code \\ --Code Section
\\ --Function: main
Func main
push ebp
mov ebp, esp
Push 6
Push 5
call hitme
Push eax
call msgbox
pop ebp
retn
\\ --Function: hitme
Func hitme
push ebp
mov ebp, esp
add esp, 2
mov ebx, [ebp-12]
mov eax, [ebp-12]
imul ebx
mov ebx, eax
mov ecx, [ebp-8]
mov eax, [ebp-8]
imul ecx
mov ecx, eax
add ecx, ebx
mov [ebp-8], ecx
sub esp, 2
pop ebp
retn
```





