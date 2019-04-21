# Multithreaded C++11 nlohmann/json Abseil GoogleTest Bazel Quick Start #

# Name

This project is named 'k9' because I was thinking about dogs.

# Purpose

A modern opinionated standards-compliant multi-platform multithreaded C++ project that parses JSON files, intended as a starting point for new projects. Go build something awesome!

# License

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0).

# Disclaimer

The author makes not promises about the code herein. Use at your own risk. I am not responsible.

# Prerequisites

- [gcc](https://gcc.gnu.org/install)
- [Bazel](https://docs.bazel.build/versions/master/install.html)

See the 'osx' script in this repo for OSX setup.

# Dependencies

- [Abseil](https://abseil.io) is currently the best way to write modern C++ that works with old C++11 parsers
- [nlohmann/json](https://github.com/nlohmann/json) is the best JSON parser for modern C++
- [GoogleTest](https://github.com/google/googletest) is the best of breed library for C++ unit testing and mocking

# Origin

This project was created by following the [Abseil Bazel QuickStart](https://abseil.io/docs/cpp/quickstart) in March 2019.

# Contributions

PR's are welcome. Please obey the .editorconfig file.

# Builder

Bazel is IMO the best C++ build tool available today. CMake is the most popular. Nobody appears to be using boost-build besides Boost.

I chose Bazel (by Google) because it works well with Abseil and GoogleTest (also by Google). Although Bazel is tricky to configure, CMake is worse. Bazel is well enough documented for my needs but beware old examples that use deprecated features.

The hardest part with all of the code herein was getting a 2019 version of [Bazel](https://bazel.build) to work with nlohmann/json, which doesn't use Bazel. I started with https://github.com/nathanws/bazel-examples but it is out date and required literally hours (not days, at least) of trial and error. The experience was maddening. The WORKSPACE file herein is a working example that will assist you greatly when you need additional dependencies that don't use Bazel.

# Run the tests

```bash
bazel test //:k9_test
```

# Run the 'main' executable

Currently just exits

```bash
bazel run //:k9 -- arg1 arg2 arg3
```

# ToDo

1. Add Boost
2. Add logging (syslog and console)
3. Add Doxygen-to-HTML
4. Get rid of the OSX-only warning:
```
clang: warning: argument unused during compilation: '-pthread'
```
