# OpenFGA Provenance Implementation & Consumption

_NOTE: The following document was derived from the [Argo CD provenance implementation document](https://github.com/cncf/tag-security/blob/main/provenance-implementation/argo/argo-cd.md). We chose to use this as a template as it has already been accepted by the [tag-security](https://github.com/cncf/tag-security) group of CNCF._

## OpenFGA Provenance Intent

The OpenFGA project has a variety of resources distributed on each release, and provenance artifacts are automatically generated for each.

Within each release, you will find a number of .tar.gz files along with a checksums file that covers all of the artifacts. An SBOM is generated at the same time as the release for each artifact, and is also given a signature using a PEM certificate.

Separate from the release assets, container images are also released and signed.

### Release Assets
Each [OpenFGA release](https://github.com/openfga/openfga/releases) produces a series of artifacts, and each of these artifacts is explained in more detail in the table below:

| **Artifact**                              | **Description**                                  | **Example**                            |
|-------------------------------------------|--------------------------------------------------|----------------------------------------|
| `openfga_<version>_<os>_<arch>.tar.gz`      | OpenFGA binary artifacts                         | openfga_1.3.6_linux_arm64.tar.gz       |
| `openfga_<version>_<os>_<arch>.tar.gz.sbom` | Software Bill of Materials (SBOM)                | openfga_1.3.6_darwin_amd64.tar.gz.sbom |
| `openfga.intoto.jsonl`                      | Attestation of OpenFGA binary and SBOM artifacts |                                        |
| `checksums.txt`                             | Checksum of the release artifacts                |                                        |
| `checksums.txt.pem`                         | Certificate generated by cosign for signing      |                                        |
| `checksums.txt.sig`                         | Checksum signature signed by cosign              |                                        |

## Prerequisite Technology

In order to streamline your validation process, we recommend installing the following tools. These can be installed locally or in an automated pipeline.

- cosign `v2.0.0` or higher [installation instructions](https://docs.sigstore.dev/cosign/installation)
- slsa-verifier [installation instructions](https://github.com/slsa-framework/slsa-verifier#installation)
- crane [installation instructions](https://github.com/google/go-containerregistry/blob/main/cmd/crane/README.md) (for container verification only)

## Validation Processes

There are separate validation processes for each of the following artifacts:

- Container Image
- SBOM
- OpenFGA server Artifacts

### Container Image Validation

A [SLSA](https://slsa.dev/) Level 3 provenance is generated using [slsa-github-generator](https://github.com/slsa-framework/slsa-github-generator).

The following command will verify the signature of an attestation and how it was issued. It will contain the payloadType, payload, and signature.

Run the following command as per the [slsa-verifier documentation](https://github.com/slsa-framework/slsa-verifier/tree/main#containers):

```bash
# Get the immutable container image to prevent TOCTOU attacks https://github.com/slsa-framework/slsa-verifier#toctou-attacks
IMAGE=openfga/openfga:v1.3.6
IMAGE="${IMAGE}@"$(crane digest "${IMAGE}")
# Verify provenance, including the tag to prevent rollback attacks.
slsa-verifier verify-image "$IMAGE" \
    --source-uri github.com/openfga/openfga \
    --source-tag v1.3.6
```

If you only want to verify up to the major or minor verion of the source repository tag (instead of the full tag), use the `--source-versioned-tag` which performs semantic versioning verification:

```shell
slsa-verifier verify-image "$IMAGE" \
    --source-uri github.com/openfga/openfga \
    --source-versioned-tag v1 # Note: May use v1.3 for minor version verification.
```

The attestation payload contains a non-forgeable provenance which is base64 encoded and can be viewed by passing the `--print-provenance` option to the commands above:

```bash
slsa-verifier verify-image "$IMAGE" \
    --source-uri github.com/openfga/openfga \
    --source-tag v1.3.6 \
    --print-provenance | jq
```

If you prefer using cosign, follow these [instructions](https://github.com/slsa-framework/slsa-github-generator/blob/main/internal/builders/container/README.md#cosign).

> [!NOTE]
> `cosign` or `slsa-verifier` can both be used to verify image attestations.
> Check the documentation of each binary for detailed instructions.


## Verification of OpenFGA artifacts with SLSA attestations

A single attestation (e.g. `openfga.intoto.jsonl`) from each release is provided. This can be used with [slsa-verifier](https://github.com/slsa-framework/slsa-verifier#verification-for-github-builders) to verify that the OpenFGA binary artifact(s) were generated using OpenFGA workflows on GitHub and ensures it was cryptographically signed.

```bash
slsa-verifier verify-artifact openfga_1.3.6_linux_amd64.tar.gz \
  --provenance-path openfga.intoto.jsonl \
  --source-uri github.com/openfga/openfga \
  --source-tag v1.3.6
```

If you only want to verify up to the major or minor verion of the source repository tag (instead of the full tag), use the `--source-versioned-tag` which performs semantic versioning verification:

```shell
slsa-verifier verify-artifact openfga_1.3.6_linux_amd64.tar.gz \
  --provenance-path openfga.intoto.jsonl \
  --source-uri github.com/openfga/openfga \
  --source-versioned-tag v1 # Note: May use v1.3 for minor version verification.
```

The payload is a non-forgeable provenance which is base64 encoded and can be viewed by passing the `--print-provenance` option to the commands above:

```bash
slsa-verifier verify-artifact openfga_1.3.6_linux_amd64.tar.gz \
  --provenance-path openfga.intoto.jsonl \
  --source-uri github.com/openfga/openfga \
  --source-tag v1.3.6 \
  --print-provenance | jq
```

## Verification of SBOM

A single attestation (e.g. `openfga_1.3.6_linux_amd64-sbom.intoto.jsonl`) from each release is provided along with the sbom (e.g. `openfga_1.3.6_linux_amd64.tar.gz.sbom`). This can be used with [slsa-verifier](https://github.com/slsa-framework/slsa-verifier#verification-for-github-builders) to verify that the SBOM was generated using OpenFGA workflows on GitHub and ensures it was cryptographically signed.

```bash
slsa-verifier verify-artifact openfga_1.3.6_linux_amd64.tar.gz.sbom \
  --provenance-path openfga.intoto.jsonl \
  --source-uri github.com/openfga/openfga \
  --source-tag v1.3.6
```

***

## Verification with Kubernetes Policy controllers

> [!NOTE]
> We encourage all users to verify signatures and provenances with your admission/policy controller of choice. Doing so will verify that an image was built by us before it's deployed on your Kubernetes cluster.

Cosign signatures and SLSA provenances are compatible with several types of admission controllers. Please see the [cosign documentation](https://docs.sigstore.dev/cosign/overview/#kubernetes-integrations) and [slsa-github-generator](https://github.com/slsa-framework/slsa-github-generator/blob/main/internal/builders/container/README.md#verification) for supported controllers.