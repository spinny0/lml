# Liron package registry

This is the default registry for LML in Liron 0.8 and later. From a Liron project, install a starter package with `lml install greeter` and import it with `require("greeter")`. The bundled `3d` example also works offline.

## Submit a package

1. Put your `.fe` files and an `lml-package.json` manifest in a package directory. The manifest includes `name`, `version`, and the `.fe` file to load as `entry`.
2. Run `lml pack` from that directory. It creates `<name>-<version>.zip` beside the directory and prints the SHA-256.
3. Fork this repository. Put the ZIP at `packages/<name>/<version>/<name>-<version>.zip` and add the version under `packages` in `index.json`. Use the published URL on `raw.githubusercontent.com`, the checksum from `lml pack`, and the manifest entry path. Open a pull request with a link to the source and instructions for trying it.

Leave existing ZIPs and checksums intact. Publish changes with a new version. Maintainers review package source and verify the archive and metadata before merging. Packages are source code and run with the same permissions as the program that imports them.
