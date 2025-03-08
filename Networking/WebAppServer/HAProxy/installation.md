Ubuntu:

1. Update the package list and Install HAProxy:

-  sudo apt update
- sudo apt install haproxy

3. Start the HAProxy service:

- sudo systemctl status haproxy
- Sudo service haproxy status

5. Enable HAProxy to start on boot:

- sudo systemctl enable haproxy
- sudo service haproxy start

7. Configuration:

The main configuration file for HAProxy is usually located at /etc/haproxy/haproxy.cfg. You'll need to edit this file to define your backend servers, frontend settings, and any other configurations specific to your environment