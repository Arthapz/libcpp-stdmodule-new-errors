```
#install xmake
#update it to dev
xmake update -s dev
#compile LLVM from master

xmake f --toolchain=clang --ar=llvm-ar
xmake b -vD
```

```
checking for platform ... windows
checking for architecture ... x64
[  0%]: generating.module.deps src\main.cpp
checking for clang-scan-deps ... ok
checking for flags (-fvisibility-inlines-hidden) ... ok
> clang "-fvisibility-inlines-hidden" "-Qunused-arguments" "-m64"
checking for flags (-std=c++23) ... ok
> clang "-std=c++23" "-Qunused-arguments" "-m64"
checking for flags (-stdlib=libc++) ... ok
> clang "-stdlib=libc++" "-Qunused-arguments" "-m64"
checking for flags (-fexperimental-library) ... ok
> clang "-fexperimental-library" "-Qunused-arguments" "-m64"
clang-scan-deps --format=p1689 -- clang -x c++ -c src\main.cpp -o build\.objs\test\windows\x64\release\src\main.cpp.obj -Qunused-arguments -m64 -std=c++23 -Iinclude -fexceptions -fcxx-exceptions -stdlib=libc++ -fexperimental-library
checking for flags (clang_modules_cache_path) ... ok
> clang "-fmodules-cache-path=C:\Users\arthu\AppData\Local\Temp\.xmake\230818" "-Qunused-arguments" "-m64"
[  0%]: generating.module.deps stdmodules\std.cppm
checking for flags (-Wno-reserved-module-identifier) ... ok
> clang "-Wno-reserved-module-identifier" "-Qunused-arguments" "-m64"
clang-scan-deps --format=p1689 -- clang -x c++ -c stdmodules\std.cppm -o build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj -Qunused-arguments -m64 -std=c++23 -fexceptions -fcxx-exceptions -isystem C:\Dev\llvm\include\c++\v1 -stdlib=libc++ -fexperimental-library -Wno-reserved-module-identifier
checking for flags (clang_module_output) ... ok
> clang "-fmodule-output=" "-Qunused-arguments" "-m64"
[  9%]: compiling.module.release std
clang -c -x c++-module -fmodule-output=build\.gens\stdmodules\windows\x64\release\rules\modules\cache\a3c3afdf\std.pcm -Qunused-arguments -m64 -std=c++23 -fexceptions -fcxx-exceptions -isystem C:\Dev\llvm\include\c++\v1 -stdlib=libc++ -fexperimental-library -Wno-reserved-module-identifier -fmodules-cache-path=build\.gens\stdmodules\windows\x64\release\rules\modules\cache -o build\.objs\stdmodules\windows\x64\release\stdmodules\std.cppm.obj stdmodules\std.cppm
checking for flags (-fdiagnostics-color=always) ... ok
> clang "-fdiagnostics-color=always" "-Qunused-arguments" "-m64"
error: @programdir\modules\private\async\runjobs.lua:256: @programdir\rules\c++\modules\modules_support\clang.lua:300: @programdir\modules\core\tools\gcc.lua:797: In file included from stdmodules\std.cppm:23:
stdmodules/std/new.inc:24:14: error: no member named 'get_new_handler' in namespace 'std'; did you mean 'set_new_handler'?
   24 |   using std::get_new_handler;
      |         ~~~~~^~~~~~~~~~~~~~~
      |              set_new_handler
C:\Program Files (x86)\Windows Kits\10\Include\10.0.22621.0\ucrt\new.h:32:42: note: 'set_new_handler' declared here
   32 |             _CRTIMP2 new_handler __cdecl set_new_handler(_In_opt_ new_handler _NewHandler) throw();
      |                                          ^
1 error generated.
```