# Vendored packages

## onnxruntime-swift-package-manager

Microsoft removed `https://github.com/microsoft/onnxruntime-swift-package-manager` in November 2026. `BitChordKit/Package.swift` uses this copy by path instead.

- Version: 1.24.2, upstream commit `b7fb7f7dea8a2469e6335d95a61b8f36d0dc83b2` (the revision pinned in `BitChordKit/Package.resolved` before the copy).
- How the copy was made: every file tracked at that commit, taken unmodified from a Swift Package Manager checkout of it. Upstream CI and pipeline configuration (`.github/`, `.pipelines/`, `.config/`, `.gitignore`) was left out. No other file was changed or added.
- Licence: MIT, in `onnxruntime-swift-package-manager/LICENSE`.
- The prebuilt library is still downloaded from `download.onnxruntime.ai`, and Swift Package Manager checks it against the checksum in the package's `Package.swift`.
- Checksum of the tree: `8c51a8232793a153e9ac6f7ad5c30ec8dbce144491b7b6d19449b11215e0f70d`. To check it, run this from `Vendor/onnxruntime-swift-package-manager`:

  ```sh
  find . -type f | LC_ALL=C sort | xargs shasum -a 256 | shasum -a 256
  ```

Upstream files are not edited here: tests, scripts and docs inside the copy are as Microsoft published them. Fixes belong upstream.
