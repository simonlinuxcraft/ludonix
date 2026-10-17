# Changelog

## 0.1.8: PlayStation 3 and Switch

- PlayStation 3 through RPCS3: Ludonix installs the AppImage its makers publish, finds the games of its list and
  folders, checks for the firmware, sets up the controller and turns on a 60 FPS patch from rpcs3.net where the
  game has one. Save states are in the Guide menu
- Nintendo Switch through Eden from Flathub. It needs the keys and firmware of your own console
- While a console game runs on GNOME, the main monitor switches to a refresh rate that is a multiple of the
  game's frame rate and back when it ends, so a 60 FPS game no longer judders on a 144 or 320 Hz screen
- Discord shows Steam games and PS3 games
- For new installs: GE-Proton downloads again (its files are named differently since 11-4), PCSX2 and
  DuckStation start a game only once they are set up, and the shield works on Ubuntu 24.04
- Dolphin compiles shaders before the game starts and stutters less on new effects; PCSX2 turns on its
  widescreen and no-interlacing patches
- The desktop library puts programs and launchers first, with tabs, counts and a star for favourites
- "Continue" in the Guide menu brings the game back onto the main monitor
- "Check" names only the program whose start failed, and closing a program no longer counts as a failed start

## 0.1.7: Steam library

- Every installed game of the Steam libraries shows in the library, with its cover and banner from Steam's own
  cache and the playtime Steam counts. It starts through Steam, shows as running, can be ended from the band or
  the controller, and its page opens it in Steam or in Steam's uninstall dialog. Proton, the Steam runtimes and
  other tools are left out
- Updates come from the new repository simonlinuxcraft/ludonix (`https://simonlinuxcraft.github.io/ludonix/apt`);
  the package switches its apt source by itself, and the update check in the window follows

## 0.1.6: Now called Ludonix

- Exe Runner is now Ludonix, with a new icon: it plays console games and runs a whole library, not only
  .exe files. The package, the `exe-runner` command, settings and environments stay as they are, and updates
  arrive as before
- TV mode has a home screen of its own: the games in one row, the chosen one large with its scene filling the
  screen, platform, year, genre and description beside it. L1 and R1 switch between favourites, all games, each
  platform and apps; the time is at the top, and a controller that runs low gets a warning
- Save states for console games in the Guide menu: quick save, quick load and the saved states with their
  pictures. Ludonix backs the game up every five minutes and before every load, so a dead end or a wrong pick
  costs a few minutes at most (PCSX2 through its PINE socket; DuckStation, Dolphin and RMG through their
  hotkeys; PPSSPP its current slot)
- Covers keep their own shape in TV mode and in the game row: PlayStation cases square, N64 boxes wide
- PS2 games kept as BIN/CUE start: PCSX2 cannot read the cue sheet, so Ludonix hands it the image
- Guide opens a panel on the left over the running game, with its cover, platform, how long it runs and its
  playtime: keep playing, end the game, turn the controller off or shut the PC down (after a question, the
  controllers go off with it), with each controller's player lights and its battery in ten bars, and the time.
  While it is open the game gets no input from that controller. Holding Guide no longer ends the game, so the
  DualSense's own power off leaves it running; holding Select and Start still ends it
- Favourites: a star on a game's page and in TV mode; they form a collection, and console games can be in
  collections now too
- TV mode shows the game's cover while it starts, and after ten minutes without input fades to its slowly moving
  art, so nothing stands still on an OLED TV
- A DualSense that connects lights up in Ludonix's blue
- The second controller is player two in Dolphin, PCSX2 and DuckStation; emulators number the controllers in
  the order of their player lights
- Nintendo 64 games run with RMG, installed from Flathub like the other emulators, with both controllers set up
- GameCube games start in full screen on the primary monitor with the controller mapped; Dolphin no longer
  asks before quitting
- 60 frames per second where the emulator's patch list has a patch for the game (PCSX2, DuckStation), else the
  full 50 of a PAL game, with a switch on the game's page
- A game's page shows genre, players, developer, publisher, release and a description (from the German
  Wikipedia, else the English one or Lutris, machine translated), and gets a banner of its own: a scene of a
  console game, Steam's art of a Steam game
- Console games carry their title in your language where Wikidata knows it ("Der Schatzplanet" instead of
  "Disney's Treasure Planet"), and German file names get their umlauts back
- TV mode hides what only the desk needs (file choosers, removing environments), shows the controller's button
  names, and a held direction keeps moving
- PSP: L1 and R1 work as L and R; L2 and R2 no longer pause the game or change the analog speed; PPSSPP renders
  at the screen's resolution
- PlayStation games start again with DuckStation's Flatpak (broken in 0.1.5)
- The file dialog lists every console file type, Nintendo 64, CHD and M3U files too
- Many fixes from a review of the whole app, among them disc images with several programs, offline starts on
  the newest installed runner and every other environment hidden from a running program

## 0.1.5: Couch play fixes

- PCSX2 and DuckStation open games on the primary monitor, the one Sunshine streams by default, instead of the
  monitor the mouse pointer is on; TV mode goes full screen on the primary monitor too
- Holding Guide ends the game reliably: an emulator that does not close is ended after a few seconds, a Windows
  game that ignores the close request has its environment ended, and a game that still runs is reported
- PCSX2 and DuckStation hide the mouse pointer in full screen and no longer ask before quitting; Exe Runner sets
  this once, a later change in the emulator stays
- Moonlight's Start+Select+LB+RB and a controller that disconnects while Guide is held no longer end the game
- With the controller, A ticks checkboxes and a list saves once the presses stop; TV mode stays on after a
  language change

## 0.1.4: More programs, fewer surprises

- New app icon, in every size of the hicolor theme and as SVG
- Menu entries name their icon instead of pointing at the extracted file, and the icon is kept in the user's
  hicolor folder, so an icon theme can bring its own picture for a program
- Icons taken from a program are decoded with a size and memory limit, so a crafted file cannot make Exe
  Runner allocate gigabytes
- A program that crashes in DXVK right at the start gets one more try with WineD3D, Wine's own Direct3D, and
  keeps it when it runs
- A crash names what happened and in which module, in the window, under Check and in the error report; a
  function missing in one of Wine's DLLs installs the runtime that has it
- Japanese, Chinese and Korean programs start with their language's code page, so their menus and texts are
  no longer garbled
- A program can be uninstalled on its own through its own uninstaller; the environment and the other
  programs in it stay
- Batch scripts (.bat, .cmd) start like programs, and a Windows shortcut (.lnk) from a Windows partition
  starts the program it points to
- Check shows the controllers plugged in and whether Windows programs can read them fully, with the package
  to install when they cannot
- GameRanger can start games from other environments: their folders get a drive letter in its environment and
  their registry keys come along
- Console games (PSP, PlayStation 1 and 2, GameCube, Wii, DS, Game Boy) are recognised and opened with their
  native emulator, which Exe Runner installs from Flathub when it is missing
- Console games show in the library with their box art and playtime: those opened through Exe Runner and
  those in the game folders set up in PCSX2, DuckStation, Dolphin and PPSSPP; a release of one country gets
  that country's box
- An Emulators page in the main menu installs, opens and removes the emulators and shows how each is installed
- With "Load cover pictures" switched off, no game name is sent anywhere; before, the switch had no effect
- Controller and TV mode: the window can be used with a controller from the couch (Sunshine and Moonlight
  included), A starts, B goes back, Select switches a full-screen TV mode; holding Guide for two seconds, or
  Select and Start, ends the running game. Console games can be ended from Exe Runner too, and PCSX2,
  DuckStation and PPSSPP start them in full screen; the pointer hides while the controller is in use
- Discord Rich Presence: the running game shows in the Discord status with cover, platform, year and play time
  (Discord as a package, Flatpak or Snap); on by default, switch in the settings

## 0.1.3: Imports and safer starts

- Environments of Wine, Bottles, Lutris and Heroic, and exports of Exe Runner, can be imported as new
  environments ("Umgebung importieren…" in the main menu); the source stays as it is
- An installer of a program that is installed already is offered as an update into its environment, so saves
  and settings stay
- With Ludusavi installed, saves are backed up before an update, a changed runner, a fallback runner and
  runtimes installed again, and can be put back from the program's page
- Programs that are no games and whose files use no networking library start without network access; a switch
  per environment decides either way
- Other languages come from a catalog file per language (lang/template.json for translators)
- Windows programs can no longer write to fixed disks and network shares outside their own drive letters (USB
  devices stay writable), and login files of other tools are hidden from them
- The Windows version is set completely after a .NET runtime is installed; Epic Games Launcher's installer
  refused with "Windows 10 required" before. "Prüfen" shows environments whose version still differs
- An installer in a folder that holds other installers no longer runs in another program's environment
- The "please wait" window of GE-Proton 11's protonfixes no longer flashes at every start
- X11 sessions under SDDM (KDE) get a display inside the shield; the package depends on bubblewrap and xdg-utils
- Xbox controllers reach games again in environments where an older version had installed Microsoft's XInput;
  "Erweitert" can hand a pad to DirectInput for a game that only reads that, and "Controller testen" opens
  Wine's controller panel
- "Zurücksetzen" in "Prüfen" fixes a wrong Windows version at once, and Wine's tools use the runner of the
  environment

## 0.1.2: Updates and Steam games

- Exe Runner looks for its own updates at each start and under "Auf Updates prüfen" in the main menu, and installs
  them after asking for your password (from this version on; older copies update through apt)
- A program from a game Steam installed (for example a game's workshop uploader or editor) is started through
  Steam: such programs need the running Steam client and failed with "Steam could not be initialized" before;
  starting it with Proton without Steam stays possible
- After an update a "What's new" window shows once what changed

## 0.1.1: New look, smarter installs

- New window: the library shows games as covers in a row or a grid, launchers and programs apart, collections from
  your own tags, sorting and a list view, a "Weiterspielen" card and the week's playtime; every program has a page
  of its own with playtime per day and session, its settings and tools; "Prüfen" and the settings are pages too
- Opening a file shows the steps of the analysis and then what Exe Runner will do: install, start, a better way on
  Linux, the Windows VM or why it cannot run, with the runtimes it sets up first and where an installer can put the
  program ("Wohin installieren?", also in the main menu)
- Installers learn what they lack while they run: a package that needs .NET is noticed even when the installer
  deletes it after failing, and the installer starts again with .NET 4.8; Microsoft Store packages get an
  explanation instead of an error
- EA app installs on the first try (it gets .NET 4.8 first) and shows as "EA" in the library
- A Visual C++ runtime refused because a newer one is installed counts as installed, so GOG Galaxy no longer shows
  it as failed after every start
- GOG Galaxy no longer hangs when minimized; its desktop notifications, which showed as a black area, are turned off
- Windows programs can no longer change files in your home folder outside their own environment, the cache and the
  folder they were started from; shell, autostart and settings files stay read-only, and other apps' sockets and
  systemd are out of their reach
- The window's header is its title bar; rounded window corners can be tried in the settings
- Each program gets its own shader cache with room for big games (NVIDIA, Mesa, VKD3D), so games stutter less
  once they ran; it goes when the program is removed
- On a scaled monitor under GNOME, Windows programs use Proton's Wayland driver and draw at the monitor's own
  pixels instead of being enlarged soft (NVIDIA needs driver 555 or newer)
- "Prüfen" says when variable refresh rate (VRR) is possible but off, when the NVIDIA driver is too old for
  Wayland, and when the protection of private data cannot run
- Folders, archives and disc images find the installer inside again
- Reads the headers of Windows programs itself: a crafted .exe can no longer make the analysis take gigabytes of
  memory
- Archives are unpacked only as what their first bytes say (zip, 7z, rar) and only when 7z listed them fully,
  links inside are refused; disc images must hold a CD or DVD file system
- Windows VM: a file from a folder you did not hand over reaches Windows as a copy, not with its folder; the
  hidden program search runs without clipboard; the program list Windows returns is limited
- Settings stored in a prefix are checked again when read, files Exe Runner keeps there are written without
  following links a program put there, and "Beenden erzwingen" only uses a wineserver of an installed runner
- Error reports also hide IP addresses and long lowercase tokens

## 0.1.0: First test build

- Reads a Windows program before it runs and picks the way: GE-Proton in a prefix of its own, a Windows VM for
  programs with drivers, or a plain explanation for games whose anti-cheat locks Linux out (AreWeAntiCheatYet
  list included)
- Installs runtimes on its own and learns missing ones from crashes and message boxes, falls back to an older
  GE-Proton when a new one breaks a program
- Library with covers (Steam, GOG, Lutris, Battle.net), playtime, a "Weiterspielen" banner, menu entries with the
  right dock icons, "Öffnen mit" for the file types a program registers, "Zu Steam hinzufügen"
- Pick a game's picture from what Exe Runner finds (Battle.net, Steam, GOG, Lutris), or use your own
- World of Warcraft and its Forever beta as separate entries, started through Battle.net
- Games from stores show as games, not as the store: a store's shortcut leads to its game (GOG Galaxy's
  Rayman 2), Epic, Ubisoft and EA app games are found from the stores' own data and start through their store,
  GOG games start directly
- A game's settings programs (DirectX, nGlide, configuration, editors) sit on its page instead of the shelf
- Takes over `.exe` and `.msi` double-clicks, also archives, disc images and folders
- Secrets such as SSH keys, browser profiles and other prefixes are hidden from Windows programs
- Windows VM with dockur/windows and FreeRDP RemoteApp, from your own ISO (not yet tested with a real install)
- "Prüfen" checks the system and every program and fixes what it can
- German and English, GNOME style, light and dark, Wayland and X11, smooth scrolling in WebKitGTK
- Updates through its own apt repository, signed, with the last three versions kept
