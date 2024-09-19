# Supported platforms for sixit C++ Libs
In our speak, "platform" = "CPU+Compiler+OS". 

## Supported CPUs:
- x64
- ARM64
- RISC-V64
- WASM32 (that WASM virtual CPU which you can run anywhere these days; supports 64-bit arithmetics but sizeof(void*) is still 4)

Planned:
- s390x
- WASM64 (as soon as there is [realistic support](https://webassembly.org/features/) for Memory64)
- Power

NOT planned by ourselves, but we welcome pull requests as long as they're concentrated within sixit/cpual;
- legacy 64-bit CPUs such as SPARC, PA-RISC, Itanium, MIPS64 - as long as there is at least one recent major compiler supporting them, AND you have a working box to run CI on at least once a week (!).

NOT planned by ourselves, but we welcome pull requests, as long as you have working box to run CI on (!); note, however, that they're unlikely to be 100% optimal (lots of sixit:: code is optimized for 64-bit arithmetics):
- x86
- ARM32
- RISC-V32
- MIPS-32
- anything-else which has a standard C++ compiler

NOT likely:
- legacy CPUs/MCUs which are not supported by more-or-less-recent stock C++ compilers (such as AVR8)

## Supported Compilers
- Clang starting from 12.x (we hope to add support starting from 10.x too, going further back in time is unlikely)
- MSVC starting from _MSC_VER=19.32 (we hope to add support for 19.29 too, going further back in time is unlikely)
- GCC starting from 11.x (we hope to add support for 10.x too, going further back in time is unlikely)

NOT planned by ourselves ATM, but we welcome pull requests as long as they're NOT spread all over the lib, AND you have working box to run CI on (!):
- ICX, NVCC, newer (Clang-based) XlC, any other Clang-frontend-based

Unlikely:
- legacy custom-frontend-based compilers, such as ICC, pre-clang-XlC, etc.

## Supported OSs (in alpabetical order)
- Android
- iOS
- Linux
- MacOS X (both Intel and ARM)
- Windows

WIP:
- WASM/Browser (whatever emscripten provides when running within browser)
- WASM/Sandbox (our own [quecto](https://en.wikipedia.org/w/index.php?title=Quecto)-pseudo-OS to run purely-computing things; designed to be unable to hurt the host)

Planned:
- FreeBSD
- WASM/WASI
- Consoles (XBox/PS/Switch)

NOT planned by ourselves, but we welcome pull requests as long as they're concentrated within sixit/osal (to be released soon, see below);
- pretty much anything which makes at least some sense - as long as you have working box to test it on (!).

#### Currently Officially Tested Configurations
sixit/sarge CI Tier 1 (cannot merge to trunk unless CI passes):
- Linux/x64/GCC 11.3
- Linux/x64/Clang 12
- Win/x64/MSVC 19.32
- MacOS/M2/Apple-Clang 15
- Android/ARM (build only)
- Android/x64 (build only, adding simulator tests in progress)
- iOS/ARM (build only)

sixit/sarge CI Tier 3 (run manually on regular basis):
- Linux/RISC-V64/GCC 12

Planned:
- Win/ARM/MSVC
- dual builds ("legacy" and "new") for GCC/x64
- dual builds ("legacy" and "new") for Clang/x64
- dual builds ("legacy" and "new") for MSVC/x64
