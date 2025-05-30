# Creating an OnPrem LakeHouse with Teradata NOS and MinIO
## NOS Error Resolution
### Native Object Store user error: Error type: 1 http code: 400 lib code: 99 exception: Unable to connect to endpoint (URL not found in DNS lookup).
```sh
# INSIDE TERADATA VM TERMINAL
dbscontrol

# RUN INSIDE THE CONTROL PANEL REPL
display NOS
# DBS Control Record - Native Object Store Fields:
#
#    1. EnableNOS                       = TRUE    (Enabled)
#    .........
#    101. Disable HTTPS                 = FALSE    (Enabled)
#    .........
#    134. AllowToForceS3pathstyle       = FALSE    (Disabled)
#
# Enter a command, HELP, or QUIT:

MODIFY NOS 101 = T
MODIFY NOS 134 = T
WRITE
QUIT
```
