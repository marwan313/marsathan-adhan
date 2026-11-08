# marsathan-adhan

Adhan recordings that the Serenity (marsathan) prayer app downloads when a user selects them.

## How the app uses this repository

- `sounds.json` (on `main`) is the list of sounds the app shows. The app fetches it on start and when the
  sound picker opens, so adding a sound here needs no app update.
- Each entry's `url` points at a release asset. `size` must be the exact byte size of that file: the app
  rejects a download whose size differs.
- The Makkah adhan (`default`) is bundled in the app and is not listed here.

### Adding a sound

1. Create a new release (for example `v3`) and upload the MP3.
2. Add an entry to `sounds.json` with a new unique `id` (letters, digits, `_` or `-`), the Arabic `name`,
   a `description` (muezzin, and the credit line if the license requires one), the asset `url` and its `size`.
3. Never delete or replace an asset that `sounds.json` already points to: installed apps may still download it.

## Sources and licenses

Release `v1` holds the recordings that previously shipped inside the app.

Release `v2` holds recordings from Wikimedia Commons. Each was converted to mono MP3 (96 kb/s) with its
loudness normalized to match the other sounds, and two were trimmed as noted. The adapted files are
offered under the same license as their source.

| File | Source | Author | License | Changes |
|---|---|---|---|---|
| `commons_makkah2013.mp3` | [Adhan, Great Mosque of Mecca - Jan 21, 2013](https://commons.wikimedia.org/wiki/File:Adhan,_Great_Mosque_of_Mecca_-_Jan_21,_2013.webm) | Seyfula Islam | [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/) | Audio extracted from video, first 6 s removed, normalized |
| `commons_maghrib2012.mp3` | [Maghrib Adhan at the Masjid al Haram, Mecca - 25 Feb, 2012](https://commons.wikimedia.org/wiki/File:Maghrib_Adhan_at_the_Masjid_al_Haram,_Mecca_-_25_Feb,_2012.webm) | 3omar Faruq | [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/) | Audio extracted from video, trimmed to 1:52–4:56 (the adhan), normalized |
| `commons_beautiful.mp3` | [Beautiful adhan](https://commons.wikimedia.org/wiki/File:Beautiful_adhan.ogg) | Adam-synagda | [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) | Converted, normalized |
| `commons_andrewler.mp3` | [Azan](https://commons.wikimedia.org/wiki/File:Azan.ogg) | Andrewler | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Converted, normalized |
| `commons_hassan2.mp3` | [Llamada a oración Mezquita Hassan II](https://commons.wikimedia.org/wiki/File:Llamada_a_oraci%C3%B3n_Mezquita_Hassan_II.wav) | Fraguando | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Converted, normalized |
| `commons_mahur.mp3` | [AzaanMaahur](https://commons.wikimedia.org/wiki/File:AzaanMaahur.ogg) | Saeed Hatamzadeh-Varmazyar | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | Converted, normalized |
