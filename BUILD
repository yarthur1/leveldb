# note: 
# when compiling leveldb, -Wno-sign-compare is added to compiler flags,
# in order to turn off many warnings.
# Another approach is to modify the source code to fix the warnings,
# but it will make those source code have may diffs to upstream leveldb code,
# which makes it more noisy to merge upstream modifications. 


cc_library(name = "leveldb",
           srcs = ["db/*.cc","helpers/memenv/memenv.cc","table/*.cc","util/*.cc"],
           excludes = ["*/*_test.cc", "helpers/memenv/*_test.cc", "util/*_test.cc", "util/env_windows*.cc"],
           deps = [
        #    "//third_party/gmock/BUILD:gmock",
           ":gtest",
                   ],
           cxxflags = ["-Wno-sign-compare",
           "-Ileveldb",
           "-Ileveldb/include",
           "-DLEVELDB_PLATFORM_POSIX",
           "-Ileveldb/third_party/googletest/googlemock/include",
        "-Ileveldb/third_party/googletest/googletest/include",
        "-Ileveldb/third_party/googletest/googletest",
           ],
        #    cxxflags = ["-Wno-sign-compare"],
           )

# cc_library(name = "benchmark",
#            srcs = ["third_party/benchmark/src/*.cc"],
#            excludes = ["third_party/benchmark/src/benchmark_main.cc"],
#            deps = [
#                    ],
#           #  cxxflags = ["-Wno-sign-compare"],
#            )

cc_library(name = "gtest",
           srcs = ["third_party/googletest/googletest/src/*.cc",
           "third_party/googletest/googlemock/src/*.cc"],
           excludes = [
           "third_party/googletest/googletest/src/gtest-all.cc",
            "third_party/googletest/googletest/src/gtest_main.cc",
            "third_party/googletest/googlemock/src/gmock-all.cc",
            "third_party/googletest/googlemock/src/gmock_main.cc"],
           deps = [
                   ],
           cxxflags = ["-Wno-sign-compare",
           "-Ileveldb/third_party/googletest/googlemock/include",
           "-Ileveldb/third_party/googletest/googletest/include",
           "-Ileveldb/third_party/googletest/googletest"],
           ext_cxxflags = ["-Ileveldb/third_party/googletest/googlemock/include",
           "-Ileveldb/third_party/googletest/googletest/include",
          ],
           )
# cc_library(name = "testutil",
#            srcs = ["util/testutil.cc", "util/testharness.cc"],
#            deps = [":leveldb", "//base/common/BUILD:base"],
#            cxxflags = ["-Wno-sign-compare"],
#            )

# cc_test(name = "leveldb_test",
#         srcs = ["*/*_test.cc"],
#         deps = ["//base/testing/BUILD:test_main", ":leveldb", ":testutil"],
#         cxxflags = ["-Wno-sign-compare"],
#         )

cc_binary(name = "db_bench",
          srcs = ["benchmarks/db_bench.cc"],
          deps = [":leveldb",
          # ":benchmark",
          ":gtest",
          ],
          cxxflags = ["-Wno-sign-compare",
          "-Ileveldb",
          "-Ileveldb/include",
          "-Ileveldb/third_party/googletest/googlemock/include",
        "-Ileveldb/third_party/googletest/googletest/include",
        "-Ileveldb/third_party/googletest/googletest",
        "-DLEVELDB_PLATFORM_POSIX",],
         )

# cc_library(name = "third_party_utility",
#            srcs = ["third_party_utility.cc"],
#            )
