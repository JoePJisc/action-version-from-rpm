<!--
SPDX-FileCopyrightText: 2025 Jisc Services Limited
SPDX-FileContributor: Joe Pitt

SPDX-License-Identifier: GPL-3.0-only
-->
# GitHub Action - Get Latest Version from RPM Repo

Get the latest semantic version number from a package's RPM Repo.

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| mirror_list_url | The URL to download the mirror list from. | Yes |  |
| package_name | The name of the package to check. | Yes |  |
| package_arch | The package architecture to check. | No | x86_64 |
| greater_equal_version | The minimum version to accept. e.g. 2.0.0 | No | None |
| less_than_version | The version to accept versions less than, e.g. 3.0.0. | No | None |

## Outputs

| Output | Description | Example |
|--------|-------------|---------|
| version | The latest version number. | 2.5.3 |

## Example

```yaml
      - name: Get Latest Nextcloud Version
        id: version
        uses: JoePJisc/action-version-from-rpm@v1
        with:
          mirror_list_url: https://shibboleth.net/cgi-bin/mirrorlist.cgi/rockylinux9
          package_name: shibboleth
```
