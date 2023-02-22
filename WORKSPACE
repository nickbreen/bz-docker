load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "b1e80761a8a8243d03ebca8845e9cc1ba6c82ce7c5179ce2b295cd36f7e394bf",
    urls = ["https://github.com/bazelbuild/rules_docker/releases/download/v0.25.0/rules_docker-v0.25.0.tar.gz"],
)

load("@io_bazel_rules_docker//toolchains/docker:toolchain.bzl", docker_toolchain_configure = "toolchain_configure")

docker_toolchain_configure(
    name = "docker_config",
    docker_path = "/usr/bin/podman",
    gzip_path = "/usr/bin/gzip",
    xz_path = "/usr/bin/xz",
)

load("@io_bazel_rules_docker//repositories:repositories.bzl", container_repositories = "repositories")

container_repositories()

load("@io_bazel_rules_docker//repositories:deps.bzl", container_deps = "deps")

container_deps()

load("@io_bazel_rules_docker//container:container.bzl", "container_pull")

container_pull(
    name = "debian",
    registry = "index.docker.io",
    repository = "debian",
    tag = "stable-slim",
)

container_pull(
    name = "fedora",
    registry = "index.docker.io",
    repository = "fedora",
    tag = "37",
)

container_pull(
    name = "ubuntu",
    registry = "index.docker.io",
    repository = "ubuntu",
    tag = "kinetic",
)

container_pull(
    name = "rockylinux",
    registry = "index.docker.io",
    repository = "rockylinux",
    tag = "8",
)

container_pull(
    name = "centos",
    registry = "index.docker.io",
    repository = "centos",
    tag = "6",
)
