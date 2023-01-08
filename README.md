# Spotify Customization Hack With Spicetify & SpotX


# Install Spotify client with flatpak

```
[op@rhel ~]$ cd ~flatpak install flathub com.spotify.Client
```

# Install Spotx (No suport for Snap)
``` [op@rhel CustomApps]$ bash <(curl -sSL https://raw.githubusercontent.com/SpotX-CLI/SpotX-Linux/main/install.sh) -ce -E leftsidebar
```
Spotify should now work with no ads whatsoever. Note that ads can also be removed with Spicetify Extensions


# Install Spicetify 
```
[op@rhel ~]$ curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.sh | sh
```

Add permissions to spotify installation folders
``
[op@rhel ~] sudo chmod a+wr /home/op/.var/app/com.spotify.Client
[op@rhel ~] sudo chmod a+wr /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify

```

Add these paths to spicetify's config file (`config-xpui.ini `)
``
[op@rhel ~]sudo vi config-xpui.ini

``

Edit 
``` 
spotify_path            = /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify
and
prefs_path              = /home/op/.var/app/com.spotify.Client/config/spotify/prefs
```

Save and do 
```
[op@rhel ~] spicetify apply
```

# Install Spicetify Themes and Extensions

You can install it with 
```
curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-marketplace/main/resources/install.sh | sh
```
or manually download the latest release here https://github.com/spicetify/spicetify-marketplace/releases and unzip into `~/.config/spicetify/CustomApps/`
```
[op@rhel ~] wget https://github.com/spicetify/spicetify-marketplace/releases/download/v0.8.4/spicetify-marketplace.zip && cd unzip spicetify-marketplace ~/.config/spicetify/CustomApps/
```

# Applying Theme 
```
[op@rhel ~]$ cd /home/op/.config/spicetify/Themes
[op@rhel ~]$ spicetify spicetify config current_theme tHeMe_nAmE 
```
# Applying theme with Marketplace
Make sure there is a `marketplace` folder in `/home/op/.config/spicetify/CustomApps`
```
[op@rhel ~]$ spicetify config custom_apps marketplace
[op@rhel ~]$ spicetify apply
```

[op@rhel ~][op@rhel ~]
