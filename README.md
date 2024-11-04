# Rclone Help
Do you remember the how to setup rclone, or initate transfers, me neither... Here's everything you need to know.

# Install rclone
Install rclone for mac on your macbook and rclone for linux on the Alpine cluster in projects/. https://rclone.org/downloads/
 
# Setup onedrive remote
Follow this markdown for detailed instructions

# Rclone copy from Sharepoint to your macbook
```
rclone copy -P --tpslimit 10 --fast-list remote-name:/path-to-transfer-location-on-sharepoint recieving-directory-name
```
For example:
```
rclone copy -P --tpslimit 10 --fast-list Sharepoint:/Genetic_and_Environmental_Data/Species_genetic_data/LOSH/downsampled_bam_Holden/x5.0 .
```

# Rclone copy from macbook to sharepoint
```
rclone copy -P --tpslimit 10 --fast-list sending-directory-name remote-name:/path-to-transfer-location-on-sharepoint
```
For example:
```
rclone copy -P --tpslimit 10 --fast-list /results/bqsr-round-0/downsample-5.0x/overlap_clipped Sharepoint:/Genetic_and_Environmental_Data/Species_genetic_data/LOSH/downsampled_bam_Holden/x5.0
```

# scp

# rsync
