# The `aware-tectonic-bundles` crate

> **Aware Software fork** of [`tectonic_bundles`] 0.4.1. The only functional
> change is in `src/cache.rs` (fenced `AWARE REPORTS PATCH`): a warm bundle
> cache is served without contacting the network — upstream 0.4.x re-fetches
> the bundle digest on every bundle open, adding a network round-trip (and a
> hard network dependency) to every run even when all files are cached.
> The library name is kept as `tectonic_bundles`, so `use tectonic_bundles::…`
> works unchanged. Maintained at <https://github.com/ikhomyakov/tectonic>;
> intended for use by [`aware-tectonic`].
>
> [`tectonic_bundles`]: https://crates.io/crates/tectonic_bundles
> [`aware-tectonic`]: https://crates.io/crates/aware-tectonic

This crate is part of [the Tectonic
project](https://tectonic-typesetting.github.io/en-US/). It implements various
Tectonic "bundles" that provide access to collections of TeX support files.

- [API documentation](https://docs.rs/tectonic_bundles/).
- [Main Git repository](https://github.com/tectonic-typesetting/tectonic/).


## Cargo features

This crate provides the following [Cargo features][features]:

[features]: https://doc.rust-lang.org/cargo/reference/features.html

- `geturl-curl`: use the [curl] crate to implement HTTP requests. In order for
  this to take effect, you must use `--no-default-features` because
  `geturl-reqwest` is a default feature and it takes precedence
- `geturl-reqwest`: use the [reqwest] crate to implement HTTP requests (enabled
  by default)
- `native-tls-vendored`: if using [reqwest], activate the `vendored` option in
  the [native-tls] crate, causing OpenSSL to be vendored

[curl]: https://docs.rs/curl/
[reqwest]: https://docs.rs/reqwest/
[native-tls]: https://github.com/sfackler/rust-native-tls
