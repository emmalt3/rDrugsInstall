# Privacy Policy

**Last Updated:** 18 June 2026

## 1. Data We Collect
To provide community utility and harm-reduction features, we collect and process the following information:

### Discord Identifiers
* Discord User IDs (considered pseudonymous personal data under GDPR).

### Moderation Data
* Role history, mute/ban timestamps, and moderator-provided reasons.

### User Content
* Suggestions submitted through the suggestion system.
* LaTeX source code submitted for rendering.

### Command Interaction Data
* The names of commands invoked and the parameters provided by the user (e.g., LaTeX expressions, moderation reasons) are logged to internal staff channels to support community safety and operational auditing.

### Transient Message Data
* Content and metadata of recently deleted messages are cached for "snipe" functionality.

### Safety & Health Data (Special Category Data)
For members utilising the **User in Crisis (UIC)** or **Sobriety** features, we process:
* Intervention timestamps and moderator-provided safety notes.
* Sobriety start dates and addiction categories (where opted-in by the user).

## 2. Legal Basis for Processing (GDPR Compliance)
We process your data under the following legal frameworks:
* **Legitimate Interests:** For server security, prevention of ban evasion, and moderation accountability.
* **Vital Interests (Art. 9(2)(c)):** Processing safety data (UIC) where necessary to protect the life or physical safety of a user.
* **Consent:** For sobriety tracking, data is only processed when a user explicitly initiates the feature.
* **Operational Auditing:** Real-time logging of command outcomes (Executed, Denied, or Errored) to ensure accountability and detect attempted misuse of administrative tools.

## 3. Data Storage and Security
* All data is stored on a private, self-hosted, hardened server running Arch Linux.
* We use PostgreSQL for persistent storage and Redis for caching.
* Access is strictly limited to the Bot Lead Developer and Team Owner.
* **International Transfers:** Data processed by the bot transits through Discord Inc. servers (USA). By using Discord, you acknowledge their privacy practices.

## 4. Data Retention
* **LaTeX Cache:** Periodically purged.
* **Suggestions:** Retained until approved, denied, or manually deleted.
* **Moderation & Safety Records:** Retained as long as necessary for community safety. Under GDPR, moderation logs may be kept even after a user leaves to prevent ban evasion (Legitimate Interest).
* **Sobriety Data:** Deleted immediately upon user request or manual reset.
* **Snipe Cache:** Snipe data is stored in a volatile cache and is automatically purged after 24 hours.

## 5. Your Rights (GDPR Art. 15-21)
Users have the following rights regarding their data:
* **Access:** Request a copy of all data stored about you.
* **Rectification:** Request correction of inaccurate data.
* **Erasure:** Request deletion of your data (subject to moderation/security retention requirements).
* **Objection:** Object to the processing of your data for specific purposes.

To exercise these rights, please follow the contact instructions in Section 6. Requests for erasure will be honored unless the data is required for active moderation (e.g., maintaining a ban) or community safety purposes.

## 6. Contact Information & Data Controller
The Data Controller responsible for this bot is the r/Drugs Lead Developer. For any privacy-related inquiries, data access requests, or concerns, please reach out via:

* **Email:** emma.rdrugs@gmail.com
* **Discord:** @emmalt3
* **Reddit:** u/possibly\_emma
