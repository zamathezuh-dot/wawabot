# wawabot
the successor to buttsbot: wawafies messages
# WawaBot 🤖

WawaBot is a simple, configurable IRC bot written in Perl. It connects to a server and joins channels to randomly replace words in users' messages with "wawa" (or any other word you configure).

## Requirements

You'll need Perl and a few modules from CPAN:

* `Bot::BasicBot`
* `YAML::Any`
* `POE`

You can install them using the `cpan` client:

```sh
cpan Bot::BasicBot YAML::Any POE
```

## Setup

1.  **Clone the repository:**
    ```sh
    git clone <your-repo-url>
    cd wawabot
    ```

2.  **Configure the bot:**
    Copy the `conf.yml` file and edit it with your bot's details. You **must** provide the server, nickname, and at least one channel. For Twitch, you'll also need an OAuth token.

3.  **Create list files:**
    The bot uses three text files to manage channels, friends, and ignored users. You can create them empty to start:
    ```sh
    touch chanlist.txt friendlist.txt ignorelist.txt
    ```
    - `chanlist.txt`: A list of channels to join on startup, one per line (e.g., `#mychannel`).
    - `friendlist.txt`: A list of nicks to "wawa" more frequently.
    - `ignorelist.txt`: A list of nicks to never "wawa".

4.  **Run the bot:**
    ```sh
    perl wawabot.pl
    ```

## Commands

-   `!wawa <message>`: Makes the bot "wawa" your message on demand.
-   `!wawaabout`: Displays info about the bot.
-   `!ignoreme`: Adds you to the bot's ignore list.
-   `!unignoreme`: Removes you from the bot's ignore list.
-   `!joinme`: (In the bot's home channel) Makes the bot join your personal channel.
-   `!leaveme`: (In the bot's home channel) Makes the bot leave your personal channel.
