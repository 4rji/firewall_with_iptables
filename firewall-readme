# firewall-ipt

`firewall-ipt` is an interactive `iptables` helper for quickly managing host firewall rules from a menu.

## What It Does

- Creates and applies custom rules for `INPUT`, `OUTPUT`, and `FORWARD`
- Lists current rules with line numbers
- Enables/disables base firewall policies
- Provides security profiles:
  - **Aggressive mode**: `INPUT=DROP`, `FORWARD=DROP`, `OUTPUT=DROP`
  - **Internet mode**: same default-drop posture, but allows outbound DNS/HTTP/HTTPS
- Deletes rules by chain + line number

## Aggressive Mode (Examples)

Aggressive mode blocks all outbound traffic unless explicitly allowed.

Example outbound allow rules after enabling aggressive mode:

```bash
# DNS
iptables -A OUTPUT -p udp --dport 53 -j ACCEPT
iptables -A OUTPUT -p tcp --dport 53 -j ACCEPT

# HTTPS
iptables -A OUTPUT -p tcp --dport 443 -j ACCEPT
iptables -A OUTPUT -p udp --dport 443 -j ACCEPT

# Optional SSH outbound
iptables -A OUTPUT -p tcp --dport 22 -j ACCEPT
```

This gives you a strict allowlist model: only traffic you define is allowed out.
