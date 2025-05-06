# ps5-ezremote-dpi

A payload that runs in the background to receive package install request. Only supports http/https URLs.

## Instructions
 - Send ezremote-dpi.elf to elfloader
 - Wait for the message "ezRemote DPI listening on port 9040" to appear
 - Send URL to install
   ```bash
   echo 'https://example.org/game.pkg' | nc PS5_IP 9040
   ```