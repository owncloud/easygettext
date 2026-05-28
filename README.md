# easygettext

<!-- OSPO-managed README | Generated: 2026-04-16 | v2 -->

[![License](https://img.shields.io/badge/License-See%20Repository-blue.svg)](LICENSE) [![ownCloud OSPO](https://img.shields.io/badge/OSPO-ownCloud-blue)](https://kiteworks.com/opensource)

A fork of the [Polyconseil/easygettext](https://github.com/Polyconseil/easygettext) library providing simple gettext token extraction tools for HTML, Jade/Pug, JavaScript/ES7+, Vue, TypeScript, and Nativescript Vue files. It also includes a PO-to-JSON converter for use in frontend internationalization workflows.

> **Note:** This repository is in maintenance/legacy mode and is no longer actively developed.

## Getting Started

Install via npm:

```bash
npm install --save-dev easygettext
```

Extract gettext tokens from templates:

```bash
gettext-extract --output dictionary.pot foo.html bar.pug component.vue
```

Convert PO files to JSON:

```bash
gettext-compile --output translations.json fr.po en.po
```

## Documentation

- [npm package](https://www.npmjs.com/package/easygettext)
- [Upstream repository](https://github.com/Polyconseil/easygettext)

## Features

Capabilities of the gettext extraction toolchain:

### Supported File Types

- HTML
- Jade/Pug
- JavaScript/ES7+
- Vue (both `<template>` and `<script>` sections)
- TypeScript
- Nativescript Vue

### Token Extraction (`gettext-extract`)

Extract translatable strings from source files into a POT dictionary:

```bash
gettext-extract --output dictionary.pot foo.html bar.pug component.vue sourcefile.js
```

**CLI options:**

```
gettext-extract [--attribute EXTRA-ATTRIBUTE] [--filterPrefix FILTER-PREFIX]
                [--output OUTFILE] [--parser auto|acorn|babel] <FILES>
```

Recognized token formats include `<div translate>`, `<get-text>`, `<i18n>`, `<translate>`, Angular filter expressions (`{{ 'text' | translate }}`), and JavaScript functions (`$gettext()`, `$pgettext()`, `$ngettext()`).

Custom master tokens can be provided via `--attribute`:

```bash
gettext-extract --attribute v-translate --output dictionary.pot foo.html
```

Use `--parser babel` for optional-chaining, nullish-coalesce, or other Babel plugins.

### PO-to-JSON Compilation (`gettext-compile`)

Convert PO files to a sanitized JSON format for frontend use:

```bash
gettext-compile --output translations.json fr.po en.po de.po
```

### Vue Component Extraction

Translatable strings inside both `<template>` and `<script>` sections of `.vue` files are extracted using the same rules as HTML and JavaScript extraction.

### Multi-File Extraction

Use the UNIX `find` command to extract from all files in a folder:

```bash
gettext-extract --attribute v-translate --output dictionary.pot $(find src/components -type f -name '*.vue')
```

## Part of ownCloud Infrastructure

This is a forked utility library used in the ownCloud build toolchain for extracting translatable strings from frontend source files.

> **Note:** This repository is currently in Archived/Legacy mode. It is a fork of [Polyconseil/easygettext](https://github.com/Polyconseil/easygettext) and is no longer actively maintained.

## Community & Support

**[Star](https://github.com/owncloud/easygettext)** this repo and **Watch** for release notifications!

- [ownCloud Website](https://owncloud.com)
- [Community Discussions](https://github.com/orgs/owncloud/discussions)
- [Matrix Chat](https://app.element.io/#/room/#owncloud:matrix.org)
- [Documentation](https://doc.owncloud.com)
- [Enterprise Support](https://owncloud.com/contact-us/)
- [OSPO Home](https://kiteworks.com/opensource)

## Contributing

We welcome contributions! Please read the [Contributing Guidelines](CONTRIBUTING.md)
and our [Code of Conduct](CODE_OF_CONDUCT.md) before getting started.

### Workflow

- **Rebase Early, Rebase Often!** We use a rebase workflow. Always rebase on the target branch before submitting a PR.
- **Dependabot**: Automated dependency updates are managed via Dependabot. Review and merge dependency PRs promptly.
- **Signed Commits**: All commits **must** be PGP/GPG signed. See [GitHub's signing guide](https://docs.github.com/en/authentication/managing-commit-signature-verification).
- **DCO Sign-off**: Every commit must carry a `Signed-off-by` line:
  ```
  git commit -s -S -m "your commit message"
  ```
- **GitHub Actions Policy**: Workflows may only use actions that are (a) owned by `owncloud`, (b) created by GitHub (`actions/*`), or (c) verified in the GitHub Marketplace.

## Security

**Do not open a public GitHub issue for security vulnerabilities.**

Report vulnerabilities at **<https://security.owncloud.com>** -- see [SECURITY.md](SECURITY.md).

Bug bounty: [YesWeHack ownCloud Program](https://yeswehack.com/programs/owncloud-bug-bounty-program)

## License

See [LICENSE](LICENSE) for license details.

## About the ownCloud OSPO

The [Kiteworks Open Source Program Office](https://kiteworks.com/opensource), operating under
the [ownCloud](https://owncloud.com) brand, launched on May 5, 2026, to steward the open source
ecosystem around ownCloud's products. The OSPO ensures transparent governance, license compliance,
community health, and sustainable collaboration between the open source community and
[Kiteworks](https://www.kiteworks.com), which acquired ownCloud in 2023.

- **OSPO Home**: <https://kiteworks.com/opensource>
- **GitHub**: <https://github.com/owncloud>
- **ownCloud**: <https://owncloud.com>

For questions about the OSPO or licensing, contact ospo@kiteworks.com.

### License Migration to Apache 2.0

The OSPO is driving a strategic relicensing of ownCloud repositories toward the
[Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0), following
the [Apache Software Foundation's third-party license policy](https://www.apache.org/legal/resolved.html).

Individual repositories will migrate as their audit is completed. The LICENSE file
in each repo reflects its **current** license status (not the target).

**Current license: Not detected.** The OSPO will determine the current license status of this
repository before planning any migration steps. If you know the intended license, please open an
issue or contact ospo@kiteworks.com.
