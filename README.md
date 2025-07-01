# Rclone & Rsync Transfer Guide
Do you remember the how to setup rclone, or initate transfers, me neither... This guide helps you quickly set up and transfer files between your MacBook, SharePoint (via OneDrive), and the Alpine HPC cluster. Just copy and paste.

## Install rclone
Install rclone for mac on your macbook and rclone for linux on the Alpine cluster in projects/ https://rclone.org/downloads/
 
## Setup onedrive remote
Follow this markdown for detailed instructions

## Rclone copy from Sharepoint to your macbook
```
rclone copy -P --tpslimit 10 --fast-list remote-name:/path-to-transfer-location-on-sharepoint recieving-directory-name
```

## Rclone copy from macbook to sharepoint
```
rclone copy -P --tpslimit 10 --fast-list sending-directory-name remote-name:/path-to-transfer-location-on-sharepoint
```

## rsync
Rsync is commonly available on most clusters. I use rsync to transfer between Ovis & Alpine. Run rsync from Ovis. Alpine does not support rsync or scp for outbound transfers. 
```
rsync path-to-sending-directory/* reciever-address:/path-to-recieving-directory
```

Receiver addresses:

Alpine
```
foxhol@colostate.edu@login.rc.colorado.edu:
```
Ovis
```
foxhol@ovis.biology.colostate.edu
```

Helpful rsync flags

| Flag               | Purpose                            |
| ------------------ | ---------------------------------- |
| `-a`               | Archive mode (preserves structure) |
| `-v`               | Verbose output                     |
| `-h`               | Human-readable sizes               |
| `--info=progress2` | Show detailed progress             |
| `-n` / `--dry-run` | Trial run (no changes made)        |
| `-r`               | recurse into directories           |

Example Dry Run
```
rsync -avh --info=progress2 --dry-run /source/dir/ foxhol@colostate.edu@login.rc.colorado.edu:/dest/dir/
```


