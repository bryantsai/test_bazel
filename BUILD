load("@io_bazel_rules_docker//python:image.bzl", "py_image")
load("@io_bazel_rules_docker//container:container.bzl", "container_image", container_push)

py_image(
    name = "py_image",
    srcs = ["py_image.py"],
    deps = [],
    main = "py_image.py",
)

container_image(
    name = "py_docker",
    base = ":py_image",
    env = {
        "BITNAMI_APP_NAME" : "flask",
    },
    ports = ["5000"],
)

container_push(
    name = "push_docker",
    image = ":docker_image",
    registry = "index.docker.io",
    repository = "bryantsai/ubuntu",
    tag = "14.04",
)
