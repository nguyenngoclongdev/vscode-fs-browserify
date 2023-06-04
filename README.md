[![CI](https://github.com/nguyenngoclongdev/vscode-fs-browserify/actions/workflows/ci.yml/badge.svg)](https://github.com/nguyenngoclongdev/vscode-fs-browserify/actions/workflows/ci.yml)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/nguyenngoclongdev/vscode-fs-browserify/)

[![npm version](https://img.shields.io/npm/v/@vscode-utility/fs-browserify.svg?style=flat-square)](https://www.npmjs.org/package/@vscode-utility/fs-browserify)
[![Gitpod Ready-to-Code](https://img.shields.io/badge/Gitpod-Ready--to--Code-blue?logo=gitpod&style=flat-square)](https://gitpod.io/#https://github.com/nguyenngoclongdev/vscode-fs-browserify)
[![install size](https://img.shields.io/badge/dynamic/json?url=https://packagephobia.com/v2/api.json?p=@vscode-utility/fs-browserify&query=$.install.pretty&label=install%20size&style=flat-square)](https://packagephobia.now.sh/result?p=@vscode-utility/fs-browserify)
[![npm bundle size](https://img.shields.io/bundlephobia/minzip/@vscode-utility/fs-browserify?style=flat-square)](https://bundlephobia.com/package/@vscode-utility/fs-browserify@latest)
[![npm downloads](https://img.shields.io/npm/dt/@vscode-utility/fs-browserify.svg?style=flat-square)](https://npm-stat.com/charts.html?package=@vscode-utility/fs-browserify)
[![Known Vulnerabilities](https://snyk.io/test/npm/@vscode-utility/fs-browserify/badge.svg)](https://snyk.io/test/npm/@vscode-utility/fs-browserify)

# @vscode-utility/fs-browserify

When developing vscode extensions, it is essential to ensure compatibility between the desktop and web versions of vscode (https://vscode.dev or https://github.dev).

Using `@vscode-utility/fs-browserify`, you can access and manipulate files stored locally or remotely, making it easier to develop vscode extensions that work seamlessly on both the desktop and web versions of vscode.

This library utilizes a portion of the [File System](https://code.visualstudio.com/api/references/vscode-api#FileSystem) provided by the [VS Code API](https://code.visualstudio.com/api/references/vscode-api).

If you find this package useful for your projects, please consider supporting me by [Buy Me a Coffee](https://ko-fi.com/D1D2LBPX9). It's a great way to help me maintain and improve this package in the future. Your support is truly appreciated!

<a href='https://ko-fi.com/D1D2LBPX9' target='_blank'>
    <img height='36' style='border:0px;height:36px;' src='https://storage.ko-fi.com/cdn/kofi3.png?v=3' border='0' alt='Buy Me a Coffee' />
</a>

## Installation

**npm**

```sh
npm install @vscode-utility/fs-browserify
```

**yarn**

```sh
yarn add @vscode-utility/fs-browserify
```

**pnpm**

```sh
pnpm add @vscode-utility/fs-browserify
```

## Usage

```typescript
import { fs } from '@vscode-utility/fs-browserify';

// Retrieve file metadata
await fs.statAsync(path);

// Retrieve all directory entries
await fs.readDirectoryAsync(path);

// Create a new directory
await fs.createDirectoryAsync(path);

// Read the full content of a file
await fs.readFileAsync(path, options);

// Append the provided data to a file
await fs.appendFileAsync(path, content);

// Write data to a file and replace its full contents
await fs.writeFileAsync(path, content);

// Delete a file
await fs.deleteAsync(path, options);

// Rename a file or folder
await fs.renameAsync(source, target, options);

// Copy files or folders
await fs.copyAsync(source, target, options);

// Check if a given path exists or not in the file system
await fs.existAsync(source);

// Truncates the file to change the size of the file i.e either increase or decrease the file size
await fs.existAsync(path, length);

// Check the permissions of a given file
fs.access(path);
```

## Compare functions

| @vscode-utility/fs-browserify | fs (node)         | fs (vscode api)        |
| ----------------------------- | ----------------- | ---------------------- |
| fs.`statAsync`()              | fs.`stat`()       | fs.`stat`()            |
| fs.`readDirectoryAsync`()     | fs.`readDir`()    | fs.`readDirectory`()   |
| fs.`createDirectoryAsync`()   | fs.`mkdir`()      | fs.`createDirectory`() |
| fs.`readFileAsync`()          | fs.`readFile`()   | fs.`readFile`()        |
| fs.`appendFileAsync`()        | fs.`appendFile`() | <sub>undefined</sub>   |
| fs.`writeFileAsync`()         | fs.`writeFile`()  | fs.`writeFile`()       |
| fs.`deleteAsync`()            | fs.`rmdir`()      | fs.`delete`()          |
| fs.`renameAsync`()            | fs.`rename`()     | fs.`rename`()          |
| fs.`copyAsync`()              | fs.`cp`()         | fs.`copy`()            |
| fs.`existAsync`()             | fs.`exist`()      | <sub>undefined</sub>   |
| fs.`truncateAsync`()          | fs.`truncate`()   | <sub>undefined</sub>   |
| fs.`watch`()                  | fs.`watch`()      | <sub>undefined</sub>   |
| fs.`access`()                 | fs.`access`()     | <sub>undefined</sub>   |

-   @vscode-utility/fs-browserify

    -   Provides seamless compatibility for both the desktop and web versions of VS Code
    -   Supports additional functions that are missing from the [File System API](https://code.visualstudio.com/api/references/vscode-api#FileSystem)

-   fs (node)

    -   Only works with the desktop version of VS Code

-   fs (vscode api)

    -   Missing some necessary functions for the File System

## Feedback

If you discover a bug, or have a suggestion for a feature request, please
submit an [issue](https://github.com/nguyenngoclongdev/vscode-fs-browserify/issues).

## LICENSE

This extension is licensed under the [MIT License](LICENSE)
