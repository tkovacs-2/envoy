load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

licenses(["notice"])  # Apache 2

envoy_package()

envoy_cc_library(
    name = "json_internal_lib",
    srcs = ["json_internal.cc"],
    hdrs = ["json_internal.h"],
    external_deps = [
        "json",
    ],
    deps = [
        "//envoy/json:json_object_interface",
        "//source/common/common:assert_lib",
        "//source/common/common:hash_lib",
        "//source/common/common:utility_lib",
        "//source/common/protobuf:utility_lib",
    ],
)

envoy_cc_library(
    name = "json_loader_lib",
    srcs = ["json_loader.cc"],
    hdrs = ["json_loader.h"],
    deps = [
        ":json_internal_lib",
        "//envoy/json:json_object_interface",
        "//source/common/runtime:runtime_features_lib",
    ],
)
