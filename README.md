# Murali's Nix config

[Original Instructions for this setup](https://github.com/Misterio77/nix-starter-configs/tree/main?tab=readme-ov-file)

## Important bits

If you maked changes to config, run these commands:
```bash
# Ensure bash. zsh doesn't like the ".#" in commands
bash
cd /home/murali/Documents/nix-config
export NIX_CONFIG="experimental-features = nix-command flakes"
nix flake update
cp /etc/nixos/hardware-configuration.nix nixos/
git add .;git commit -m"update hardware config";git push
sudo nixos-rebuild switch --flake .#nixos

#
# May need to pull home-manager
nix shell nixpkgs#home-manager

bash
home-manager switch --flake .#murali@nixos
```
