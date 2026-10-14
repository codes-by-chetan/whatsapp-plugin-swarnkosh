# Sources included with this engine release

Engine version: 1.0.0

`dependency-sources.tar.gz` contains the engine source/build files under `plugin/` and the exact installed npm package files for dependencies resolved during the build under `plugin/node_modules/`. This includes bundled packages and imports removed by tree shaking that the bundler must still resolve. Existing license files and copyright notices are preserved. No Swarnkosh desktop application source, credentials or signing keys are included.

## Reproducing the JavaScript bundle

Extract the archive, enter `plugin/`, use Node.js 22 or later, then run `npm ci --ignore-scripts` and `node build.mjs --no-app-seed`. Installation downloads the exact dependencies and build tooling from package-lock.json. The unsigned outputs appear under `.build/`. Signing and repository publication are separate operations and are not needed to rebuild the engine.

## Scope and limitations

This is an archive of published npm package contents, not a complete archive of every upstream source repository. Build tools and platform executables are not included. The published whatsapp-rust-bridge package contains precompiled WebAssembly without its original Rust/Cargo sources; its upstream is https://github.com/jlucaso1/whatsapp-rust-bridge. The full installed libsignal package is included and declares GPL-3.0. Its upstream is https://github.com/WhiskeySockets/libsignal-node. Read THIRD_PARTY_NOTICES.txt and assess the license obligations before distribution; this archive is not a guarantee of legal compliance.

## Bundled package versions

- @borewit/text-codec@0.2.2
- @cacheable/memory@2.2.0
- @cacheable/node-cache@1.7.6
- @cacheable/utils@2.5.0
- @hapi/boom@9.1.4
- @hapi/hoek@9.3.0
- @protobufjs/aspromise@1.1.2
- @protobufjs/base64@1.1.2
- @protobufjs/eventemitter@1.1.1
- @protobufjs/float@1.0.2
- @protobufjs/pool@1.1.0
- @protobufjs/utf8@1.1.2
- @tokenizer/inflate@0.4.1
- @whiskeysockets/baileys@7.0.0-rc14
- async-mutex@0.5.0
- atomic-sleep@1.0.0
- content-type@2.1.0
- curve25519-js@0.0.4
- debug@4.4.3
- dijkstrajs@1.0.3
- eventemitter3@5.0.4
- fast-redact@3.5.0
- file-type@21.3.4
- has-flag@3.0.0
- hashery@1.5.1
- hookified@1.15.1
- ieee754@1.2.1
- libsignal@6.0.0
- long@5.3.2
- lru-cache@11.5.3
- media-typer@2.0.0
- ms@2.1.3
- music-metadata@11.16.1
- on-exit-leak-free@2.1.2
- p-queue@9.3.5
- p-timeout@7.0.2
- pino-std-serializers@7.1.0
- pino@9.6.0
- pngjs@5.0.0
- protobufjs@7.6.6
- qrcode@1.5.4
- quick-format-unescaped@4.0.4
- safe-stable-stringify@2.5.0
- sonic-boom@4.2.1
- strtok3@10.4.1
- supports-color@5.5.0
- thread-stream@3.2.0
- token-types@6.1.2
- uint8array-extras@1.6.0
- whatsapp-rust-bridge@0.5.4
- win-guid@0.2.1
- ws@8.22.0

## Additional packages used during build resolution

- @keyv/serialize@1.1.1
- cacheable@2.5.0
- hookified@2.2.0
- keyv@5.6.0
- qified@0.10.1
