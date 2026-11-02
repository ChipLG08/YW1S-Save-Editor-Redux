<div align="center">
    <img src="./assets/icon.png"/>
</div>

# YW1S Save Editor Redux

An Android application that loads the `main.bin` file from Yo-kai Watch 1 Smartphone using Shizuku, allowing you to edit and save the data from `game0.yw` to `game3.yw`.

## Implemented Features

- Support for Spanish, English, and Japanese.
- Kotlin port of the encryption and decryption logic from `crypt.py` / `check.py`.
- Selection of `game0.yw`, `game1.yw`, `game2.yw`, or `game3.yw` within `main.bin` to extract the Yo-kai list.
- Save directory selection: `/Android/data/`, `/Android/media/`, and `(Custom)`.
- Editing of individual stats and other attributes through a Compose interface.
- Display of the item list and modification of existing quantities within safe limits.
- Read-only display of Equipment, Key Items, the Expendekai status, and the Wayfarer Manor.
- Automatic creation of a backup named `main.bin.bak` when saving. The temporary file is validated before replacing the original.
- Support for Android 13 and later.

## Target Files

- `/data/user/<current_user_ID>/Android/data/jp.co.level5.yws1/files/save/main.bin`
- `/data/user/<current_user_ID>/Android/media/jp.co.level5.yws1/save/main.bin`
- `/(Custom directory)/main.bin`

The directory must contain a `main.bin` file.

## Usage

1. Start Shizuku after completing its initial setup (required to access `/Android/media/` and `/Android/data/`).
2. Open the application and grant Shizuku permissions when prompted.
3. Choose the directory containing the `main.bin` file you want to edit.
4. Select the save file you want to edit, from `game0.yw` to `game3.yw`.
5. Edit the Yo-kai or save data.
6. Press `Save` to apply the changes to the selected save file.
7. If you did not edit the file directly from `/data/user/<current_user_ID>/Android/data/jp.co.level5.yws1/files/save/main.bin`, copy the modified `main.bin` to that location, or to `/data/user/<current_user_ID>/Android/media/jp.co.level5.yws1/save/main.bin` (only if you have changed the save path so that the game loads the save file from there).

## Warnings

- Shizuku running in ADB mode (without root access) can only access `/Android/media/`. It cannot access other applications internal data, so accessing `/Android/data/` in this mode is not possible.
- Root access and Shizuku are required to access `/Android/data/`.
- If your `main.bin` file is stored in a directory other than the two listed above, no additional permissions are required.
- A backup (`.bak`) is automatically created before writing any changes, but use the application at your own risk.
- If you encounter any bugs, please report them to the original creator.

## License

- The code in this project is distributed under the MIT License. See the `LICENSE` file for more information.
- For information about the licenses of third-party materials included in this project, see `THIRD_PARTY_NOTICES.md`.
