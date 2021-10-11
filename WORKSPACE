workspace(name = "example_benchmark")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("//tools:deps.bzl", "example_benchmark_dependencies")

example_benchmark_dependencies()

load("@bark_project//tools:deps.bzl", "bark_dependencies")
bark_dependencies()

load("@com_github_nelhage_rules_boost//:boost/boost.bzl", "boost_deps")
boost_deps()

# -------- Benchmark Database -----------------------
git_repository(
    name = "benchmark_database",
    commit = "422b0ddd316ab46ac79dcd72a45645e197cf7da1",
    remote = "https://github.com/bark-simulator/benchmark-database",
)

load("@benchmark_database//util:deps.bzl", "benchmark_database_dependencies")
benchmark_database_dependencies()

load("@benchmark_database//load:load.bzl", "benchmark_database_release")
benchmark_database_release()

load("@rule_monitor_project//util:deps.bzl", "rule_monitor_dependencies")
rule_monitor_dependencies()

load("@planner_rules_mcts//util:deps.bzl", "planner_rules_mcts_dependencies")
planner_rules_mcts_dependencies()

# load("@planner_miqp//util:deps.bzl", "planner_miqp_dependencies")
# planner_miqp_dependencies()

load("@pybind11_bazel//:python_configure.bzl", "python_configure")
python_configure(name = "local_config_python") 