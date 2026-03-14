# Detection Rules

## SSH Brute Force Detection

-Logic:
16 failed logins within 9 seconds.

-Log Source on Ubuntu Server:
 sudo tail -f /var/log/auth.log
 2026-03-14T04:19:11.983244+00:00 ubuntu sshd[8503]: Failed password for archlinux from 192.168.56.1 port 42306 ssh2
 2026-03-14T04:19:11.998481+00:00 ubuntu sshd[8505]: Failed password for archlinux from 192.168.56.1 port 42308 ssh2
 2026-03-14T04:19:13.413531+00:00 ubuntu sshd[8501]: Failed password for archlinux from 192.168.56.1 port 42290 ssh2
 2026-03-14T04:19:13.426218+00:00 ubuntu sshd[8508]: Failed password for archlinux from 192.168.56.1 port 50792 ssh2
 2026-03-14T04:19:15.126135+00:00 ubuntu sshd[8503]: Failed password for archlinux from 192.168.56.1 port 42306 ssh2
 2026-03-14T04:19:15.134580+00:00 ubuntu sshd[8505]: Failed password for archlinux from 192.168.56.1 port 42308 ssh2
 2026-03-14T04:19:15.145753+00:00 ubuntu sshd[8501]: Failed password for archlinux from 192.168.56.1 port 42290 ssh2
 2026-03-14T04:19:15.157429+00:00 ubuntu sshd[8508]: Failed password for archlinux from 192.168.56.1 port 50792 ssh2
 2026-03-14T04:19:17.884340+00:00 ubuntu sshd[8503]: Failed password for archlinux from 192.168.56.1 port 42306 ssh2
 2026-03-14T04:19:17.898212+00:00 ubuntu sshd[8505]: Failed password for archlinux from 192.168.56.1 port 42308 ssh2
 2026-03-14T04:19:17.899601+00:00 ubuntu sshd[8501]: Failed password for archlinux from 192.168.56.1 port 42290 ssh2
 2026-03-14T04:19:17.905604+00:00 ubuntu sshd[8508]: Failed password for archlinux from 192.168.56.1 port 50792 ssh2
 2026-03-14T04:19:20.218567+00:00 ubuntu sshd[8503]: Failed password for archlinux from 192.168.56.1 port 42306 ssh2
 2026-03-14T04:19:20.225374+00:00 ubuntu sshd[8505]: Failed password for archlinux from 192.168.56.1 port 42308 ssh2
 2026-03-14T04:19:20.231888+00:00 ubuntu sshd[8501]: Failed password for archlinux from 192.168.56.1 port 42290 ssh2
 2026-03-14T04:19:20.235599+00:00 ubuntu sshd[8508]: Failed password for archlinux from 192.168.56.1 port 50792 ssh2

- rule.mitre.id:
   	 T1078, T1110
- rule.mitre.tactic:
   	 Defense Evasion, Persistence, Privilege Escalation, Initial Access, Credential Access
- rule.id:
   	 40112

