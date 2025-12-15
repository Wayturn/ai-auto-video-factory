# AI Auto Video Factory

An **AI-powered auto video generation system** that converts  
**text → voice → subtitles → template-based videos**  
through a fully automated and scalable batch pipeline.

This project focuses on **large-scale personalized video generation**
(e.g. 50–4000 videos) using modular and replaceable AI components.

---

## What is this?

This project is an **AI Auto Video Factory** designed to automate
the entire content production pipeline:

- Text input
- AI voice generation
- Subtitle generation
- Template-based video composition
- Batch processing and export

Instead of generating a single video at a time, this system is built
to handle **batch jobs** efficiently and reliably.

---

## System Architecture

![System Architecture](docs/architecture.svg)

The system is designed with a **modular and replaceable architecture**.
Each component can be independently upgraded or swapped without
affecting the overall pipeline.

---

## Core Pipeline

The system follows a centralized batch-processing workflow:

1. User inputs text or structured data via Web UI
2. FastAPI backend validates the request and creates batch jobs
3. Batch Pipeline Engine orchestrates all tasks
4. Voice is generated via a pluggable TTS module (default: GPT-SoVITS)
5. Subtitles are generated automatically
6. Video templates are composed with audio, subtitles, and assets
7. Final videos are exported to storage

---

## Modules Overview

### Web UI
- Text input
- Batch upload (CSV / Excel)
- Template selection
- Job submission and download

### FastAPI Backend
- API gateway
- Request validation
- Job creation and lifecycle control
- Pipeline coordination

### Batch Pipeline Engine (Core)
- Task orchestration
- Batch processing
- Job queue handling
- Error handling and retry logic

### Voice Clone / TTS Module (Pluggable)
- Default engine: **GPT-SoVITS**
- Text-to-speech inference
- Output: WAV audio
- Designed to be replaceable (e.g. XTTS, CosyVoice, Bark)

### Subtitle Generator
- Text segmentation
- Audio-text alignment
- Subtitle generation (SRT / VTT)

### Video Template Composer
- Template-based video rendering
- Audio, subtitle, image, and background music integration
- Built with ffmpeg / moviepy

### Storage / Output
- Audio files
- Subtitle files
- Final rendered videos (MP4)
- Supports local or cloud storage

---

## Design Principles

- **Modular architecture**
- **Pluggable AI components**
- **Batch-first workflow**
- **Separation of orchestration and inference**
- **Production-oriented pipeline design**

This project treats AI models as **replaceable modules**, while the
pipeline itself is the core product.

---

## Current Status

- [x] System architecture design
- [x] Modular pipeline concept established
- [x] Voice clone module integrated (GPT-SoVITS)
- [x] Batch processing workflow validated
- [ ] Subtitle generation refinement
- [ ] Video template automation improvements
- [ ] Web UI integration
- [ ] Deployment and demo preparation

---

## Roadmap

- Improve batch reliability and monitoring
- Add job queue and task status tracking
- Support multiple TTS engines
- Add video template presets for common use cases
- Prepare demo and landing page
- Explore enterprise deployment options

---

## Target Use Cases

- Large-scale personalized video generation
- Corporate announcements and training videos
- Marketing and campaign content automation
- Educational content production
- Religious or organizational message distribution

---

## License

This project is for research and product prototyping purposes.
Model licenses and usage restrictions depend on the underlying AI components.
