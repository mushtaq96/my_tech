***

# my_tech

***

## **Installed Tools**

- **Terminator** (terminal emulator)
- **Fish Shell**
  - Configure: `fish_config`
- **Sublime Text 3**
- **pip3** (Python package manager)
- **Anaconda** (for Jupyter Notebook)
- **Gnome Tweaks**
- **autoenv** (pip package for Python env activation)
- **bucklespring**: Keyboard sound nostalgia
  - `sudo apt install bucklespring` (or use `snap`)
- **Tree**
  - `sudo apt-get install tree`
  - Show with file sizes `tree -h`
  - Show hidden files `tree -a`
  - Show only directories `tree -d`

## **Useful Commands & Filters**

- **Tree Exclude Pattern**
  ```sh
  tree -I "node_modules|__pycache__"
  ```
- **Find Largest Files**
  ```sh
  find . -type f -exec du -h {} + | sort -rh | head -20
  ```
- **Explicit Code Filtering**
  ```sh
  code2prompt . --exclude="node_modules/**,.venv/**,__pycache__/**,public/**,*.svg,*.ico,package-lock.json" .
  ```

***

## **Important Resources**

- [Ubuntu Snap Basics](https://tutorials.ubuntu.com/tutorial/basic-snap-usage#0)
- [Knowing Machines - Models](https://knowingmachines.org/models-all-the-way#section5)
- [Google Ngrams Books](https://books.google.com/ngrams/)
- ["ChatGPT is a Blurry JPEG"](https://www.newyorker.com/tech/annals-of-technology/chatgpt-is-a-blurry-jpeg-of-the-web)
- [Codecademy LLM Token Prediction](https://static-assets.codecademy.com/Courses/intro-to-llms/next_token_prediction/llm_next_token_prediction.html)

***

## **System Info & Package Management**

- **Apt Cache Location**  
  `/var/cache/apt/archives`
- Example usage:
  ```sh
  sudo apt-get install <package>
  sudo apt-get update
  ```
- **Apt** is CLI for package management on Ubuntu/Debian/Mint.

***

## **Conda & Fish Shell Tips**

- Conda + Fish Shell has issues.  
  [StackOverflow Guide](https://stackoverflow.com/questions/34280113/add-conda-to-path-in-fish/34280406#34280406)

***

## **Browser Extensions**

- (Firefox) HTTPS Everywhere, Grammarly, Wikiwand, Adblock Plus, Momentum, Hoxx VPN, Onetab, English Popup Dictionary
- (Chrome) [Web Search Navigator](https://github.com/infokiller/web-search-navigator) (keyboard shortcuts for web surfing)

***

## **Node.js and Package Managers**

- **NVM (Node Version Manager)**
  1. List installed: `nvm ls`
  2. Install version: `nvm install 16.14`
  3. Use version: `nvm use 16.14`
  4. Verify: `node -v`
  5. Install deps: `yarn install`
  - Settings are local to each terminal

- **Yarn vs npm:**  
  Stick to one per project; delete the other’s lock file before installing.

***

## **Port Conflicts**

- Find process: `lsof -i :3000`
- Kill process: `kill -9 <PID>`

***

## **VS Code Shortcuts**

- Collapse all code blocks: `Ctrl+K`, then `Ctrl+0`
- Unfold all: `Ctrl+K`, then `Ctrl+J`
- Collapse Explorer directories: 
  - Focus Explorer: `Ctrl+Shift+E` 
  - Collapse: `Ctrl+Left Arrow`
 
## **VS Code Settings**

- Html Preview
```
{
    "editor.formatOnSave": true,
    "[html]": {
        "editor.defaultFormatter": "vscode.html-language-features"
    }
}
```

***

## **Common Commands**

- Show tree excluding dirs:  
  `tree -I "node_modules|env|build|dist"`
- Find process using port:  
  `lsof -i :8000`
- Kill process:  
  `kill -9 <PID>`

***

## **SSL Python Fixes**

Add to your shell config:
```sh
export SSL_CERT_FILE=/etc/ssl/certs/ca-certificates.crt
export REQUESTS_CA_BUNDLE=/etc/ssl/certs/ca-certificates.crt
source ~/.bashrc
```
Fixes most requests/SSL issues.

***

## **GitHub SSH Setup Cheatsheet**

> Quick steps to configure SSH for GitHub on a new device.

### 1. Check for Existing SSH Keys
```sh
ls -al ~/.ssh
```
### 2. Generate a New SSH Key
```sh
ssh-keygen -t ed25519 -C "your_email@example.com"
# Or:
# ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
### 3. Add SSH Key to ssh-agent
```sh
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```
### 4. Add SSH Key to GitHub
```sh
cat ~/.ssh/id_ed25519.pub
```
Go to GitHub → Settings → SSH and GPG keys → **New SSH Key**. Paste and save.

### 5. Test SSH Connection
```sh
ssh -T git@github.com
```
### 6. Clone via SSH
```sh
git clone git@github.com:username/repo.git
```
What happens invisibly when you type, ssh root@192.0.0.1
1. Server encrypts secret: "Prove you're you: 7x=42"
2. Your laptop decrypts: "x=6 ✓ Math works!"
3. Server checks: "Correct! Welcome aboard!"

Harden Security (Critical) - Create a non-root user
adduser mushtaq  # follow prompts
usermod -aG sudo mushtaq  # grant sudo access (Ubuntu)
as root, pasted public key from Hetzner here.
# 1. Create .ssh directory for mushtaq
mkdir -p /home/mushtaq/.ssh

# 2. Move the public key into authorized_keys
mv /home/mushtaq/id_ed25519.pub /home/mushtaq/.ssh/authorized_keys

# 3. Set correct ownership (critical!)
chown -R mushtaq:mushtaq /home/mushtaq/.ssh

# 4. Set secure permissions (critical!)
chmod 700 /home/mushtaq/.ssh
chmod 600 /home/mushtaq/.ssh/authorized_keys
Test
ssh mushtaq@[IPV6]
***

## **Hackathon Visual Tools**

- [Napkin.ai](https://www.napkin.ai/) — generate visuals from text
- [GitDiagram.com](https://gitdiagram.com/) — visualize code repos

***

## **Blockchain Tools**

- [mempool.space](https://mempool.space/de/)
- [Antpool.com](https://v3.antpool.com/home)
- [Bitnodes.io](https://bitnodes.io/nodes/live-map/)
- [Biteaddress.org](https://www.biteaddress.org/)

***

## **Uncommon Job Portals**

- [CyberForum Jobbörse](https://www.cyberforum.de/jobboerse)
- [join-nxtgn.com](https://join-nxtgn.com/jobportal/)
- [Developer Media Jobs](https://jobs.developer-media.de/Suchergebnis.html?jsjn=ai&jsjnid=&jsjo=&jsjoid=)
- [Computersware](https://jobs.computerwoche.de/Job/Software-Developer-w-m-d.1837525075.html?jssi=43153135764385159&jsix=7&jssc=0)
- [South Germany](https://stellenmarkt.sueddeutsche.de/job/softwareentwickler-fuer-kuenstliche-intelligenz-machine-learning-engineer-m-w-d.1834922385.html)

***

  du -h --max-depth=1 . | sort -h

Windows
$ py --list
Installed Pythons found by C:\windows\py.exe Launcher for Windows
 -3.9-64 *
 -3.14-64
 py -3.9 -m venv venv
 source venv/Scripts/activate

Tab Does not work ON WSL Vs code
 ctrl+shift+p (opens command pallete), then search and select 'Toggle Tab Moves Focus'.


 Termux SSH
 ssh username@<ipaddress> -p 8022



# 💾 WSL2 & Docker Disk Space Guide

**Two WSL2 "balloons" silently eat SSD. Clean monthly, shrink quarterly.**

## 🚨 Symptoms (fix NOW)
- Windows <15GB free
- Task Manager 100% Disk
- WSL/Docker "No space left"

## 🧹 Monthly Clean (add to ~/.bashrc)
```bash
alias clean="rm -rf ~/.cache/* && npm cache clean --force && docker system prune -a --volumes -f"
clean
🔧 Shrink VHDX (when <20GB free)
powershell
wsl --shutdown
diskpart
select vdisk file="[YOUR_PATH]\ext4.vhdx"
attach vdisk readonly
compact vdisk
detach vdisk
exit
📈 Example Results
text
Ubuntu: 88GB → 59GB (-29GB)
Docker: 27GB → 22GB (-5GB)
```

RemovePaywalls.com: Prepend the site URL with removepaywalls.com/ or use its browser extensions. 
Bypass Paywalls Clean: A widely used Chrome/Firefox extension that bypasses many paywalls, including Bloomberg’s. 
Reader Mode: Use your browser’s reader view to strip away paywall scripts. 
Archive.today (or archive.ph): Load the article through the archiving service to access content.

German Resources
https://leichte-sprache.de/
https://www1.wdr.de/hilfe/leichte-sprache/index.html
https://learngerman.dw.com/de/24012026-langsam-gesprochene-nachrichten/a-75639506
