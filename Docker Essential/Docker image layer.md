![](https://i.imgur.com/lJJYMgG.png)

A Docker image layer is a fundamental concept in Docker that represents a specific modification to the file system inside a container. Each layer is <span style="background:#fff88f">immutable, meaning it cannot be changed</span>, and is stored in the Docker engine's cache for efficient image creation.

## Copy-on-Write (CoW)

Union file systems use a copy-on-write mechanism. When a file is modified in a container, instead of directly modifying the original file, a copy of the file is created, and the changes are applied to the copy. This preserves the original file intact. This mechanism ensures that each<span style="background:#fff88f"> layer is immutable</span>, which is a key characteristic of Docker images.