# Activity Tracker

A macOS menu bar time tracker. It records which app, window and file you are
working in, pauses when you step away, and attributes that time to a project —
without a timer to start or a timesheet to fill in.

This repository exists only to distribute it: the two scripts below and the
signed app. The source is private.

## Install, or update

```bash
curl -fsSL https://raw.githubusercontent.com/damian-debug/activity-tracker-install/main/install.sh | bash
```

The same command installs and updates. Updating keeps your tracked history,
projects, rules and permissions. Works on Apple Silicon and Intel, macOS 14 and
later. No GitHub account needed.

Full guide, including what to do if the menu bar icon does not appear:
**[INSTALL.md](INSTALL.md)**.

## Uninstall

```bash
curl -fsSL https://raw.githubusercontent.com/damian-debug/activity-tracker-install/main/uninstall.sh | bash
```

Removes the app, its login item, its permissions and its preferences, then asks
whether to delete your tracked history — keeping it by default.

## Your data

Everything stays in a database on your own Mac. The app makes no network
requests of any kind: no account, no server, and nobody else can see your
activity. Sharing hours is an export you choose to make.

## Is this download genuine?

`install.sh` refuses any build not signed with Activity Tracker's certificate,
so a tampered or substituted download cannot install. To check a copy you
already have:

```bash
codesign --verify --deep --strict \
  -R='certificate leaf = H"3f945c138150ced62d00c0ce0555cab797fa5acb"' \
  "/Applications/Activity Tracker.app" && echo genuine
```

The app is signed but not notarized by Apple, which is why it is installed from
a terminal rather than a download link — `curl` does not attach the quarantine
flag that would make macOS block it. See INSTALL.md for the detail.

## Problems

Contact Damian.
