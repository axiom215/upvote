package(default_visibility = ["//upvote"])

load(
    "//upvote:builddefs.bzl",
    "py_appengine_library",
    "upvote_appengine_test",
)

# AppEngine Libraries
# ==============================================================================

py_appengine_library(
    name = "all",
    deps = [
        ":alert",
        ":binary",
        ":cache",
        ":cert",
        ":event",
        ":host",
        ":metrics",
        ":mixin",
        ":note",
        ":package",
        ":policy",
        ":rule",
        ":singleton",
    ],
)

py_appengine_library(
    name = "alert",
    srcs = ["alert.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "binary",
    srcs = ["binary.py"],
    deps = [
        ":event",
        ":mixin",
        ":note",
        ":rule",
        ":user",
        ":vote",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/datastore:utils",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "cache",
    srcs = ["cache.py"],
    srcs_version = "PY2AND3",
)

py_appengine_library(
    name = "cert",
    srcs = ["cert.py"],
    deps = [
        ":binary",
        ":mixin",
        "//upvote/gae/bigquery:tables",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "event",
    srcs = ["event.py"],
    deps = [
        ":mixin",
    ],
)

py_appengine_library(
    name = "exemption",
    srcs = ["exemption.py"],
    deps = [
        ":mixin",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/lib/exemption:monitoring",
        "//upvote/gae/taskqueue:utils",
    ],
)

py_appengine_library(
    name = "host",
    srcs = ["host.py"],
    deps = [
        ":mixin",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/utils:env_utils",
        "//upvote/gae/utils:mail_utils",
        "//upvote/gae/utils:template_utils",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "metrics",
    srcs = ["metrics.py"],
    deps = [
        "//upvote/gae/lib/analysis/virustotal:constants",
    ],
)

py_appengine_library(
    name = "mixin",
    srcs = ["mixin.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "note",
    srcs = ["note.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "package",
    srcs = ["package.py"],
    deps = [
        ":binary",
        ":mixin",
        ":user",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/datastore:utils",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "policy",
    srcs = ["policy.py"],
    deps = [
        ":mixin",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "rule",
    srcs = ["rule.py"],
    deps = [
        ":mixin",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/utils:user_utils",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "singleton",
    srcs = ["singleton.py"],
    deps = [
        "//common/cloud_kms:kms_ndb",
    ],
)

py_appengine_library(
    name = "user",
    srcs = ["user.py"],
    deps = [
        ":mixin",
        "//upvote/gae:settings",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/datastore:utils",
        "//upvote/gae/taskqueue:utils",
        "//upvote/gae/utils:mail_utils",
        "//upvote/gae/utils:template_utils",
        "//upvote/gae/utils:user_utils",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "utils",
    srcs = ["utils.py"],
    deps = [
        ":cert",
        ":event",
        ":exemption",
        ":host",
        ":package",
        ":rule",
        ":user",
        "//upvote/gae:settings",
        "//upvote/gae/utils:user_utils",
        "//upvote/shared:constants",
    ],
)

py_appengine_library(
    name = "vote",
    srcs = ["vote.py"],
    deps = [
        ":user",
        "//upvote/gae/datastore:utils",
        "//upvote/shared:constants",
    ],
)

# AppEngine Unit Tests
# ==============================================================================

upvote_appengine_test(
    name = "alert_test",
    size = "small",
    srcs = ["alert_test.py"],
    deps = [
        ":alert",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "binary_test",
    size = "small",
    srcs = ["binary_test.py"],
    deps = [
        ":binary",
        ":cert",
        ":event",
        ":vote",
        "//common/testing:basetest",
        "//external:mock",
        "//upvote/gae:settings",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/datastore:utils",
        "//upvote/gae/datastore/models:utils",
        "//upvote/gae/lib/testing:basetest",
        "//upvote/shared:constants",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "cert_test",
    size = "small",
    srcs = ["cert_test.py"],
    deps = [
        ":cert",
        "//external:mock",
        "//upvote/gae:settings",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/datastore/models:binary",
        "//upvote/gae/lib/testing:basetest",
        "//upvote/shared:constants",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "event_test",
    size = "small",
    srcs = ["event_test.py"],
    deps = [
        ":event",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/datastore/models:utils",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "exemption_test",
    size = "small",
    srcs = ["exemption_test.py"],
    deps = [
        ":exemption",
        ":host",
        "//common/testing:basetest",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "host_test",
    size = "small",
    srcs = ["host_test.py"],
    deps = [
        ":host",
        ":policy",
        "//upvote/gae/lib/testing:basetest",
    ],
)

upvote_appengine_test(
    name = "mixin_test",
    size = "small",
    srcs = ["mixin_test.py"],
    deps = [
        ":mixin",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "note_test",
    size = "small",
    srcs = ["note_test.py"],
    deps = [
        ":note",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "package_test",
    size = "small",
    srcs = ["package_test.py"],
    deps = [
        ":package",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/lib/testing:basetest",
        "//upvote/shared:constants",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "rule_test",
    size = "small",
    srcs = ["rule_test.py"],
    deps = [
        ":rule",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/lib/testing:basetest",
        "//upvote/shared:constants",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "singleton_test",
    size = "small",
    srcs = ["singleton_test.py"],
    deps = [
        ":singleton",
        "//external:mock",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "user_test",
    size = "small",
    srcs = ["user_test.py"],
    deps = [
        ":user",
        "//common/testing:basetest",
        "//external:mock",
        "//upvote/gae:settings",
        "//upvote/gae/bigquery:tables",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/datastore:utils",
        "//upvote/gae/lib/testing:basetest",
        "//upvote/shared:constants",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "utils_test",
    size = "small",
    srcs = ["utils_test.py"],
    deps = [
        ":cert",
        ":event",
        ":host",
        ":rule",
        ":utils",
        "//external:mock",
        "//upvote/gae:settings",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/datastore:utils",
        "//upvote/gae/lib/testing:basetest",
        "//upvote/gae/utils:user_utils",
        "//upvote/shared:constants",
        "@absl_git//absl/testing:absltest",
    ],
)

upvote_appengine_test(
    name = "vote_test",
    size = "small",
    srcs = ["vote_test.py"],
    deps = [
        ":mixin",
        ":vote",
        "//external:mock",
        "//upvote/gae/datastore:test_utils",
        "//upvote/gae/datastore:utils",
        "//upvote/gae/lib/testing:basetest",
        "@absl_git//absl/testing:absltest",
    ],
)
