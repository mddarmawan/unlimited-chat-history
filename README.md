# Unlimited Chat History

Increases the Minecraft client chat history from the vanilla ~100 lines to **16384**.

A NeoForge port of [More Chat History by JackFred](https://modrinth.com/mod/morechathistory) (CC0-1.0), which only supports Fabric/Quilt.

- **Target:** Minecraft 26.1.2 / NeoForge 26.1.2.112 / Java 25, client-side only
- **Source:** https://github.com/mddarmawan/unlimited-chat-history

## Build

Requires JDK 25 (NeoForge 26.x). Gradle can auto-provision it via the toolchain resolver.

```
./gradlew build
```

Jar output: `build/libs/unlimitedchathistory-1.0.0.jar`.

## Test in the dev environment

```
./gradlew runClient
```

Gradle downloads Minecraft + NeoForge and launches the game with the mod loaded.
Spam a few chat lines, then scroll up; the history goes well past 100.

## Install

1. Install NeoForge for Minecraft 26.1.2 (easiest via [Prism Launcher](https://prismlauncher.org/)).
2. Drop `unlimitedchathistory-1.0.0.jar` into the instance's `mods/` folder.
3. Client-side only; do not install on a server.

## Layout

```
src/main/java/io/github/mddarmawan/unlimitedchathistory/
  UnlimitedChatHistory.java            # @Mod entrypoint (client only)
  mixins/ChatComponentMixin.java       # the ported mixin
src/main/resources/unlimitedchathistory.mixins.json
src/main/templates/META-INF/neoforge.mods.toml
gradle.properties                      # mod id / name / version / license
```

## Credits

Original logic by **JackFred** ([More Chat History](https://modrinth.com/mod/morechathistory), CC0-1.0).

## License

CC0-1.0 (public domain dedication), inherited from the upstream original.
