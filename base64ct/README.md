# [RustCrypto]: Constant-Time Base64

[![crate][crate-image]][crate-link]
[![Docs][docs-image]][docs-link]
[![Build Status][build-image]][build-link]
![Apache2/MIT licensed][license-image]
![Rust Version][rustc-image]
[![Project Chat][chat-image]][chat-link]

Pure Rust implementation of Base64 ([RFC 4648]).

Implements multiple Base64 variants without data-dependent branches or lookup
tables, thereby providing portable "best effort" constant-time operation.

Supports `no_std` environments and avoids heap allocations in the core API
(but also provides optional `alloc` support for convenience).

[Documentation][docs-link]

## About

This is a Base64 library designed for sidechannel resistance, aimed at purposes
like encoding/decoding the "PEM" format used to store things like cryptographic
private keys.

The paper [Util::Lookup: Exploiting key decoding in cryptographic libraries][Util::Lookup]
demonstrates how the leakage from non-constant-time Base64 parsers can be used
to practically extract RSA private keys from SGX enclaves.

## Supported Base64 variants

- Standard Base64: `[A-Z]`, `[a-z]`, `[0-9]`, `+`, `/`
- URL-safe Base64: `[A-Z]`, `[a-z]`, `[0-9]`, `-`, `_`
- bcrypt Base64: `.`, `/`, `[A-Z]`, `[a-z]`, `[0-9]`
- `crypt(3)` Base64: `.`, `-`, `[0-9]`, `[A-Z]`, `[a-z]`

## Minimum Supported Rust Version

This crate requires **Rust 1.51** at a minimum.

We may change the MSRV in the future, but it will be accompanied by a minor
version bump.

## License

Licensed under either of:

 * [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
 * [MIT license](http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.

[//]: # (badges)

[crate-image]: https://img.shields.io/crates/v/base64ct.svg
[crate-link]: https://crates.io/crates/base64ct
[docs-image]: https://docs.rs/base64ct/badge.svg
[docs-link]: https://docs.rs/base64ct/
[build-image]: https://github.com/RustCrypto/formats/actions/workflows/base64ct.yml/badge.svg
[build-link]: https://github.com/RustCrypto/formats/actions/workflows/base64ct.yml
[license-image]: https://img.shields.io/badge/license-Apache2.0/MIT-blue.svg
[rustc-image]: https://img.shields.io/badge/rustc-1.51+-blue.svg
[chat-image]: https://img.shields.io/badge/zulip-join_chat-blue.svg
[chat-link]: https://rustcrypto.zulipchat.com/#narrow/stream/300570-formats

[//]: # (links)

[RustCrypto]: https://github.com/rustcrypto
[RFC 4648]: https://tools.ietf.org/html/rfc4648
[Util::Lookup]: https://arxiv.org/pdf/2108.04600.pdf
