clowder-common-bash
===================

Simple client access helper functions for the configuration for the Clowder operator

**Please note** this is a work in progress and it's in a very early stage, function names, output format, and structure of returned data is likely to change

Prerequisites
-------------

[jq](https://stedolan.github.io/jq) is required to extract data (however it is not required to detect whether if the ClowderEnvironment is active or not.

Bash version >= 4 is **recommended** as future releases will make use of hashmaps

Usage
-----

To access the different configuration, load the `clowder-config-main` file in your shell

```
curl -o https://raw.githubusercontent.com/Victoremepunto/clowder-common-bash/master/clowder-config-main >> clowder-config-main && source clowder-config-main
```

Then try and run some commands:

```bash

$ isClowderEnabled
# would return 0 or 1 whether if the Clowder environment is detected

# returns the webPort key of the Clowder config map
$ ClowderConfigWebPort
8080
```

Test
----

Give it a quick test run with the help of the included `test.json` file

```
ACG_CONFIG="test.json" isClowderEnabled && ClowderConfigWebPort
```
