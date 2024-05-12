These are patches in my gentoo system's /etc/portage/patches/ folder for various
programs. They're total hacks meant to improve the programs in some way to my
liking. Being hacks (and also being lazy) I probably won't ever attempt to
upstream any of these, but if you have come across this repo by chance and want
to do it yourself, feel free. I claim no special copyright over these patches,
if you must consider them licensed under the same as their parent projects.

Some notes follow on what the patches do and what version they have most recently been applied to. (It's possible they work for future versions and I just haven't bothered updating this readme.)

* *atril* - 1.26.0-r5 - When auto-scrolling a PDF, I wanted atril (aka evince)
  to show me an estimate time of how long it will take to reach the end of the
  document. This hack does that.
* *mate-system-monitor* - 1.26.2 - I believe this is a patch that landed in
  1.28, but basically the mate system monitor broke at some point and was no
  longer showing and saving selected fields like Memory, this fixes that. Will
  probably remove when I update to 1.28.
* *mate-notification-daemon* - 1.26.0-r1 - This patch is actually two-fold. The
  first part just returns FALSE early on for the check on whether a screensaver
  is active. (Why is it checking?!) Why? Because I have nuked mate-screensaver
  so that only xscreensaver runs, and because of that, my notifications stopped
  working because the screensaver check produces an error when the
  mate-screensaver isn't even running.

  The second part of the patch is for persistent notifications so long as they
  reach mate's daemon. It just logs them to a hard-coded file in my home
  directory. This is nice to scan with other programs and produce further alerts
  on, or just to see what I missed if I'm AFK for a while. I basically have a
  shell open always with tail -f on the file.
* *xscreensaver* - 6.08 - The top left pixel was always lit for the fireworks
  screensaver and it was bugging me
* *compiz* - 9999 - Compiz is dead but I still hold out, I want my wobbly
  windows forever! Anyway, I got this patch from somewhere, presumably it
  prevents screen tearing on nvidia cards. I'm not sure if it really does
  anything, though I don't notice screen tearing (much?) so maybe...
