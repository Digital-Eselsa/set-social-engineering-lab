# Command Notes

Record the commands you actually used and note any differences caused by your Kali/SET version. Do not paste secrets or captured credential values.

## Start SET

```bash
sudo -i
setoolkit
```

- `sudo -i`: opens a root login shell for administrative tasks.
- `setoolkit`: launches the Social-Engineer Toolkit menu.

## Network checks

Use these only to inspect your own isolated lab:

```bash
ip addr
ip route
ping -c 4 <DVWA-LAB-IP>
```

Replace `<DVWA-LAB-IP>` with the verified IP address of your DVWA VM.

## Evidence handling

Before committing:
- inspect screenshots for visible usernames, passwords, tokens, cookies, or personal information;
- redact sensitive values in a copy of the evidence;
- do not alter the original capture if it is required for local analysis;
- never add raw credential-harvesting output to a public repository.

## Version notes

- Kali release:
- SET version:
- DVWA version:
- Date:
- Deviations from the lab handout:
