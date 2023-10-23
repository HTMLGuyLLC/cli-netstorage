Akamai CLI for Netstorage

*NOTE REGARDING MAINTAINING THIS PACKAGE:* The CLI-NetStorage package is currently no longer officially maintained by Akamai's engineering teams. The package still works but there will be no ongoing maintenance or features added. This package will receive occasional vulnerability scanning to upgrade third-party libraries to newer versions with minimal testing. Use at your own risk. We recommend the use of the NetStorage Usage API instead: https://techdocs.akamai.com/netstorage-usage/reference/api - Last Update: October 2023.

*NOTE:* This tool is intended to be installed via the Akamai CLI package manager, which can be retrieved from the releases page of the [Akamai CLI](https://github.com/akamai/cli) tool.

*NOTE:* This tool is only supported for use with ObjectStore, not with the older FileStore system.  Any use of the tool to work with FileStore directories is unsupported.

### Credentials
* Various values associated with the Storage Group and Upload Account are required for use in calls made to the API. Once the Upload Account has fully propagated (after enabling the HTTP API), you can view it in the NetStorage Groups UI to gather this information. Select the Upload Account entity.
* Locate the Upload Account in which you've enabled the NetStorage HTTP API, and click it to open Detail View. (You can type the name of the target account in the Filter field to limit results in this table.)
* Click the Edit button.

Make note of the following values:
* The "*Key*" Value - 
  * Under "Upload Accounts" select the account
  * Click the "edit" icon in the upper right
  * Under "Access methods" click the Netstorage HTTP CMS API tab
  * The key is in the resulting table
* The "*Id*" in the Upload Account Details content panel.  
* The Storage Group Name (*group*) - This is revealed in the second column of the table in the Upload Directory Association content panel.

Select the Storage Groups entity.
* Input the Storage Group Name you noted in the Filter field.
* Click its entry in the table to open Detail View.
* In the Storage Group Details, make note of the NetStorage HTTP API entry for the *host* entry

Once you have gathered all the values, run 'akamai netstorage setup' to save them to your system.

## Overview
The Akamai Netstorage CLI is a utility for interacting with Akamai's NetStorage platform from the command line.  

```
Usage: akamai netstorage <command> <args> [options]

Commands:
  setup                     Setup authentication for Netstorage
  du                        disk usage stats
  mkdir <directory>         create a new directory
  rmdir <directory>         delete a directory
  dir <directory>           view a directory structure
  quick-delete <directory>  recursively delete a directory
  list <directory>          view a directory listing
  upload <file>             upload a file
  download <file>           download a file
  delete <file>             delete a file
  rename <file> <location>  rename/move a file
  symlink <file> <target>   create a symlink
  mtime <file>              update modification time for a file
  stat <file>               see file information

Command options:
  --config <config>    Config file
                       [file] [default: ~/.akamai-cli/.netstorage/auth]

  --section <section>  Section for config file
                       [string] [default: default]

  --cpcode <cpcode>    Default CPCode
                       [string]

  --help               Show help
                       [commands: help] [boolean]

  --version            Show version number
                       [commands: version] [boolean]
```
Copyright (C) Akamai Technologies, Inc
Visit http://github.com/akamai/cli-netstorage for detailed documentation
