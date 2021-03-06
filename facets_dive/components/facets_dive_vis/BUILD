package(default_visibility = ["//visibility:public"])

load("@org_tensorflow_tensorboard//tensorboard/defs:web.bzl", "tf_web_library")
load("@org_tensorflow_tensorboard//tensorboard/defs:vulcanize.bzl", "tensorboard_html_binary")

licenses(["notice"])  # Apache 2.0

tf_web_library(
    name = "facets_dive_vis",
    srcs = [
        "facets-dive-vis.html",
        "facets-dive-vis.ts",
        "typings.d.ts",
    ],
    path = "/facets-dive/components/facets-dive-vis",
    deps = [
        "//facets_dive/lib:axis",
        "//facets_dive/lib:bounded-object",
        "//facets_dive/lib:data-example",
        "//facets_dive/lib:grid",
        "//facets_dive/lib:label",
        "//facets_dive/lib:layout",
        "//facets_dive/lib:sorting",
        "//facets_dive/lib:sprite-mesh",
        "//facets_dive/lib:stats",
        "//facets_dive/lib:string-format",
        "//facets_dive/lib:wordtree",
        "@org_polymer_iron_resizable_behavior",
        "@org_tensorflow_tensorboard//tensorboard/components/tf_imports:d3",
        "@org_tensorflow_tensorboard//tensorboard/components/tf_imports:polymer",
        "@org_tensorflow_tensorboard//tensorboard/components/tf_imports:threejs",
    ],
)

tf_web_library(
    name = "test",
    testonly = True,
    srcs = [
        "test.html",
        "test.ts",
    ],
    path = "/facets-dive/components/facets-dive-vis",
    deps = [
        ":facets_dive_vis",
        "//facets_dive/lib/test:externs",
        "@org_tensorflow_tensorboard//tensorboard/components/tf_imports:web_component_tester",
    ],
)

tensorboard_html_binary(
    name = "devserver",
    testonly = True,
    input_path = "/facets-dive/components/facets-dive-vis/test.html",
    output_path = "/facets-dive/components/facets-dive-vis/runner.html",
    deps = [":test"],
)
