# Investigation

## Timeline:

2026-03-14T04:19:17.884340+00:00 ubuntu sshd[8503]: Failed password for admin from 192.168.56.1 port 42306 ssh2
2026-03-14T04:19:17.898212+00:00 ubuntu sshd[8505]: Failed password for admin from 192.168.56.1 port 42308 ssh2
2026-03-14T04:19:17.899601+00:00 ubuntu sshd[8501]: Failed password for admin from 192.168.56.1 port 42290 ssh2
2026-03-14T04:19:17.905604+00:00 ubuntu sshd[8508]: Failed password for admin from 192.168.56.1 port 50792 ssh2
2026-03-14T04:19:20.218567+00:00 ubuntu sshd[8503]: Failed password for admin from 192.168.56.1 port 42306 ssh2
2026-03-14T04:19:20.225374+00:00 ubuntu sshd[8505]: Failed password for admin from 192.168.56.1 port 42308 ssh2
2026-03-14T04:19:20.231888+00:00 ubuntu sshd[8501]: Failed password for admin from 192.168.56.1 port 42290 ssh2
2026-03-14T04:19:20.235599+00:00 ubuntu sshd[8508]: Failed password for admin from 192.168.56.1 port 50792 ssh2
2026-03-14T04:19:20.652634+00:00 ubuntu sshd[8501]: error: maximum authentication attempts exceeded for admin from 192.168.56.1 port 42290 ssh2 [preauth]
2026-03-14T04:19:20.653931+00:00 ubuntu sshd[8501]: Disconnecting authenticating user archlinux 192.168.56.1 port 42290: Too many authentication failures [preauth]
2026-03-14T04:19:20.654036+00:00 ubuntu sshd[8501]: PAM 4 more authentication failures; logname= uid=0 euid=0 tty=ssh ruser= rhost=192.168.56.1  user=archlinux
2026-03-14T04:19:20.654141+00:00 ubuntu sshd[8501]: PAM service(sshd) ignoring max retries; 5 > 3
2026-03-14T04:19:20.739582+00:00 ubuntu sshd[8512]: pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=192.168.56.1  user=archlinux
2026-03-14T04:19:22.614339+00:00 ubuntu sshd[8503]: Failed password for admin from 192.168.56.1 port 42306 ssh2
2026-03-14T04:19:22.629128+00:00 ubuntu sshd[8505]: Failed password for admin from 192.168.56.1 port 42308 ssh2
2026-03-14T04:19:22.654443+00:00 ubuntu sshd[8508]: Failed password for admin from 192.168.56.1 port 50792 ssh2
2026-03-14T04:19:22.709462+00:00 ubuntu sshd[8512]: Failed password for admin from 192.168.56.1 port 50794 ssh2
2026-03-14T04:19:24.255049+00:00 ubuntu sshd[8508]: Connection closed by authenticating user archlinux 192.168.56.1 port 50792 [preauth]
2026-03-14T04:19:24.255534+00:00 ubuntu sshd[8508]: PAM 4 more authentication failures; logname= uid=0 euid=0 tty=ssh ruser= rhost=192.168.56.1  user=archlinux
2026-03-14T04:19:24.255655+00:00 ubuntu sshd[8508]: PAM service(sshd) ignoring max retries; 5 > 3
2026-03-14T04:19:24.269410+00:00 ubuntu sshd[8503]: Accepted password for admin from 192.168.56.1 port 42306 ssh2
2026-03-14T04:19:24.273296+00:00 ubuntu sshd[8503]: pam_unix(sshd:session): session opened for user admin(uid=1000) by archlinux(uid=0)
2026-03-14T04:19:24.284849+00:00 ubuntu systemd-logind[631]: New session 100 of user morgana.
2026-03-14T04:19:24.321558+00:00 ubuntu sshd[8512]: Connection closed by authenticating user archlinux 192.168.56.1 port 50794 [preauth]

## Event Description

) Failed password for admin from 192.168.56.1 port XXXX ssh2
	Incorrect password attempt for user "admin". Each line = one failed attempt in a parallel connection.

) error: maximum authentication attempts exceeded for admin from 192.168.56.1 port 42290 ssh2 [preauth]
	OpenSSH detected that the maximum number of authentication attempts for this connection was exceeded.

) Disconnecting authenticating user admin 192.168.56.1 port 42290: Too many authentication failures [preauth]
	Connection closed due to too many authentication failures in this specific session.

) PAM 4 more authentication failures; ... user=admin
	PAM (Pluggable Authentication Modules) logged additional accumulated failure).

) PAM service(sshd) ignoring max retries; 5 > 3
	PAM is ignoring the configured retry limit (likely pam_tally or faillock with deny=3) because the number of failures (5) already exceeds the limit (3). Common when multiple parallel connections accumulate failures.

) pam_unix(sshd:auth): authentication failure; ... user=admin
	Authentication failure recorded by the pam_unix module (local password check).

) Connection closed by authenticating user admin 192.168.56.1 port XXXX [preauth]
	Connection closed (usually after exceeding attempts or client gave up).

) Accepted password for archlinux from 192.168.56.1 port 42306 ssh2
	Correct password accepted on this connection (port 42306). Successful login.

) pam_unix(sshd:session): session opened for user admin(uid=1000) by archlinux(uid=0)
	SSH session opened for user archlinux (UID 1000). "by archlinux" indicates the sshd process was started/handled under user archlinux (likely root or sudo context).

) systemd-logind[631]: New session 100 of user archlinux.
	systemd-logind registered a new login session.
