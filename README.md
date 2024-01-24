
This repository contains my dotfiles managed by [dotdrop](https://dotdrop.readthedocs.io/en/latest/), a utility for managing dotfiles. The following instructions will guide you on how to set up and replicate my environment.

## Getting Started

### Repository Setup

Create a repository on github or your preffered platform.

1. **Clone the Repository:**

   Clone your dotfiles repository (replace `<some-url>` with your actual repository URL):

   ```bash
   git clone <some-url>/my-dotfiles
   cd my-dotfiles
   ```

2. **Create a Dotfiles Directory:**

   Within the repository, create a directory to store your dotfiles. This directory is referred to as "dotpath" in the dotdrop configuration and defaults to "dotfiles".

   ```bash
   mkdir dotfiles
   ```

3. **Add a Config File:**

   Obtain a minimal config file from dotdrop's repository:

   ```bash
   wget https://raw.githubusercontent.com/deadc0de6/dotdrop/master/config.yaml
   ```

   This config file serves as the central configuration for dotdrop.

### Import Dotfiles

Now, you can import your existing dotfiles into the dotfiles directory using dotdrop. For example, to import the `~/.bashrc` file:

```bash
dotdrop import ~/.bashrc
```

You should see an output similar to:

```plaintext
   _       _      _
__| | ___ | |_ __| |_ __ ___  _ __
/ _` |/ _ \| __/ _` | '__/ _ \| '_|
\__,_|\___/ \__\__,_|_| \___/| .__/  v1.12.9
                             |_|
-> "/home/your-username/.bashrc" imported
1 file(s) imported.
```

Your config.yaml should also be updated:

```yaml
config:
  backup: true
  banner: true
  create: true
  dotpath: dotfiles
  keepdot: false
  link_dotfile_default: nolink
  link_on_import: nolink
  longkey: false
dotfiles:
  f_bashrc:
    src: bashrc
    dst: ~/.bashrc
profiles:
  probook:
    dotfiles:
    - f_bashrc
```

## Additional Resources

- [Dotdrop Documentation - Repository Setup](https://dotdrop.readthedocs.io/en/latest/getting-started/#repository-setup)
- [Dotdrop Documentation - Installation](https://dotdrop.readthedocs.io/en/latest/installation/)

These resources provide more detailed information on setting up your dotfiles repository and installing dotdrop.

Feel free to customize this repository to suit your needs, and enjoy the benefits of managing your dotfiles efficiently with dotdrop!
