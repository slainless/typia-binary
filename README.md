# @slainless/typia-binary

A prebuilt [ttsc](https://ttsc.dev) plugin cache for [typia](https://typia.io).
Simply install the package and it will install the prebuilt plugin of typia to the running device's ttsc plugin so it can skip the build ritual.

## Why

1. IMHO, requiring you to build on your end defeats the point of software packages in general.
2. It is a hassle to setup cache for every single project even if you can share cache.
3. It takes too long to build on a constrained build agent.

## Use

Before installing the package, make sure to:

1. Allow `postinstall` execution (depends on package manager.)
2. Recommended: Use the EXACT matching versions of `ttsc`, `typia`, and `typescript` in the table below because those combinations are what were used to build the plugin.
   In theory, you can use different version because the correct hash will be calculated on install (as long as the hashing logic match ttsc's internal hashing logic). But I can't guarantee it, feel free to try.
3. Use default GO flags when running ttsc. Don't set any flag like `CGO_ENABLED`, etc.

| package version | ttsc   | typescript | typia  |
| --------------- | ------ | ---------- | ------ |
| 15.0.1          | 0.30.4 | 7.0.2      | 15.0.1 |

Install the package: `npm install @slainless/typia-binary` then allow the postinstall to run.

In case the postinstall was not executed properly, just run `npx @slainless/typia-binary`.