# YouTube Video Summarizer

A powerful Python tool that automatically downloads, transcribes, and summarizes YouTube videos using state-of-the-art AI models. This project combines YouTube data extraction, speech recognition, and text summarization to create comprehensive video summaries.

## Features

- 🎥 Downloads YouTube videos using `yt-dlp`
- 🗣️ Transcribes video audio using OpenAI's Whisper model
- 📝 Generates segment-wise and complete video summaries using BART
- ⚡ Processes videos in segments for efficient handling of long content
- 📊 Includes video metadata (title, channel, views, duration)
- 💾 Exports results in structured JSON format

## Prerequisites

- Python 3.7+
- YouTube Data API key
- CUDA-capable GPU (optional, but recommended for faster processing)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/youtube-video-summarizer.git
cd youtube-video-summarizer
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Set up your YouTube API key:
   - Go to the [Google Cloud Console](https://console.cloud.google.com)
   - Create a new project or select an existing one
   - Enable the YouTube Data API v3
   - Create credentials (API key)

## Usage

1. Replace the placeholder API key and video URL in the script:

```python
API_KEY = "YOUR_API_KEY"
video_url = "YOUR_YOUTUBE_VIDEO_URL"
```

2. Run the script:

```python
python main.py
```

3. The script will generate a `video_summary.json` file containing:
   - Video metadata
   - Segment-wise transcriptions and summaries
   - Complete video summary

## Example Output

```json
{
    "video_id": "abc123xyz",
    "title": "Sample Video Title",
    "channel": "Channel Name",
    "duration": 300,
    "view_count": "1000000",
    "segments": [
        {
            "start_time": 0,
            "end_time": 60,
            "transcription": "...",
            "summary": "..."
        }
    ],
    "full_summary": "Complete video summary..."
}
```

## Configuration

The `YouTubeVideoSummarizer` class accepts several parameters that can be customized:

- `segment_duration`: Length of video segments for processing (default: 60 seconds)
- `chunk_length_s`: Audio chunk length for transcription (default: 30 seconds)
- Model parameters for both transcription and summarization can be adjusted in the class initialization

## Dependencies

- `google-api-python-client`: YouTube API interaction
- `yt-dlp`: Video downloading
- `transformers`: AI models for transcription and summarization
- `torch`: PyTorch for AI model operations
- `moviepy`: Video processing
- `pydub`: Audio processing
- `opencv-python`: Video frame processing
- `numpy`: Numerical operations

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments

- OpenAI's Whisper model for speech recognition
- Facebook's BART model for text summarization
- YouTube Data API for video metadata
