# Attack Scenarios

## SSH Brute Force

Tool: Hydra

Command:
hydra -l ID_USER -P wordlist.txt ssh://192.168.56.4 -t 4 -V

) hydra → main tool.
) -l ID_USER → fixed login (example: -l ubuntu or -l root), use -L users.txt if testing multiple users.
) -P wordlist.txt → file with passwords (one per line).
) -t 4 → 4 parallel tasks (threads/simultaneous connections) ideal for SSH, much >4 causes "connection refused" or temporary ban).
) -V → verbose mode (shows each attempt: [22][ssh] host: 192.168.56.4   login: ID_USER   password: attempt).
) ssh://192.168.56.4 → protocol + target (modern URI format).
) -f (optional but recommended) → stop immediately after finding a valid password.

## Expected Logs in Wazuh

) Rule 5712: SSHD: Attempt to login using a known user (individual failures).
) Rule 5763: SSHD brute force trying to get access to the system (correlates multiple failures).
) If success after brute force: custom rule or 5710/5503 + login success event.
) Dashboard: Security events → filter by rule.id:5763 or srcip of the attacker.


