In Unix-like systems, **service managers** are tools used to manage system services (`starting`, `stopping`, `enabling`, and monitoring services). Here's where you can find and manage them:

---

### **1. Common Service Managers**

#### **Systemd** (Most Modern Linux Distros)

- **Location**: Services are defined as unit files in `/etc/systemd/system/` or `/lib/systemd/system/`.
- **Commands**:
    - Start a service: `sudo systemctl start <service_name>`
    - Stop a service: `sudo systemctl stop <service_name>`
    
    - is active : `systemctl is-active <service_name>`
    - is enabled : `systemctl is-enabled <service_name>`
	- View status: `sudo systemctl status <service_name>`
	
    - Enable at boot: `sudo systemctl enable <service_name>`
    - Disable: `sudo systemctl disable <service_name>`

	- mask services: `systemctl mask <services_name>` can't started or stopped enabled or disabled.
	- un mask services: `systemctl unmask <services_name>` can started or stopped enabled or disabled.
	
    - List all unites: `sudo systemctl list-units`
	    - `--type service` type unites : 
		    - `automount mount scope slice swap`
		    - `timer device path service socket target`
	    - `--state running` state of unites
	-  List all unites active on startup `sudo systemctl list-unit-files`

service in-active and disable ===> active and enabled
- `systemctl enable <s_n>` and `systemctl start <s_n>`.
- `system enable --now <s_n>` : to enable and start services.
now we want to disable and stop services 
- `systemctl stop <s_n>` and `systemctl disable <s_n>`.
- `systemctl disable --now <s_n>`.
