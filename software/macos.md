# MacOS

Show desktop background path on desktop

```bash
defaults write com.apple.dock desktop-picture-show-debug-text -bool TRUE;killall Dock
```

Bypass unknown app developer security installation from command line:

```bash
sudo xattr -r -d com.apple.quarantine /Applications/App.app
```
