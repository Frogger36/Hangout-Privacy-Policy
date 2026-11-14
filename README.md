# Privacy Policy — Hangout Night Bot

**Effective date:** November 14, 2026
**Last updated:** November 14, 2026

This Privacy Policy explains what information the Hangout Night Discord bot (the "Bot", "we", "us") collects, why it collects it, how it is stored, how long it is kept, and what choices you have. It applies to everyone who interacts with the Bot, including server owners and staff who configure it and members of any server the Bot is in.

By adding the Bot to a server or interacting with it, you acknowledge the practices described here. If you do not agree, please do not use the Bot, and server owners may remove it at any time.

---

## 1. Summary

- The Bot stores **only what it needs to run its features**: server settings, a counting game state, truth-or-dare prompts, and weekly activity totals.
- The Bot **does not store the content of your messages**. It reads message text only to run the counting game, and only in the configured counting channel.
- Weekly activity stats (message counts and voice time) are **wiped every week**.
- The Bot **does not sell, rent, or share** your data with anyone, and does not use it for advertising, profiling, or AI training.
- All data is stored in a local database on the machine that hosts the Bot. It is **not sent to any third-party service** other than Discord itself.

---

## 2. Information We Collect

The Bot receives information from Discord as part of normal operation. The tables below describe exactly what is **stored** and what is only **processed temporarily** (used in memory and then discarded).

### 2.1 Information stored in the database

Each server the Bot is in has its own separate database.

| Data | What it contains | Why | Feature |
|---|---|---|---|
| **Server configuration** | Role IDs for staff permission tiers (moderator, admin, manager), the counting channel ID, weekly leader role IDs, the internal owner-role setting, and whether config commands are enabled | To remember how each server has set up the Bot | All features |
| **Weekly leader winners** | The Discord user ID of the current holder of each weekly leader role, and the date of the last weekly reset | To remove the role from last week's winner when a new winner is chosen | Weekly Roles |
| **Weekly activity totals** | Per user: Discord user ID, **number** of messages sent this week, and seconds spent in voice channels this week | To determine who receives the weekly "most messages" and "most voice time" roles | Weekly Roles |
| **Open voice sessions** | Discord user ID and the time the user joined a voice channel | To calculate voice time when the user leaves | Weekly Roles |
| **Counting game state** | The current count, the high score, and the Discord user ID of the last person who counted | To run the counting game and stop the same person counting twice in a row | Counting |
| **Truth or Dare prompts** | The text of truths and dares added by server staff | To provide prompts for `/truthordare` | Truth or Dare |

Truth or Dare prompts are stored **without** any record of who added them.

### 2.2 Information processed temporarily (not stored)

| Data | How it is used |
|---|---|
| **Message content in the counting channel** | Read to check whether the message is a valid number or math expression. The text is never saved. |
| **The fact that a message was sent** | Used to increase a user's weekly message **count**. The content of the message is not read or stored for this purpose. |
| **Voice channel join/leave events** | Used to start and stop voice-time tracking. Which channel you were in is not stored. |
| **Recent counting history** | A short in-memory list of who made recent counts, used to roll the count back correctly if a count is edited or deleted. It is lost whenever the Bot restarts. |
| **Connect 4 games** | Players, board state, and piece colors are held in memory only for the duration of a game, and are discarded when the game ends or expires after 5 minutes of inactivity. |
| **Command interactions** | When you use a slash command or button, Discord sends the Bot your user ID, display name, roles, and the server/channel you used it in. This is used to respond and to check permissions, and is not stored. |
| **Server membership and role data** | Used to check staff permissions and to give or remove weekly leader roles. Not stored beyond the role IDs listed above. |
| **Server member count** | May be shown in the Bot's status message. Not stored. |

### 2.3 Information we do not collect

The Bot does **not** collect or store:

- The content of messages (outside the temporary counting check described above)
- Direct messages. The Bot does not respond to commands in DMs.
- Attachments, images, files, or links you post
- Presence or activity information (online status, games, Spotify, and so on)
- Email addresses, IP addresses, phone numbers, or payment information
- Voice audio. The Bot never joins voice channels or listens to audio.
- Usernames, nicknames, or avatars. Only numeric Discord IDs are stored.

---

## 3. How We Use Information

Information is used **only** to provide the Bot's features:

- **Permissions:** deciding who can use staff and configuration commands
- **Weekly Roles:** counting weekly messages and voice time, and awarding leader roles every Sunday at 00:00 UTC
- **Counting:** validating counts, tracking the current count and high score, and handling edits or deletions
- **Truth or Dare:** storing and randomly selecting staff-provided prompts
- **Connect 4:** running games between members
- **Bot status:** optionally displaying a server's member count

We do not use your information for advertising, marketing, analytics, profiling, automated decision-making beyond the features listed above, or training machine learning or AI models.

---

## 4. Discord Permissions and Intents

The Bot requests the following privileged gateway intents from Discord:

- **Message Content:** required so the counting game can read numbers and equations in the counting channel
- **Server Members:** required so the Bot can find members in order to give and remove weekly leader roles

The Bot does **not** request the Presence intent.

---

## 5. Data Storage and Security

- Data is stored in SQLite database files on the machine that hosts the Bot. Each server's data is kept in a separate file.
- The data is not uploaded to cloud databases, analytics platforms, or any third-party service.
- Access to the host machine and the database files is limited to the Bot operator.
- The Bot's console output may temporarily show server names, server IDs, and occasionally user or role IDs (for example, when an error occurs while assigning a role). This output is used only for troubleshooting.

No method of storage or transmission is completely secure. We take reasonable steps to protect stored data but cannot guarantee absolute security.

---

## 6. Data Retention

| Data | How long it is kept |
|---|---|
| Weekly activity totals | Deleted every Sunday at 00:00 UTC, when the weekly reset runs |
| Open voice sessions | Deleted when you leave voice, and cleared every time the Bot restarts |
| Weekly leader winner IDs | Kept until replaced by the next week's winner |
| Counting game state | Kept while the Bot is in the server. The last counter's ID is replaced with each new count and cleared when the count resets. |
| Truth or Dare prompts | Kept until removed by server staff |
| Server configuration | Kept while the Bot is in the server, or until changed by server staff |
| In-memory data (Connect 4, counting history, interactions) | Discarded when no longer needed, and always on restart |

**If the Bot is removed from a server**, that server's stored data is not deleted automatically. A server owner can request deletion at any time (see Section 8).

---

## 7. Data Sharing

We do **not** sell, rent, trade, or otherwise share your information with third parties.

Information may be visible to others as a natural part of using the Bot inside Discord. For example:

- Weekly leader roles are visible to other members of the server.
- Counting messages, reset announcements, and game results are posted publicly in the channel where they happen.
- Truth or Dare prompts can be viewed by staff through the configuration panel.

All Bot activity passes through Discord, which processes data under its own [Privacy Policy](https://discord.com/privacy) and [Terms of Service](https://discord.com/terms). We are not responsible for Discord's practices.

We may disclose information if required to do so by law or in response to a valid legal request.

---

## 8. Your Rights and Choices

Depending on where you live, you may have rights over your personal data, including the right to:

- **Access:** ask what data the Bot holds about you
- **Correction:** ask for inaccurate data to be corrected
- **Deletion:** ask for your data to be deleted
- **Objection or restriction:** ask that your data not be processed

To make a request, contact us using the details in Section 12. Please include your Discord user ID and, if relevant, the server ID. We will respond within a reasonable time, and within any period required by applicable law.

**Other ways to limit data collection:**

- **Members:** weekly stats only record activity in channels the Bot can see. Not sending messages or joining voice in a server with the Bot means no activity totals are recorded for you.
- **Server owners:** you can remove the Bot from your server at any time and request deletion of all of your server's data.
- **Server staff:** you can remove Truth or Dare prompts and change configuration at any time using the Bot's config commands.

---

## 9. Legal Basis for Processing (EEA/UK Users)

Where the GDPR or UK GDPR applies, we process data on the basis of **legitimate interests**: providing the Bot's features to the servers that have chosen to add it, in a way that members would reasonably expect from a community bot. You may object to this processing at any time by contacting us.

---

## 10. Children's Privacy

The Bot is intended for use on Discord, which requires users to be at least 13 years old (or the minimum age of digital consent in your country). We do not knowingly collect information from anyone under that age. If you believe a child has provided information through the Bot, contact us and we will delete it.

---

## 11. Changes to This Policy

We may update this Privacy Policy from time to time, for example when features are added or changed. The "Last updated" date at the top shows when it was last revised. Significant changes will be reflected in this document. Continuing to use the Bot after changes take effect means you accept the updated policy.

---

## 12. Contact

For questions, concerns, or data requests about this Privacy Policy or the Bot, contact:

- **Bot operator:** [YOUR NAME OR HANDLE]
- **Discord:** [YOUR DISCORD USERNAME OR SUPPORT SERVER INVITE]
- **Email:** [YOUR CONTACT EMAIL]
