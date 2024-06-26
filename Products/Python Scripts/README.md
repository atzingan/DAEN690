## Table Generation Script User Guide

`HarvestTableGen.exe` and `HunterTableGen.exe` are Windows executable files used to generate data tables for the different Flyway Data Books.
Both of these files can ran directly in a Windows prompt console as commands. Both of these script executables are equipped with a full documented ommandline interface.

Perform the following steps to execute a script for `HarvestTableGen.exe` or `HunterTableGen.exe`):
1. Download the script (with `exe` extension) and save it to a local directory, such as in the `Documents` folder.
2. In Windows, perform a search by typing `cmd` in the Windows search box and open the Windows Prompt console tool.
3. In console, change directory to the Windows folder with the downloaded script executable file.
4. Execute the script by typing the name of the script along with valid arguments and options.
5. An Excel Workbook (XLSX) file is generated in the same directory. Each Excel tab corresponds to a species or group.

### 1. Using HarvestTableGen.exe

For usage instructions, execute the following command in console:

`HarvestTableGen.exe --help`

Script usage intructions will be printed on screen with all available options.
![HarvestTableGen Console](/images/harvest_table_gen_console.png)



The path to the CSV harvest dataset must be passed in as an argument to the scripts.
`.\HarvestTableGen.exe WingData.csv`

**Optional "options" follow the filename argument. Available options include:**
1. `--help` - including this option will print the script usage instructions.
2. `--flyway` - Name of the flyway. Options are `Atlantic Flyway, Mississipi Flyway, Central Flyway, Pacific Flyway`. E.g `--flyway="Pacific Flyway"`. **Values are case sensitive. Default is `Atlatnic Flyway`**.
3. `--season` - Season range to generate. Use the notation <START>:<END>. E.g. `--seaons="1999:2021"`. **Default is ALL**.
4. `--species_name` - A comma seperated list of species or grouping of species to generate tables. Multiple species can be combined together into a named group using the notation <GROUP_NAME>:(<SPECIES#1>, <SPECIES#2>, <SPECIES#3>). E.g. `--species_name="Duck:(Mallard|American Black Duck|Wigeon)"`. Using comma separated notation, additional species can be added following the group declaration. **Values are case sensitive. Default is ALL**.
5. `--species_aou` - A comma seperated list of species AOU or grouping of AOU to generate tables. Multiple species can be combined together into a named group using the notation <GROUP_NAME>:(<AOU#1>, <AOU#2>, <AOU#3>). E.g. `--species_aou="Duck:(ABDU|AGWT|AMWI|COGO|BAGO),BBWD,STEI"`. **Values are case sensitive. If both Species and Species AOU options are used, Species AOU will take precedent. Default is ALL**.

#### Example Usage

1. Generate harvest data tables for Pacific Flyway with seasons from 1999 to 2022 for each species name Mallard, Widgeon:

`HarvestTableGen.exe WingData.csv --flyway="Pacific Flyway" --seasons="1999:2022" --species_name="Mallard,Wigeon'`

2. Generate harvest data tables for Atlantic Flyway for all seasons in the dataset for each species name Mallard, Widgeon:

`HarvestTableGen.exe WingData.csv --flyway="Atlantic Flyway" --species_name="Mallard,Wigeon'`

3. Generate harvest data tables for Atlantic Flyway for all seasons in the dataset for a "Duck" group and other species, using species AOU:

`HarvestTableGen.exe WingData.csv --flyway="Atlantic Flyway" --species_aou="Duck:(ABDU|AGWT|AMWI|COGO|BAGO),BBWD,STEI"`

### 2. Using HunterTableGen.exe

For usage instructions, execute the following command in console:

`HunterTableGen.exe --help`

Script usage intructions will be printed on screen with all available options.
![HunterTableGen Console](/images/hunter_table_gen_console.png)


The path to the CSV harvest dataset must be passed in as an argument to the scripts.
`.\HunterTableGen.exe vw_hunter.csv`

**Optional "options" follow the filename argument. Available options include:**
1. `--help` - including this option will print the script usage instructions.
2. `--flyway` - Name of the flyway. Options are AF, MF, CF, and PF. E.g `--flyway="CF". **Values are case sensitive. Default is AF**.
3. `--season` - Season range to generate. Use the notation <START>:<END>. E.g. `--seaons="1999:2021"`. **Default is ALL**.
4. `--species_group` - A comma seperated list of species groups to generate tables. Possible values are `brant, ducks, geese, sea ducks`. E.g. `--species_group="brant,ducks,geese,sea ducks"`. **Values are case sensitive. Default is ALL.**'

#### Example Usage

1. Generate hunter data tables for Pacific Flyway with seasons from 1999 to 2022 for each species group ducks, brant:

`HarvestTableGen.exe WingData.csv --flyway="Pacific Flyway" --seasons="1999:2022" --species_group="ducks,brant"`

2. Generate harvest data tables for Atlantic Flyway for all seasons in the dataset for all species groups, separately:

`HarvestTableGen.exe WingData.csv --flyway="Atlantic Flyway"`

## Python (Py) Scripts

The script ending with the extension `.py` are program scripts written in Python. These are the code scripts behind the executables `HarvestTableGen.exe` and `HunterTableGen.exe`. They are not needed to execute the `exe` executable files and only made available for reference and/or future code development work to extend current functionalities.


