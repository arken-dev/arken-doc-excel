# CHARON DOC EXCEL

Package for support excel read/writer in charon platform.

## BUILD

clone in package directory

cd charonplatform/packages
git clone git@github.com:charonplatform/charon-doc-excel.git
cd charonplatform
- mkdir build
- cd build
- cmake ..
- make -j4 (4 is number of cores)

### Examples
- Create and read xls file

```
local workbook  = Excel.workbook()
local worksheet = workbook:addWorksheet("Planilha1")
local cell      = worksheet:cell(1, 1)
cell:setString("Hello World !")
workbook:save("myfile.xls")

local workbook1  = Excel.workbook()
workbook1:load("myfile.xls")
local worksheet1 = workbook:getWorksheet("Planilha1")
local cell1      =  worksheet1:cell(1, 1)

assert( cell1:getString() == "Hello World !", cell1:getString() )
```
more examples in tests directory

##LICENSE
This project is licensed under the CPOL License - see the [LICENSE.md](LICENSE.md) file for details
