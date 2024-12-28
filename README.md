# Openbangla Keyboard Overlay 

This repo contains OpenBangla Keyboard Overlays which will install the develop branch od OpenBangla Keyboard but with my preferred logo! 

## Steps for fcitx5
1. Git clone this repo and move openbangla-fcitx5-overlay.nix file to ```/etc/nixos/```
2. Edit the ```configuration.nix``` file and add these lines
  ```
nixpkgs.overlays = [
    (import /etc/nixos/openbangla-fcitx5-overlay.nix)
  ];

i18n.inputMethod = {
    enabled = "fcitx5";
    fcitx5.addons = with pkgs; [
        openbangla-keyboard
    ];
   };

```
3. Rebuild your nixos configuration by the command ```sudo nixos-rebuild switch```
4. Done! 

## Steps for ibus

1. Git clone this repo and move openbangla-ibus-overlay.nix file to ```/etc/nixos/```
2. Edit the ```configuration.nix``` file and add these lines
  ```
nixpkgs.overlays = [
    (import /etc/nixos/openbangla-ibus-overlay.nix)
  ];

i18n.inputMethod = {
    type = "ibus";
    ibus.engines = with pkgs.ibus-engines; [
        openbangla-keyboard
    ];
   };

```
3. Rebuild your nixos configuration by the command ```sudo nixos-rebuild switch```
4. Done! 
