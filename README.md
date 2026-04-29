# cffjs

[![cffjs on npm](https://img.shields.io/npm/v/cffjs.svg)](https://www.npmjs.com/package/cffjs)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/continuous-foundation/cffjs/blob/main/LICENSE)
![CI](https://github.com/continuous-foundation/cffjs/workflows/CI/badge.svg)

Types and utilities for working with [`CITATION.cff`](https://github.com/citation-file-format/citation-file-format) files in TypeScript.

The Citation File Format provides citation metadata for software and datasets in YAML.

## Install

```bash
npm install cffjs
```

## Usage

```ts
import { readCFF, writeCFF, validateCFF } from 'cffjs';

const cff = readCFF('./CITATION.cff');

validateCFF(cff);

writeCFF(cff, './output');
```

## API

### Reading & Writing

- `readCFF(file)` - Read CFF data from a `CITATION.cff` file (or directory containing one). Returns the parsed object without validation.
- `writeCFF(cff, directory)` - Write CFF data as `CITATION.cff` into the given directory, creating it if needed.

### Validating

- `validateCFF(input)` - Validate an in-memory CFF object against the CFF 1.2.0 JSON schema. Throws on failure.
- `validateCFFFile(file)` - Read a CFF file and validate it. Throws on failure.

### MyST Conversion

Convert [MyST](https://mystmd.org) frontmatter into CFF data:

- `mystFrontmatterToCFF(frontmatter, abstract?)` - Convert MyST `PageFrontmatter` into a complete CFF document.
- `mystFrontmatterToCFFReference(frontmatter, abstract?)` - Convert MyST `PageFrontmatter` into a CFF `Reference` entry.

### Types

The package exports TypeScript types for `CFF`, `ReferenceCFF`, `PersonCFF`, `EntityCFF`, and `IdentifierCFF`, along with the `ReferenceType` and `ReferenceStatus` enums.

## Scope

- Reading, writing, and validating `CITATION.cff` files
- Conversion from MyST frontmatter to CFF
- CFF version 1.2.0 only

### Potential goals

- Conversion to MyST frontmatter
- Support for other CFF versions
- Conversion to/from other formats (e.g. BibTeX)
- CLI

<p style="text-align: center; color: #aaa; padding-top: 50px">
  Made with love by
  <a href="https://continuous.foundation" target="_blank" style="color: #aaa">
    Continuous Science Foundation <img src="https://cdn.curvenote.com/static/site/csf/icon.svg" style="height: 1em" />
  </a>
</p>
