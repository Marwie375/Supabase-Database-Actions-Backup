# Supabase Database Actions Backup

Forked from: https://github.com/sesto-dev/supabase-database-backup

Please see the original ^ repo for intructions and features  
Video Guide: https://www.youtube.com/watch?v=TY68pfWps64

## Features
- Automatic Daily Backups: Scheduled backups run every day at midnight.
- Role, Schema, and Data Separation: Creates modular backup files for roles, schema, and data.
- Flexible Workflow Control: Enable or disable backups with a simple environment variable.
- GitHub Action Integration: Leverages free and reliable GitHub Actions for automation.
- Easy Database Restoration: Clear steps to restore your database from backups.


### Updated Versions

- [actions/checkout@v4.2.2](https://github.com/actions/checkout) 
- [supabase/setup-cli@v2.21.1](https://github.com/supabase/setup-cli) 
- [git-auto-commit-action@v5.1](https://github.com/stefanzweifel/git-auto-commit-action) 

Modify the amount of backups your store by changing ([see here](https://github.com/wycks/Supabase-Database-Actions-Backup/blob/316ce895dcb5c3e804f21b57b40421cd14f5a144/workflows/backup.yaml#L77))

        // +6 keeps the last 5 backups based on datetime list 
        tail -n +6 
        

## Improvements

#### Better Timestamps:
- Added dedicated timestamp generation step
- Timestamps now include hours, minutes, and seconds

#### Organization + Storage Efficiency:
- Creates dated folders for each backup
- Compresses backups into .tar.gz files
- Removes temporary files after compression

#### Cleanup:
- Added automatic cleanup of old backups (keeps last 5)

#### Better Git Handling:
- Added fetch-depth: 0 for better Git history
- Improved commit options for reliability

#### Error Handling:
- Uses GitHub's warning annotation for disabled backups
