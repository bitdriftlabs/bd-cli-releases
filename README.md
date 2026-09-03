# bd-cli-releases

Public repository for bd-cli releases.

## Publishing a release

Run the **Publish bd-cli release** workflow from the Actions tab and provide the
`bd-cli` version without a leading `v` (for example, `0.1.36`). The workflow
downloads the Linux arm64, Linux x86_64, macOS arm64, macOS x86_64, and macOS
universal `.tar.gz` archives and raw executables from `dl.bitdrift.io`, verifies
their published SHA-256 checksums, then attaches them and a combined
`checksums.txt` file to a GitHub release tagged `v<version>`.
