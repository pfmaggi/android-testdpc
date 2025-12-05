android_library(
    name = "setupcompat",
    srcs = ["@setupcompat//:srcs"],
    custom_package = "com.google.android.setupcompat",
    idl_parcelables = ["@setupcompat//:idl_parcelables"],
    idl_srcs = ["@setupcompat//:idl_srcs"],
    manifest = "@setupcompat//:manifest",
    proguard_specs = ["@setupcompat//:proguard_flags"],
    resource_files = ["@setupcompat//:res"],
    deps = [
        ":partnerconfig",
        "@maven//:androidx_annotation_annotation",
        "@maven//:com_google_errorprone_error_prone_annotations",
    ],
    visibility = ["//visibility:public"],
)

android_library(
    name = "partnerconfig",
    srcs = ["@setupcompat//:partnerconfig_srcs"],
    custom_package = "com.google.android.setupcompat.partnerconfig",
    exports_manifest = 1,
    manifest = "@setupcompat//:partnerconfig_manifest",
    deps = [
        ":setupcompat_util",
        "@maven//:androidx_annotation_annotation",
        "@maven//:androidx_window_window",
    ],
    visibility = ["//visibility:public"],
)

android_library(
    name = "setupcompat_util",
    srcs = ["@setupcompat//:util_srcs"],
    custom_package = "com.google.android.setupcompat",
    manifest = "@setupcompat//:manifest",
    deps = [
        "@maven//:androidx_annotation_annotation",
    ],
)
