# Murali's Nix config

[Original Instructions for this setup](https://github.com/Misterio77/nix-starter-configs/tree/main?tab=readme-ov-file)

## Important bits

If you maked changes to config, run these commands:
```bash
cd /home/murali/Documents/nix-config
export NIX_CONFIG="experimental-features = nix-command flakes"
nix flake update
cp /etc/nixos/hardware-configuration.nix nixos/
git add .;git commit -m"update hardware config";git push
sudo nixos-rebuild switch --flake .#nixos
home-manager switch --flake .#murali@nixos
```
