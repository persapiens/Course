[Setup](../Setup.md#setup) > Install homebrew

# Install homebrew.

This will download a bash script and save to "brew.sh".

```bash|{type:'command'}
curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh -o brew.sh
```

We then will make sure the file is exectuable, and then print it out so we can inspect it.
```bash|{type:'command'}
chmod +x brew.sh
cat brew.sh
```

Run installer.
```bash
./brew.sh
```

We should now be able to run `brew`!

```bash|{type:'command'}
brew -v
```