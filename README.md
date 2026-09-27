# Home Assistant add-on: evcc Supercharged

[![Add repository](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Ffelipefc10%2Fhassio-evcc-supercharged)

- [evcc Supercharged](evcc_supercharged/): evcc with whole-house load management against the ICP trip curve.

The image is built from [felipefc10/evcc](https://github.com/felipefc10/evcc/tree/supercharged)
and published as `felipefc10/evcc-supercharged` on Docker Hub.

## Releasing

1. Tag the `supercharged` branch of felipefc10/evcc, e.g. `0.316.0-sc8`, and push the tag. The
   "Supercharged image" workflow builds and pushes the image.
2. Set `version` in `evcc_supercharged/config.yaml` to the same tag and push. Home Assistant
   offers the update.

## Following upstream evcc

In felipefc10/evcc: sync `master` with evcc-io/evcc, rebase `supercharged` onto the new upstream
release tag, run the tests, then release as above with `<upstream>-sc1`.
