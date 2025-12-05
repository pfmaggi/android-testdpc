genrule(
    name = "copy_idl_srcs",
    srcs = ["@setupcompat//:idl_srcs"],
    outs = [
        "java/com/google/android/setupcompat/ISetupCompatService.aidl",
        "java/com/google/android/setupcompat/portal/IPortalProgressCallback.aidl",
        "java/com/google/android/setupcompat/portal/IPortalProgressService.aidl",
        "java/com/google/android/setupcompat/portal/IPortalRegisterResultListener.aidl",
        "java/com/google/android/setupcompat/portal/ISetupNotificationService.aidl",
        "java/com/google/android/setupcompat/portal/v1_1/IPortalProgressCallback.aidl",
    ],
    cmd = """
        for src in $(locations @setupcompat//:idl_srcs); do
            REL_PATH=$${src#*main/aidl/}
            DEST=$(@D)/java/$$REL_PATH
            mkdir -p $$(dirname $$DEST)
            cp $$src $$DEST
        done
    """,
)

genrule(
    name = "copy_idl_parcelables",
    srcs = ["@setupcompat//:idl_parcelables"],
    outs = [
        "java/com/google/android/setupcompat/portal/NotificationComponent.aidl",
        "java/com/google/android/setupcompat/portal/ProgressServiceComponent.aidl",
    ],
    cmd = """
        for src in $(locations @setupcompat//:idl_parcelables); do
            REL_PATH=$${src#*main/aidl/}
            DEST=$(@D)/java/$$REL_PATH
            mkdir -p $$(dirname $$DEST)
            cp $$src $$DEST
        done
    """,
)

android_library(
    name = "setupcompat",
    srcs = ["@setupcompat//:srcs"],
    custom_package = "com.google.android.setupcompat",
    idl_parcelables = [":copy_idl_parcelables"],
    idl_srcs = [":copy_idl_srcs"],
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
