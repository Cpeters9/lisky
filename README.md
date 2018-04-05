# Lisk Commander

Lisk Commander allows you to communicate with a remote or local node and carry out Lisk-related functionality using an interactive or non-interactive command line tool.

[![Build Status](https://jenkins.lisk.io/buildStatus/icon?job=lisk-commander/development)](https://jenkins.lisk.io/job/lisk-commander/job/development/)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)
<a href="https://david-dm.org/LiskHQ/lisk-commander"><img src="https://david-dm.org/LiskHQ/lisk-commander.svg" alt="Dependency Status"></a>
<a href="https://david-dm.org/LiskHQ/lisk-commander/?type=dev"><img src="https://david-dm.org/LiskHQ/lisk-commander/dev-status.svg" alt="devDependency Status"></a>

## Prerequisites

Lisk Commander requires [Node.js](https://nodejs.org/) as the underlying engine for code execution. Node.js is supported on most operating systems. Follow the instructions for your operating system on the [Node.js downloads page](https://nodejs.org/en/download/). You will need version 6.11.x or higher. NPM is automatically installed along with Node.js.

## Installation

### From NPM

```sh
$ npm install --global --production lisk-commander
```

Upon successful completion, NPM will add the `lisk-commander` executable to your PATH.

### From Source

Clone the Lisk Commander repository using Git and install the dependencies:

```sh
$ git clone https://github.com/LiskHQ/lisk-commander.git
$ cd lisk-commander
$ npm install
```

Before running the executable you will need to build Lisk Commander:

```sh
npm run build
```

#### Adding the Lisk Commander executable to your PATH

WARNING: If you have installed Lisk Commander globally via NPM (see [Install Lisk Commander via NPM](docs:lisk-commander-installation-npm)), following the instructions in this section is not recommended as they will introduce conflicts.

If you would like to add the `lisk` executable to your PATH you have two options: option 1 will install the current state of the code you are installing globally, while option 2 will only link to the code and therefore automatically reflect changes you make going forward.

##### 1. Install globally

Running this command from within the repository will add Lisk Commander to your global NPM packages, and add the `lisk` executable to your PATH. Be aware that any previous globally installed Lisk Commander version will get overridden with this local version.

```sh
$ npm install --global --production
```

Note that you will have to repeat this process for each subsequent build of Lisk Commander.

##### 2. Create a symlink

The other option is to ask NPM to create a symlink in the global folder that links to the package.

```sh
$ npm link
```

This will also add `lisk` to your PATH, but you won't have to repeat the process if you pull or create a new build. Be aware that any previous globally installed Lisk Commander version will get overridden with this local version.

## Usage

### Interactive use

To run commands interactively:

```sh
$ lisk
 _      _     _       _____                                          _
| |    (_)   | |     / ____|                                        | |
| |     _ ___| | __ | |     ___  _ __ ___  _ __ ___   __ _ _ __   __| | ___ _ __
| |    | / __| |/ / | |    / _ \| '_ ` _ \| '_ ` _ \ / _` | '_ \ / _` |/ _ \ '__|
| |____| \__ \   <  | |___| (_) | | | | | | | | | | | (_| | | | | (_| |  __/ |
|______|_|___/_|\_\  \_____\___/|_| |_| |_|_| |_| |_|\__,_|_| |_|\__,_|\___|_|

Running v0.3.0.
Type `help` to get started.

lisk> help

  Commands:

    help [command...]                    Provides help for a given command.
    exit                                 Exits Lisk Commander.
    env                                  Print environmental configuration.
    get [options] <type> <input>         Get information from <type> with parameter <input>.
                                         Types available: account, address, block, delegate, transaction
                                         E.g. get delegate lightcurve
                                         e.g. get block 5510510593472232540
    list [options] <type> <variadic...>  Get information from <type> with parameters <input, input, ...>.
                                         Types available: accounts, addresses, blocks, delegates, transactions
                                         E.g. list delegates lightcurve tosch
                                         E.g. list blocks 5510510593472232540 16450842638530591789
    set <variable> <value>               Set configuration <variable> to <value>. Configuration is
                                         persisted in `~/.lisk-commander/config.json`.
lisk>
```

### Non-interactive use

To run commands and options directly from the command line:

```sh
$ lisk get delegate lightcurve --json
```

## Settings

Configuration is stored in a config file placed in the user's home directory (run `help set` to see the exact location). If this is unavailable a default configuration is used. The following settings can be updated (and will be persisted if possible):

| Command                                  | Description                                               |
| ---------------------------------------- | --------------------------------------------------------- |
| <code>set json true&#124;false</code>    | Sets default to JSON output (true) or text output (false) |
| <code>set testnet true&#124;false</code> | Set default to testnet (true) or mainnet (false)          |

## Documentation

Further information can be found on our documentation site:

* [Introduction](https://docs.lisk.io/v1.3/docs/lisk-commander-introduction)
* [Pre-Installation](https://docs.lisk.io/v1.3/docs/lisk-commander-pre-installation)
* [Installation](https://docs.lisk.io/v1.3/docs/lisk-commander-installation)
  * [Install-from-NPM](https://docs.lisk.io/v1.3/docs/lisk-commander-installation-npm)
  * [Install-from-Source](https://docs.lisk.io/v1.3/docs/lisk-commander-installation-source)
* [Upgrading](https://docs.lisk.io/v1.3/docs/lisk-commander-upgrading)
  * [Upgrading-from-NPM](https://docs.lisk.io/v1.3/docs/lisk-commander-upgrading-npm)
  * [Upgrading-from-Source](https://docs.lisk.io/v1.3/docs/lisk-commander-upgrading-source)
* [Usage](https://docs.lisk.io/v1.3/docs/lisk-commander-usage)
  * [Configuration](https://docs.lisk.io/v1.3/docs/lisk-commander-usage-configuration)
  * [Usage](https://docs.lisk.io/v1.3/docs/lisk-commander-usage-interactive-and-noninteractive)
  * [Commands](https://docs.lisk.io/v1.3/docs/lisk-commander-usage-commands)

## Get Involved

Lisk Commander is an open-source project and all contributions are welcome.

If you find a bug or want to make feature request, please create an [issue](https://github.com/LiskHQ/lisk-commander/issues) with as much detail as you can.

## Run Tests

Lisk Commander has an extensive set of unit tests. To run the tests, please install Lisk Commander from source, and then run the command:

```sh
$ npm test
```

## Contributors

https://github.com/LiskHQ/lisk-commander/graphs/contributors

## License

Copyright © 2017–2018 Lisk Foundation

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the [GNU General Public License][license]
along with this program. If not, see <http://www.gnu.org/licenses/>.

[license]: https://github.com/LiskHQ/lisk-commander/tree/master/LICENSE
