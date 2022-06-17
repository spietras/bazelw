# bazelw

[`bazelisk`](https://github.com/bazelbuild/bazelisk) wrapper ♻️

## About

[`bazelisk`](https://github.com/bazelbuild/bazelisk) is a great wrapper for [`Bazel`](https://bazel.build),
but you still need to get the appropriate binary for your system.
This is an extra step that each developer needs to do.
So why not wrap the wrapper?

`bazelw` is a single-file script for both Unix and Windows,
that acts like `bazelisk`,
but downloads it beforehand if it's not already downloaded.
This way you can just put this script in your repository
and everyone can build your app without worrying about any extra steps.

## Quickstart

### Unix

[Click here to download](https://spietras.github.io/bazelw/bazelw) (mark as executable after) or use `curl`:

```sh
curl -O spietras.github.io/bazelw/bazelw && chmod +x bazelw
```

### Windows

[Click here to download](https://spietras.github.io/bazelw/bazelw.bat) or use `curl`:

```cmd
curl -O spietras.github.io/bazelw/bazelw.bat
```

## Usage

Just put [`bazelw`](https://spietras.github.io/bazelw/bazelw) (Unix)
and [`bazelw.bat`](https://spietras.github.io/bazelw/bazelw.bat) (Windows)
in your repository and execute whatever you want as you would with bare `Bazel`.

### Unix

```sh
./bazelw --help
```

### Windows

```cmd
bazelw --help
```

## Advanced usage

`bazelw` only checks if `bazelisk` binary already exists on your system.
But it might be outdated or it might be some different file just named this way.
You can force `bazelw` to download the binary
by setting the `BAZELW_UPDATE` environment variable to anything non-empty.

## Requirements

Since you are here,
there is some probability that you might be interested
in being able to build your software with the lowest set of dependencies possible.

If you use `bazelw` then the following dependencies are needed to build anything with `Bazel`.

Linux:

- `curl`
- `glibc`
- `gcc` or any other C compiler (with `CC` variable set)

Windows:

- `curl`
- [`Microsoft Visual C++ Redistributable`](https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist)
- [`Developer Mode`](https://docs.microsoft.com/en-us/windows/apps/get-started/enable-your-device-for-development) enabled
