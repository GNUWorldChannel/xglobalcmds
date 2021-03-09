NOTE:

    Parameters enclosed in <>'s are mandatory.
    Parameters enclosed in []'s are optional.
    x|y means x or y.
    <nick> refers to a person's IRC nickname that they are online with.
    <username> refers to a person's username as it appears in the userlist; not to be confused with <nick>. For more information about usernames and how to determine a person's username, refer to the VERIFY and INFO commands (level 0).
    All commands shown with the <username> field can also work by specifying a user's IRC nickname that they are online with by preceding their nickname with an equal (=) sign. For example, consider a person with the nickname ^[Test]^ and username Test. The ACCESS command can be performed on this user in either of these 2 methods:
        /msg X access <#channel> Test
        /msg X access <#channel> =^[Test]^

    The 1st method directly queries X as to whether or not the username "Test" is in the userlist. The 2nd method makes X lookup ^[Test]^'s username if they are authenticated, which refer's to their username of "Test". This can be performed with any command that requires a <username>, but will only work if the user is authenticated, otherwise a "No Match" reply or equivalent will be returned.

LEVEL 1000 Commands

    QUOTE
    Makes X issue a RAW Command.
    Please note. This command is dangerous and should only be used for debugging purposes. It enables you to talk as the server gnuworld runs as.
    /msg X quote <raw>

LEVEL 900 Commands

    SHUTDOXN
    Makes X shutdown.
    /msg X shutdown
    REHASH
    Makes X rehash various parts of it's system.
    Options available:
        TRANSLATIONS
        Reloads all translations from the database. Useful if you added or updated languages.
        /msg X rehash translations
        HELP
        Reloads the help entries from the database.
        /msg X rehash help
        CONFIG
        Reloads the configuration table.
        /msg X rehash config

LEVEL 800 Commands

    SAY
    Makes X send a message to a channel.
    /msg X say <channel> <message>
    SERVNOTICE
    Makes X send a servernotice to a channel.
    /msg X servnotice <channel> <message>
    NEWPASS
    Allows a CService Administrator to change a username's password, other than their own.
    /msg X@channels.undernet.org NEWPASS username NewPassword


LEVEL 750 Commands

    REGISTER
    Registers a channel assigned to a specified username.
    /msg X register <channel> <username>
    PURGE
    Purges a channel or username with a specified reason.
    This command will fail if NOPURGE is set.
    /msg X purge <channel|username> <reason>
    SET
    Sets specific flags on a channel.
    Available channelflags on this level:
        SPECIAL
        Marks a channel as special. It's userlist is not shown on the website.
        /msg X set <channel> special <on|off>
        NOFORCE
        Toggles the usability of the FORCE command in a specified channel.
        /msg X set <channel> noforce <on|off>
        NOREG
        Toggles the noreg flag on a specified channel.
        /msg X set <channel> noreg <on|off>
        NEVERREG
        Toggles the neverreg flag on a specified channel.
        /msg X set <channel> neverreg <on|off>

LEVEL 600 Commands

    REMIGNORE
    Removes a specific ignore from the list.
    /msg X remignore <user@hostmask>
    ADDCOMMENT
    Appends a comment to a specified username.
    /msg X addcomment <username> <comment>
    SCANHOST
    Searches the net to find a user matching a specific hostname.
    Use -all to get the list should it exceed a limit of 15 entries.
    /msg X scanhost <hostmask> [-all]
    SCANUNAME
    Searches the network for usernames matching a specified mask. Also displays the signup ip used to register the account.
    Use -all to get the list should it exceed a limit of 15 entries.
    /msg X scanuname <mask> [-all]
    SET
    Sets specific flags on a channel.
    Available channelflags on this level:
        COMMENT
        Adds a comment about the channel with a maximum of 200 characters.
        /msg X set <channel> comment <comment>
        LOCKED
        Locks the channelsettings of a channel only to be changed by an administrator.
        /msg X set <channel> locked <on|off>

LEVEL 501 Commands

    SET
    Sets specific flags on a channel.
    Available channelflags on this level:
        NOPURGE
        Marks a channel as not to be purged.
        /msg X set <channel> nopurge <on|off>
        SUSPEND
        Suspends a channel.
        /msg X set <channel> suspend <on|off>
        TEMPMAN
        Marks a channel as having a temporary manager.
        /msg X set <channel> tempman <on|off>
        CAUTION
        Toggles the caution flag on a channel, useful to warn others to look more into the history of a channel.
        /msg X set <channel> caution <on|off>
        VACATION
        Marks a channel as the manager being absent with channel services being notified about it.
        /msg X set <channel> vacation <on|off>
        EMAIL
        Allows a CService Admin to change an email address for an account or username.
        /msg X set EMAIL <username> <new-confirmed@email.com>

LEVEL 1 Commands

    STATUS
    Displays the status of a registered channel.
    /msg X status <channel>

LEVEL * Commands

    FORCE
    Forces your accesslevel on a channel. When issued you will have temporary access to a channel at the level of your * access. You will be able to perform commands in the channel up to that level.
    This command will not work in channels that have NOFORCE set.
    /msg X force <channel>
    SET
    Sets a specific personal setting on your account.
    The following option(s) are available:
        DISABLEAUTH
        Toggles your usability of admin priviledges. If disableauth is on, you will not be able to act as administrator.
        /msg X set disableauth <on|off>
    STATS
    If a channel is specified, will show the application stats of the channel. If no option is specified, will show global statistics.
    /msg X stats [channel]
    UNFORCE
    Removes your forced access from the channel.
    /msg X unforce <channel>
