package(default_visibility = ["//visibility:public"])

load("//tools:defaults.bzl", "ng_module", "ng_package")

ng_module(
    name = "effects",
    srcs = glob([
        "*.ts",
        "src/**/*.ts",
    ]),
    module_name = "@ngrx/effects",
    deps = [
        "//modules/store",
        "@rxjs",
        "@rxjs//operators",
    ],
)

ng_package(
    name = "npm_package",
    srcs = glob(["**/*.externs.js"]) + [
        "package.json",
        "//modules/effects/testing:package.json",
    ],
    entry_point = "modules/effects/index.js",
    packages = [
        "//modules/effects/migrations:npm_package",
        "//modules/effects/schematics:npm_package",
        "//modules/effects/schematics-core:npm_package",
    ],
    deps = [
        ":effects",
        "//modules/effects/testing",
    ],
)
