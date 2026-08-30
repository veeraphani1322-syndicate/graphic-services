# Graphic Services branding

This repository follows the upstream RustDesk project while shipping an
independent product identity.

## Product identity

- Product name: **Graphic Services**
- Description: **Graphic Services Remote Desktop**
- Upstream project: <https://github.com/rustdesk/rustdesk>
- License: GNU Affero General Public License v3.0 (`LICENCE`)

The current brand name is applied to Flutter desktop and mobile application
labels, Windows version metadata, macOS/iOS display names, Android service
labels, Linux desktop entries, and the shared runtime application name. The
runtime override lives in the root application so upstream submodules remain
publishable without a separate branded submodule fork.

The original Graphic Services mark uses two connected paths to represent a
secure two-way remote session. Its violet-to-cyan palette is defined in
`res/logo.svg`; `res/logo-header.svg` is the repository header treatment.
Generated platform icon sets must be refreshed from this source before release.

## Compatibility boundary

Internal names are deliberately unchanged where they are part of the build,
storage, IPC, deep-link, service, or network compatibility surface. Examples
include the Rust crate and executable name, `rustdesk://`, existing bundle IDs,
service identifiers, environment-variable names, and protocol symbols.
Changing these requires a separately tested migration across every supported
platform; it is not a text-replacement task.

## Following upstream

The official RustDesk repository is configured as the `upstream` remote. Add
the organization's fork as `origin` before publishing:

```bash
git remote add origin <graphic-services-repository-url>
git fetch upstream
git switch master
git merge --ff-only upstream/master
git switch branding/graphic-services
git rebase master
```

Resolve upstream changes on the branding branch, run the platform-relevant
builds and tests, and publish only to the organization's own remote.

## Distribution obligations

Keep `LICENCE`, copyright notices, modification history, and upstream
attribution. When distributing binaries or operating a modified networked
version, provide corresponding source in the manner required by AGPL-3.0.
This file is an engineering checklist, not legal advice.
