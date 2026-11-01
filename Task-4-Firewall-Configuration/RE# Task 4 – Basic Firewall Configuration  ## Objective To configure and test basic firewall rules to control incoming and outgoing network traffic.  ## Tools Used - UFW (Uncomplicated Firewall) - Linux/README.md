# Task 4 - Firewall Configuration

## Objective

To configure and test firewall rules on Windows and Kali Linux.

## Windows Firewall

A temporary inbound firewall rule was created to block TCP port 23.

- Protocol: TCP
- Local Port: 23
- Action: Block
- Rule: Block TCP Port 23 - Task 4

The connection was tested using:

`Test-NetConnection 127.0.0.1 -Port 23`

The test result showed:

`TcpTestSucceeded : False`

The temporary Windows firewall rule was removed after testing.

## Kali Linux Firewall

UFW was configured on Kali Linux.

SSH traffic was allowed using:

`sudo ufw allow 22/tcp`

The firewall was enabled using:

`sudo ufw enable`

The status was verified using:

`sudo ufw status`

Result:

`Status: active`

`22/tcp ALLOW`

## Evidence

This repository contains:

1. Windows firewall rule screenshot
2. TCP port 23 settings screenshot
3. PowerShell connectivity test screenshot
4. Kali Linux UFW status screenshot
5. Firewall configuration report

## Conclusion

The task demonstrated basic firewall configuration and testing on Windows and Kali Linux.
