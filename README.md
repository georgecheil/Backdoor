# Backdoor

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



## For server.py

This Python script implements a basic remote shell for controlling a target machine from a remote location. 
It allows the user to execute commands on the target machine, upload and download files, take screenshots, and manage a keylogger. 
The tool operates on a client-server model and assumes a trusted network environment.


### Features:

1. **Command Execution:**
   - Enter commands on the server-side terminal, and they will be executed on the target machine.

2. **File Transfer:**
   - Upload and download files between the server and the target machine.

3. **Screenshot Capture:**
   - Capture screenshots from the target machine.

4. **Keylogging:**
   - Start, stop, and dump keylog records from the target machine.

5. **Persistence:**
   - Implement persistence on the target machine for the script to maintain its execution.

### Usage:

1. **Server Side:**
   - Run the server script on a machine with a static IP address: `python server.py`.
   - The server listens for incoming connections on the specified IP and port.

2. **Client Side:**
   - Execute the client script on the target machine: `python backdoor.py`.
   - The client attempts to connect to the server.

3. **Commands:**
   - Enter various commands such as `quit`, `clear`, `cd`, `upload`, `download`, `screenshot`, `help`, etc., on the server-side terminal.

4. **Help Command:**
   - Use the `help` command to display a list of available commands and their descriptions.

### Notes:

- The server listens on IP address `192.168.1.4` and port `5555`. Update the script with the appropriate IP and port if necessary.
- Ensure that you have the necessary permissions to run scripts and execute commands on the target machine.
- Use this tool responsibly and only on systems you have explicit permission to access.



## For commandandcontrol.py

Same implementation with `server.py`.

Adjustments have been made to ensure multiple client connections at once.


## For keylogger.py

This Python script implements a basic keylogger that captures keystrokes and writes them to a log file. 

The keylogger operates in the background, using the pynput library to monitor key presses.

Additionally, the script provides functionality for reading the logs, writing keystrokes to a file, and self-destructing to maintain stealth.

### Features:

1. **Keylogging:**
   - Captures keystrokes, including Backspace, Enter, Shift, Space, Caps Lock, and regular alphanumeric keys.

2. **Log Storage:**
   - Saves the captured keystrokes to a log file located in the 'appdata' directory with the filename 'processmanager.txt'.

3. **Self-Destruct Functionality:**
   - Provides the ability to trigger self-destruction, removing the log file and stopping the keylogger.

### Usage:

1. **Keylogger Initialization:**
   - Create an instance of the `Keylogger` class: `keylog = Keylogger()`.

2. **Threaded Execution:**
   - Start the keylogger in a separate thread to run in the background: `t = threading.Thread(target=keylog.start)`.
   - Execute the thread: `t.start()`.

3. **Log Retrieval:**
   - Periodically retrieve and print the captured keystrokes from the log file: `logs = keylog.read_logs()`.

4. **Self-Destruct:**
   - Trigger self-destruction when needed: `keylog.self_destruct()`.

### Notes:

- The log file is stored in the 'appdata' directory with the filename 'processmanager.txt'. Update the `path` variable in the script if necessary.
- The keylogger operates in the background and captures keystrokes globally. Ensure that you have appropriate permissions to run such scripts on the target machine.


### Disclaimer:

This tool is for educational purposes only. 
Misuse of this tool for unauthorized access to computer systems is illegal and strictly prohibited. 
The author is not responsible for any damages or legal consequences arising from the use of this tool.
Use it responsibly and only on systems for which you have explicit permission.

