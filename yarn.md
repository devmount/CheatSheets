# Yarn

## Setup

    yarn init

## Dependencies

### Installation

    yarn

### Adding new dependency

    yarn add [package]
    yarn add [package]@[version]
    yarn add [package]@[tag]
    yarn add [package] --dev
    yarn add [package] --peer
    yarn add [package] --optional

### Upgrading a dependency

    yarn upgrade [package]
    yarn upgrade [package]@[version]
    yarn upgrade [package]@[tag]

### Removing a dependency

    yarn remove [package]

## Update Yarn itself

    curl --compressed -o- -L https://yarnpkg.com/install.sh | bash
