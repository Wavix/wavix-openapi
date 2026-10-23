# Releasing

This repository is published from Wavix's internal source. Do not edit `docs/` or `fern/` here, and do not create tags or GitHub releases by hand.

A release arrives as one push of the updated specs and an annotated tag `v<version>`. The tag starts `.github/workflows/release.yml`, which creates the GitHub release from the tag message and asks Fern to regenerate the SDKs (`wavix-node-sdk`, `wavix-python-sdk`, `wavix-ruby-sdk`, `wavix-go-sdk`) at the same version. Fern opens a pull request in each SDK repository; merging it publishes that SDK and creates its release.

If a `release.yml` run fails, fix the cause and use "Re-run failed jobs".
