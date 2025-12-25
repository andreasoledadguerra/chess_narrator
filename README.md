# ♟️ Chess Narrator

Convert chess games (PGN) into audio narratives in Spanish.

## Features
- Automatic parsing of PGN files
- AI-generated narratives
- High-quality TTS audio
- Support for multiple free APIs

## Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/chess-narrator.git
cd chess-narrator

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Configure environment variables
cp .env.example .env
# Edit .env with your API keys
```

## Quick Start
```python
from src.pipeline import ChessNarrator
from src.config import load_config

# Initialize
config = load_config()
narrator = ChessNarrator(config)

# Process a game
narrator.process(
    pgn_path='examples/sample_games/kasparov_deep_blue.pgn',
    output_path='output/audio/game.mp3'
)
```

## Architecture
```
PGN File → Parser → LLM (Narrative) → TTS → Audio File
```

### Components:
- **Parser**: Extracts moves and metadata from PGN
- **Narrator**: Generates natural language narrative using LLM
- **TTS**: Converts text to speech

## Configuration

Edit `config/config.yaml` to customize:
- LLM provider (Gemini, Groq)
- TTS engine (gTTS, Edge TTS)
- Narrative style
- Language settings

## Testing
```bash
pytest tests/
```

## Examples

Check the `examples/` folder for sample games and usage demos.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License

## Acknowledgments

- [python-chess](https://python-chess.readthedocs.io/) for PGN parsing
- Google Gemini API for narrative generation
- Edge TTS for audio synthesis