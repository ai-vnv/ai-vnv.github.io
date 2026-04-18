# Local Development Setup — Linux / macOS

Step-by-step guide to install everything and run this site locally on Linux or macOS.

## 1. Install Git

### macOS

Git is included with Xcode Command Line Tools:

```bash
xcode-select --install
```

### Linux

```bash
# Ubuntu / Debian
sudo apt update && sudo apt install git

# Fedora
sudo dnf install git

# Arch
sudo pacman -S git
```

### Verify

```bash
git --version
```

## 2. Install Ruby

### macOS

Ruby comes pre-installed on macOS, but it's an older system version. Install a newer one:

**Option A — Homebrew (simplest):**

```bash
# Install Homebrew if you don't have it
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Ruby
brew install ruby

# Add Homebrew Ruby to your PATH
# For Apple Silicon (M1/M2/M3/M4):
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
# For Intel Mac:
# echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.zshrc

source ~/.zshrc
```

**Option B — rbenv (if you need multiple Ruby versions):**

```bash
brew install rbenv ruby-build
rbenv install 3.3.0
rbenv global 3.3.0
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
source ~/.zshrc
```

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev
```

Configure a local gem directory (avoids needing `sudo` for gem installs):

```bash
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### Fedora

```bash
sudo dnf install ruby ruby-devel gcc gcc-c++ make
```

### Arch Linux

```bash
sudo pacman -S ruby base-devel
```

### Verify

Open a **new** terminal:

```bash
ruby -v    # Should show 3.x or 2.7+
gem -v
```

## 3. Install Jekyll and Bundler

```bash
gem install jekyll bundler
```

Verify:

```bash
jekyll -v
bundler -v
```

## 4. Clone and run the site

```bash
git clone https://github.com/ai-vnv/personal-website-template.git
cd personal-website-template
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000) in your browser. Press `Ctrl+C` to stop the server.

## 5. Make it yours

1. Open `_config.yml` in any text editor (nano, vim, VS Code, etc.)
2. Change `title`, `author`, and `social-network-links` to your info
3. Save the file — the site will rebuild automatically if the server is running

## Troubleshooting

### macOS: "You don't have write permissions for the /Library/Ruby/Gems"

You're using the system Ruby. Install Ruby via Homebrew or rbenv (see Step 2).

### `bundle install` fails with permission errors

Never use `sudo` with gem/bundle. Configure a local gem directory instead (see the Ubuntu section in Step 2).

### Missing development headers on Linux

```bash
# Ubuntu/Debian
sudo apt install ruby-dev

# Fedora
sudo dnf install ruby-devel
```

### Port 4000 already in use

```bash
bundle exec jekyll serve --port 4001
```

### Live reload (auto-refresh on file changes)

```bash
bundle exec jekyll serve --livereload
```
