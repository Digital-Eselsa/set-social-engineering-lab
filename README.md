# Social-Engineer Toolkit (SET) Lab Workflow

A GitHub-ready workspace for documenting the **Explore the Social Engineer Toolkit (SET)** practical exercise in an isolated, authorized training lab.

## Lab purpose

This exercise explores the SET menu, reviews website attack vectors, and demonstrates how a credential-harvesting page can collect **test-only dummy input** in a controlled virtual environment. The purpose is to understand phishing risks and improve defensive awareness.

> **Safety and authorization:** Perform this exercise only on virtual machines and systems you own or have explicit written permission to test. Keep the lab on an isolated host-only/internal network. Do not expose the cloned page to the public internet, distribute it to real users, or enter real email, network, or website credentials. Use only the dummy values supplied in the lab. Do not commit real credentials, session tokens, personal data, or unredacted capture output to GitHub.

## Repository structure

```text
SET-Lab-GitHub-Workflow/
├── README.md
├── .gitignore
├── docs/
│   └── lab-handout.docx
├── screenshots/
│   └── .gitkeep
├── evidence/
│   ├── browser/
│   │   └── .gitkeep
│   └── terminal-output/
│       └── .gitkeep
├── reports/
│   └── .gitkeep
├── notes/
│   └── answers.md
└── commands/
    └── commands.md
```

| Folder/file | What belongs here |
|---|---|
| `docs/` | The plain, unbranded lab handout supplied with this workflow. |
| `screenshots/` | Numbered screenshots showing key stages of the exercise. |
| `evidence/browser/` | Browser evidence from the isolated lab, with sensitive values obscured. |
| `evidence/terminal-output/` | Sanitized SET output and relevant terminal evidence. |
| `reports/` | Sanitized XML/report examples or report notes. Never commit live credentials or tokens. |
| `notes/answers.md` | Your answers to the questions and reflection prompts. |
| `commands/commands.md` | Commands used, their purpose, and any environment-specific notes. |

## Requirements

- Kali Linux VM with SET installed.
- DVWA VM available inside the same isolated lab network.
- VirtualBox (or another hypervisor) with an internal/host-only network configured.
- Firefox or another browser in Kali.
- Permission to test every system involved.

The original lab example uses `DVWA.vm` and the `10.6.6.0/24` network, with Kali at `10.6.6.1` and DVWA at `10.6.6.13`. Your VM addresses may differ. Confirm the addresses in your own lab before proceeding; do not assume these values apply to your environment.

## Execution workflow

### 1. Prepare and verify the lab

1. Start the Kali and DVWA virtual machines.
2. Confirm both VMs are connected to the same isolated internal/host-only network.
3. Confirm that Kali can reach the DVWA VM.
4. Open `http://DVWA.vm/` in Kali Firefox. If the lab's DNS/hosts mapping is not configured, use the DVWA VM's verified lab IP address.
5. Record the actual VM names, IP addresses, network mode, and date in `notes/answers.md`.

**Evidence:** Save a screenshot showing the lab environment and the DVWA login page. Do not include unrelated personal information.

### 2. Launch and explore SET

In a Kali terminal, start a root shell and launch SET:

```bash
sudo -i
setoolkit
```

Read the license terms and accept them only if you agree and are authorized to use the tool.

Explore the main menu and the Social-Engineering Attacks submenu. Review the descriptions of the available options. Return to the menu with the option shown by SET or `Ctrl+C` where appropriate.

**Evidence:** Capture the SET main menu and the Social-Engineering Attacks submenu. Record the answer to the Part 1 question in `notes/answers.md`.

### 3. Review website attack-vector options

Within the SET menus, review the website attack-vector descriptions and the credential-harvesting method descriptions. This workflow is for understanding the lab's controlled demonstration only.

Before proceeding, confirm:
- the target is your own DVWA VM;
- the network is isolated from public and production systems;
- the test will use dummy input only;
- no real users will be sent a link.

Record the relevant menu option names and your answers in `notes/answers.md`.

### 4. Conduct the controlled DVWA demonstration

Follow the unbranded lab handout in `docs/lab-handout.docx` for the exercise sequence. Keep the demonstration confined to the Kali and DVWA VMs.

- Use only the DVWA training login page.
- Use only the dummy username and password printed in the handout, or other clearly fictional test values.
- Do not use a personal Gmail account, real password, or any credential that grants access to a real service.
- Do not create or distribute a phishing link outside the isolated lab.
- Stop the test if traffic leaves the lab network or an unexpected host is involved.

**Evidence:** Capture the browser page and the relevant terminal result, after masking any test values or tokens before saving or sharing.

### 5. Review and sanitize the report

If the lab generates a report, inspect it locally. Treat all captured form data, tokens, and session-related values as sensitive even when they were generated during a test.

Before adding any report to this repository:
1. Remove or replace usernames, passwords, tokens, cookies, and personal data.
2. Confirm the report contains no real account information.
3. Prefer a short sanitized excerpt or a written summary over a raw capture file.
4. Never commit unredacted credential-harvesting output.

Place only sanitized report material in `reports/`.

### 6. Complete the reflection

Answer every question in `notes/answers.md`. Explain what the demonstration shows about user awareness, URL inspection, credential reuse, and defensive controls. Do not include actual credentials or tokens in your answers.

## Screenshot and evidence naming

Use a consistent sequence, for example:

```text
screenshots/
├── 01-lab-network.png
├── 02-dvwa-login-page.png
├── 03-set-main-menu.png
├── 04-set-social-engineering-menu.png
├── 05-set-website-attack-menu.png
└── 06-controlled-lab-result-redacted.png
```

Only add screenshots you actually captured. The starter repository intentionally contains no fabricated screenshots.

## Suggested completion checklist

- [ ] Kali and DVWA are running in an isolated lab network.
- [ ] DVWA login page opens from Kali.
- [ ] SET launches successfully.
- [ ] Main menu and Social-Engineering Attacks menu reviewed.
- [ ] Website attack-vector descriptions reviewed.
- [ ] Controlled demonstration completed using dummy values only.
- [ ] Screenshots captured and checked for sensitive information.
- [ ] Report material sanitized before inclusion.
- [ ] All lab questions and reflection completed.
- [ ] README and evidence folders updated.
- [ ] Repository reviewed for secrets before pushing to GitHub.

## GitHub upload workflow

From a terminal opened in this repository folder:

```bash
git init
git add .
git status
git commit -m "Document SET social engineering lab"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Replace the remote URL with your own GitHub repository URL. If the repository already exists locally, do not run `git init` again. Review `git status` and inspect the files before every push.

## Defensive learning outcomes

Use the findings to discuss:
- why users should inspect URLs before entering credentials;
- why HTTPS alone does not prove that a page is legitimate;
- the importance of phishing-awareness training;
- multi-factor authentication and phishing-resistant authentication;
- password managers and unique passwords;
- email/web filtering, reporting processes, and monitoring for suspicious credential submissions.

## Responsible-use statement

This repository is intended for authorized cybersecurity education in a closed lab. It is not a guide to targeting third parties. Any assessment outside the lab requires explicit written authorization, a defined scope, and appropriate safeguards.
