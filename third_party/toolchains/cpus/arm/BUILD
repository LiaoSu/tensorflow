package(default_visibility = ["//visibility:public"])

# The following line is only here to make this project import into IDEs that embed
# a Bazel toolchain.
licenses(["notice"])

cc_toolchain_suite(
    name = "toolchain",
    toolchains = {
        "armeabi|compiler": ":cc-compiler-armeabi",
        "local|compiler": ":cc-compiler-local",
        "armeabi": ":cc-compiler-armeabi",
        "k8": ":cc-compiler-local",
        "piii": ":cc-compiler-local",
        "arm": ":cc-compiler-local",
        "s390x": ":cc-compiler-local",
    },
)

filegroup(
    name = "empty",
    srcs = [],
)

filegroup(
    name = "arm_linux_all_files",
    srcs = [
        "@arm_compiler//:compiler_pieces",
    ],
)

cc_toolchain(
    name = "cc-compiler-local",
    all_files = ":empty",
    compiler_files = ":empty",
    cpu = "local",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 1,
    toolchain_identifier = "local_linux",
)

cc_toolchain(
    name = "cc-compiler-armeabi",
    all_files = ":arm_linux_all_files",
    compiler_files = ":arm_linux_all_files",
    cpu = "armeabi",
    dwp_files = ":empty",
    linker_files = ":arm_linux_all_files",
    objcopy_files = "arm_linux_all_files",
    strip_files = "arm_linux_all_files",
    supports_param_files = 1,
    toolchain_identifier = "arm-linux-gnueabihf",
)
