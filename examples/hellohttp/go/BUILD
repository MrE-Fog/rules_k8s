# Copyright 2017 The Bazel Authors. All rights reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("@io_bazel_rules_docker//go:image.bzl", "go_image")
load("@k8s_deploy//:defaults.bzl", "k8s_deploy")

package(default_visibility = ["//visibility:public"])

go_image(
    name = "server",
    srcs = ["main.go"],
    goarch = "amd64",
    goos = "linux",
    importpath = "github.com/bazelbuild/not-my-project/examples/hellohttp/go",
    pure = "on",
)

k8s_deploy(
    name = "staging",
    args = [
        "--v=2",
    ],
    images = {
        "hello-http-image:latest": ":server",
    },
    template = "//examples/hellohttp:deployment.yaml",
)
