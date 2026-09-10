# Local working-tree package build

All development repositories use `feature/progressive-deploy`.

```sh
./build-local --os darwin --arch arm64
./build-local --os darwin --arch amd64
./build-local --os linux --arch arm64
./build-local --os linux --arch amd64
```

This wrapper invokes the sibling `fatima-package/scripts/build-local.py`.
It snapshots the local source trees, builds the commands/OPM processes with the
local core/proto module, and writes the standard tarball in this directory.
No GitHub push or remote source checkout is required. The tarball contains
`packing-info.json` with commit/branch/dirty status and source content hashes.

Install a built tarball directly, using the existing FATIMA_HOME:

```sh
python3 ../fatima-package/scripts/install-local.py ./fatima-package.darwin-arm64.tar.gz --restart
```

For a first installation, add `--initialize`. Existing configurations are preserved.
Full design, TUI usage, compatibility rules and verification are documented in
`../fatima-package/docs/progressive-deploy-usage.md`.
The additional gRPC/TUI operating commands (`rocron`, `rostop`, `rostart`,
`rodis`, `ropack`, `roproc`) and their compatibility tests are documented in
`../fatima-package/docs/grpc-operations.md`. These preserve the legacy HTTP
handlers and use the existing 9190/9180 listening ports.

Build release archives after committing all source repositories. Verify that
every repository in `packing-info.json` has `dirty: false`; this makes each
archive traceable to the completed command commits.
