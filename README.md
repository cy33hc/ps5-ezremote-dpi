# ps5-ezremote-dpi

A payload that runs in the background to receive package install request similar to etaHEN DPI. Only supports http/https URLs. This is a standalone payload that doesn't need etaHEN or kstuff. This payload is auto started by [ezRemote Client homebrew](https://github.com/cy33hc/ps5-ezremote-client) if it's not loaded.

## Instructions
 - Run the umtx exploit
 - Start the elfloader
 - Send ezremote-dpi.elf to elfloader
 - Wait for the message "ezRemote DPI listening on port 9040" to appear
 - Send URL to install from Linux
   ```bash
   echo 'https://example.org/game.pkg' | nc PS5_IP 9040
   ```
 - Send URL to install from Windows
   - Create a text file with the URL in content. Make sure there is no spaces before and after the URL.
   - Then use etaHEN [send_payload.ps1](https://github.com/etaHEN/etaHEN/blob/main/send_payload.ps1) powershell script to send the URL to install
     ```bash
     send_payload.ps1 -Payload "C:\path\to\pkg.txt" -IP "192.168.xxx.xxx" -Port 9040
     ```
