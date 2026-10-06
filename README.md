# DARKSITE CLAN BUG

## Start the bot

Run the bot from this repository directory, not from another project such as `/opt/subby-lab`:

```bash
cd ~/DARKSITE-CLAN-BUG
npm install
npm start
```

The process prints its listening URL and remains ready for a session request.

## Pair a WhatsApp number from the terminal

Set the full international number without `+`, spaces, or punctuation:

```bash
PHONE_NUMBER=2348012345678 npm start
```

The pairing code is printed as:

```text
[pairing] 2348012345678: XXXX-XXXX
```

Enter that code in WhatsApp under **Linked devices**. Existing sessions in `sessions/` are loaded automatically.

## Diagnostics

Startup, pairing, connection, message-processing, and fatal errors are printed to the terminal. The HTTP health endpoint is:

```bash
curl http://127.0.0.1:3000/api/status
```

If another Node process is showing a different banner, verify the running path with:

```bash
ps aux | grep '[n]ode'
readlink -f /proc/<PID>/cwd
```

The process must be started from this repository.
