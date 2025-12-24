# Oh My Posh - Stark Theme Configuration

This repository contains my personal Oh My Posh terminal prompt configuration.

## What is Oh My Posh?

[Oh My Posh](https://ohmyposh.dev/) is a prompt customization engine that transforms your command-line interface with a highly personalized, visually appealing prompt. It's built in Go for speed and works across multiple shells and operating systems.

**Key Features:**

- Display contextual information like Git status, cloud info, language versions, and system metrics
- Smart caching and async operations for instant rendering
- One configuration works everywhere: PowerShell, Bash, Zsh, Fish, Nu Shell, and more
- Cross-platform: Windows, macOS, Linux, WSL, containers, and SSH sessions

## About This Configuration

This is my custom Oh My Posh theme called **Stark**, featuring:

- **User session** display with diamond style
- **Current path** with folder separators
- **Git status** with dynamic colors based on working state
- **Language versions** display for Node.js, Go, Julia, Python, Ruby
- **Azure Functions** indicator when in function projects
- **AWS profile** display
- **Root/admin** indicator
- **Execution time** for commands
- **Command status** indicator
- **Right prompt** with Spotify/YouTube Music player status, battery level, and time
- **Custom prompt character** on new line

## Installation

### 1. Install Oh My Posh

**macOS:**

```bash
brew install jandedobbeleer/oh-my-posh/oh-my-posh
```

**Linux:**

```bash
curl -s https://ohmyposh.dev/install.sh | bash -s
```

**Windows (PowerShell):**

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

### 2. Install a Nerd Font

Oh My Posh uses Nerd Fonts for icons. Install one of these fonts and configure your terminal to use it:

- [Meslo LGM NF](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/Meslo.zip)
- [FiraCode NF](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.1.1/FiraCode.zip)
- Browse more at [Nerd Fonts](https://www.nerdfonts.com/)

**macOS quick install:**

```bash
brew tap homebrew/cask-fonts
brew install --cask font-meslo-lg-nerd-font
```

### 3. Configure Your Shell

**Recommended:** Load the configuration directly from GitHub (always stays up-to-date):

#### For Zsh (macOS/Linux default)

Add this line to your `~/.zshrc`:

```bash
eval "$(oh-my-posh init zsh --config https://raw.githubusercontent.com/reykjavik-labs/local-configs/refs/heads/main/configs/oh-my-posh/stark.omp.json?token=GHSAT0AAAAAADRIOGHLIWTJDQKRRD7Q5WBQ2KMBEBQ)"
```

Then reload your configuration:

```bash
source ~/.zshrc
```

#### For Bash

Add this line to your `~/.bashrc` or `~/.bash_profile`:

```bash
eval "$(oh-my-posh init bash --config https://raw.githubusercontent.com/manu-reyes/oh-my-posh/refs/heads/main/stark.omp.json)"
```

Then reload:

```bash
source ~/.bashrc
```

#### For PowerShell

Add this line to your PowerShell profile (find location with `$PROFILE`):

```powershell
oh-my-posh init pwsh --config https://raw.githubusercontent.com/manu-reyes/oh-my-posh/refs/heads/main/stark.omp.json | Invoke-Expression
```

Then reload:

```powershell
. $PROFILE
```

#### For Fish

Add this line to your `~/.config/fish/config.fish`:

```fish
oh-my-posh init fish --config https://raw.githubusercontent.com/manu-reyes/oh-my-posh/refs/heads/main/stark.omp.json | source
```

### 4. Alternative: Local Installation

If you prefer to use a local copy of the configuration:

```bash
git clone https://github.com/manu-reyes/oh-my-posh.git ~/.config/oh-my-posh
```

Then use the local path in your shell configuration:

```bash
# For Zsh
eval "$(oh-my-posh init zsh --config ~/.config/oh-my-posh/stark.omp.json)"

# For Bash
eval "$(oh-my-posh init bash --config ~/.config/oh-my-posh/stark.omp.json)"

# For PowerShell
oh-my-posh init pwsh --config ~/.config/oh-my-posh/stark.omp.json | Invoke-Expression

# For Fish
oh-my-posh init fish --config ~/.config/oh-my-posh/stark.omp.json | source
```

## Customization

To customize the theme, edit the `stark.omp.json` file. The configuration uses JSON format and follows the [Oh My Posh schema](https://ohmyposh.dev/docs/configuration/overview).

Key sections:

- `blocks.segments`: Defines what information appears in the prompt
- `terminal_background`: Sets the expected terminal background color
- `colors`: Customize foreground and background colors for each segment

## Updating Oh My Posh

```bash
# macOS
brew upgrade oh-my-posh

# Linux
oh-my-posh upgrade

# Windows
winget upgrade JanDeDobbeleer.OhMyPosh
```

## Troubleshooting

**Icons not displaying correctly?**

- Make sure you've installed a Nerd Font
- Configure your terminal to use the Nerd Font
- Some terminal emulators may need to be restarted

**Prompt is slow?**

- Check which segments are fetching data (Git, language versions)
- Consider disabling `fetch_version` for language segments you don't use
- Review the [performance documentation](https://ohmyposh.dev/docs/configuration/segment)

**Colors look wrong?**

- Adjust the `terminal_background` value in the config
- Check your terminal's color scheme settings
- Review the [color overrides documentation](https://ohmyposh.dev/docs/configuration/colors)

**Seeing "CONFIG ERROR" or config not loading from GitHub?**

If you're loading the config directly from GitHub using a raw URL and seeing errors:

- **Make sure the repository is public** - Oh My Posh cannot access configuration files from private GitHub repositories without authentication
- If you need to keep the repo private, use a local path instead:

  ```bash
  eval "$(oh-my-posh init zsh --config /path/to/local/oh-my-posh/stark.omp.json)"
  ```

- After making the repository public, you may need to wait a few minutes for GitHub's CDN to propagate the changes
- Clear your shell cache by opening a new terminal window or running `source ~/.zshrc`

## Resources

- [Oh My Posh Documentation](https://ohmyposh.dev/docs)
- [Themes Gallery](https://ohmyposh.dev/docs/themes)
- [Segments Reference](https://ohmyposh.dev/docs/segments/overview)

## License

This configuration is free to use and modify for personal or commercial purposes.

---

**Author:** Manuel Reyes
**GitHub:** [@manu-reyes](https://github.com/manu-reyes)
