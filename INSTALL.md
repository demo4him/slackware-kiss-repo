# Slackware KISS – Installation Guide

This guide explains how to install Slackware KISS Desktop on Slackware 15.0 x86_64.

The recommended procedure uses the text-based Links browser to download Slackware KISS Tools.

## Requirements

- Slackware Linux 15.0 x86_64
- Slackpkg+
- Python 3
- Links
- Internet connection
- Root privileges for package installation and repository configuration

## 1. Download Slackware KISS Tools using Links

Open a terminal as your regular user and start Links with the direct package URL:

```bash
links https://demo4him.github.io/slackware-kiss-repo/15.0/x86_64/packages/slackware-kiss-tools-1.0.1-noarch-1.txz
```

When Links offers to download the file, save it to a directory where your user can write, for example:

```text
/home/your-user/Downloads/
```

If your Links build does not offer a download prompt for the direct package URL, use the terminal download method in the alternative section below.

## 2. Install Slackware KISS Tools

Become root, then install the downloaded package. Replace `/home/your-user/Downloads/` with the directory where you saved it:

```bash
installpkg /home/your-user/Downloads/slackware-kiss-tools-1.0.1-noarch-1.txz
```

## 3. Configure the Repository

As root, run:

```bash
slackware-kiss-setup
```

The setup script configures Slackpkg+ to use the local Slackware KISS package directory. It preserves the existing Slackpkg+ security configuration and creates a backup if configuration changes are needed.

## 4. Install Slackware KISS Desktop

As root, run:

```bash
slackware-kiss-install
```

The command synchronizes the repository, verifies package MD5 checksums and starts the Slackpkg+ installation process.

## 5. Update Slackware KISS Desktop

To synchronize the repository and check for available package upgrades, run:

```bash
slackware-kiss-update
```

## 6. Synchronize the Repository Manually

To download and verify repository packages without installing or upgrading anything, run:

```bash
slackware-kiss-sync
```

## Alternative: Download using wget

If you prefer the terminal, download the Tools package with:

```bash
wget -P "$HOME/Downloads" https://raw.githubusercontent.com/demo4him/slackware-kiss-repo/main/15.0/x86_64/packages/slackware-kiss-tools-1.0.1-noarch-1.txz
```

Then install it as root, using the actual download path:

```bash
installpkg /home/your-user/Downloads/slackware-kiss-tools-1.0.1-noarch-1.txz
```

Continue with the repository configuration in Step 3.

## Notes

- Download the package as a regular user; use root privileges for package installation and repository configuration.
- The Links instructions use a direct package URL because GitHub Pages does not provide a usable directory listing in Links.
- Repository synchronization downloads packages and verifies their MD5 checksums before making them available locally.
- MD5 verification detects file corruption but does not provide cryptographic publisher authentication.
- Existing local packages are not automatically deleted when they disappear from the remote repository.
- Slackware KISS Tools uses Slackpkg+ for package management.

## Project Links

- [Slackware KISS Repository](https://github.com/demo4him/slackware-kiss-repo)
- [Slackware KISS Desktop](https://github.com/demo4him/slackware-kiss-desktop)

---

**Slackware KISS — Keep It Simple.**
