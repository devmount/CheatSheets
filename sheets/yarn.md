# Yarn

## Setup

```bash
yarn init
```

## Dependencies

### Installation

```bash
yarn
```

### Adding new dependency

```bash
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
yarn add [package] --dev
yarn add [package] --peer
yarn add [package] --optional
```

### Upgrading a dependency

```bash
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

### Removing a dependency

```bash
yarn remove [package]
```

## Update Yarn itself

For Yarn v1.x and v2.x:

```bash
curl --compressed -o- -L https://yarnpkg.com/install.sh | bash
```

## Clear Cache

```bash
yarn cache clean
```
