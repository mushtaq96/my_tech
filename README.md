***

# my_tech (Ubuntu 18 Machine Cheatsheet)

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

***

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


***
