# Break-out
Juego de romper bloques

Mueve el cursor para que la barra inferior se desplaze horizontalmente



<p align="center">
	<img src="https://raw.githubusercontent.com/Archerd6/Break-out/e57eba556d338259dd8575ba227b741f4745f65e/imgs/Break-out.png" style="width:80%">
</p>

<details>
<summary><strong>S E T U P</strong></summary>

   > This is step-by-step how to install these dotfiles. Just [R.T.F.M](https://en.wikipedia.org/wiki/RTFM).

   > This setup only provided for **Arch Linux** (and all Arch-based distributions)

   1. Install the [git version of AwesomeWM](https://github.com/awesomeWM/awesome/).

      ```sh
      paru -S awesome-git
      ```

   2. Install dependencies and enable services

      + Dependencies

         ```sh
         paru -Sy picom-git alacritty todo-bin papirus-icon-theme acpi acpid \
         acpi_call wireless_tools jq inotify-tools polkit-gnome xdotool xclip maim \
         brightnessctl alsa-utils alsa-tools pulseaudio pulseaudio-alsa \
         redshift mpd mpc mpdris2 ncmpcpp playerctl ffmpeg bluez-utils gpick --needed 
         ```

      + Services

         ```sh
         # For automatically launching mpd on login
         systemctl --user enable mpd.service
         systemctl --user start mpd.service

         # For charger plug/unplug events (if you have a battery)
         sudo systemctl enable acpid.service
         sudo systemctl start acpid.service
         ```

   3. Install needed fonts

      You will need to install a few fonts (mainly icon fonts) in order for text and icons to be rendered properly.

      Necessary fonts:
      + **Iosevka**  - [here](https://github.com/ryanoasis/nerd-fonts/)
      + **Icomoon**  - [here](https://www.dropbox.com/s/hrkub2yo9iapljz/icomoon.zip?dl=0)
      + **Material Design** - [here](https://github.com/Templarian/MaterialDesign-Font)

      Once you download them and unpack them, place them into `~/.fonts` or `~/.local/share/fonts`
      and run this command for your system to detect the newly installed fonts.

      ```sh
      fc-cache -v
      ```
   
   4. Install my AwesomeWM configuration files

      > Clone this repository

      ```sh
      git clone https://github.com/rxyhn/dotfiles.git
      cd dotfiles
      ```

      > Copy config and binaries files

      ```sh
      cp -r config/* ~/.config/
      cp -r bin/* ~/.local/bin/
      cp -r misc/. ~/
      ```

      > You have to add `TODO_PATH` in your env variable

      ```sh
      export TODO_PATH="path/to/todo"
      ```

   5. Configure stuff

      The relevant files are inside your `~/.config/awesome` directory.

      + User preferences and default applications

         In `rc.lua` there is a *Default Applications* section where user preferences and default applications are defined.
         You should change those to your liking.

         Note: For the weather widgets to work, you will also need to create an account on [openweathermap](https://openweathermap.org), get your key, look for your city ID, and set `openweathermap_key` and `openweathermap_city_id` accordingly.

   6. Lastly, log out from your current desktop session and log in into `AwesomeWM.`

</details>

<br>
