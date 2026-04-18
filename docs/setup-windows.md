# Local Development Setup — Windows

Step-by-step guide to install everything and run this site locally on Windows.

## 1. Install Git

1. Download from [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Run the installer — keep all default options
3. Open a **new** terminal and verify:

```cmd
git --version
```

## 2. Install Ruby

1. Go to [https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)
2. Download the **Ruby+Devkit** installer (pick the one marked `=> recommended`)
3. Run the installer — keep all default options checked
4. At the end, a terminal will pop up asking to install MSYS2. Press **Enter** to install option `[1] MSYS2 base`
5. When it finishes, press **Enter** again to close

### Verify

Open a **new** Command Prompt or PowerShell:

```cmd
ruby -v
gem -v
```

Both should print version numbers.

## 3. Install Jekyll and Bundler

```cmd
gem install jekyll bundler
```

Verify:

```cmd
jekyll -v
bundler -v
```

## 4. Clone and run the site

```cmd
git clone https://github.com/ai-vnv/personal-website-template.git
cd personal-website-template
bundle install
bundle exec jekyll serve
```

Open [http://localhost:4000](http://localhost:4000) in your browser. Press `Ctrl+C` to stop the server.

## 5. Make it yours

1. Open `_config.yml` in any text editor (Notepad, VS Code, etc.)
2. Change `title`, `author`, and `social-network-links` to your info
3. Save the file — the site will rebuild automatically if the server is running

## Troubleshooting

### `gem install jekyll` fails with SSL errors

Update RubyGems:

```cmd
gem update --system
```

### `bundle install` fails with native extension errors

Make sure you installed the **Ruby+Devkit** version (not the one without Devkit). Re-run the MSYS2 setup:

```cmd
ridk install
```

Select option `[1]` and let it complete.

### Jekyll serve shows encoding errors

Add this to the top of your `_config.yml`:

```yaml
encoding: utf-8
```

### Port 4000 already in use

```cmd
bundle exec jekyll serve --port 4001
```
