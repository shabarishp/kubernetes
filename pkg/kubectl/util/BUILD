load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "service_port.go",
        "util.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:darwin": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:dragonfly": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:freebsd": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:nacl": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:netbsd": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:openbsd": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:plan9": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:solaris": [
            "umask.go",
        ],
        "@io_bazel_rules_go//go/platform:windows": [
            "umask_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "k8s.io/kubernetes/pkg/kubectl/util",
    visibility = ["//build/visible_to:pkg_kubectl_util_CONSUMERS"],
    deps = [
        "//pkg/apis/core:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/runtime:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/intstr:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:android": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:darwin": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:dragonfly": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:freebsd": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:nacl": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:netbsd": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:openbsd": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:plan9": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:solaris": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//pkg/kubectl/util/crlf:all-srcs",
        "//pkg/kubectl/util/hash:all-srcs",
        "//pkg/kubectl/util/i18n:all-srcs",
        "//pkg/kubectl/util/logs:all-srcs",
        "//pkg/kubectl/util/slice:all-srcs",
        "//pkg/kubectl/util/term:all-srcs",
        "//pkg/kubectl/util/transport:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//build/visible_to:pkg_kubectl_util_CONSUMERS"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "service_port_test.go",
        "util_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/kubernetes/pkg/kubectl/util",
    deps = [
        "//pkg/apis/core:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/intstr:go_default_library",
    ],
)
