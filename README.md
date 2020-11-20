# GitHub2Synology

A simple Ash (practically "BusyBox bash") script designed to run on the Synology DS range of file storage servers to backup all repositories (and wikis) for a user from Github.

## Running

1. Ensure you have `git` installed on the Synology - this can be download from the [SynoCommunity](https://synocommunity.com/). The script also needs cUrl and [jq](https://stedolan.github.io/jq/) but these seem standard on Synologys.

2. Now login to Github and go to [https://github.com/settings/tokens]( https://github.com/settings/tokens) and create a personal access token with the following scopes:
    - repo (repo itself including all subs) - Full control of private repositories
    - admin:org read:org - Read org and team membership

3. Add this token as the OAUTH_TOKEN in line 7 on the `github2synology.sh` script. (`OAUTH_TOKEN="[PUT YOUR TOKEN HERE BETWEEN THE QUOTES]"`)
4. Ensure the backup path is correct on line 9. (`BACKUP_PATH="/volume1/serverBackups/github/backup"`)
5. Copy the script over to your Synology and run it (all via SSH)
