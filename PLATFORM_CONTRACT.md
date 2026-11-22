# Platform contract

## Build targets

- x64 builds are required for supported applications and server targets.
- macOS builds must include both x64 and ARM64.
- Linux ARM64 is optional and enabled per project request.
- Linux desktop releases use AppImage with Zsync updates; Windows and macOS use their platform release artifacts.
- Go servers are deployed as Docker images, with Nix deployment optional.

## Release policy

Releases happen only when a version is explicitly pinned. Routine commits, merges, CI passes, and dependency updates do not publish releases or update production deployments.

A release is created only for the exact pinned version/revision after its required CI checks pass. The release workflow builds the required platform/architecture matrix, attaches clearly named artifacts and checksums, and publishes the pinned version. Linux ARM64 is included only when requested for that project.

Changing the pinned version is an intentional release decision. Pin changes should be reviewed, and release artifacts must correspond to that exact pin. Failed checks block publishing; fixes require a new validated run before release.
