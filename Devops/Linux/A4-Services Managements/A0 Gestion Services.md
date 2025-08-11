# Linux Started !
1. bios -> GRAP -> kernel -> run first process `systemd` PID = 1.
- systemd initialized system :
	1. configure date and time.
	2. configure network.
	3. mount system files.
	4. create console
	5. run `services`.


===> can access systemd by Cmd `systemctl`.
- systemd have Unites `files configuration management united`:
	1. services
	2. target
	3. timer
	4. mount
	5.  . . .

- name unites : `<unites>.<type unites>` 
	- services : sshd.services
	- target : poweroff.target  