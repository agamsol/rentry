### 🧾 RENTRY API - Batch Version
> [rentry.org](https://rentry.org/) is markdown-powered pastebin/publishing service with preview, custom urls and editing.
>
> This repository contains a simple script that allows pasting and editing from command line interface.

##### ⚠️ PLEASE NOTE:
**The script in this repository was not made by the official authors of [rentry.org](https://rentry.org/) and it is a replica for the repository of [radude/rentry](https://github.com/radude/rentry). what makes it different is the language used in the 2 repositories.**
> Same purpose - based on different language.

#### DEPENDENCIES
> These depencies apply to rentry.cmd version 1.0.0.4
- Powershell 3.0 ([according to microsoft docs](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/convertfrom-json?view=powershell-7.2#:~:text=See%20other%20examples%20below.,cmdlet%20supports%20JSON%20with%20comments.))
- cURL Must be added to path.

    assuming that curl is pre-installed in windows **since Windows 10, version 1803 or later** you should be ok (else you'd want to specify a curl installation using the `--curl` flag)
- [rentry.org](https://rentry.org/) must be online to use this script.

### 📫 Download the API
- Download the [API's Source code](https://github.com/agamsol/rentry/blob/main/rentry.cmd) and save it in a folder
- Copy the path to the folder
- open a cmd window
- type `cd /d "<paste_path_here>"`
- after this you can use the API by calling its file name.

### ❓ USING THE API
#### Primary commands
- `--help`     View the help page - Default page in a case non of the primary commands were specified
- `--new`      Create new entry
- `--edit`     Edit existing entry
- `--delete`   Delete existing entry
- `--raw`      Display a paste as RAW
- `--if-exist` Check if entry exists at all

#### Options (Sub Commands)
_NOTE: The order of specified options does not matter and all options are recorded._
-  `--url <entry>`                    Specify a URL
-  `--edit-code <code>`               Specify code to edit or delete the entry
-  `--file "<file.txt>"`              Specify path to file to upload or to output the RAW function
-  `--curl "full\path\to\curl.exe"`   Specify custom curl installation file

Below I made a small chart for the required options for each primary command.

In each case of use at least 1 primary command should be specified.
the primary commands are the ones in the first row of the chart
the first column shows the sub commands that each primary command needs.

USAGE | `--help` | `--new` | `--edit` | `--delete` | ``--raw`` | `--if-exist` |
:----: | :------: | :---: |:----: | :------: | :---: | :--: |
`--url`   | <span style="color:green">not needed</span> | <span style="color:orange">optional</span> | <span style="color:red">required</span> | <span style="color:red">required</span> | <span style="color:red">required</span> | <span style="color:red">required</span> |
`--edit-code` | <span style="color:green">not needed</span>  | <span style="color:orange">optional</span> | <span style="color:red">required</span> | <span style="color:red">required</span> | <span style="color:green">not needed</span> | <span style="color:green">not needed</span> |
`--file`   | <span style="color:green">not needed</span>  | <span style="color:red">required</span> | <span style="color:red">required</span> | <span style="color:green">not needed</span> | <span style="color:orange">optional</span> | <span style="color:green">not needed</span> |
`--curl`   | <span style="color:green">not needed</span>  | <span style="color:orange">optional</span> | <span style="color:orange">optional</span> | <span style="color:orange">optional</span> | <span style="color:orange">optional</span> | <span style="color:orange">optional</span> |

Example for reading the chart:
- To use the `--edit` function you must specify a `--url`, `--edit-code` and `--file`

#### EXAMPLES OF USE
- `call rentry.cmd --new --file "file.txt"`
    - Create new entry and POST the content inside file.txt in it.

- `call rentry.cmd --new --url myurl --edit-code mycode --file file.txt`
    - Create new entry with custom URL and code and POST

- `call rentry.cmd --edit --url myurl --edit-code mycode --file "file.txt"`
    - Edit entry using its url and code and replace the content with the new one in the file

- `call rentry.cmd --delete --url myurl --edit-code mycode`
    - Delete the entry using its url and code.

- `call rentry.cmd --raw --url myurl`
    - Display the paste's text in the terminal

- `call rentry.cmd --raw --url myurl --file "file.txt"`
    - Save the entry's content to a file.

- `call rentry.cmd --if-exist --url myurl`
    - Check if entry exists using its URL

##### Example to specify curl installation file
- `call rentry.cmd --raw --url myurl --curl "C:\Users\Agam\Desktop\files\curl.exe"`
    - use specified curl version to perform the raw command

#### 📝 Change Log

#### What has changed at version 1.0.0.4 (This Version)
- Support new domain of rentry (rentry.org)
- Reduced code using a BaseURL variable
- New Entry Creation Format: [ URL={URL} ] [ EDIT_CODE={EDIT_CODE} ]

<details>
    <summary>🔎 View older versions</summary>

#### What has changed at version 1.0.0.3
- Removed part of label in line which could cause problems in some cases

#### What has changed at version 1.0.0.2
- Added errorlevels for all exit cases (0 = success | 1 = error)

#### What has changed at version 1.0.0.1
- Added new flag `--if-exist` - this helps to check if entry exists at all by returning an `Ok`
- Fixed forgotten line where printed debugging issues
- Fixed Code-Page issues
- Fixed custom cURL spaces path

</details>

#### Contact information and support 📚
> Feel free to contact me in discord, <span style="color:#7289DA">Agam#0001</span>

> Im also available in the [r/batch discord server](https://discord.gg/gPMcxXZjkb). **(you can and should ping me there)**
