---
layout: default
title: "Audio Widget Demo"
---

# Audio Widget Examples

This page demonstrates the audio widget for streaming audio content.

## Basic Audio Player

Simple audio player with controls (placeholder - no actual file):

{% include widgets/audio-widget.html 
   id="basic-audio" 
   title="Sample Audio Track" 
   source="/assets/audio/sample.mp3"
   caption="Example audio player" %}

**Note:** This is a placeholder. Actual audio files should be added via Git LFS or hosted externally.

## Podcast Episode Example

Audio player configured for podcast episodes:

{% include widgets/audio-widget.html 
   id="podcast-episode" 
   title="Digital Garden Podcast - Episode 1: Getting Started" 
   source="https://example.com/podcasts/episode-1.mp3"
   caption="Duration: 42:15"
   caption_url="/podcast-series" %}

## Music Track Example

{% include widgets/audio-widget.html 
   id="music-track" 
   title="Ambient Garden Sounds" 
   source="https://example.com/audio/ambient-garden.mp3"
   caption="Relaxing background music for your digital garden" %}

## With Caption Link

Link to more information about the audio content:

{% include widgets/audio-widget.html 
   id="audio-with-link" 
   title="Interview: Jane Doe on Digital Gardens" 
   source="https://example.com/interviews/jane-doe.mp3"
   caption="Read the full transcript"
   caption_url="/transcripts/jane-doe" %}

## Usage Code

```liquid
{% raw %}
{% include widgets/audio-widget.html 
   id="my-audio" 
   title="Audio Title" 
   source="/path/to/audio.mp3"
   caption="Optional caption"
   caption_url="/optional-link"
   autoplay="false" %}
{% endraw %}
```

## Supported Audio Formats

The widget supports multiple audio formats:
- **MP3** (.mp3) - Most compatible
- **OGG** (.ogg) - Open format
- **WAV** (.wav) - Uncompressed, large files
- **AAC** (.m4a) - High quality
- **FLAC** (.flac) - Lossless compression

## Git LFS Recommendations

For audio files stored in the repository:

1. Enable Git LFS (see [Onboarding Guide]({{ '/docs/ONBOARDING.html#git-lfs' | relative_url }}))
2. Store files in `/assets/audio/`
3. Compress audio appropriately:
   - Podcasts: 64-96 kbps MP3
   - Music: 128-192 kbps MP3
   - High fidelity: 256-320 kbps or FLAC

## External Hosting Options

For better performance and storage management:

- **SoundCloud**: Easy embedding and streaming
- **Anchor/Spotify**: For podcasts
- **AWS S3 + CloudFront**: Custom hosting with CDN
- **Cloudinary**: Media management platform

Reference external URLs in the `source` parameter:

```liquid
source="https://soundcloud.com/user/track"
source="https://cdn.example.com/audio/file.mp3"
```

## Best Practices

1. **Keep file sizes reasonable**: Compress audio appropriately
2. **Use descriptive titles**: Help users know what they're listening to
3. **Provide context with captions**: Mention duration, topic, or series
4. **Consider autoplay carefully**: Default is `false` for better UX
5. **Test cross-browser**: Audio format support varies

## Accessibility Features

- Standard HTML5 audio controls
- Keyboard navigation supported
- Screen reader compatible
- Title attribute for context

## Player Features

Built-in HTML5 audio controls include:
- Play/Pause
- Volume control
- Seek bar
- Download option (in supported browsers)
- Playback speed (in some browsers)

---

[Back to Examples]({{ '/examples/' | relative_url }}) | [Onboarding Guide]({{ '/docs/ONBOARDING.html' | relative_url }})
