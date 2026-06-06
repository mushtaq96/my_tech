
-----

# 🛠️ My Tech Stack & Ops Manual

## **1. Environment & Core Tools**

  * **Terminal:** Terminator + **Fish Shell** (Run `fish_config` for web UI setup).
  * **Editors:** Sublime Text 3, VS Code.
  * **Python/Data:** Anaconda (Jupyter), `pip3`, `autoenv` (auto-activate venv).
  * **Utility:** `tree` (Visualize structure), `Gnome Tweaks`, `bucklespring` (Mechanical keys sounds).

### **Tree Shortcuts**

  * **Standard:** `tree -h` (sizes), `tree -a` (hidden), `tree -d` (dirs only).
  * **Clean View:** `tree -I "node_modules|__pycache__|env|build|dist"`.

-----

## **2. System & Package Management**

  * **Apt (Debian/Ubuntu):** Cache at `/var/cache/apt/archives`.
  * **Conda + Fish:** Known path issues. [SO Fix](https://stackoverflow.com/questions/34280113/add-conda-to-path-in-fish/34280406#34280406).
  * **Node.js (NVM):**
      * `nvm ls` | `nvm install 16.14` | `nvm use 16.14` | `node -v`.
      * **Rule:** Use one lockfile. Delete `package-lock.json` if using `yarn.lock` (and vice versa).

-----

## **3. Critical Snippets & Fixes**

### **Network & Port Conflicts**

  * **Identify:** `lsof -i :3000` (or `:8000`)
  * **Kill:** `kill -9 <PID>`

### **SSL Python/Requests Fix**

Add to shell config to resolve certificate errors:

```sh
export SSL_CERT_FILE=/etc/ssl/certs/ca-certificates.crt
export REQUESTS_CA_BUNDLE=/etc/ssl/certs/ca-certificates.crt
```

### **The "Clean" Alias (WSL/Docker/Node)**

Add this to `~/.bashrc` or `~/.config/fish/config.fish`:

```bash
alias clean="rm -rf ~/.cache/* && npm cache clean --force && docker system prune -a --volumes -f"
```

### **Find Largest Files**

```sh
find . -type f -exec du -h {} + | sort -rh | head -20
```

-----

## **4. GitHub & Remote Access (SSH)**

1.  **Check:** `ls -al ~/.ssh`
2.  **Generate:** `ssh-keygen -t ed25519 -C "email@example.com"`
3.  **Agent:** `eval "$(ssh-agent -s)"` && `ssh-add ~/.ssh/id_ed25519`
4.  **Connect:** `ssh -T git@github.com`
5.  **Termux:** `ssh username@<ipaddress> -p 8022`

### **Server Hardening (New User Setup)**

1.  `adduser mushtaq`
2.  `usermod -aG sudo mushtaq`
3.  **Permissions (Critical):**
      * `chmod 700 ~/.ssh`
      * `chmod 600 ~/.ssh/authorized_keys`
      * `chown -R mushtaq:mushtaq ~/.ssh`

-----

## **5. Software Guides & Shortcuts**

### **VS Code**

  * **Fold/Unfold Code:** `Ctrl+K, 0` / `Ctrl+K, J`
  * **Collapse Explorer:** `Ctrl+Shift+E` → `Ctrl+Left Arrow`
  * **WSL Tab Fix:** `Ctrl+Shift+P` \> *Toggle Tab Moves Focus*
  * **HTML Formatter Settings:**

<!-- end list -->

```json
{
    "editor.formatOnSave": true,
    "[html]": { "editor.defaultFormatter": "vscode.html-language-features" }
}
```

### **WSL2 Disk Shrink (Windows PowerShell)**

```powershell
wsl --shutdown
diskpart
# select vdisk file="C:\PATH\TO\ext4.vhdx"
attach vdisk readonly
compact vdisk
detach vdisk
```

### **Software KVM (Microsoft PowerToys)**

Fix: Firewall > Allow App > PowerToys.MouseWithoutBorders > Check Public.

-----

## **6. Browsing & Resources**

### **Extensions**

  * **Core:** HTTPS Everywhere, Grammarly, Wikiwand, Adblock Plus, OneTab, Hoxx VPN.
  * **Dev:** Web Search Navigator (Keyboard shortcuts), Wappalyzer (Stack identifier).
  * **Research:** RemovePaywalls.com, Bypass Paywalls Clean, Archive.ph, [Google Ngrams](https://books.google.com/ngrams/)

### **Reading List**

  * [Knowing Machines](https://knowingmachines.org/models-all-the-way#section5)
  * [ChatGPT is a Blurry JPEG](https://www.newyorker.com/tech/annals-of-technology/chatgpt-is-a-blurry-jpeg-of-the-web)
  * [LLM Token Prediction Visualizer](https://static-assets.codecademy.com/Courses/intro-to-llms/next_token_prediction/llm_next_token_prediction.html)

### **German Language Support**

  * [Leichte Sprache (WDR)](https://www1.wdr.de/hilfe/leichte-sprache/index.html)
  * [DW Langsam gesprochene Nachrichten](https://learngerman.dw.com/de/24012026-langsam-gesprochene-nachrichten/a-75639506)

-----

## **7. Specialized Tools**

  * **Visuals:** [Napkin.ai](https://www.napkin.ai/), [GitDiagram.com](https://gitdiagram.com/)
  * **Blockchain:** [mempool.space](https://mempool.space/), [Bitnodes](https://www.google.com/search?q=https://bitnodes.io/), [Biteaddress](https://www.biteaddress.org/), [Antpool](https://v3.antpool.com/home)
  * **Jobs:** [CyberForum](https://www.cyberforum.de/jobboerse), [Join-nxtgn](https://join-nxtgn.com/jobportal/), [Developer Media](https://jobs.developer-media.de/Suchergebnis.html?jsjn=ai&jsjnid=&jsjo=&jsjoid=), [Computerwoche (Dev Job)](https://jobs.computerwoche.de/Job/Software-Developer-w-m-d.1837525075.html?jssi=43153135764385159&jsix=7&jssc=0), [South Germany (AI/ML Job)](https://stellenmarkt.sueddeutsche.de/job/softwareentwickler-fuer-kuenstliche-intelligenz-machine-learning-engineer-m-w-d.1834922385.html).

-----

### 📥 Inbox (Unsorted)

**Version Control your Configs:** Take your shell configs (`.bashrc`, `.fish_config`) and VS Code `settings.json` and put them in a **private GitHub "Dotfiles" repository**. That way, on a new laptop, you just `git clone` and your whole environment is ready in seconds.

**Use a Password Manager for SSH keys:** Don't just store the steps; store your non-sensitive public keys and configurations in something like Bitwarden or 1Password so you can copy-paste them instantly.

Use File Explorer to find large files:
Open File Explorer → Go to C: → Search bar: size:gigantic

sudo du -h --max-depth=2 /home/$USER | sort -hr | head -n 20
