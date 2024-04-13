# vscode_container_fix
Fixing gaps in documentation with questionably good ideas since 2024.

## Context
VSCode docs have a nice section on [using a named volume for the source tree](https://code.visualstudio.com/remote/advancedcontainers/improve-performance#_use-a-named-volume-for-your-entire-source-tree) for some performance gains (and general cleanliness) when using Dev Containers.  Unfortunately, this requires you to actually inspect the container and clone the repo first, and can leave your container in weird states that can error loop VSCode on container init (i.e. if you delete the volume with the Workspace and rebuild).

This is a pretty hacky way to make sure the container can recover and restart. This should work with forwarded ssh keys from the host - you might need to do some config to make sure that works though.
