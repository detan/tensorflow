# Description:
#   contains parts of TensorFlow that are experimental or unstable and which are not supported.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//tensorflow:__subpackages__"])

load("//tensorflow:tensorflow.bzl", "cuda_py_tests")

py_library(
    name = "ctc_py",
    srcs = [
        "__init__.py",
        "ctc_ops.py",
    ],
    srcs_version = "PY2AND3",
)

cuda_py_tests(
    name = "ctc_decoder_ops_test",
    srcs = ["ctc_decoder_ops_test.py"],
    additional_deps = [
        ":ctc_py",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

py_test(
    name = "ctc_loss_op_test",
    srcs = ["ctc_loss_op_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":ctc_py",
        "//tensorflow:tensorflow_py",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
