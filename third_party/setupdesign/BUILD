android_library(
    name = "setupdesign",
    srcs = ["@setupdesign//:srcs"],
    custom_package = "com.google.android.setupdesign",
    exports_manifest = 1,
    manifest = "@setupdesign//:manifest",
    proguard_specs = [
        "@setupdesign//:proguard_flags",
    ],
    resource_files = ["@setupdesign//:res"],

    deps = [
        ":setupdesign_strings",
        "//third_party/setupcompat:setupcompat",
        "//third_party/setupcompat:partnerconfig",
        "@maven//:com_google_android_material_material",
        "@maven//:androidx_annotation_annotation",
        "@maven//:androidx_appcompat_appcompat",
        "@maven//:androidx_recyclerview_recyclerview",
        "@maven//:androidx_window_window",
        "@maven//:androidx_core_core",
        "@maven//:androidx_customview_customview",
        "@maven//:androidx_fragment_fragment",
        "@maven//:androidx_vectordrawable_vectordrawable",
        "@maven//:com_google_errorprone_error_prone_annotations",
    ],
    visibility = ["//visibility:public"],
)

android_library(
    name = "setupdesign_strings",
    manifest = "@setupdesign//:strings_manifest",
    resource_files = ["@setupdesign//:strings_res"],
)
