🗺️ Win11DesktopMover — Roadmap
🎯 Near‑term improvements
1. Jump to first / last virtual desktop
Description:  
Add the ability to instantly jump to the first or last virtual desktop.

Implementation plan:

Detect current desktop index

When moving left → jump to desktop[0]

When moving right → jump to desktop[last]

Optional: dedicated hotkeys for these actions

2. “Start with Windows” toggle
Description:  
A tray menu checkbox that enables or disables autostart.

Implementation plan:

Add a tray menu item

When enabled → create a .url shortcut in the Startup folder

When disabled → remove the shortcut

Persist state in config.toml

3. Full uninstall (self‑removal)
Description:  
A tray menu option that completely removes the application.

What should be removed:

the executable itself

%AppData%/Win11DesktopMover folder

config.toml

state.json

app.log

autostart shortcut (if present)

Implementation plan:

Add “Uninstall…” menu item

On click:

show a confirmation MessageBox

delete config files

remove autostart entry

delete the executable via a temporary .bat script

exit the application

4. Switch to a specific desktop (Win+Ctrl+Shift+1..0)
Description:  
Allows jumping directly to any virtual desktop by index.

Implementation plan:

Add 10 hotkeys: 1–9 and 0

0 = 10th desktop

On press → SwitchDesktop(desktops[index])

Validate that the target desktop exists

Add configuration options in config.toml

📌 After licensing system is introduced
5. Licensing & “lifetime” activation
Description:

activation system

disabling donation banner

Pro‑only features

offline license support (as long as Win API allows)

6. Improved tray UI
Description:

checkboxes

hotkey configuration

update checker

license info

7. Improved config recovery
Description:

automatic backup of corrupted config

logging the reason for recovery

🧩 Future ideas
Move window to a specific desktop (not just switch)

Create new desktops via hotkey

Remove empty desktops

Cyclic switching (last → first)

Portable mode (no AppData usage)
