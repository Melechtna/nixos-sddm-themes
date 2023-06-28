# nixos-sddm-themes

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
