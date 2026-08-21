# Cleanlist homepage redesign preview

- `/`           option-e, current. Same artifact as `/option-e/`, kept at the root so the
                short link always shows the live direction.
- `/option-e/`  option-e, the current direction. Portal-true light bands on cool ink.
- `/option-d/`  option-d, the designer's cool palette (cobalt, slate, teal on near-white).

Built from `tasks/home-redesign-aug2026/v5/option-{d,e}/` via `node _deploy.mjs --verify`,
which inlines every local asset, resolves `url()` inside the inlined CSS, and checks magic
bytes plus a base64 round trip on all 117 image payloads before it writes anything.

Verify a build by serving `_dist/index.html` from an EMPTY directory, never through
`_serve.sh`: four defects have only ever shown up in the built artifact (a dropped `defer`,
runtime-constructed image paths, a photo map emitted five times, and an opaque `body`
painting over the ground canvas).
