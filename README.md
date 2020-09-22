# ARKEN DOC EXCEL

Package for support excel read/writer in arken platform.

## BUILD

- clone in package directory
```
cd arkenplatform
git clone git@github.com:arkenplatform/arken-doc-excel.git packages/arken-doc-excel
Cloning into 'packages/arken-doc-excel'...
remote: Enumerating objects: 30, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (22/22), done.
remote: Total 30 (delta 10), reused 25 (delta 5), pack-reused 0
Receiving objects: 100% (30/30), 65.68 KiB | 0 bytes/s, done.
Resolving deltas: 100% (10/10), done.
Checking connectivity... done.
```

- build  project

```
mkdir build
cd build
cmake ..
make -j4 (4 is number of cores)

ARKEN BACKEND embedded
ARKEN BASE64 embedded
ARKEN DIGEST embedded
ARKEN MVM CONTAINER deque-stack
etc, etc
PACKAGE: arken-doc-excel
-- Configuring done
-- Generating done
-- Build files have been written to: /home/ariveira/projetos/arken/build

Linking CXX shared library ../../../deps/libexcel.so
Linking CXX shared library ../../../../clib/arken/doc/Excel.so
```

## EXAMPLE
- Create and read xls file

```
local workbook  = Excel.workbook()
local worksheet = workbook:addWorksheet("worksheet-1")
local cell      = worksheet:cell(1, 1)
cell:setString("Hello World !")
workbook:save("myfile.xls")

local workbook1  = Excel.workbook()
workbook1:load("myfile.xls")
local worksheet1 = workbook:getWorksheet("worksheet-1")
local cell1      =  worksheet1:cell(1, 1)

assert( cell1:getString() == "Hello World !", cell1:getString() )
```
- more examples in tests directory

## LICENSE
This project is licensed under the CPOL License - see the [LICENSE.md](LICENSE.md) file for details
