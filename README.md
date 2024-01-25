# pnpm-override

The package `@react-aria/button` version `3.3.3` depends on: `@react-aria/interactions` version range `^3.5.1`. This semver range is incorrect. `@react-aria/interactions@3.11.0` will break it, even though it is in the semver range of `^3.5.1`.

The package `@react-aria/menu` version `3.6.1` depends on: `@react-aria/interactions` version range `^3.11.0`. It will not work with an older version of `react-aria/interactions` like version `3.5.1`.

We need to convince our package manager that `react-aria/button` really *does* need to work with version `3.5.1`, and that we can't just use the latest major version. We also need to make sure our package manager doesn't try to use a version below the minimum version that `react-aria/menu` supports.

Check out the commit history on this repo to see various attempts at changing the `resolutions` and `pnpm.overrides` settings in `package.json`, and to see their effects on `yarn.lock` and `pnpm-lock.yaml`, all with the goal of pairing each package with the latest dependency it *actually* supports.
