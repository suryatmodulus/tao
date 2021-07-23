# Changelog

## \[0.5.0]

- Move `global_shortcut` mod to the lib root.
  - [6e72e54c](https://github.com/tauri-apps/tao/commit/6e72e54c9bb897a8f4319f3f5ec8f7d96bec75d2) refactor: move `global_shortcut` mod to lib roo ([#145](https://github.com/tauri-apps/tao/pull/145)) on 2021-07-20
- Remove Clipboard MenuItem on Linux since they only work on a few sepcific widget.
  - [969052ab](https://github.com/tauri-apps/tao/commit/969052abab84ff6ad7b43f39e444e944b2de862d) fix(linux): remove clipboard menuitems on Linux ([#150](https://github.com/tauri-apps/tao/pull/150)) on 2021-07-21
- Fix `no key equivalent for Accelerator` for `Space`, `Escape`, `Minus` and `Equal` keycode.
  - [ecd3c405](https://github.com/tauri-apps/tao/commit/ecd3c405cd57852e3a55a9a6539784b99f32bf6c) fix(accelerator): add missing KeyCode to prevent `no key equivalent for Accelerator` ([#148](https://github.com/tauri-apps/tao/pull/148)) on 2021-07-20
- Removed `SystemTrayExtWindows::remove()`, the icon will be automatically removed when `SystemTray` is dropped.
  - [cc9d2b17](https://github.com/tauri-apps/tao/commit/cc9d2b1726d378ee28ca69e6e5e2255c2d71f214) refactor: refactor `system_tray` impl on windows ([#153](https://github.com/tauri-apps/tao/pull/153)) on 2021-07-22
- Add `MenuItem::SelectAll` implementation on windows.
  - [222adeb2](https://github.com/tauri-apps/tao/commit/222adeb238c290b8101507aed976869c34a8d4ab) feat(window): add `Select all` native menu item ([#146](https://github.com/tauri-apps/tao/pull/146)) on 2021-07-21
- Add flags to support all other possible unix systems.
  - [546f51a3](https://github.com/tauri-apps/tao/commit/546f51a3974c15af0d6c84525d3c8e448911f8a8) Add flags to support other unix systems. ([#142](https://github.com/tauri-apps/tao/pull/142)) on 2021-07-20

## \[0.4.0]

- On Windows, Allow resizing of `decorations: false` aka borderless window.
  - [f35dd03d](https://github.com/tauri-apps/tao/commit/f35dd03dc6f15d51fb348c6b404c195ba2401339) fix(windows): fix aero-snap and resizing of borderless window, fixes [#103](https://github.com/tauri-apps/tao/pull/103) [#104](https://github.com/tauri-apps/tao/pull/104) ([#110](https://github.com/tauri-apps/tao/pull/110)) on 2021-07-07
- Do not close the window on `CloseRequested` event and let the user handle it, keeping compatibility with macOS and Windows behavior.
  - [ea7330ef](https://github.com/tauri-apps/tao/commit/ea7330eff77dba8ab0b5e65d82313a7b15733190) fix(linux): do not close window on `CloseRequested` event ([#114](https://github.com/tauri-apps/tao/pull/114)) on 2021-07-05
- On Windows, fix Aero-Snap for `decorations: false` aka borderless window.
  - [f35dd03d](https://github.com/tauri-apps/tao/commit/f35dd03dc6f15d51fb348c6b404c195ba2401339) fix(windows): fix aero-snap and resizing of borderless window, fixes [#103](https://github.com/tauri-apps/tao/pull/103) [#104](https://github.com/tauri-apps/tao/pull/104) ([#110](https://github.com/tauri-apps/tao/pull/110)) on 2021-07-07
- Implement `MonitorHandle` and related methods on Linux.
  - [6fcfa629](https://github.com/tauri-apps/tao/commit/6fcfa62959800e6205068e74fa8648b5e12c6103) feat(linux): implement `MonitorHandle` and related methods ([#125](https://github.com/tauri-apps/tao/pull/125)) on 2021-07-12
- Add `is_menu_visilbe` getter on `Window`
  - [308411ca](https://github.com/tauri-apps/tao/commit/308411caeacc3b7c701d8d857964248a3411dfaa) feat: add `is_menu_visible` ([#108](https://github.com/tauri-apps/tao/pull/108)) on 2021-07-06
- On macOS, make sure the `set_focus` is triggered even if the window is not visible.
  - [3da167aa](https://github.com/tauri-apps/tao/commit/3da167aad9dad8ec2e3b3af52175a74a5ef07b99) fix(macos): `set_focus` should be triggered even if the window isn't visible ([#128](https://github.com/tauri-apps/tao/pull/128)) on 2021-07-14
- Fix `with_visible(bool)` in `WindowBuilder` for macOS.
  - [a0ac7075](https://github.com/tauri-apps/tao/commit/a0ac7075bdc5b9e37900c0f38b97a86071ce1dfd) fix(macos): Window state (`visible`) ([#119](https://github.com/tauri-apps/tao/pull/119)) on 2021-07-06
- Mark enums as `#[non_exhaustive]` to prevent breaking changes on enum update.
  - [9b906f50](https://github.com/tauri-apps/tao/commit/9b906f508477f0a67cc3b853909c24fe754b86c9) refactor: add `#[non_exhaustive]` attributes to enums ([#90](https://github.com/tauri-apps/tao/pull/90)) on 2021-07-07
- Remove `with_focus` and `focus` field in `WindowAttribute`. Use `set_focus` instead in most cases.
  - [e2399bc9](https://github.com/tauri-apps/tao/commit/e2399bc92642601d999a2579c0626dfe017a262c) Remove `with_focus` and `focus` field in `WindowAttribute` ([#121](https://github.com/tauri-apps/tao/pull/121)) on 2021-07-06
- Revert d344825 and move `set_skip_taskbar` back behind a `WindowExtWindows` and `WindowExtUnix`.
  - [a641d3a3](https://github.com/tauri-apps/tao/commit/a641d3a317c132661abf08723e4f87fb515e00ed) refactor: Revert d344825, move `set_skip_taskbar` behind platform-ext ([#118](https://github.com/tauri-apps/tao/pull/118)) on 2021-07-06
- `SystemTray` expose `set_menu` to update the system tray menu once created.
  - [578dd23e](https://github.com/tauri-apps/tao/commit/578dd23e02bbc63a2d2362b823730c470c1c029c) feat: implement `set_menu` for system tray ([#106](https://github.com/tauri-apps/tao/pull/106)) on 2021-07-14
- Only show window behaviour when it is visible. winuser::ShowWindow will show the window and make with_visible(false) obsolete.
  - [ff0903f6](https://github.com/tauri-apps/tao/commit/ff0903f62b7e206fd9018a7140f5d2729d4ab8ba) Only show window behaviour when it is visible ([#126](https://github.com/tauri-apps/tao/pull/126)) on 2021-07-14
- Add `with_skip_taskbar` behind `WindowBuilderExtWindows` and `WindowBuilderExtUnix`.
  - [e7cdb950](https://github.com/tauri-apps/tao/commit/e7cdb950c719a0efd93538324ba8773dd2c7abcc) feat(taskbar): add `with_skip_taskbar` for windows and linux ([#127](https://github.com/tauri-apps/tao/pull/127)) on 2021-07-14

## \[0.3.1]

- Add `window_id` to `MenuEvent`.
  - [96651dcc](https://github.com/tauri-apps/tao/commit/96651dccd2f81229a6a7d8a0fc8ffb122c099b30) feat(menu): Add `window_id` to `MenuEvent` ([#89](https://github.com/tauri-apps/tao/pull/89)) on 2021-06-22
- Prevent duplicate `MenuEvent` on window menu in Windows.
  - [8cf4033f](https://github.com/tauri-apps/tao/commit/8cf4033f81e1b0cdfd88e86cf34cdcd174e1a3a9) fix(windows): menu event ([#91](https://github.com/tauri-apps/tao/pull/91)) on 2021-06-22

## \[0.3.0]

- Drop the event callback before exiting on macOS.
  - [52ebebbc](https://github.com/tauri-apps/tao/commit/52ebebbc5cc2913bb4b50ea7743e9f6be21e6657) Drop the event callback before exiting ([#86](https://github.com/tauri-apps/tao/pull/86)) on 2021-06-18
- Add `clipboard` api exposing `read_text` and `write_text`.
  - [cf22c902](https://github.com/tauri-apps/tao/commit/cf22c902d4c961be0f6cfba6a8c865e11073b027) feat: clipboard api ([#85](https://github.com/tauri-apps/tao/pull/85)) on 2021-06-21
- Fix LoopDestroyed to really exit the application.
  - [55e52a91](https://github.com/tauri-apps/tao/commit/55e52a9149adf37131e365fa667a97f9a24f1e4f) Fix LoopDestroy condition to really exit the app on 2021-06-01
- Implement all control flow variants
  - [16e2ac06](https://github.com/tauri-apps/tao/commit/16e2ac06c2f0c180a17fb8021005dec51a57af49) Add change file on 2021-05-19
- Add checks before focusing window
  - [1bd3b1c0](https://github.com/tauri-apps/tao/commit/1bd3b1c0fbdbf4e8a9bfade34a7e217f26114859) Add change file on 2021-05-22
- Add `is_visible` getter on `Window`
  - [c402a38b](https://github.com/tauri-apps/tao/commit/c402a38b1bbf240f4d2553c3f2b4edf86f03c270) feat: Add `is_visible` getter to `Window` ([#61](https://github.com/tauri-apps/tao/pull/61)) on 2021-05-27
- **Breaking change**: New keyboard API, including `Accelerator` and `GlobalShortcut`.

`WindowEvent::ModifiersChanged` is emitted when a new keyboard modifier is pressed. This is your responsibility to keep a local state. When the modifier is released, `ModifiersState::empty()` is emitted.

`WindowEvent::KeyboardInput` as been refactored and is exposing the event `KeyEvent`.

All menus (`ContextMenu` and `MenuBar`), now includes `Accelerator` support on Windows, macOS and Linux.

New modules available: `keyboard`, `accelerator` and `platform::global_shortcut`.

*Please refer to the docs and examples for more details.*

- [01fc43b0](https://github.com/tauri-apps/tao/commit/01fc43b05ea41463d512c0e3497971edc543ac9d) refactor: keyboards events ([#82](https://github.com/tauri-apps/tao/pull/82)) on 2021-06-21
- **Breaking change**: New menu/tray API.

System tray now expose `set_icon()` to update the tray icon after initialization. The `system_tray::SystemTrayBuilder` has been moved to the root of the package as a module and available on Windows, Linux and macOS, only when the `tray` feature is enabled. Windows expose a `remove()` function available with `SystemTrayExtWindows`.

Menu builder has been rebuilt from scratch, exposing 2 different types, `ContextMenu` and `MenuBar`.

Please refer to the docs and examples for more details.

- [7546dbd1](https://github.com/tauri-apps/tao/commit/7546dbd157b5387249337c5166849e2868c0ab7c) refactor: menu & tray ([#77](https://github.com/tauri-apps/tao/pull/77)) on 2021-06-03
- Fix match branch of run loop observer on iOS.
  - [4e9fede6](https://github.com/tauri-apps/tao/commit/4e9fede6b63d4cf60ea0a6b974a61a00bd2b47df) Add change file on 2021-05-23
- - `skip_taskbar` is renamed to `set_skip_taskbar`.
- `set_skip_taskbar` is now available on `Window` and is no longer behind a PlatformExt.
- `set_skip_taskbar` takes a boolean to either show or hide the window icon from the taskbar.
- Add `with_skip_taskbar` to `WindowBuilder`.
- [c0aac091](https://github.com/tauri-apps/tao/commit/c0aac0911e77b8b0b709d20fa9d1a3297b38e7ee) add `with_skip_taskbar` on 2021-05-29
- Add `skip_taskbar` implementation for windows
  - [83341701](https://github.com/tauri-apps/tao/commit/83341701843122f57139cf7583db345385b81d3c) feat: add `skip_taskabr` impl for windows ([#78](https://github.com/tauri-apps/tao/pull/78)) on 2021-05-29

## \[0.2.6]

- Add `is_decorated` getter on `Window`
  - [8237e2f3](https://github.com/tauri-apps/tao/commit/8237e2f3d54a012f3a89aea84112fb125863b582) add changefile on 2021-05-13
- Add `is_resizable` getter on `Window`
  - [c87f3bf9](https://github.com/tauri-apps/tao/commit/c87f3bf925df3692a44982c72cfea7484758bccc) add changefile on 2021-05-13
- Fix panic from borrowing in event loop on linux.
  - [12d7ccbc](https://github.com/tauri-apps/tao/commit/12d7ccbc4dd31ae35a45dd56542c5377d5235ecc) Fix event loop on linux on 2021-05-17
- Implement `set_focus()` and `with_focus()` for macOS, Windows and Linux.
  - [448e4c17](https://github.com/tauri-apps/tao/commit/448e4c17e2ba58257b6c23041faeae0551189536) Add change file on 2021-05-07

## \[0.2.5]

- Fix Priority import on Linux.
  - [20128896](https://github.com/tauri-apps/tao/commit/201288960e6af87a2e4ae9a75b3d53a874edbd3e) Add change file on 2021-05-17

## \[0.2.4]

- Refactor control flow implementation to wait.
  - [f5514f04](https://github.com/tauri-apps/tao/commit/f5514f04819f13493e75dfc844c7b06ec17bb071) Add change file on 2021-05-15

## \[0.2.3]

- Split feature flags (menu and tray).
  - [0035ac31](https://github.com/tauri-apps/tao/commit/0035ac31ea32fd1b04339a678e321411b779a5b6) Add changefile on 2021-05-10

## \[0.2.2]

- Add dox flag to skip link lib when building doc.
  - [565114c1](https://github.com/tauri-apps/tao/commit/565114c16a27b321e326195ad1f248ffa721c3a3) Add dox flag on 2021-05-09

## \[0.2.1]

- Update covector script to fix doc build.
  - [25f291f2](https://github.com/tauri-apps/tao/commit/25f291f2385b9505b31b8db2c74fd2aad4b7d699) Update covector script to fix doc build on 2021-05-09

## \[0.2.0]

- Update README and bump version.
  - [324eca05](https://github.com/tauri-apps/tao/commit/324eca05d3075e5610f83d1161e23ace656f586e) Update README.md on 2021-05-08
- Implement menu item varients for Linux.
  - [0637570f](https://github.com/tauri-apps/tao/commit/0637570f151f3ad6d5fcaa37dbacb84a5b53624a) Add change file on 2021-05-06
- Implement status bar on Linux.
  - [e17bce40](https://github.com/tauri-apps/tao/commit/e17bce40df35f4b8e9ff018a5e9b14f446eee899) Add change file on 2021-05-07
  - [86743720](https://github.com/tauri-apps/tao/commit/867437209f820f461239505201e7b21d8d66495c) \[skip ci] Update change file description on 2021-05-07
- Implement basic menu builder for macOS, Windows and Linux.
  - [ecd528d6](https://github.com/tauri-apps/tao/commit/ecd528d6c137c7d3ca8d5f16bb3f082b961db6d9) Add change file on 2021-05-04
  - [47640216](https://github.com/tauri-apps/tao/commit/476402167ce7209b57a180453733132b777c44f5) \[skip ci] Update changelog on 2021-05-05
- Add menu feature flag and rename status bar to system tray.
  - [06d95ad0](https://github.com/tauri-apps/tao/commit/06d95ad03c15b3da1601007ef1b81ea90310d177) Cargo fmt & clippy on 2021-05-08
- Implement basic menu builder for macOS, Windows and Linux.
  - [63868365](https://github.com/tauri-apps/tao/commit/63868365613bfd3f6c6d2155e9b3120f7fb9962e) Add change file on 2021-05-05
  - [94254074](https://github.com/tauri-apps/tao/commit/942540745e3c8365ac4d0813e9ae40dc7090a2cd) \[ci skip] Update changelog on 2021-05-06
  - [e17bce40](https://github.com/tauri-apps/tao/commit/e17bce40df35f4b8e9ff018a5e9b14f446eee899) Add change file on 2021-05-07
  - [86743720](https://github.com/tauri-apps/tao/commit/867437209f820f461239505201e7b21d8d66495c) \[skip ci] Update change file description on 2021-05-07
