# Releasing

## Release process

Releases are fully automated. The only step required is to push a version tag.

Use semantic versioning with a `v` prefix:

```
v<major>.<minor>.<patch>
```

Examples: `v1.0.0`, `v1.2.3`

```bash
git tag v1.0.1
git push origin v1.0.1
```

The package version is derived from the tag (the leading `v` is stripped).

Pushing a tag triggers the [Release workflow](.github/workflows/release.yml), which:

1. Builds the package
2. Creates a [GitHub Release](https://github.com/singlestore-labs/singlestore-connector-r2dbc/releases/) with auto-generated release notes
3. Publishes the package to [Maven Central](https://central.sonatype.com/artifact/com.singlestore/r2dbc-singlestore)

## Driver-Server Version Compatibility Matrix

After each release, add a row for the new version. While CI has no pinned engine matrix, take the list from the [EOL policy](https://docs.singlestore.com/db/v9.1/support/singlestore-software-end-of-life-eol-policy/) as of the new tag's date.

| Driver Version | Release date | Supported engine versions | Java Version |
| -------------- | ------------ | ------------------------- | ------------ |
| 1.0.0          | 2025-12-11   | 8.5, 8.7, 8.9, 9.0        | >= 8         |
| 0.0.1-beta     | 2025-11-07   | 8.5, 8.7, 8.9, 9.0        | >= 8         |
