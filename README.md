# Serverless Go Build Extended (For Comptabilitiy with Serverless Offline)

[![Serverless][ico-serverless]][link-serverless]
[![License][ico-license]][link-license]
[![NPM][ico-npm]][link-npm]

Forked from [Sean Keenan](https://github.com/sean9keenan)'s super helpful [serverless-go-build](https://github.com/sean9keenan/serverless-go-build) repository.

This version of the repository has an additional configuration option, `useBinPathForHandler`.

```
custom:
  go-build:
    useBinPathForHandler: true
```

When `useBinPathForHandler` is set to true, the plugin will assume that the path set in your functions section of the `serverless.yml` file refers to the resulting build location, and *not* the source Go file.

If you set your handler to `bin/hello/main`, it will assume that the source Go file is at `./hello/main.go`. 

## But why?

Other plugins such as `serverless-offline` require that the handler of a function point at the actual binary that needs to be run. 