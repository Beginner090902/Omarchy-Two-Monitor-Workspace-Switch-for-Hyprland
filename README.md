# Two-Monitor Workspace Switch for Hyprland

## Automated script for synchronized workspace switching on dual monitors

### 🔧 Description

This project provides a simple shell script setup for Hyprland that allows you to switch workspaces across two monitors simultaneously.
Whenever you press Super + <number>, monitor 1 will switch to workspace <number> and monitor 2 will switch to workspace (<number> + 5) — for example:

Super + 1 → monitor1: workspace 1, monitor2: workspace 6

Super + 2 → monitor1: workspace 2, monitor2: workspace 7
… up to Super + 5 → workspace 5 and workspace 10.

This is ideal for dual-monitor setups where you want mirrored or paired workspaces with one shortcut.

### ✅ Features

Two-monitor workspace pairing with one keybind

Compatible with Hyprland on Arch/Omarchy

Minimal shell script, easy to adapt and extend

Does not require complex window-manager rules

### 🛠 Installation

Clone the repository in your Hyperland config

    cd .config/hypr/
    git clone https://github.com/Beginner090902/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland.git



When Make the scripts executable: 

    cd .config/hypr/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland/two-monitor-setupskript

    chmod +x v-monitor1.sh v-monitor2.sh v-monitor3.sh v-monitor4.sh v-monitor5.sh 

## Set your monitor config right. For me it was this.

### in .config/hypr/monitor.conf

###
    env = GDK_SCALE,2
    monitor=DP-2,2560x1440@143,0x0,1
    monitor=DP-1,2560x1440@59,2560x0,1

    # Workspaces zuweisen
    workspace = 1, monitor:DP-2
    workspace = 2, monitor:DP-2
    workspace = 3, monitor:DP-2
    workspace = 4, monitor:DP-2
    workspace = 5, monitor:DP-2

    workspace = 6, monitor:DP-1
    workspace = 7, monitor:DP-1
    workspace = 8, monitor:DP-1
    workspace = 9, monitor:DP-1
    workspace = 10, monitor:DP-1
###
### Monitor names must match your setup check with.

    hyprctl monitors

## Now the last Step 
### Edit the .contig.hypr/bindings.conf
With this 

###
    bind = SUPER, 1, exec, .config/hypr/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland/two-monitor-setupskript/v-monitor1.sh
    bind = Super, 2, exec, .config/hypr/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland/two-monitor-setupskript/v-monitor2.sh
    bind = Super, 3, exec, .config/hypr/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland/two-monitor-setupskript/v-monitor3.sh
    bind = Super, 4, exec, .config/hypr/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland/two-monitor-setupskript/v-monitor4.sh
    bind = Super, 5, exec, .config/hypr/Omarchy-Two-Monitor-Workspace-Switch-for-Hyprland/two-monitor-setupskript/v-monitor5.sh
###



## Now Reload Hyprland configuration:

    hyprctl reload  


### 📋 Usage

Super + <number>: switch both monitors to the paired workspaces.

