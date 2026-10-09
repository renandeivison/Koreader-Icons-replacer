# KOReader Icon Customizer

A single HTML page to swap the icons of the **KOReader** interface, of the **SimpleUI** plugin and of **ZenOS**. Pick an SVG or PNG for each icon you want to change and download a ready-to-install package. Everything runs in your browser: nothing is uploaded, and it works offline.

> Unofficial community project. Not affiliated with KOReader or SimpleUI.

## How to use

Open `koreader-icones.html` in any modern browser (or host it, e.g. with GitHub Pages).

### KOReader icons

1. Open the **KOReader** tab, choose a replacement for each icon you want to change, and click **Generate zip**.
2. Extract the zip. You get a `koreader/icons` folder.
3. Copy the `icons` folder into KOReader's data folder on your device, merging with the existing one if there is one.
4. Restart KOReader.

KOReader loads icons from `<data folder>/icons` before its built-in ones, and the file name must match the original icon name (`.svg` or `.png`). Typical data folders: `koreader/` on Kindle, `.adds/koreader/` on Kobo. Only the Kindle layout was checked against the KOReader sources, so please confirm the path for your device.

### SimpleUI icon packs

1. Open the **SimpleUI** tab, name your pack, choose icons and click **Generate pack**.
2. Copy the `.zip` (do not extract it) to the device.
3. In SimpleUI: **Style → Icons → Icon Packs → Install pack from ZIP…**, pick the file, then tap the pack to apply it. No restart needed.

A pack only overrides the icons it contains. To restore everything in SimpleUI, use **Style → Icons → System Icons → Reset All System Icons**.

### ZenOS icon packs

1. Open the **ZenOS** tab, name your pack, choose icons and click **Generate pack**. You get a zip with a single folder inside (`pack.json` plus your icons), the format ZenOS expects.
2. Copy the `.zip`, without extracting it, to `koreader/icons/zen` on the device. ZenOS creates this folder and installs the zip by itself.
3. In ZenOS: **Zen Settings → Interface → Custom icons**: turn the switch on, open **Custom icon pack**, choose your pack and restart KOReader.

A pack can be partial: icons you don't change keep the ZenOS or KOReader defaults. To go back, turn the Custom icons switch off or choose another pack, then restart. ZenOS rejects files over 5 MiB.

## Features

- **Three tabs:** KOReader (102 icons), SimpleUI (44 icon slots) and ZenOS (62 icons), each with its own instructions and buttons.
- **Collapsible sections** with a quick-jump bar: navigation bar, header, footer, reader, Wi-Fi, quick actions, menu tabs, and more. Each section shows how many icons you changed.
- **Current icon next to your replacement,** with a live preview. Remove a single change at any time, or clear them all.
- **Generates only what you changed:** a `koreader/icons` zip for KOReader, or a ready-to-install pack (with `pack.lua`) for SimpleUI.
- **Default packs:** download the original icons to restore them.
- **Languages:** English (default), Português (Brasil) and Español. Your choice is remembered.
- **Single file, no dependencies,** light and dark themes.

## Limitations

- Tested against KOReader 2026.07.1, SimpleUI 2.7.1 and the ZenOS icon-pack format (ZenOS main branch, 2026.07 icon baseline). Icon names can change between versions; names that no longer exist are simply ignored.
- Verified by reading the sources and running the page in a simulated browser. Not yet verified on physical devices.
- The SimpleUI README mentions `sui_action_recent`, `sui_action_random_document` and `sui_action_search_library`, but version 2.7.1 does not recognize them, so they are not offered.
- `icon-not-found` is loaded by KOReader from a fixed path and cannot be overridden from the user folder, so it is not offered.
- The default SimpleUI pack covers only the 42 slots that have a preview.

- **ZenOS tab:** only the 62 icons that ZenOS documents as replaceable are offered.

## License and credits

The page embeds icons from other projects. They keep their own licenses:

- **KOReader icons** (`resources/icons/mdlight`, from [KOReader](https://github.com/koreader/koreader)): Material Design Icons Light, Copyright (c) 2015-2017 Austin Andrews, licensed under the **SIL Open Font License 1.1**.
- **SimpleUI icons** (from [SimpleUI](https://github.com/doctorhetfield-cmd/simpleui.koplugin) by Doctor Hetfield): Copyright (c) 2026 doctorhetfield-cmd, licensed under the **MIT License**.
- **ZenOS icons** (22 icons: Home, Library, Navbar tabs and lookup actions, from [ZenOS](https://github.com/xZenLabs/zen-os)): the ZenOS repository licenses them under the **GNU GPL v3.0**. Some of these files carry SVG Repo (svgrepo.com) origin marks and may also be subject to their original authors' licenses.

The full license texts are stored inside the HTML file and shown on their own page: click **Credits and licenses** at the bottom of the tool to open it in a new tab. This way the HTML file can be shared on its own and still carries them. If you redistribute the page, keep that link and the texts behind it.

Because the page embeds GPL-3.0 icons from ZenOS, **the page as a whole is distributed under the GNU General Public License v3.0**. Copyright (C) 2026 renandeivison. See the `LICENSE` file. The HTML file is its own source code, so you can study and modify it freely under the same license.
