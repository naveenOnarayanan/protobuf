load("@rules_pkg//:mappings.bzl", "pkg_filegroup", "pkg_files", "strip_prefix")

test_suite(
    name = "tests",
    tests = [
        "//java/core:tests",
        "//java/kotlin:tests",
        "//java/kotlin-lite:tests",
        "//java/lite:tests",
        "//java/util:tests",
    ],
)

filegroup(
    name = "release",
    srcs = [
        "//java/core:release",  # contains lite.
        "//java/kotlin:release",
        "//java/kotlin-lite:release",
        "//java/util:release",
    ],
)

################################################################################
# Packaging rules
################################################################################

pkg_files(
    name = "dist_files",
    srcs = [
        "BUILD",
        "README.md",
        "bom/pom.xml",
        "lite.md",
        "pom.xml",
    ],
    strip_prefix = strip_prefix.from_root(""),
    visibility = ["//pkg:__pkg__"],
)

pkg_filegroup(
    name = "all_dist_files",
    srcs = [
        ":dist_files",
        "//java/core:dist_files",
        "//java/internal:dist_files",
        "//java/kotlin:dist_files",
        "//java/kotlin-lite:dist_files",
        "//java/lite:dist_files",
        "//java/util:dist_files",
    ],
    visibility = ["//pkg:__pkg__"],
)
