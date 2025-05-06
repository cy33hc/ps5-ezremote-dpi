# ps5-ezremote-dpi

A payload that runs in the background to receive package install request similar to etaHEN DPI. Only supports http/https URLs. This is a standalone payload that doesn't need etaHEN or kstuff. This payload is auto started by [ezRemote Client homebrew](https://github.com/cy33hc/ps5-ezremote-client) if it's not loaded.

## Instructions
 - Run the umtx exploit
 - Start the elfloader
 - Send ezremote-dpi.elf to elfloader
 - Wait for the message "ezRemote DPI listening on port 9040" to appear
 - Send URL to install
   ```bash
   echo 'https://example.org/game.pkg' | nc PS5_IP 9040
   ```
