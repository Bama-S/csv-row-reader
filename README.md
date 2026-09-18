# CSV Voice Row Reader

A browser-based CSV row reader with speech output, voice navigation, and automatic timed traversal.

## Features

- Import any CSV; no student data is embedded.
- Displays the complete imported CSV.
- Reads each row aloud.
- Reads the actual register number using only its last four digits, spoken individually.
- Voice commands: **Next**, **Repeat**, **Previous**, **Stop**.
- Start from any row.
- Automatic traversal: specify seconds between rows and start; no voice command or Next button is required.
- Manual **YES — NEXT ROW** fallback.

## Getting Started

There are two ways to use the CSV Voice Row Reader.

### Option 1: Voice Navigation

Use this option when you want to control row traversal using voice commands.

1. Import your CSV file
2. Click **Enable Voice Input**.
3. Accept the **microphone permission** when Chrome asks.
4. Select the starting row if required.
5. Click **Read Current Row**.
6. After the row is read, use the following voice commands:
   - **"Next"** — move to the next row
   - **"Previous"** — move to the previous row
   - **"Repeat"** — read the current row again
   - **"Stop"** — stop voice navigation

The program reads the current row and then waits for your voice command before proceeding.

### Option 2: Automatic Traversal — Without Voice

Use this option when you do not want to use voice commands.

1. Import your CSV file.
2. Select the starting row if required.
3. Enter the required time interval in **Automatic row interval (seconds)**.
4. Click **Start Automatic Traversal**.

The program will:

- read the current row;
- wait for the specified number of seconds;
- automatically move to the next row;
- read the next row;
- continue until the last row is reached.

No microphone, voice command, or **Next** button is required in this mode.

To stop the automatic traversal, click **Stop Automatic Traversal**.

## Running locally

### Ubuntu / Linux

In a terminal, change to the folder containing the HTML:

```bash
cd <directory containing html>
python3 -m http.server 8000
```

Then open Chrome:

```text
http://localhost:8000/csv_voice_row_reader.html
```

Allow microphone access when prompted.

### Windows

In Command Prompt, change to the folder containing the HTML:

```bat
py -m http.server 8000
```

Then open:

```text
http://localhost:8000/csv_voice_row_reader.html
```

Allow microphone access.

## CSV Format

The first row must contain column headings.

- **Column 1:** Register No. — required
- **Column 2:** Name — optional
- **Columns 3 onward:** Marks / values

The Name column is optional. If a Name column is present, the program reads the name aloud. If it is not present, the program reads the register number followed by the marks/values.

Example without Name:

```csv
Register No,Q1,Q2,Q3,Q4,Total
2022012345,18,17,20,55,110
2022012346,16,19,18,53,106
```

The complete CSV is displayed. The register number spoken is the final four digits only. For example, `2024012345` is spoken as `2 3 4 5`.


## Privacy

The selected CSV is processed in the browser. This application does not upload the CSV to a server.

## Browser

Google Chrome is recommended for voice input. Speech recognition can depend on browser, operating-system, microphone permissions, and the speech-recognition service.

## License

MIT License.
