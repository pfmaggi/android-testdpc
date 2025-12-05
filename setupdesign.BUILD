package(default_visibility = ["//visibility:public"])

filegroup(
    name = "srcs",
    srcs = glob([
        "main/src/**/*.java",
    ], allow_empty = True),
)

filegroup(
    name = "manifest",
    srcs = ["main/AndroidManifest.xml"],
)

filegroup(
    name = "res",
    srcs = glob(
        [
            "main/res/**",
        ],
        exclude_directories = 1,
        allow_empty = True,
    ),
)

filegroup(
    name = "proguard_flags",
    srcs = ["proguard.flags"],
)

filegroup(
    name = "strings_manifest",
    srcs = ["strings/AndroidManifest.xml"],
)

filegroup(
    name = "strings_res",
    srcs = glob(["strings/res/**"], allow_empty = True),
)
