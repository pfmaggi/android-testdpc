# This target replaces the usage of @robolectric//bazel:android-all
# providing the necessary Android SDK jars for Robolectric via Maven artifacts.

java_library(
    name = "android-all",
    visibility = ["//visibility:public"],
    exports = [
        "@maven//:org_robolectric_android_all",
    ],
)
