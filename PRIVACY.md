---
layout: legal
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

**Last Updated:** 28 October 2026

## 1. Scope

This policy covers the **r/Drugs Utilities Bot**, a single-server Discord application operated by the r/Drugs administration team. The bot operates only within the official r/Drugs Discord server and processes no data from any other server.

## 2. Data We Collect

### Discord Identifiers
* Discord user IDs, role IDs, channel IDs, and message IDs (considered pseudonymous personal data under GDPR).
* Discord usernames and display avatars, where these appear in staff-facing logs.

### Moderation Data
* Role assignment and removal history, including which role, whether it was added or removed, by what method (command, manual, or automatic), and by whom.
* Timeout and ban timestamps, and moderator-provided reasons.
* Staff leave status. When a staff member switches on staff leave with `/staff-leave`, the bot records their user ID, the staff level they held, and when their leave began, so that their roles can be restored when they return.

### Message Content

The bot reads the text of messages posted in channels it can access. It does this for four purposes:

* To recognise and execute four moderator-only text commands that are typed in chat with a `+` prefix (`+agemute`, `+dunmute`, `+silence`, `+snipe`).
* To detect mathematical and chemical notation written in LaTeX and render it to an image in reply.
* To capture the content of a message at the moment it is deleted, so moderators can review what was removed.
* To keep a record of pinned messages. Each community channel holds at most a set number of pins. When a channel goes over that number, the oldest pin is unpinned and a copy is posted to a staff-only archive channel.

**Most message text is processed in memory and discarded immediately.** Three categories are written to storage:

* **Deleted messages.** When a message is deleted, its text, the author's username and avatar URL, and the URLs of any attachments or stickers are cached for 24 hours. One entry is held per channel and is overwritten by the next deletion in that channel. This supports a moderator-only command that displays the most recently deleted message.
* **LaTeX source.** When a message containing LaTeX notation is rendered to an image, the submitted source is stored in a render cache for 7 days so that identical expressions do not need to be recompiled.
* **Archived pins.** When a pin is rotated out of a community channel, a copy of its text, its author, its channel, the time it was pinned, and up to ten attached images or videos is posted to a staff-only Discord channel. If the original message is later deleted, the copy is removed automatically. The bot's database keeps only the message, channel and author IDs and timestamps, never the text.

### User-Submitted Content
* Suggestions submitted through `/suggestion`.
* LaTeX source and custom document preambles submitted through `/latex` or written in chat.
* Context supplied when a staff vote is opened with `/call-vote`.
* Message content that triggers the automated moderation filter. This includes both our own word/regex filter and Discord's built-in AutoMod, for the specific rule(s) we have configured the bot to monitor. The triggering message text, channel, and timestamp are stored for moderation review and may be reproduced, in a fenced code block, in a staff-only moderation log channel. For content blocked by Discord's AutoMod before it was ever sent, the channel and message identifiers may be unavailable, but the attempted message text is still retained under the same terms.
* When a bot feature fails, the technical detail of the failure — the error message, stack trace, and reference ID — is written to a private channel accessible only to the Data Controller, for diagnostic purposes. Where the failure was caused by user-submitted content, that content may appear in the error detail. This applies in particular to LaTeX source that fails to compile, since the compiler reproduces the offending line in its output.

### Command Interaction Data
* The names of commands invoked, the parameters supplied, the invoking user, the channel, and the outcome (Executed, Permission Denied, or Errored) are posted to internal staff-only channels. This full-fidelity logging is performed to ensure immediate situational awareness for our staff team and is processed under the Vital Interests and Public Interest legal bases.

### Safety Data (Special Category Data)
For members subject to the **User in Crisis (UIC)** protocol we process:
* The member's user ID, the acting moderator's user ID, the timestamp, the moderator-written reason for the intervention, and whether the crisis-resources direct message was successfully delivered.

### What we do not collect
* We do not request or receive presence, activity, or voice state data.
* We do not read message history beyond what is described above.
* We do not collect data from any Discord server other than r/Drugs.

## 3. Legal Basis for Processing (GDPR Compliance)

We process your data under the following legal frameworks:

* **Legitimate Interests:** Server security, prevention of ban evasion, moderation accountability, and the provision of community utility features such as LaTeX rendering.
* **Vital Interests (Art. 9(2)(c)):** Processing safety data (UIC) where necessary to protect the life or physical safety of a user.
* **Operational Auditing:** Real-time logging of command outcomes (Executed, Denied, or Errored) to ensure accountability and to detect attempted misuse of administrative tools.

## 4. Data Storage and Security

* All data is stored on a single private, self-hosted, hardened server running Arch Linux, with AES-256 full-disk and bootloader encryption.
* We use PostgreSQL for persistent storage and Redis for caching. Both are bound to the local machine only and are not reachable over the network.
* Application log files and nightly database backups are held on the same machine.
* **No data is transmitted to any third-party service, analytics provider, advertising network, or external API.** The bot communicates only with Discord's own API and with the local database and cache.
* Access is strictly limited to the Bot Lead Developer and Team Owner.
* **International Transfers:** Data processed by the bot transits through Discord Inc. servers (USA). By using Discord, you acknowledge their privacy practices.

## 5. Data Retention

- **Deleted-message cache** — 24 hours, automatic expiry
- **LaTeX render cache (source and image)** — 7 days, automatic daily cleanup
- **LaTeX compilation error messages** — 5 minutes
- **Temporary render files** — Removed on completion; any residual files removed within 24 hours
- **Active role, timeout, and age-verification timers** — Deleted when the timer is processed
- **Staff leave records** — Deleted when the staff member returns from leave, when they are emergency demoted, or when their on-leave roles are removed by hand
- **Role change history** — 90 days
- **Routine operational audit entries (startup, shutdown, restart)** — 30 days
- **Other operational audit entries** — 180 days
- **Crisis intervention records** — Retained without a fixed expiry
- **Suggestions** — Retained without a fixed expiry
- **Custom donator role registrations** — Until removed by staff
- **Personal LaTeX settings (preamble, theme)** — Until changed or reset by the user
- **Rotating application log files** — 7 days
- **Database backups** — 7 days
- **Automod trigger records** — 30 days
- **Developer error archive** — 90 days
- **Archived pinned messages** — Until the original message is deleted. If a whole channel is deleted, its archived copies are kept until removed by staff
- **Pin archive records (IDs and timestamps)** — Kept while the archived copy exists; deleted 30 days after the original message is deleted

**Message content specifically** is retained for no more than 7 days in live storage, and no more than approximately 14 days once backup rotation is accounted for. There are three exceptions. Message text that triggers the automated moderation filter is retained for 30 days, so that moderators reviewing a member's conduct can see a pattern of behaviour rather than a single incident. A fragment of message content may appear in the developer error archive described above (for example, LaTeX source that failed to compile), which follows that archive's 90-day retention. And a pinned message that is rotated out of a community channel is copied to a staff-only archive channel, where the copy is kept until the original message is deleted; if a whole channel is deleted, its archived copies remain until staff remove them.

Crisis intervention records, moderation history, and suggestions are retained without a fixed expiry because they are necessary for community safety, moderation accountability, and the prevention of ban evasion. Under GDPR, moderation records may be kept after a user leaves the server on a Legitimate Interest basis.

## 6. Opt-Out and User Controls

**There is no opt-out from message content processing.** The features described in Section 2 operate on messages posted in any channel where the bot is present. A member who does not wish their messages to be read by the bot should not post in channels where it has access.

The following controls are available:

* **LaTeX settings.** You may clear your stored custom preamble at any time with `/latex preamble reset`.
* **Automatic expiry.** The deleted-message cache and the LaTeX render cache expire on their own and require no action from you.
* **Archived pins.** Deleting your original message removes its archived copy automatically.
* **Erasure requests.** See Sections 7 and 8.

## 7. Your Rights (GDPR Art. 15-21)

Users have the following rights regarding their data:
* **Access:** Request a copy of all data stored about you.
* **Rectification:** Request correction of inaccurate data.
* **Erasure:** Request deletion of your data (subject to moderation and security retention requirements).
* **Objection:** Object to the processing of your data for specific purposes.

To exercise these rights, please follow the contact instructions in Section 8. Requests for erasure will be honoured unless the data is required for active moderation (for example, maintaining a ban) or for community safety purposes.

## 8. Contact Information & Data Controller

The Data Controller responsible for this bot is the r/Drugs Lead Developer. For any privacy-related inquiries, data access requests, or concerns, please reach out via:

* **Email:** emma.rdrugs@gmail.com
* **Discord:** @emmalt3
* **Reddit:** u/possibly\_emma

## 9. Changes to This Policy

This policy may be updated as the bot's features change. The date at the top of this document reflects the most recent revision. Material changes affecting how member data is processed will be announced in the r/Drugs Discord server.
