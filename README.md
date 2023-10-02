# nixos-sddm-themes

 It's just https://store.kde.org/p/1312658 but I swapped out the background for something I personally use all the time. I really shouldn't have to go this far for a simple background change.

I don't plan to actually make any changes to what I'm using here, it's litteraly just a background swap because....NixOS

# Installation:
First, download the SDDTheme.nix for whichever theme you'd like, each can be found in the branches, then copy or move it to /etc/nixos/

Second, you'll need to add these lines to your configuration.nix

  services.xserver.displayManager.sddm.enable = true;
  services.xserver.displayManager.sddm.theme = "sugar-candy";

  nixpkgs.config.packageOverrides = pkgs: rec {
    sddmtheme = pkgs.callPackage ./SDDMTheme.nix {};
  };

environment.systemPackages = with pkgs; [ sddmtheme ];

Keeping in mind that some of these may already exist.