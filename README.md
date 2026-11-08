# Linux Command Guide

A beginner-to-advanced Linux command reference that explains **what each command does, how to use it, and where to use it** in real sysadmin, DevOps and SOC work.

**Live site:** `https://varun70.github.io/linux-command-guide/`

No build step. No dependencies. The whole site is one `index.html` file.

## Features

- **119 commands in 18 categories**, from `pwd` and `ls` to `journalctl`, `tcpdump` and `auditctl`
- **Command cards** with syntax, the options that matter, copyable examples, where to use it, a common mistake and related commands
- **Search by command or by task**, for example "disk space" or "who logged in"
- **Filters** for level (beginner, intermediate, advanced), role (everyday, sysadmin, DevOps, SOC analyst) and risk (safe, use with care, destructive)
- **Take a command apart:** select each piece of a real command to see what it does
- **Learning path** with six levels and a milestone for each
- **Nine practice projects**, including a disk-full drill, a hardened SSH server and a SOC hunt
- **Danger zone** for commands that can destroy data, with a preview, back up, act, verify habit
- Light and dark themes, mobile friendly, and a "Mark as learned" checkbox that saves in your browser

## Categories

Navigation and help, files and folders, reading and editing text, searching and filtering, permissions and ownership, users and groups, processes, system monitoring, disks and storage, networking, packages, archives and backup, services (systemd), logs, shell and scripting, SSH and remote access, security and SOC, scheduling.

## Run it locally

Open `index.html` in any browser. That is all.

Or serve it on your machine:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Host it on GitHub Pages

1. Push this repository to GitHub.
2. Open **Settings**, then **Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select **main** and **/ (root)**, then **Save**.
4. After a minute the site is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

## Add or edit a command

Every command is one line in the `<script>` section of `index.html`:

```js
c('name', 'category', level, danger, 'What it does',
  'syntax',
  [['option', 'meaning']],
  [['example command', 'what it does']],
  'Where to use it',
  'Common mistake',
  'related commands',
  'e s d o');
```

- `category`: one of `nav files text search perms users proc monitor disk net pkg archive systemd logs script ssh security cron`
- `level`: `1` beginner, `2` intermediate, `3` advanced
- `danger`: `0` safe, `1` use with care, `2` destructive
- last value: who uses it, where `e` is everyday, `s` sysadmin, `d` DevOps and `o` SOC analyst

Copy an existing line, change the text, save, and refresh the page.

## Project structure

```
.
├── index.html   # the whole website (HTML, CSS and JavaScript)
└── README.md
```

## Safety notice

Linux runs exactly what you type, often with no undo. Try destructive commands (`rm -rf`, `dd`, `mkfs`, `chmod -R`) only in a virtual machine or container you can throw away.

Only use security tools such as `nmap`, `tcpdump` and `nc` on systems you own or have written permission to test.

## Sources

- [GNU Coreutils manual](https://www.gnu.org/software/coreutils/manual/coreutils.html)
- [Linux man pages](https://man7.org/linux/man-pages/)
- [ArchWiki](https://wiki.archlinux.org/)
- [Red Hat Enable Sysadmin](https://www.redhat.com/sysadmin/)
- [Ubuntu documentation](https://help.ubuntu.com/community/UFW)
- [The Linux Command Line](https://linuxcommand.org/tlcl.php) by William Shotts

Always confirm flags with `man` on your own system, because options differ between GNU, BSD and BusyBox.

## Author

Built by **YOUR NAME**.

## License

MIT. Add a `LICENSE` file if you want others to reuse it.
