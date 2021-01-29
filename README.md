<h1 align="center">ATHERCRC32 - Memory block protection</h1>
<p>
  <img src="https://raw.githubusercontent.com/keowu/ATHERCRC32/main/Screenshots/Capturar4.PNG" alt="ATHERCRC32 Lib">
</p>
<p align="center">ATHERCRC32 Provide developers with a complete framework for using CRC32 in functions/classes in memory, and protecting your software against WriteProcessMemory or changes during execution in memory, protecting your intellectual property.</p>
<hr>
<h3 align="center">Very simple to use</h3>

```c++
//__________________________________
// INCLUDE FOR ATHERCRC32 LIB
//__________________________________
#include "includes/ATHERCRC32.h"
//__________________________________

// Create an ATHERCRC instance
ATHERCRC32* ATHERCRC = new ATHERCRC32();
ATHERCRC32_WARNING* ATHERCRCWARNING = new ATHERCRC32_WARNING();

//Simple steps to implement for functions that are not class members

// We get the size of the process memory function
unsigned int iTamanho = ATHERCRC->obtemTamanhoDeUmaFuncaoDaMemoria(minhaFuncao);

// We calculate the CRC32
uint32_t CRC32MinhaFuncao = ATHERCRC->calcularCRC32DEUMAFUNCAO(minhaFuncao, iTamanho);

// Even simpler implementation for methods and classes

// Getting a pointer to a specific method / function of a class
auto pFuncaoParaVoidCasting = ATHERCRC->pvoid_cast(&MyClassTest::MyFunction);

// Calculating the size in memory
iTamanho = ATHERCRC->obtemTamanhoDeUmaFuncaoDaMemoria(pFuncaoParaVoidCasting);

// Calculating the CRC32
CRC32MinhaFuncao = ATHERCRC->calcularCRC32DEUMAFUNCAO(pFuncaoParaVoidCasting, iTamanho);

```

<h3 align="center">Simple to implement and much simpler to detect</h3>

```c++
    // It will be displayed and calculated that the CRC32 of the memory block is wrong and has been changed
    // Just detect, and writes to the console that a change was found in the process memory block.
    ATHERCRCWARNING->AntiMemoryWriteDectLite(minhaFuncao, iTamanho, CRC32MinhaFuncao);

    // It will be displayed and calculated that the CRC32 of the memory block is correct
    //You can assign between true and false if you want to show a warning to your user.
    ATHERCRCWARNING->AntiMemoryWriteDetect(minhaFuncao, iTamanho, CRC32MinhaFuncao, true);
```

<h3 align="center">See protection working</h3>

<p>
  <img src="https://github.com/keowu/ATHERCRC32/blob/main/Screenshots/Capturar1.PNG?raw=true" alt="demo1">
  In this example using the x32dbg tool I found the memory pointer of a string that I would like to modify
</p>

<p>
  <img src="https://raw.githubusercontent.com/keowu/ATHERCRC32/main/Screenshots/Capturar2.PNG" alt="demo2">
  I decided to modify the function and its received parameters and its strings
</p>

<p>
  <img src="https://raw.githubusercontent.com/keowu/ATHERCRC32/main/Screenshots/Capturar3.PNG" alt="demo3">
  After making some modifications, and cracking attempts and changes in the process memory
</p>

<p>
  <img src="https://raw.githubusercontent.com/keowu/ATHERCRC32/main/Screenshots/Capturar4.PNG" alt="demo4">
  <img src="https://raw.githubusercontent.com/keowu/ATHERCRC32/main/Screenshots/Capturar5.PNG" alt="demo4">
  I decided to run the software after my modifications and I was detected and the software was protected from my attack.
</p>

<h2 align="center">Copyright (C) Keowu | ATHERCRC32 OpenSource | please leave a like in the repository if this library is useful for you</h2>
