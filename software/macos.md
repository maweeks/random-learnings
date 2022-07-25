# MacOS

Show desktop background path on desktop

```bash
defaults write com.apple.dock desktop-picture-show-debug-text -bool TRUE;killall Dock
```

Bypass unknown app developer security installation from command line:

```bash
sudo xattr -r -d com.apple.quarantine /Applications/App.app
```

Change dock show / hide speed:

```bash
# defaults are 0.5
defaults write com.apple.dock autohide-delay -float 0.1;
defaults write com.apple.dock autohide-time-modifier -float 0.3;
killall Dock
```
