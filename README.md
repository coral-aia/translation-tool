# Translation Tool

A command-line translation tool that provides real-time English to Chinese translation with a self-hosted backend and interactive side panel display.

## Features

- **Command-line Interface**: Easy-to-use CLI for translating text
- **Self-hosted Backend**: Python-based translation service
- **Side Panel Display**: Clean, formatted output showing translations
- **Batch Translation**: Translate multiple sentences at once
- **Interactive Mode**: Real-time translation as you type

## Project Structure

```
translation-tool/
├── backend/
│   ├── app.py              # Flask server
│   ├── translator.py       # Translation logic
│   ├── requirements.txt    # Python dependencies
│   └── config.py          # Configuration settings
├── cli/
│   ├── main.py            # CLI entry point
│   ├── client.py          # API client
│   └── display.py         # UI/Display logic
├── tests/
│   ├── test_translator.py
│   └── test_api.py
└── README.md
```

## Installation

### Prerequisites
- Python 3.8+
- pip

### Setup

1. Clone the repository:
```bash
git clone https://github.com/coral-aia/translation-tool.git
cd translation-tool
```

2. Install dependencies:
```bash
pip install -r backend/requirements.txt
```

## Usage

### Start the Backend Server

```bash
python backend/app.py
```

The server will run on `http://localhost:5000`

### Use the CLI Tool

```bash
python cli/main.py
```

**Interactive mode:**
```bash
python cli/main.py --interactive
```

**Translate a single sentence:**
```bash
python cli/main.py "Hello, how are you?"
```

**Translate from file:**
```bash
python cli/main.py --file input.txt
```

## Examples

```bash
$ python cli/main.py "Good morning"
┌─────────────────────────────────────────┐
│         TRANSLATION RESULT              │
├─────────────────────────────────────────┤
│ English: Good morning                   │
│ Chinese: 早上好                         │
└─────────────────────────────────────────┘
```

## API Endpoints

- `POST /translate` - Translate English to Chinese
  - Request: `{"text": "Hello"}`
  - Response: `{"english": "Hello", "chinese": "你好"}`

- `GET /health` - Health check

## Configuration

Edit `backend/config.py` to customize:
- Server host and port
- Translation model
- API timeout settings

## License

MIT License
