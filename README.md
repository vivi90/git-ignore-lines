# Line ignores for Git
Sometimes it's required to ignore some lines in files (for example auth keys in configuration files).

## How to clone
 1. Fork this repository.
 2. Clone it.
 3. Add the filter by issuing the following commands:
 ```bash
 git config filter.ignorelines.clean "grep -Evi \$(cat .gitignorelines | tr -d '\r' | sed -z '$ s/\n$//' | tr '\n' '|')"
 git config filter.ignorelines.smudge "cat"
 ```
 4. Test it.
 5. Remove the example file `example.ini` and edit `.gitignorelines`.
 11. Use it :-)

## Good to know
 - The filter works case-insensitive.
 - All keywords inside the `.gitignorelines` file are working as partial matches.
 - The `.gitignorelines` file doesn't support comments inside it.
 - The `|` character is used as an delimiter for the `grep` command, 
   so please avoid using it inside the `.gitignorelines` file.

## Based on
 - [Kache](https://stackoverflow.com/users/234593/kache)'s approach: https://stackoverflow.com/a/16244970/3699361 (License: CC BY-SA 4.0)
 - [Janito Vaqueiro Ferreira Filho](https://stackoverflow.com/users/1687321/janito-vaqueiro-ferreira-filho)'s `grep` usage: https://stackoverflow.com/a/12760691/3699361 (License: CC BY-SA 3.0)
 - [Tom Hale](https://stackoverflow.com/users/5353461/tom-hale)'s `sed` usage: https://stackoverflow.com/a/58129173/3699361 (License: CC BY-SA 4.0)
## License
This project is free software under the terms of the CC BY 4.0 license.
For more details please see the LICENSE file or: [Creative Commons](http://creativecommons.org/licenses/by/4.0)

## Credits
 * 2021 by Vivien Richter <vivien-richter@outlook.de>
 * Git repository: [GitHub](https://github.com/vivi90/git-ignore-lines.git)
