# YouTube Shorts AI Generator

🎬 Automated YouTube Shorts generation using Google Gemini API, Pexels, and Google TTS.
**100% Free & Open Source** ✨

## Features

✅ **Completely Free** - No API costs, uses free tiers of Google APIs
✅ **Fully Automated** - 9-node workflow for end-to-end video generation
✅ **Fast Processing** - Generates shorts in seconds
✅ **High Quality** - Uses industry-leading Google APIs
✅ **Easy Setup** - Simple Python implementation
✅ **Scalable** - Works from your laptop or cloud server

## Architecture

```
NODE 1: INPUT HANDLER
   ↓
NODE 2: CONTENT ANALYZER
   ↓
NODE 3: SCRIPT GENERATOR
   ├─→ NODE 4: VISUAL DESCRIPTION
   │   └─→ NODE 5: IMAGE GENERATOR
   ├─→ NODE 6: METADATA GENERATOR
   └─→ NODE 7: AUDIO GENERATOR
      ↓
   NODE 8: VIDEO ASSEMBLY
      ↓
   NODE 9: YOUTUBE UPLOADER
```

## Installation

```bash
git clone https://github.com/rahul-1066/youtube-shorts-ai-generator.git
cd youtube-shorts-ai-generator
pip install -r requirements.txt
```

## Setup

1. **Get Google API Credentials**
   - Go to [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project
   - Enable: Gemini API, Text-to-Speech API, YouTube Data API v3
   - Create OAuth 2.0 credentials

2. **Set Environment Variables**
   ```bash
   export GOOGLE_API_KEY="your-api-key"
   export YOUTUBE_CLIENT_ID="your-client-id"
   export YOUTUBE_CLIENT_SECRET="your-client-secret"
   ```

3. **Get Pexels API Key**
   - Sign up at [pexels.com/api](https://www.pexels.com/api/)
   - Create `.env` file with your keys

## Usage

```python
from youtube_shorts_generator import YouTubeShortsGenerator

generator = YouTubeShortsGenerator()

result = generator.generate_short(
    topic="AI and Machine Learning",
    style="educational",
    duration=30  # seconds
)

print(f"Video URL: {result['youtube_url']}")
print(f"Script: {result['script']}")
print(f"Title: {result['title']}")
```

## Cost Breakdown

| Service | Cost | Usage |
|---------|------|-------|
| Google Gemini | $0 | 60 calls/min free tier |
| Text-to-Speech | $0 | 1M characters/month free |
| YouTube API | $0 | 1M+ quota daily |
| Pexels | $0 | Unlimited free images |
| **TOTAL** | **$0/month** | - |

## Workflow Nodes Explained

### Node 1: Input Handler
Accepts user input (topic, style, video reference)

### Node 2: Content Analyzer
Extracts 3-5 key ideas and identifies best Shorts angles

### Node 3: Script Generator
Creates 15-30 second scripts with hooks using Google Gemini

### Node 4: Visual Description
Breaks script into visual scenes with detailed prompts

### Node 5: Image Generator
Fetches images from Pexels matching visual descriptions

### Node 6: Metadata Generator
Creates YouTube title, description, tags, hashtags

### Node 7: Audio Generator
Generates voiceover using Google Text-to-Speech

### Node 8: Video Assembly
Combines images, audio, and text into MP4 using FFmpeg

### Node 9: YouTube Uploader
Uploads to YouTube with metadata using YouTube API

## Requirements

- Python 3.9+
- ffmpeg
- Google Cloud credentials
- Pexels API key

## Project Structure

```
youtube-shorts-ai-generator/
├── src/
│   ├── nodes/
│   │   ├── input_handler.py
│   │   ├── content_analyzer.py
│   │   ├── script_generator.py
│   │   ├── visual_description.py
│   │   ├── image_generator.py
│   │   ├── metadata_generator.py
│   │   ├── audio_generator.py
│   │   ├── video_assembler.py
│   │   └── youtube_uploader.py
│   ├── utils/
│   │   ├── config.py
│   │   ├── logger.py
│   │   └── api_clients.py
│   └── main.py
├── tests/
├── requirements.txt
├── .env.example
└── README.md
```

## Configuration

Copy `.env.example` to `.env` and fill in your credentials:

```
GOOGLE_API_KEY=your-key
YOUTUBE_CLIENT_ID=your-id
YOUTUBE_CLIENT_SECRET=your-secret
PEXELS_API_KEY=your-key
```

## Testing

```bash
python -m pytest tests/
```

## Roadmap

- [ ] Node 1: Input Handler implementation
- [ ] Node 2: Content Analyzer with Gemini API
- [ ] Node 3: Script Generator
- [ ] Node 4-7: Visual, Audio, Metadata nodes
- [ ] Node 8: Video Assembly with FFmpeg
- [ ] Node 9: YouTube Upload integration
- [ ] CLI interface
- [ ] Web UI dashboard
- [ ] Scheduled generation (cron jobs)
- [ ] Analytics dashboard

## Contributing

Contributions welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use in your projects!

## Author

**Rahul** - AI Engineer | CAD Developer | Portfolio

- GitHub: [@rahul-1066](https://github.com/rahul-1066)
- LinkedIn: [Your LinkedIn]
- Portfolio: [Your Portfolio]

## Support

If you find this useful, please ⭐ star the repo!

For issues or questions, open an Issue on GitHub.
