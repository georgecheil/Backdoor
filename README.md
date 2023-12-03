# backdoor

## For backdoor.py

The purpose of this tool is to establish a covert connection between a client and a server, allowing the server to execute various commands on the client machine remotely. 
The script uses a basic client-server model with a persistent connection.


### Features:

1. **Persistent Connection:**
   - The client attempts to establish a persistent connection to a predefined IP address and port (192.168.1.4:5555 in this case).

2. **Command Execution:**
   - The server can send various commands to the client, and the client will execute them on the target machine.

3. **File Transfer:**
   - The tool supports downloading and uploading files between the server and the client.

4. **Screenshot Capture:**
   - The client can capture a screenshot of the target machine and send it to the server.

5. **Keylogging:**
   - The tool includes basic keylogging functionality. It can start, stop, and dump keylog records from the client machine.

6. **Persistence:**
   - The client can be configured for persistence on the target machine, ensuring that it runs every time the machine starts.

### Usage:

1. **Server Side:**
   - Run the server on a machine with a static IP address using the command: `python backdoor.py`.
   - The server waits for incoming connections and can send commands to connected clients.

2. **Client Side:**
   - The client script should be executed on the target machine.
   - The client attempts to connect to the server and awaits commands.

3. **Commands:**
   - The server can send various commands such as `quit`, `background`, `help`, `clear`, `cd`, `upload`, `download`, `screenshot`, `keylog_start`, `keylog_dump`, `keylog_stop`, `persistence`, and `sendall`.

### Note:

- Ensure that you have Python installed on both the server and client machines.
- Use this tool responsibly and only on systems you have explicit permission to access.

### Disclaimer:

This tool is for educational purposes only. Misuse of this tool for unauthorized access to computer systems is illegal and strictly prohibited. The author is not responsible for any damages or legal consequences arising from the use of this tool.
