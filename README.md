# Rclone Help

Do you remember the how to setup rclone, or initate transfers, me neither... Here's everything you need to know.

1. Install rclone

2. Setup remote. Here is a markdown with all the info you need.

# Rclone copy from Sharepoint to your macbook
```
sharepoint:/path-to-transfer-location-on-sharepoint recieving-directory-name
```
For example:
```
rclone copy -P --tpslimit 10 --fast-list sharepoint:/Genetic_and_Environmental_Data/Species_genetic_data/LOSH/downsampled_bam_Holden/x5.0 .
```

# Rclone copy from macbook to sharepoint
```
rclone copy -P --tpslimit 10 --fast-list sending-directory-name sharepoint:/path-to-transfer-location-on-sharepoint
```
For example:
```
rclone copy -P --tpslimit 10 --fast-list /results/bqsr-round-0/downsample-5.0x/overlap_clipped sharepoint:/Genetic_and_Environmental_Data/Species_genetic_data/LOSH/downsampled_bam_Holden/x5.0
```

# scp

# rsync
