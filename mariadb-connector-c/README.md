
# Building mariadb-connector-c from source with MinGW64
1. update MSYS and MINGW64 to the latest version
2. start MING64 console
3. prepare unpacking and a build directory
`tar xvf mariadb-connector-c-x.x.x.tar.gz`
`cd mariadb-connector-c-x.x.x`
4. for fixing the issue at [ 36%] Linking C shared module remote_io.dll
`patch -p1 < mariadb-connector-c.patch`
5. create and use build dir
`mkdir build ; cd build`
`cmake .. -G "MSYS Makefiles" -D CMAKE_BUILD_TYPE=Release`
`make -jX` (X=number of CPU cores you would like to spent during compilation)
6. on my very slow and limited N4120 laptop the build process got stuck during compilation at 15% progress. If it happens, kill the process and restart.
7. if should compile until the end!
