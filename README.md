# mock-cac-pki-crl

Public revocation lists (CRLs) and the root certificate for the **test-only** mock CAC CA used with [mock-cac-pki](https://github.com/chaitanyaachanta/mock-cac-pki). Okta's Smart Card IdP fetches these URLs to check revocation:

- `root.crl`: CRL of the test root CA (covers the sub-CA)
- `intermediate.crl`: CRL of the test sub-CA (covers client certs)
- `root.cer`: the test root certificate (Authority Information Access target)

These files are public by design: they hold **no private keys**. They expire after a year. Refresh them with `PKI_DIR=... ./mock-cac-pki.sh crl`, then copy `PKI_DIR/crl/*` here and push.
