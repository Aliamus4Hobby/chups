# chups "Check UPS" (Network UPS Tools CLI Utility)

A lightweight, platform-agnostic Bash utility wrapper for Network UPS Tools (`upsc`). It offers quick single-line status reporting, a live dashboard, and automated multi-init driver stack recovery during hardware lockups.

## Features

- **Default Mode**: Prints a single, clean line showing current battery charge—perfect for scripting, desktop status modules, or piping into tools like `cowsay`.
- **Continuous Monitoring (`-c`)**: Launches an interactive, alternate-buffer live fullscreen dashboard that updates dynamically every second without polluting your terminal scrollback history.
- **Hardware Stack Reset (`-r`)**: Dynamically detects your system init architecture (`systemd`, `OpenRC/SysVinit`, or raw `upsdrvctl` binaries) to force-cycle a frozen USB connection during power transition anomalies.
- **Platform Agnostic**: Auto-discovers the local active UPS profile name dynamically via `upsc -l`.

## Installation

1. Download the script directly into your local execution path:
   ```bash
   curl -sSL https://raw.githubusercontent.com/Aliamus4Hobby/chups/main/chups -o ~/.local/bin/chups

2. Make the script executable:

    ```bash
    chmod +x ~/.local/bin/chups

## Usage: 

chups [OPTIONS]

Options:

  -r, --restart       Force-restart the NUT driver stack based on local system layout
  
  -c, --continuous    Launch the fullscreen btop-style monitoring dashboard
  
  -h, --help          Show this help message
  

Note: Running 'chups' without options prints the charge once and exits.

Examples

Standard status check:

	```bash
	$ chups
	UPS [myups] Charge: 100%

## "Fun" pipeline integrations:
	
	```bash
	$ chups | cowsay
 	______________________
	< UPS [mgeups] Charge: 95% >
	 ----------------------
        	\   ^__^
        	 \  (oo)\_______
            	(__)\       )\/\
                	||----w |
                	||     ||


Disclaimer: This was 99% halucinated by an LLM use at your own risk.
