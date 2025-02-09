[![Build action](https://github.com/tuananh/aws-cli/actions/workflows/release.yaml/badge.svg)](https://github.com/tuananh/aws-cli/actions/workflows/release.yaml)

# aws-cli

A tiny & secure Wolfi-based aws-cli container image.

## Usage

```bash
$ docker run --rm -it tuananh/aws-cli help
$ docker run --rm -ti -v ~/.aws:/root/.aws tuananh/aws-cli s3 ls
```

## Signing

This image is signed with [cosign](https://github.com/sigstore/cosign). To verify, download cosign and run

```sh
cosign verify ghcr.io/tuananh/aws-cli:latest \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com \
  --certificate-identity https://github.com/tuananh/aws-cli/.github/workflows/release.yaml@refs/heads/main
```

Output

```
Verification for ghcr.io/tuananh/aws-cli:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - The code-signing certificate was verified using trusted certificate authority certificates
```
## License

MIT License

Copyright (c) 2023 Tuan Anh Tran <me@tuananh.org>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.