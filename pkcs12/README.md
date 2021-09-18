PKCS12 v1.1 (RFC 7292) Support
===

A pure-Rust implementations of PKCS#12 v1.1 as per [RFC7292]

## ROADMAP


## TODO

**Documentation**
- [ ] Standardise README
- [ ] Add LICENSE files
- [ ] Rustdocs

**Implementation**
- [ ] Exchange modes
  - [ ] Public Key privacy/integrity
  - [ ] Password privacy/integrity
    - [ ] "Two pass" (separate MAC and encryption passwords)
- [ ] PFX ASN.1 struct
- [ ] PKCS#7 - See pkcs7/README.md
- [ ] MacData ASN.1 struct
- [ ] AuthenticatedSafe
    - [ ] Data (unencrypted)
    - [ ] EncryptedData (password-encrypted)
    - [ ] EnvelopedData (public-key encrypted)
- [ ] SafeBag / PKCS12BagSet
    - [ ] keyBag
    - [ ] pkcs8ShroudedKeyBag
    - [ ] certBag
    - [ ] crlBag
    - [ ] secretBag
    - [ ] safeContentsBag
- [ ] PKCS12Attribute
- [ ] PKCS12AttrSet


**Testing**
- [ ] Doctests
- [ ] Unit tests
- [ ] PFX compatibility testing

**Security Review**
- [ ] Fuzzing
- [ ] SAST

[RFC7292]: https://datatracker.ietf.org/doc/html/rfc7292