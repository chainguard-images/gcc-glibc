# gcc-glibc

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/chainguard-images/readme-generator
-->

[![CI status](https://github.com/chainguard-images/gcc-glibc/actions/workflows/release.yaml/badge.svg)](https://github.com/chainguard-images/gcc-glibc/actions/workflows/release.yaml)

Minimal container image for building C applications (which require glibc).

## Get It!

The image is available on `cgr.dev`:

```
docker pull cgr.dev/chainguard/gcc-glibc:latest
```

## Supported tags

| Tag | Digest | Arch |
| --- | ------ | ---- |
| `migration-20221127` | `sha256:4b30f369ae1239d0e5e553a6f1ae9bdb9b11d3cffcb7e440247a4c308957656b`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:4b30f369ae1239d0e5e553a6f1ae9bdb9b11d3cffcb7e440247a4c308957656b) | `amd64` |
| `migration-20221128` | `sha256:0e65ddecbe2cd4f23355c144f0f1aff12f083312b1a64930f1fd6bbffa1fc6d2`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:0e65ddecbe2cd4f23355c144f0f1aff12f083312b1a64930f1fd6bbffa1fc6d2) | `amd64` |
| `12` `12-bullseye` `12.2` `12.2-bullseye` `12.2.0` `12.2.0-bullseye` `12.2.0-r6` `bullseye` `latest` | `sha256:61a6d441aea5bda22ff48c37e6bf8de11e0f50595d38fb0255d6e1a42bf826e2`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:61a6d441aea5bda22ff48c37e6bf8de11e0f50595d38fb0255d6e1a42bf826e2) | `amd64` |
| `migration-20221118` | `sha256:088082f22ac08573660e83ebde23ded7af5c9d7ac1620497a782a4bf2aad9afe`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:088082f22ac08573660e83ebde23ded7af5c9d7ac1620497a782a4bf2aad9afe) | `amd64` |
| `migration-20221120` | `sha256:6c9c39566a67d7dc83b950dd6e12f5bc5157b778af3f106e968c36a0f0138ca0`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:6c9c39566a67d7dc83b950dd6e12f5bc5157b778af3f106e968c36a0f0138ca0) | `amd64` |
| `migration-20221121` | `sha256:9e47fbd259945b86cbb959b390b616ecd36a0e28008b64f509d7c4b131bc86b9`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:9e47fbd259945b86cbb959b390b616ecd36a0e28008b64f509d7c4b131bc86b9) | `amd64` |
| `migration-20221123` | `sha256:55f78476e7f94f33871eaa9e836a0d5ddb8512c41010df6e0dca9440580e81f6`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:55f78476e7f94f33871eaa9e836a0d5ddb8512c41010df6e0dca9440580e81f6) | `amd64` |
| `migration-20221126` | `sha256:7ef8862ce71af003d80181ccdca1695add799a18e21c137ded107162ffdd70ac`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:7ef8862ce71af003d80181ccdca1695add799a18e21c137ded107162ffdd70ac) | `amd64` |
| `migration` `migration-12` `migration-12.2` `migration-12.2.0` `migration-12.2.0-r6` `migration-20221129` | `sha256:9dbc2459bdcba24f54b5046a0b605bf30a1ce7ddf0f6edc42ae3700c366726a6`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:9dbc2459bdcba24f54b5046a0b605bf30a1ce7ddf0f6edc42ae3700c366726a6) | `amd64` |
| `migration-20221119` | `sha256:379b54819c56a9ac5083b40b293c456067e84cd808062dc40f2f44fe8ae4bf49`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:379b54819c56a9ac5083b40b293c456067e84cd808062dc40f2f44fe8ae4bf49) | `amd64` |
| `migration-20221122` | `sha256:12179d67c4b97990a58aa48b5b8620a075ed8b2f5aae6b1cab6b9e8c901a66c7`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:12179d67c4b97990a58aa48b5b8620a075ed8b2f5aae6b1cab6b9e8c901a66c7) | `amd64` |
| `migration-20221124` | `sha256:f7c44ad457d30a5b8916f639e9e4b0ee52ae276acbd18c1a0c0397bd8e72d378`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:f7c44ad457d30a5b8916f639e9e4b0ee52ae276acbd18c1a0c0397bd8e72d378) | `amd64` |
| `migration-20221125` | `sha256:1e670739fc9c900151e7f2e0014b5617cb9f65938d8f8963c3819183cab69d1f`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:1e670739fc9c900151e7f2e0014b5617cb9f65938d8f8963c3819183cab69d1f) | `amd64` |


## Usage

To build the C application in [examples/hello/main.c](examples/hello/main.c):

```
$ docker run --rm -v "${PWD}:/work" cgr.dev/chainguard/gcc-glibc examples/hello/main.c -o hello
```

This will write a Linux binary to `./hello`. If you're on Linux and have the glibc library, you
should be able to run it directly. Otherwise you can run it in a container e.g:

```
$ docker run --rm -v "$PWD/hello:/hello" --platform linux/amd64 cgr.dev/chainguard/glibc-dynamic /hello
Hello World!
```

Note: only `linux/amd64` is uspported at the moment.

We can also do this all in a multi-stage Dockerfile e.g:

```Dockerfile
FROM cgr.dev/chainguard/gcc-glibc as build

COPY hello.c /work/hello.c
RUN cc hello.c -o hello

FROM cgr.dev/chainguard/glibc-dynamic

COPY --from=build /work/hello /hello
CMD ["/hello"]
```

And we can also compile statically to be used in environments without glibc:


```Dockerfile
FROM cgr.dev/chainguard/gcc-glibc as build

COPY hello.c /work/hello.c
RUN cc --static hello.c -o hello

FROM cgr.dev/chainguard/static

COPY --from=build /work/hello /hello
CMD ["/hello"]
```


## Signing

All Chainguard Images are signed using [Sigstore](https://sigstore.dev)!

<details>
<br/>
To verify the image, download <a href="https://github.com/sigstore/cosign">cosign</a> and run:

```
COSIGN_EXPERIMENTAL=1 cosign verify cgr.dev/chainguard/gcc-glibc:latest | jq
```

Output:
```
Verification for cgr.dev/chainguard/gcc-glibc:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - Any certificates were verified against the Fulcio roots.
[
  {
    "critical": {
      "identity": {
        "docker-reference": "ghcr.io/chainguard-images/gcc-glibc"
      },
      "image": {
        "docker-manifest-digest": "sha256:61a6d441aea5bda22ff48c37e6bf8de11e0f50595d38fb0255d6e1a42bf826e2"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.1": "https://token.actions.githubusercontent.com",
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "159c3d9a28c2b3763d570c6e02ec5dd95921eb46",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "chainguard-images/gcc-glibc",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEYCIQDDAnTqOT1MBKO+zX8StybLr+x1626/iYE6/IwbJD8LbgIhAOFbdBcn7kyoaBuPX1X9McPCFVGdoi1Zwfu1+EYgYCk9",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiJiM2VkNGFlMDNjZTQ5NWQzYTRhMDQyZTA0NzM2MDg0OGJmODg2N2E2MmUzOTIxMjI3MDc0MWVmNDZiMjg4OWU0In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FVUNJUUNDaUlaNmVuYUJtUysxTHNMbHR2ZTlRTzVNaDZRUm1GRjJvaVlYUDY0MXpnSWdac3dTMG9CUUNzQTA0K3JNSitkNGlSVHE0dGorSS9pVG40L1NzSjJIUUQwPSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnpWRU5EUVhwcFowRjNTVUpCWjBsVlZ5czFNekV4T0c5d1dXdG1MemxaYjNGR2JraFNlVU5FWlZVNGQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEplRTFVU1RWTlJFRjVUa1JKZUZkb1kwNU5ha2w0VFZSSk5VMUVRWHBPUkVsNFYycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVV2YVdOeE0yZEhjVGhuWkVzd1pubHBZaXRXVUc5aVNucG5TVkZCVVc0M1NHdHBObEVLUVcwM2FVdDZWV3huU0V4MlQyMVNTbVkzTDNCS2FtazJaWHBrYURaTVlUVlJOSGQ1VTJJNFoyRTNXRkowUVhkTVFqWlBRMEZzWTNkblowcFVUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZWVHlzNUNpdGpkRWN5ZUhoVGJGaG9lR3RUZGxCNlUwUjVURWhyZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDJGM1dVUldVakJTUVZGSUwwSkhSWGRZTkZwa1lVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKT2IxbFhiSFZhTTFab1kyMVJkQXBoVnpGb1dqSldla3d5WkdwWmVURnVZa2RzYVZsNU9IVmFNbXd3WVVoV2FVd3paSFpqYlhSdFlrYzVNMk41T1hsYVYzaHNXVmhPYkV4dWJHaGlWM2hCQ21OdFZtMWplVGx2V2xkR2EyTjVPWFJaVjJ4MVRVUnJSME5wYzBkQlVWRkNaemM0ZDBGUlJVVkxNbWd3WkVoQ2VrOXBPSFprUnpseVdsYzBkVmxYVGpBS1lWYzVkV041Tlc1aFdGSnZaRmRLTVdNeVZubFpNamwxWkVkV2RXUkROV3BpTWpCM1JtZFpTMHQzV1VKQ1FVZEVkbnBCUWtGblVVbGpNazV2V2xkU01RcGlSMVYzVG1kWlMwdDNXVUpDUVVkRWRucEJRa0YzVVc5TlZGVTFXWHBPYTA5WFJYbFBSMDE1V1dwTk0wNXFUbXRPVkdOM1dYcGFiRTFFU214WmVsWnJDbHBFYXpGUFZFbDRXbGRKTUU1cVFXTkNaMjl5UW1kRlJVRlpUeTlOUVVWRlFrRTFSR050Vm1oa1IxVm5WVzFXYzFwWFJucGFWRUZ3UW1kdmNrSm5SVVVLUVZsUEwwMUJSVVpDUW5ScVlVZEdjR0p0WkRGWldFcHJURmRzZEZsWFpHeGplVGx1V1RKTmRGb3llSEJaYlUxM1NGRlpTMHQzV1VKQ1FVZEVkbnBCUWdwQ1oxRlFZMjFXYldONU9XOWFWMFpyWTNrNWRGbFhiSFZOU1VkTVFtZHZja0puUlVWQlpGbzFRV2RSUTBKSU1FVmxkMEkxUVVoalFUTlVNSGRoYzJKSUNrVlVTbXBIVWpSamJWZGpNMEZ4U2t0WWNtcGxVRXN6TDJnMGNIbG5Remh3TjI4MFFVRkJSMFYzVFZVMVprRkJRVUpCVFVGVFJFSkhRV2xGUVd0TVdERUtSbVEyTVRCa2VERlVkR3A0V1RGRWRVWTVjak5QWVVWbGFUTndOSFF6Wm1OQlUyUTVhM0ozUTBsUlEzcDBVRFIxVm1oME1GRjNLMjF2TkVOMmVGaHBhUW8zT0V4U1NuSlRWV0ZvYlZoYWFIcFhjVzlzY0ZGVVFVdENaMmR4YUd0cVQxQlJVVVJCZDA1dVFVUkNhMEZxUWpONE4xWjZXVmwwV1doR1F6bFdjazlDQ21RdlZHWlZWbXRwTkVkalNEYzVVVTV2YVVOSlZWbHBaell3VFc1b1MyZFVUMHR3YVRBek5sSlFkbGxpYldoblEwMUhTR1l4VkdKSE1FTXZhbkV5ZERFS2NXNUViSGhRYm1kemMwNTVaa1pFTVd4NEsydHVaWGgxT1hoNVZtcGlla1IxVGxSTlRUSTJLMmh0WW5WWGJTdGpSMEU5UFFvdExTMHRMVVZPUkNCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2c9PSJ9fX19",
          "integratedTime": 1669681465,
          "logIndex": 8048793,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/chainguard-images/gcc-glibc/.github/workflows/release.yaml@refs/heads/main",
      "githubWorkflowName": "Create Release",
      "githubWorkflowRef": "refs/heads/main",
      "githubWorkflowRepository": "chainguard-images/gcc-glibc",
      "githubWorkflowSha": "159c3d9a28c2b3763d570c6e02ec5dd95921eb46",
      "githubWorkflowTrigger": "schedule",
      "run_attempt": "1",
      "run_id": "3569818506",
      "sha": "159c3d9a28c2b3763d570c6e02ec5dd95921eb46"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [apko](https://github.com/chainguard-dev/apko).

