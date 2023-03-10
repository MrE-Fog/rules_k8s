# Copyright 2018 The Bazel Authors. All rights reserved.
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

load(":kubectl_toolchain.bzl", "kubectl_toolchain")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

# kubectl toolchain type
toolchain_type(
    name = "toolchain_type",
    visibility = ["//visibility:public"],
)

# Default kubectl toolchain that expects the 'kubectl' executable
# to be in the PATH
kubectl_toolchain(
    name = "default_kubectl",
    tool_path = "kubectl",
    visibility = ["//visibility:public"],
)

toolchain(
    name = "kubectl_linux_amd64_toolchain",
    target_compatible_with = [
        "@platforms//os:linux",
        "@platforms//cpu:x86_64",
    ],
    toolchain = "@k8s_config//:toolchain",
    toolchain_type = ":toolchain_type",
)

toolchain(
    name = "kubectl_linux_s390x_toolchain",
    target_compatible_with = [
        "@platforms//os:linux",
        "@platforms//cpu:s390x",
    ],
    toolchain = "@k8s_config//:toolchain",
    toolchain_type = ":toolchain_type",
)

toolchain(
    name = "kubectl_linux_arm64_toolchain",
    target_compatible_with = [
        "@platforms//os:linux",
        "@platforms//cpu:aarch64",
    ],
    toolchain = "@k8s_config//:toolchain",
    toolchain_type = ":toolchain_type",
)

toolchain(
    name = "kubectl_macos_x86_64_toolchain",
    target_compatible_with = [
        "@platforms//os:macos",
        "@platforms//cpu:x86_64",
    ],
    toolchain = "@k8s_config//:toolchain",
    toolchain_type = ":toolchain_type",
)

alias(
    name = "kubectl_osx_toolchain",
    actual = ":kubectl_macos_x86_64_toolchain",
)

toolchain(
    name = "kubectl_macos_arm64_toolchain",
    target_compatible_with = [
        "@platforms//os:macos",
        "@platforms//cpu:arm64",
    ],
    toolchain = "@k8s_config//:toolchain",
    toolchain_type = ":toolchain_type",
)

toolchain(
    name = "kubectl_windows_toolchain",
    target_compatible_with = [
        "@platforms//os:windows",
        "@platforms//cpu:x86_64",
    ],
    toolchain = "@k8s_config//:toolchain",
    toolchain_type = ":toolchain_type",
)
