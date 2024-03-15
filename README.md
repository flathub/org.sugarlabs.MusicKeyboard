# Music Keyboard Activity Flatpak

Displays a piano keyboard on the screen for playing music using different instruments. Notes can be played with touch screen or typing keyboard.

To know more refer https://github.com/godiard/music-keyboard-activity

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.MusicKeyboard
cd org.sugarlabs.MusicKeyboard
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak -y --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.MusicKeyboard.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.MusicKeyboard
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.MusicKeyboard.json
```