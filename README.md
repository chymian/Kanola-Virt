# Kanola Nvidia Image

Containerfile for building a Kanola Desktop + Nvidia image.

This image is based on top of [`kanola-images/plasma`](https://github.com/Kanola-Images/Kanola/pkgs/container/plasma) and offers the default Kanola Desktop experience with GNOME and Nvidia drivers.

## Build

> [!NOTE]
> The fsguard compiled plugin `.so` file should be downloaded from the [latest release](https://github.com/Vanilla-OS/vib-fsguard/releases/latest) and be placed under a `plugins` directory beside the `recipe.yml` file.

```bash
vib build recipe.yml
podman image build -t kanola-images/nplasma .
```

## Verify Image Build Provenance Attestation

All the image builds/pushes are attested for build provenance and integrity using the [attest-build-provenance`](https://github.com/actions/attest-build-provenance) action. The attestations can be verified [here](https://github.com/Kanola-Images/Kanola-Nvidia/attestations) or by having the latest version of [GitHub CLI](https://github.com/cli/cli/releases/latest) installed in your system. Then, execute the following command:

```sh
gh attestation verify oci://ghcr.io/kanola-images/nplasma:main --owner Kanola-Images
```
