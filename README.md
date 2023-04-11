# snippet_sqlite3_centos_python

https://www.webdesignsun.com/insights/upgrading-sqlite-on-centos/

https://eeinte.ch/stream/install-latest-sqlite-version-shared-hosting/ => à adapter avec bons répertoires à trouver via : 
(python3.9) [devdata@dev-data bin]$ type -a sqlite3
sqlite3 is aliased to `/home/devdata/.local/bin/sqlite3'
sqlite3 is /usr/local/bin/sqlite3
sqlite3 is /usr/bin/sqlite3

2023-04-11

[devdata@dev-data ~]$ cd /opt

[devdata@dev-data opt]$ sudo wget https://www.sqlite.org/2022/sqlite-autoconf-3400000.tar.gz
--2023-04-11 12:50:09--  https://www.sqlite.org/2022/sqlite-autoconf-3400000.tar.gz
Resolving www.sqlite.org (www.sqlite.org)... 45.33.6.223, 2600:3c00::f03c:91ff:fe96:b959
Connecting to www.sqlite.org (www.sqlite.org)|45.33.6.223|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3097756 (3.0M) [application/x-gzip]
Saving to: ‘sqlite-autoconf-3400000.tar.gz’

100%[==================================================================================>] 3,097,756   3.14MB/s   in 0.9s   

2023-04-11 12:50:11 (3.14 MB/s) - ‘sqlite-autoconf-3400000.tar.gz’ saved [3097756/3097756]

[devdata@dev-data opt]$ sudo tar xvfz sqlite-autoconf-3400000.tar.gz
sqlite-autoconf-3400000/
sqlite-autoconf-3400000/compile
sqlite-autoconf-3400000/sqlite3.c
sqlite-autoconf-3400000/sqlite3.rc
sqlite-autoconf-3400000/Makefile.msc
sqlite-autoconf-3400000/sqlite3.1
sqlite-autoconf-3400000/Makefile.in
sqlite-autoconf-3400000/install-sh
sqlite-autoconf-3400000/aclocal.m4
sqlite-autoconf-3400000/config.sub
sqlite-autoconf-3400000/Makefile.fallback
sqlite-autoconf-3400000/shell.c
sqlite-autoconf-3400000/depcomp
sqlite-autoconf-3400000/sqlite3.h
sqlite-autoconf-3400000/Makefile.am
sqlite-autoconf-3400000/missing
sqlite-autoconf-3400000/README.txt
sqlite-autoconf-3400000/ltmain.sh
sqlite-autoconf-3400000/tea/
sqlite-autoconf-3400000/tea/tclconfig/
sqlite-autoconf-3400000/tea/tclconfig/tcl.m4
sqlite-autoconf-3400000/tea/tclconfig/install-sh
sqlite-autoconf-3400000/tea/Makefile.in
sqlite-autoconf-3400000/tea/aclocal.m4
sqlite-autoconf-3400000/tea/win/
sqlite-autoconf-3400000/tea/win/makefile.vc
sqlite-autoconf-3400000/tea/win/nmakehlp.c
sqlite-autoconf-3400000/tea/win/rules.vc
sqlite-autoconf-3400000/tea/configure.ac
sqlite-autoconf-3400000/tea/doc/
sqlite-autoconf-3400000/tea/doc/sqlite3.n
sqlite-autoconf-3400000/tea/pkgIndex.tcl.in
sqlite-autoconf-3400000/tea/README
sqlite-autoconf-3400000/tea/configure
sqlite-autoconf-3400000/tea/license.terms
sqlite-autoconf-3400000/tea/generic/
sqlite-autoconf-3400000/tea/generic/tclsqlite3.c
sqlite-autoconf-3400000/config.guess
sqlite-autoconf-3400000/configure.ac
sqlite-autoconf-3400000/INSTALL
sqlite-autoconf-3400000/sqlite3ext.h
sqlite-autoconf-3400000/configure
sqlite-autoconf-3400000/Replace.cs
sqlite-autoconf-3400000/sqlite3rc.h
sqlite-autoconf-3400000/sqlite3.pc.in

[devdata@dev-data opt]$ cd sqlite-autoconf-3400000

[devdata@dev-data sqlite-autoconf-3400000]$ sudo ./configure --prefix=$HOME/.local
checking for a BSD-compatible install... /bin/install -c
checking whether build environment is sane... yes
checking for a race-free mkdir -p... /bin/mkdir -p
checking for gawk... gawk
checking whether make sets $(MAKE)... yes
checking whether make supports nested variables... yes
checking whether make supports the include directive... yes (GNU style)
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables... 
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether the compiler supports GNU C... yes
checking whether gcc accepts -g... yes
checking for gcc option to enable C11 features... -std=gnu11
checking whether gcc -std=gnu11 understands -c and -o together... yes
checking dependency style of gcc -std=gnu11... gcc3
checking for special C compiler options needed for large files... no
checking for _FILE_OFFSET_BITS value needed for large files... no
checking for gcc... (cached) gcc
checking whether the compiler supports GNU C... (cached) yes
checking whether gcc accepts -g... (cached) yes
checking for gcc option to enable C11 features... (cached) -std=gnu11
checking whether gcc -std=gnu11 understands -c and -o together... (cached) yes
checking dependency style of gcc -std=gnu11... (cached) gcc3
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking how to print strings... printf
checking for a sed that does not truncate output... /bin/sed
checking for grep that handles long lines and -e... /bin/grep
checking for egrep... /bin/grep -E
checking for fgrep... /bin/grep -F
checking for ld used by gcc -std=gnu11... /bin/ld
checking if the linker (/bin/ld) is GNU ld... yes
checking for BSD- or MS-compatible name lister (nm)... /bin/nm -B
checking the name lister (/bin/nm -B) interface... BSD nm
checking whether ln -s works... yes
checking the maximum length of command line arguments... 1572864
checking how to convert x86_64-pc-linux-gnu file names to x86_64-pc-linux-gnu format... func_convert_file_noop
checking how to convert x86_64-pc-linux-gnu file names to toolchain format... func_convert_file_noop
checking for /bin/ld option to reload object files... -r
checking for objdump... objdump
checking how to recognize dependent libraries... pass_all
checking for dlltool... no
checking how to associate runtime and link libraries... printf %s\n
checking for ar... ar
checking for archiver @FILE support... @
checking for strip... strip
checking for ranlib... ranlib
checking command to parse /bin/nm -B output from gcc -std=gnu11 object... ok
checking for sysroot... no
checking for a working dd... /bin/dd
checking how to truncate binary pipes... /bin/dd bs=4096 count=1
checking for mt... no
checking if : is a manifest tool... no
checking for stdio.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for strings.h... yes
checking for sys/stat.h... yes
checking for sys/types.h... yes
checking for unistd.h... yes
checking for dlfcn.h... yes
checking for objdir... .libs
checking if gcc -std=gnu11 supports -fno-rtti -fno-exceptions... no
checking for gcc -std=gnu11 option to produce PIC... -fPIC -DPIC
checking if gcc -std=gnu11 PIC flag -fPIC -DPIC works... yes
checking if gcc -std=gnu11 static flag -static works... no
checking if gcc -std=gnu11 supports -c -o file.o... yes
checking if gcc -std=gnu11 supports -c -o file.o... (cached) yes
checking whether the gcc -std=gnu11 linker (/bin/ld -m elf_x86_64) supports shared libraries... yes
checking whether -lc should be explicitly linked in... no
checking dynamic linker characteristics... GNU/Linux ld.so
checking how to hardcode library paths into programs... immediate
checking whether stripping libraries is possible... yes
checking if libtool supports shared libraries... yes
checking whether to build shared libraries... yes
checking whether to build static libraries... yes
checking for fdatasync... yes
checking for usleep... yes
checking for fullfsync... no
checking for localtime_r... yes
checking for gmtime_r... yes
checking for gcc -std=gnu11 options needed to detect all undeclared functions... none needed
checking whether strerror_r is declared... yes
checking whether strerror_r returns char *... no
checking for editline/readline.h... no
checking for readline/readline.h... no
checking for library containing pthread_create... -lpthread
checking for library containing pthread_mutexattr_init... none required
checking for library containing dlopen... -ldl
checking for whether to support dynamic extensions... yes
checking SQL math functions... enabled
checking for library containing ceil... -lm
checking FTS4 extension... enabled
checking FTS3 extension... disabled
checking FTS5 extension... enabled
checking for library containing log... none required
checking RTREE extension... enabled
checking Session extension... disabled
checking Build type... release
checking for posix_fallocate... yes
checking for zlib.h... yes
checking for library containing deflate... -lz
checking for library containing system... none required
checking that generated files are newer than configure... done
configure: creating ./config.status
config.status: creating Makefile
config.status: creating sqlite3.pc
config.status: executing depfiles commands
config.status: executing libtool commands

[devdata@dev-data sqlite-autoconf-3400000]$ sudo make && make install
gcc -std=gnu11 -DPACKAGE_NAME=\"sqlite\" -DPACKAGE_TARNAME=\"sqlite\" -DPACKAGE_VERSION=\"3.40.0\" -DPACKAGE_STRING=\"sqlite\ 3.40.0\" -DPACKAGE_BUGREPORT=\"http://www.sqlite.org\" -DPACKAGE_URL=\"\" -DPACKAGE=\"sqlite\" -DVERSION=\"3.40.0\" -DHAVE_STDIO_H=1 -DHAVE_STDLIB_H=1 -DHAVE_STRING_H=1 -DHAVE_INTTYPES_H=1 -DHAVE_STDINT_H=1 -DHAVE_STRINGS_H=1 -DHAVE_SYS_STAT_H=1 
-DHAVE_SYS_TYPES_H=1 -DHAVE_UNISTD_H=1 -DSTDC_HEADERS=1 -DHAVE_DLFCN_H=1 -DLT_OBJDIR=\".libs/\" -DHAVE_FDATASYNC=1 -DHAVE_USLEEP=1 -DHAVE_LOCALTIME_R=1 -DHAVE_GMTIME_R=1 -DHAVE_DECL_STRERROR_R=1 -DHAVE_STRERROR_R=1 -DHAVE_POSIX_FALLOCATE=1 -DHAVE_ZLIB_H=1 -I.    -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB  -DSQLITE_ENABLE_EXPLAIN_COMMENTS -DSQLITE_ENABLE_DBPAGE_VTAB -DSQLITE_ENABLE_STMTVTAB -DSQLITE_ENABLE_DBSTAT_VTAB  -g -O2 -MT sqlite3-shell.o -MD -MP -MF .deps/sqlite3-shell.Tpo -c 
-o sqlite3-shell.o `test -f 'shell.c' || echo './'`shell.c
mv -f .deps/sqlite3-shell.Tpo .deps/sqlite3-shell.Po
gcc -std=gnu11 -DPACKAGE_NAME=\"sqlite\" -DPACKAGE_TARNAME=\"sqlite\" -DPACKAGE_VERSION=\"3.40.0\" -DPACKAGE_STRING=\"sqlite\ 3.40.0\" -DPACKAGE_BUGREPORT=\"http://www.sqlite.org\" -DPACKAGE_URL=\"\" -DPACKAGE=\"sqlite\" -DVERSION=\"3.40.0\" -DHAVE_STDIO_H=1 -DHAVE_STDLIB_H=1 -DHAVE_STRING_H=1 -DHAVE_INTTYPES_H=1 -DHAVE_STDINT_H=1 -DHAVE_STRINGS_H=1 -DHAVE_SYS_STAT_H=1 
-DHAVE_SYS_TYPES_H=1 -DHAVE_UNISTD_H=1 -DSTDC_HEADERS=1 -DHAVE_DLFCN_H=1 -DLT_OBJDIR=\".libs/\" -DHAVE_FDATASYNC=1 -DHAVE_USLEEP=1 -DHAVE_LOCALTIME_R=1 -DHAVE_GMTIME_R=1 -DHAVE_DECL_STRERROR_R=1 -DHAVE_STRERROR_R=1 -DHAVE_POSIX_FALLOCATE=1 -DHAVE_ZLIB_H=1 -I.    -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB  -DSQLITE_ENABLE_EXPLAIN_COMMENTS -DSQLITE_ENABLE_DBPAGE_VTAB -DSQLITE_ENABLE_STMTVTAB -DSQLITE_ENABLE_DBSTAT_VTAB  -g -O2 -MT sqlite3-sqlite3.o -MD -MP -MF .deps/sqlite3-sqlite3.Tpo -c -o sqlite3-sqlite3.o `test -f 'sqlite3.c' || echo './'`sqlite3.c
mv -f .deps/sqlite3-sqlite3.Tpo .deps/sqlite3-sqlite3.Po
/bin/sh ./libtool  --tag=CC   --mode=link gcc -std=gnu11 -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB  -DSQLITE_ENABLE_EXPLAIN_COMMENTS -DSQLITE_ENABLE_DBPAGE_VTAB -DSQLITE_ENABLE_STMTVTAB -DSQLITE_ENABLE_DBSTAT_VTAB  -g -O2   -o sqlite3 sqlite3-shell.o sqlite3-sqlite3.o  -lz -lm -ldl -lpthread
libtool: link: gcc -std=gnu11 -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB -DSQLITE_ENABLE_EXPLAIN_COMMENTS -DSQLITE_ENABLE_DBPAGE_VTAB -DSQLITE_ENABLE_STMTVTAB -DSQLITE_ENABLE_DBSTAT_VTAB -g -O2 -o sqlite3 sqlite3-shell.o sqlite3-sqlite3.o  
-lz -lm -ldl -lpthread
/bin/sh ./libtool  --tag=CC   --mode=compile gcc -std=gnu11 -DPACKAGE_NAME=\"sqlite\" -DPACKAGE_TARNAME=\"sqlite\" -DPACKAGE_VERSION=\"3.40.0\" -DPACKAGE_STRING=\"sqlite\ 3.40.0\" -DPACKAGE_BUGREPORT=\"http://www.sqlite.org\" -DPACKAGE_URL=\"\" -DPACKAGE=\"sqlite\" -DVERSION=\"3.40.0\" -DHAVE_STDIO_H=1 -DHAVE_STDLIB_H=1 -DHAVE_STRING_H=1 -DHAVE_INTTYPES_H=1 -DHAVE_STDINT_H=1 -DHAVE_STRINGS_H=1 -DHAVE_SYS_STAT_H=1 -DHAVE_SYS_TYPES_H=1 -DHAVE_UNISTD_H=1 -DSTDC_HEADERS=1 -DHAVE_DLFCN_H=1 -DLT_OBJDIR=\".libs/\" -DHAVE_FDATASYNC=1 -DHAVE_USLEEP=1 -DHAVE_LOCALTIME_R=1 -DHAVE_GMTIME_R=1 -DHAVE_DECL_STRERROR_R=1 -DHAVE_STRERROR_R=1 -DHAVE_POSIX_FALLOCATE=1 -DHAVE_ZLIB_H=1 -I.    -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB  -g -O2 -MT sqlite3.lo -MD -MP -MF .deps/sqlite3.Tpo -c -o sqlite3.lo sqlite3.c
libtool: compile:  gcc -std=gnu11 -DPACKAGE_NAME=\"sqlite\" -DPACKAGE_TARNAME=\"sqlite\" -DPACKAGE_VERSION=\"3.40.0\" "-DPACKAGE_STRING=\"sqlite 3.40.0\"" -DPACKAGE_BUGREPORT=\"http://www.sqlite.org\" -DPACKAGE_URL=\"\" -DPACKAGE=\"sqlite\" -DVERSION=\"3.40.0\" -DHAVE_STDIO_H=1 -DHAVE_STDLIB_H=1 -DHAVE_STRING_H=1 -DHAVE_INTTYPES_H=1 -DHAVE_STDINT_H=1 -DHAVE_STRINGS_H=1 
-DHAVE_SYS_STAT_H=1 -DHAVE_SYS_TYPES_H=1 -DHAVE_UNISTD_H=1 -DSTDC_HEADERS=1 -DHAVE_DLFCN_H=1 -DLT_OBJDIR=\".libs/\" -DHAVE_FDATASYNC=1 -DHAVE_USLEEP=1 -DHAVE_LOCALTIME_R=1 -DHAVE_GMTIME_R=1 -DHAVE_DECL_STRERROR_R=1 -DHAVE_STRERROR_R=1 -DHAVE_POSIX_FALLOCATE=1 -DHAVE_ZLIB_H=1 -I. -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB -g -O2 -MT sqlite3.lo -MD -MP -MF .deps/sqlite3.Tpo -c sqlite3.c  -fPIC -DPIC -o .libs/sqlite3.o
libtool: compile:  gcc -std=gnu11 -DPACKAGE_NAME=\"sqlite\" -DPACKAGE_TARNAME=\"sqlite\" -DPACKAGE_VERSION=\"3.40.0\" "-DPACKAGE_STRING=\"sqlite 3.40.0\"" -DPACKAGE_BUGREPORT=\"http://www.sqlite.org\" -DPACKAGE_URL=\"\" -DPACKAGE=\"sqlite\" -DVERSION=\"3.40.0\" -DHAVE_STDIO_H=1 -DHAVE_STDLIB_H=1 -DHAVE_STRING_H=1 -DHAVE_INTTYPES_H=1 -DHAVE_STDINT_H=1 -DHAVE_STRINGS_H=1 
-DHAVE_SYS_STAT_H=1 -DHAVE_SYS_TYPES_H=1 -DHAVE_UNISTD_H=1 -DSTDC_HEADERS=1 -DHAVE_DLFCN_H=1 -DLT_OBJDIR=\".libs/\" -DHAVE_FDATASYNC=1 -DHAVE_USLEEP=1 -DHAVE_LOCALTIME_R=1 -DHAVE_GMTIME_R=1 -DHAVE_DECL_STRERROR_R=1 -DHAVE_STRERROR_R=1 -DHAVE_POSIX_FALLOCATE=1 -DHAVE_ZLIB_H=1 -I. -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB -g -O2 -MT sqlite3.lo -MD -MP -MF .deps/sqlite3.Tpo -c sqlite3.c -o sqlite3.o >/dev/null 2>&1
mv -f .deps/sqlite3.Tpo .deps/sqlite3.Plo
/bin/sh ./libtool  --tag=CC   --mode=link gcc -std=gnu11 -D_REENTRANT=1 -DSQLITE_THREADSAFE=1 -DSQLITE_ENABLE_MATH_FUNCTIONS -DSQLITE_ENABLE_FTS4 -DSQLITE_ENABLE_FTS5 -DSQLITE_ENABLE_RTREE -DSQLITE_ENABLE_GEOPOLY -DSQLITE_HAVE_ZLIB  -g -O2 -no-undefined -version-info 8:6:8  -o libsqlite3.la -rpath /home/devdata/.local/lib sqlite3.lo  -lz -lm -ldl -lpthread
libtool: link: gcc -std=gnu11 -shared  -fPIC -DPIC  .libs/sqlite3.o   -lz -lm -ldl -lpthread  -g -O2   -Wl,-soname -Wl,libsqlite3.so.0 -o .libs/libsqlite3.so.0.8.6
libtool: link: (cd ".libs" && rm -f "libsqlite3.so.0" && ln -s "libsqlite3.so.0.8.6" "libsqlite3.so.0")
libtool: link: (cd ".libs" && rm -f "libsqlite3.so" && ln -s "libsqlite3.so.0.8.6" "libsqlite3.so")
libtool: link: ar cr .libs/libsqlite3.a  sqlite3.o
libtool: link: ranlib .libs/libsqlite3.a
libtool: link: ( cd ".libs" && rm -f "libsqlite3.la" && ln -s "../libsqlite3.la" "libsqlite3.la" )
make[1]: Entering directory `/opt/sqlite-autoconf-3400000'
 /bin/mkdir -p '/home/devdata/.local/lib'
 /bin/sh ./libtool   --mode=install /bin/install -c   libsqlite3.la '/home/devdata/.local/lib'
libtool: install: /bin/install -c .libs/libsqlite3.so.0.8.6 /home/devdata/.local/lib/libsqlite3.so.0.8.6
libtool: install: (cd /home/devdata/.local/lib && { ln -s -f libsqlite3.so.0.8.6 libsqlite3.so.0 || { rm -f libsqlite3.so.0 
&& ln -s libsqlite3.so.0.8.6 libsqlite3.so.0; }; })
libtool: install: (cd /home/devdata/.local/lib && { ln -s -f libsqlite3.so.0.8.6 libsqlite3.so || { rm -f libsqlite3.so && ln -s libsqlite3.so.0.8.6 libsqlite3.so; }; })
libtool: install: /bin/install -c .libs/libsqlite3.lai /home/devdata/.local/lib/libsqlite3.la
libtool: install: /bin/install -c .libs/libsqlite3.a /home/devdata/.local/lib/libsqlite3.a
libtool: install: chmod 644 /home/devdata/.local/lib/libsqlite3.a
libtool: install: ranlib /home/devdata/.local/lib/libsqlite3.a
libtool: finish: PATH="/usr/local/bin:/usr/bin:/usr/local/sbin:/usr/sbin:/home/devdata/.local/bin:/home/devdata/bin:/sbin" ldconfig -n /home/devdata/.local/lib
----------------------------------------------------------------------
Libraries have been installed in:
   /home/devdata/.local/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the '-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the 'LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the 'LD_RUN_PATH' environment variable
     during linking
   - use the '-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to '/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------
 /bin/mkdir -p '/home/devdata/.local/bin'
  /bin/sh ./libtool   --mode=install /bin/install -c sqlite3 '/home/devdata/.local/bin'
libtool: install: /bin/install -c sqlite3 /home/devdata/.local/bin/sqlite3
 /bin/mkdir -p '/home/devdata/.local/include'
 /bin/install -c -m 644 sqlite3.h sqlite3ext.h '/home/devdata/.local/include'
 /bin/mkdir -p '/home/devdata/.local/share/man/man1'
 /bin/install -c -m 644 sqlite3.1 '/home/devdata/.local/share/man/man1'
 /bin/mkdir -p '/home/devdata/.local/lib/pkgconfig'
 /bin/install -c -m 644 sqlite3.pc '/home/devdata/.local/lib/pkgconfig'
make[1]: Leaving directory `/opt/sqlite-autoconf-3400000'

[devdata@dev-data sqlite-autoconf-3400000]$ sqlite3 --version
3.31.1 2020-01-27 19:55:54 3bfa9cc97da10598521b342961df8f5f68c7388fa117345eeb516eaa837bb4d6

[devdata@dev-data sqlite-autoconf-3400000]$ sudo echo "alias sqlite3="$HOME/.local/bin/sqlite3"" >> ~/.bashrc

[devdata@dev-data sqlite-autoconf-3400000]$ sudo echo "export LD_LIBRARY_PATH=$HOME/.local/lib:$LD_LIBRARY_PATH" >> ~/.bashrc

[devdata@dev-data sqlite-autoconf-3400000]$ source ~/.bashrc

[devdata@dev-data sqlite-autoconf-3400000]$ sqlite3 --version
3.40.0 2022-11-16 12:10:08 89c459e766ea7e9165d0beeb124708b955a4950d0f4792f457465d71b158d318

[devdata@dev-data sqlite-autoconf-3400000]$ python -c 'import sqlite3; print(sqlite3.sqlite_version)'
3.40.0
