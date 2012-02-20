rhelp is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

rhelp is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with rhelp. If not, see <http://www.gnu.org/licenses/>.


rhelp
====================================
rhelp is a simple tool to replace file and folder names with spaces, special characters and symbols.

Author
------------------------------------
Alejandro El Informático

Requirements
------------------------------------
* Perl v5.0 or any later release.

**NOTE:** rhelp use 'File::Find' and 'Win32::File' dependencies for Win systems.
You should have it by default with your installation of Perl on Win systems.

Configuration
------------------------------------
There is no pre-determined configuration. If you have problems,
edit the first line of rhelp and change the path to your Perl installation path.
If you are on Win systems, you should probably uncomment the lines that check hidden files and folders in Win system.

Installation
------------------------------------
There is no installation option but if you want to use rhelp "anywhere" copy it to your binaries path.

Usage
------------------------------------
`rhelp [args] [path]`

### Args
    -min=[int]   minimum depth level.
    -max=[int]   maximum depth level.
    -c           replace special characters.
    -s           replace spaces. End line spaces will be removed.
    -m           replace simbols. Use a separated find function.
    -a           replace special characters, spaces and symbols at the same time.
    -p           show path to file/folder.
    -hidden      search for hidden files and folders.(USE IT WITH CAUTION)
    -R           Replacement mode.(USE IT WITH CAUTION)
    -B           reverse the replacement, using rhelp.backup file.
    -h           print help.
    -v           print version.

Important
------------------------------------
in `-R` mode it will create a file named `rhelp.backup` inside the folder you designated. In it are the original and replaced names with absolute path.
Please do not delete this file unless you are sure that replaced names are correct and did not break any files or folders.

`-B` mode need the path to `rhelp.backup` file.

with `-hidden` flag it will search for hidden files and folders, be sure to use it with caution, it can break any system folder or file.
if you want to perform the replacement within a hidden folder, use `-hidden` and pass the name of the hidden folder as the path.
_i.e:_
`rhelp -s -m -hidden .hiddenFolder/`

If you don't use `-a`, rhelp will count any change as a change.
_i.e:_
`my folder$`

will count two changes:
`my-folder$`
`my folder`

Addtional information
------------------------------------
If you have not copied rhelp to your binaries path, you can use:
`perl rhelp`
`./rhelp` (UNIX systems)

You can use 'pipes' and 'redirections', depending your system.
_i.e:_
`rhelp -c -s test/ > log` (all systems)
`rhelp -s test/ | grep "myFolder"` (UNIX systems)
