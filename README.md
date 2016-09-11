# Docker image with Dart runtime and Content Shell

This image is based on `dartainers/dart-runtime` image and adds Content Shell
which is useful to run your browser tests.

## How to use

Example command to run tests with `content_shell`:

```
xvfb-run -s '-screen 0 1024x768x24' pub run test -p content-shell
```

If your tests rely on `pub serve` don't forget to start it in background first,
e.g.:

```
nohup pub serve test &
sleep 10 # give it some time to compile everything and start up
xvfb-run -s '-screen 0 1024x768x24' pub run test -p content-shell --pub-serve=8080
```

Above commands assume you are in your project's root folder (where
`pubspec.yaml` is).
