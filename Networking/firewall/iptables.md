`iptables` is a user-space utility program that allows a system administrator to configure the IP packet filter rules of the Linux kernel firewall, implemented as different Netfilter modules. The filters are organized in different tables, which contain chains of rules for how to treat network traffic packets.

Here are the key components of `iptables`:

1.  **Tables:**

   - **Filter Table (`filter`):** The default table responsible for filtering packets based on defined rules. It is used for decisions about whether to allow or deny packets.

   - **NAT Table (`nat`):** Used for Network Address Translation (NAT), allowing the modification of source or destination IP addresses in packets.

- **Mangle Table (`mangle`):** Used for specialized packet alteration, such as changing the Quality of Service (QoS) bits or marking packets for routing.

1. **Chains:**

   - Chains are sequences of rules that are applied to packets. The three default chains are:

     - **INPUT:** Applies to incoming packets destined for the local machine.

     - **OUTPUT:** Applies to locally-generated packets leaving the machine.

     - **FORWARD:** Applies to packets being routed through the machine.

1. **Rules:**

   - Rules define specific conditions and actions for packets. They consist of matching criteria and an associated target (action).

   - Example Rule: "Accept all incoming TCP traffic on port 80."

1. **Targets:**

   - Targets define the action to be taken if a packet matches a rule. Common targets include `ACCEPT`, `DROP` (discard the packet without responding), and `REJECT` (discard the packet with an error).

Here are a few examples of `iptables` commands:

- Allow incoming traffic on port 80 (HTTP):

  ```bash

  sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT

  ```

- Allow outgoing traffic on port 53 (DNS):

  ```bash

  sudo iptables -A OUTPUT -p udp --dport 53 -j ACCEPT

  ```

- Drop all incoming traffic by default:

  ```bash

  sudo iptables -P INPUT DROP

  ```

- View current rules:

  ```bash

  sudo iptables -L

  ```

Keep in mind that `iptables` commands are typically run with elevated privileges (`sudo`) as they involve configuring network-level security settings. Also, the changes made with `iptables` are not persistent by default and will be lost on a system reboot. To make changes persistent, you may use tools like `iptables-save` and `iptables-restore`, or you might integrate it with your distribution's init system or firewall management tool.