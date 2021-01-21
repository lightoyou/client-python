#
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.
#

package(default_visibility = ["//tests/behaviour:__subpackages__"])
load("//tools:behave_rule.bzl", "py_behave_test")
load("@graknlabs_dependencies//tool/checkstyle:rules.bzl", "checkstyle_test")

py_library(
    name = "steps",
    srcs = ["attribute_type_steps.py"],
    deps = [],
)

py_behave_test(
    name = "test",
    feats = ["@graknlabs_behaviour//concept/type:attributetype.feature"],
    background = ["//tests/behaviour:background"],
    steps = [
        ":steps",
        "//tests/behaviour/concept/thing/attribute:steps",
        "//tests/behaviour/concept/type/thingtype:steps",
        "//tests/behaviour/connection:steps",
        "//tests/behaviour/connection/database:steps",
        "//tests/behaviour/connection/session:steps",
        "//tests/behaviour/connection/transaction:steps",
    ],
    deps = [
        "//:client_python",
        "//tests/behaviour:context",
        "//tests/behaviour:util",
        "//tests/behaviour/config:parameters",
    ],
    native_grakn_artifact = "//tests:native-grakn-artifact",
    size = "medium",
)

checkstyle_test(
    name = "checkstyle",
    include = glob(["*"]),
    license_type = "apache",
    size = "small",
)