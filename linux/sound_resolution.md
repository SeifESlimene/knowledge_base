## ==Ubuntu 20.04 LTS==
### May be someone will find this helpful:
Don't try to switch to A2DP while some app is playing sound.
You need to disable all sound outputs first, then disconnect, connect, switch to A2DP, then select A2DP device as target.

#### Open your terminal and follow these steps:
We will use a PPA for adding Pipewire to Ubuntu 20.04, which is maintained regularly:

> `$ sudo add-apt-repository ppa:pipewire-debian/pipewire-upstream`

To update the PPA packages in your system do:
> `$ sudo apt update`

Install the package:
> `$ sudo apt install pipewire`

> `$ sudo apt install libspa-0.2-bluetooth`

Now, to install the client libraries:
> `$ sudo apt install pipewire-audio-client-libraries`

Reload the daemon:
> `$ systemctl --user daemon-reload`

Disable PulseAudio:
> `$ systemctl --user --now disable pulseaudio.service pulseaudio.socket`

If you are on Ubuntu 20.04, you also need to “mask” the PulseAudio by:
> `$ systemctl --user mask pulseaudio`


After a new update of Pipewire, you also need to enable pipewire-media-session-service:
> `$ systemctl --user --now enable pipewire-media-session.service`

You can ensure that Pipewire is now running through:
> `$ pactl info`

> This command will give the following output, in Server Name you can see:
PulseAudio (on PipeWire 0.3.28)

> If it doesn’t show up, then try restarting Pipewire by this command:

> `$ systemctl --user restart pipewire`

> If it’s still not showing your microphone, you can try rebooting once and remove and pair your Bluetooth device again to check if it works now.

If you want to rollback all the changes we did, you can do it by using:

> `$ systemctl --user unmask pulseaudio`

> `$ systemctl --user --now enable pulseaudio.service pulseaudio.socket`

> `$ systemctl --user status pulseaudio`

> `$ systemctl --user unmask pulseaudio`

> `$ systemctl --user --now enable pulseaudio.service pulseaudio.socket`

> `$ systemctl --user status pulseaudio`

> `$ systemctl --user stop pulseaudio`

> `$ systemctl --user restart pulseaudio`

> `$ systemctl --user status pulseaudio`

> `$ systemctl --user status pipewire`

> `$ pactl info`

> `$ systemctl --user restart pipewire`

> `$ bluetoothctl devices`

> `$ bluetoothctl info`
