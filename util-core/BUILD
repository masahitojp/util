target(
    dependencies = [
        "util/util-core/src/main/java",
        "util/util-core/src/main/scala",
    ],
)

target(
    name = "tests",
    dependencies = [
        "util/util-core/src/test/java",
        "util/util-core/src/test/scala",
    ],
)

# (DPB-10452) This target definition lives here because it needs to accommodate util-core
# code resolution in IntelliJ as well as `util-core-util` which contains packages
# com.twitter.concurrent and com.twitter.util
scala_library(
    name = "util-core-util",
    sources = globs(
        "src/main/scala/com/twitter/util/*.scala",
        "concurrent-extra/src/main/scala/com/twitter/concurrent/*.scala",
    ),
    compiler_option_sets = {"fatal_warnings"},
    provides = scala_artifact(
        org = "com.twitter",
        name = "util-core-util",
        repo = artifactory,
    ),
    dependencies = [
        "3rdparty/jvm/org/scala-lang/modules:scala-parser-combinators",
        "util/util-function/src/main/java",
    ],
    exports = [
        "3rdparty/jvm/org/scala-lang/modules:scala-parser-combinators",
        "util/util-function/src/main/java",
    ],
)
