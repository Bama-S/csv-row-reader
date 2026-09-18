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

## CSV format

The first row must contain column headings.

- Column 1: Register No.
- Column 2: Name (Optional) - in my opinion it is not required - if name is present it will take a long time to enter.
- Columns 3 onward: marks/ values 

Example:

```csv
Register No, 1,Q1,Q2,Q3,Q4
2022012345,18,17,20,55
2022012346,16,19,18,53
```

The complete CSV is displayed. The register number spoken is the final four digits only. For example, `2024012345` is spoken as `2 3 4 5`.

## Voice mode

Import the CSV, optionally choose a starting row, enable voice input, and click **Read Current Row**. After the row is read, say **Next** to proceed.

## Automatic mode

Enter the number of seconds in **Automatic row interval**, then click **Start Automatic Traversal**. Each row is read automatically and the program waits the specified interval before moving to the next row.

## Privacy

The selected CSV is processed in the browser. This application does not upload the CSV to a server.

## Browser

Google Chrome is recommended for voice input. Speech recognition can depend on browser, operating-system, microphone permissions, and the speech-recognition service.

## License

MIT License.
