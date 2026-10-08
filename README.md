# Notes+

**Catch every idea, bug and task before it evaporates.**

A native Mac notes app for developers juggling several projects at once. One
shortcut captures a thought from whatever app you're in, every project gets its
own board, and an iPhone app carries the same notes in your pocket.

> **No account. No sign-up. No telemetry.**
> Download it, open it, start typing. There is no Notes+ account to create and
> nothing to register — your notes live in a database on your own Mac, and they
> only go anywhere else if you connect something yourself.

<p align="center">
  <img src="assets/notes-plus-demo.gif" width="800" alt="Notes+: quick capture with ⌃Space, a project board, and the same notes on the iPhone">
</p>

<p align="center">
  <a href="../../releases/latest"><b>Download the latest release</b></a>
  &nbsp;·&nbsp; macOS 14 or later &nbsp;·&nbsp; Apple silicon and Intel &nbsp;·&nbsp; Free
</p>

## What it does

- **Capture from anywhere.** `⌃Space` opens a small popover over whatever you're
  doing. Pick a project, type the note, `⌘1`–`⌘4` tags it idea, bug, task or note,
  and `↩` files it. The app you were in keeps its place.
- **A board for every project.** Not started, in progress, done. Drag a note
  along as the work moves, or flip the board to compact cards or a list.
- **Ideas, bugs and tasks sort themselves.** Tag a note as a bug and it files
  itself under the project's Bugs. A **To do** row on Home pulls every open bug,
  task or idea out of every project into one list, highest priority first.
- **Real notes.** Rich text, checklists, images pasted straight in, and a vector
  sketch board on any note for the ideas that are a shape rather than a sentence.
- **Code keeps its shape.** Paste a query, a stack trace or a function and it
  lands in a code block of its own, coloured by language. **Prettify**
  (`⌥⇧⌘F`) tidies it.
- **On your iPhone too.** Turn on sync and your projects and notes follow you,
  through the private iCloud database of your own Apple Account.
- **Jira in one click.** File a note as a real Jira issue — screenshots included —
  and the ticket's status comes back to the note.
- **Works with Claude Code.** An MCP server lets Claude read and file notes, and
  the app can ask Claude to write a ticket description for you.
- **A local API.** Everything is scriptable over `127.0.0.1`, behind a token.
- **Shared projects.** Put one project on a Postgres database and colleagues can
  work on it with you.
- **Add to Calendar**, daily **backups** to a folder you choose, and a quick start
  guide that walks you through all of it on first launch.

## Installing

1. Download `Notes+-<version>.dmg` from the [latest release](../../releases/latest).
2. Open it and drag **Notes+** onto **Applications**.
3. Open Notes+ — the quick start guide takes it from there.

Or with Homebrew:

```bash
brew install --cask spozar/notes-plus/notes-plus
```

Releases are signed with a Developer ID and notarised by Apple, so the app opens
on a double-click with no Gatekeeper warning. If you'd rather not mount a disk
image, every release also has a `.zip` holding the identical app.

### Updating

Notes+ checks this page once a day and offers new versions in **Settings →
General** — installing is always a button you press, never something that happens
behind your back. **Release notes…** in the same panel shows what changed. Homebrew
users can `brew upgrade --cask notes-plus` instead.

### The iPhone app

The iPhone app is in TestFlight for now. To bring your notes across, turn on
**Settings → Sync with iPhone** on the Mac and sign the phone in to the same Apple
Account. Sync is off until you turn it on.

## Your first five minutes

1. **Make a project** — `⇧⌘N`, or the dashed card on Home. Give it a name and a
   colour; it comes with Ideas, Bugs and Tasks already in it.
2. **Capture something** — press `⌃Space` from any app, type a few letters of the
   project name, `↩`, then type the note and `↩` again. Stay in the popover and keep
   going: it's built for firing off several in a row.
3. **Jump in** — `⌘1` opens your first project's board. Drag a card into In
   progress, click it to open the note.
4. **Connect what you use** — Jira, Claude Code, iCloud sync and shared projects
   each have a page in the quick start guide, with the button on the page.

## Shortcuts

| | |
|---|---|
| `⌃Space` | Quick capture from any app |
| `⌘1`–`⌘9` | Jump to a project |
| `⌘0` | Home |
| `⌘N` | New note where you are |
| `⇧⌘N` | New project |
| `⇧⌘D` | New sketch |
| `⌘F` | Search every project |
| `⌃⌘1`–`⌃⌘3` | Board as cards, compact cards or a list |
| `⌘[` | Back |
| `⇧⌘L` / `⇧⌘K` | Bullet list / checklist |
| `⌥⇧⌘C` | Code block |
| `⌥⇧⌘F` | Prettify the code block |
| `⌘,` | Settings |

In quick capture: `⌘1`–`⌘4` sets the tag, `⇧↩` adds a line, `⇥` cycles
subcategories, `esc` goes back a step.

## FAQ

<details>
<summary><b>Do I need to create an account?</b></summary>

No. There is no Notes+ account, no sign-up and no email to give. Open the app and
start writing. Everything works offline, on your Mac alone.

The optional connections use accounts you already have: your own Apple Account for
iPhone sync, your own Atlassian token for Jira. None of them is required, and none
of them goes through us.
</details>

<details>
<summary><b>Is it free?</b></summary>

Yes.
</details>

<details>
<summary><b>Where are my notes kept?</b></summary>

In one SQLite database on your Mac, in
`~/Library/Application Support/se.mediaempire.notes/`. Jira tokens and database
connection strings live in the macOS keychain, never in a file.
</details>

<details>
<summary><b>Does Notes+ send my notes anywhere?</b></summary>

Not unless you connect something. Out of the box it talks to `127.0.0.1` (its own
local API) and checks GitHub once a day for updates — and you can turn that check
off in **Settings → General**. Beyond that it only reaches what you connect: Jira,
the database a shared project is on, or your own iCloud once you turn on sync.
There is no telemetry and no server of ours.
</details>

<details>
<summary><b>Can I use it without the iPhone app or iCloud?</b></summary>

Yes. Sync is off until you turn it on, and the Mac app is complete on its own.
</details>

<details>
<summary><b>Can anyone else read my synced notes?</b></summary>

Sync uses the private CloudKit database of your own Apple Account — it belongs to
your account, not to us, and we can't read it. The words in your notes travel in
CloudKit's encrypted fields, end-to-end encrypted when Advanced Data Protection is
on.
</details>

<details>
<summary><b><code>⌃Space</code> doesn't open quick capture.</b></summary>

macOS uses `⌃Space` for "Select the previous input source" when you have more than
one keyboard layout. **Settings → Quick capture** tells you if that's what's
happening. Turn that macOS shortcut off in **System Settings → Keyboard → Keyboard
Shortcuts → Input Sources**, or use the Notes+ icon in the menu bar, which always
works.
</details>

<details>
<summary><b>How do I share a project with colleagues?</b></summary>

**Share with colleagues…** on a project card's `…` menu. A shared project lives on a
Postgres database you provide — [Neon](https://neon.com)'s free tier is more than
enough for a few people — and the connection string is what lets someone in. They
paste it under **File → Join Shared Project…**. Still no Notes+ account involved:
whoever holds the string is on the project, so only give it to people you mean to.
Only the projects you share leave your Mac; everything else stays private.
</details>

<details>
<summary><b>Do I need a Jira admin to connect Jira?</b></summary>

No. Notes+ signs in as you, with an API token from your own Atlassian account, so it
can reach exactly what you can already reach in the browser. Nothing is installed
on the Jira side and nobody has to approve anything. Connect it under **Settings →
Jira**.
</details>

<details>
<summary><b>How do I back up my notes?</b></summary>

**Settings → Backup.** Pick a folder — iCloud Drive, Dropbox, an external disk —
and Notes+ writes a complete copy there daily, or whenever you press **Back up
now**. It keeps the last ten. **Restore from a backup…** in the same place shows
you what's in a backup before it replaces anything.
</details>

<details>
<summary><b>How do I uninstall it?</b></summary>

Quit Notes+ and drag it from Applications to the Bin. To remove your notes as well,
delete `~/Library/Application Support/se.mediaempire.notes/` — take a backup first
if you might want them back. With Homebrew, `brew uninstall --zap --cask
notes-plus` does both.
</details>

<details>
<summary><b>Where's the source code?</b></summary>

The source lives in a private repository. This one holds the signed releases and
their notes.
</details>

<details>
<summary><b>I found a bug, or have an idea.</b></summary>

[Open an issue](../../issues/new) here. A screenshot and your macOS version help.
</details>
