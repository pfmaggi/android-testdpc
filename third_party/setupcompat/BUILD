genrule(
    name = "copy_idl_srcs",
    srcs = ["@setupcompat//:idl_srcs"],
    outs = [
        "main/aidl/com/google/android/setupcompat/ISetupCompatService.aidl",
        "main/aidl/com/google/android/setupcompat/portal/IPortalProgressCallback.aidl",
        "main/aidl/com/google/android/setupcompat/portal/IPortalProgressService.aidl",
        "main/aidl/com/google/android/setupcompat/portal/IPortalRegisterResultListener.aidl",
        "main/aidl/com/google/android/setupcompat/portal/ISetupNotificationService.aidl",
        "main/aidl/com/google/android/setupcompat/portal/v1_1/IPortalProgressCallback.aidl",
    ],
    cmd = """
        for src in $(locations @setupcompat//:idl_srcs); do
            # We need to reconstruct the path relative to the package root.
            # The files are like external/setupcompat/main/aidl/...
            # We want to put them in $(RULEDIR)/main/aidl/...
            # Extract the part after 'main/aidl/'

            # Since we know the exact destination paths in outs, and the input order matches glob order typically,
            # but relying on order is dangerous.

            # Better approach: basename matching or just cp preserving structure if root matches?
            # The source path is external/+_repo_rules+setupcompat/main/aidl/...

            # Let's just cp specific files to specific locations if list is small? No, loop is better.

            # We simply cp the files to the $(RULEDIR)/main/aidl directory structure.
            # We assume the input paths contain "main/aidl".

            REL_PATH=$${src#*main/aidl/}
            DEST=$(@D)/main/aidl/$$REL_PATH
            mkdir -p $$(dirname $$DEST)
            cp $$src $$DEST
        done
    """,
)

genrule(
    name = "copy_idl_parcelables",
    srcs = ["@setupcompat//:idl_parcelables"],
    outs = [
        "main/aidl/com/google/android/setupcompat/portal/NotificationComponent.aidl",
        "main/aidl/com/google/android/setupcompat/portal/ProgressServiceComponent.aidl",
    ],
    cmd = """
        for src in $(locations @setupcompat//:idl_parcelables); do
            REL_PATH=$${src#*main/aidl/}
            DEST=$(@D)/main/aidl/$$REL_PATH
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
