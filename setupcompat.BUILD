package(default_visibility = ["//visibility:public"])

filegroup(
    name = "srcs",
    srcs = glob([
        "main/java/**/*.java",
        "main/java/**/*.kt",
    ], exclude = ["partnerconfig/**"]),
)

filegroup(
    name = "idl_import_root",
    srcs = glob(["main/aidl/**"]), # Best effort to expose the directory structure
)

filegroup(
    name = "idl_parcelables",
    srcs = [
        "main/aidl/com/google/android/setupcompat/portal/NotificationComponent.aidl",
        "main/aidl/com/google/android/setupcompat/portal/ProgressServiceComponent.aidl",
    ],
)

filegroup(
    name = "idl_srcs",
    srcs = [
        "main/aidl/com/google/android/setupcompat/ISetupCompatService.aidl",
        "main/aidl/com/google/android/setupcompat/portal/IPortalProgressCallback.aidl",
        "main/aidl/com/google/android/setupcompat/portal/IPortalProgressService.aidl",
        "main/aidl/com/google/android/setupcompat/portal/IPortalRegisterResultListener.aidl",
        "main/aidl/com/google/android/setupcompat/portal/ISetupNotificationService.aidl",
        "main/aidl/com/google/android/setupcompat/portal/v1_1/IPortalProgressCallback.aidl",
    ],
)

filegroup(
    name = "manifest",
    srcs = ["AndroidManifest.xml"],
)

filegroup(
    name = "proguard_flags",
    srcs = ["proguard.flags"],
)

filegroup(
    name = "res",
    srcs = glob([
        "main/res/**",
    ]),
)

filegroup(
    name = "partnerconfig_srcs",
    srcs = glob([
        "partnerconfig/java/**/*.java",
    ]),
)

filegroup(
    name = "partnerconfig_manifest",
    srcs = ["partnerconfig/AndroidManifest.xml"],
)

filegroup(
    name = "util_srcs",
    srcs = ["main/java/com/google/android/setupcompat/util/BuildCompatUtils.java"],
)
