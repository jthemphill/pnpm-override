# pnpm-override

The package `@react-aria/button@3.3.3` specifies a dependency with a semver range: `@react-aria/interactions@^3.5.1"`. This semver range is incorrect, because `@react-aria/interactions@3.11.0` will break it.

The package `@react-aria/menu@3.6.1` specifies a dependency with a semver range: `@react-aria/interactions@^3.11.0`. It will not work with `@react-aria/interactions@^3.5.1`.

We need to convince our package manager that `@react-aria/button@3.3.3` really *does* need to work with `@react-aria/interactions@3.5.1`, and that we can't just use the latest major version. We also need to make sure our package manager doesn't try to use a version below the minimum version that `@react-aria/menu@3.6.1` supports.

Check out the commit history on this repo to see various attempts at changing the `resolutions` and `pnpm.overrides` settings in `package.json`, and to see their effects on `yarn.lock` and `pnpm-lock.yaml`.
