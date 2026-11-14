# Learning Log

A personal documentation repository to keep track of new tools, commands, and technical concepts I learn throughout my engineering journey.

## 📅 Learning Session – 14 November 2026

### Tools Explored

1. **FFmpeg** – A command-line tool used for decoding, encoding, converting, and processing audio and video files.
2. **qrencode** – A command-line tool used to generate QR codes containing information such as website URLs, contact details, and text.

---

## 1. FFmpeg

### What is FFmpeg?

FFmpeg is a tool used to decode, encode, convert, and process almost any type of video or audio file. It can also extract individual frames from videos and create GIFs.

### Installation

**macOS:**

```bash
brew install ffmpeg
```

**Linux:**

```bash
sudo apt install ffmpeg
```

### Commands I Practised

**1. Extract a single frame from a video:**

```bash
ffmpeg -i lec13.mov -frames:v 1 frame.jpg
```

This extracts one frame from `lec13.mov` and saves it as `frame.jpg`.

**2. Convert a video into a GIF:**

```bash
ffmpeg -i lec13.mov frame.gif
```

**3. Create a shorter GIF:**

```bash
ffmpeg -ss 00:00:05 -t 3 -i lec13.mov frame.gif
```

This extracts a three-second portion of the video, starting at the five-second mark.

**4. Create a smaller and smoother GIF:**

```bash
ffmpeg -ss 00:00:05 -t 3 -i lec13.mov -vf "fps=15,scale=480:-1" frame.gif
```

Here:
- `-ss` specifies the starting time.
- `-t` specifies the duration.
- `-vf` applies video filters.
- `fps=15` controls the frame rate.
- `scale=480:-1` sets the width to 480 pixels while maintaining the original aspect ratio.

### File Size Comparison

| Version | File Size |
|---|---:|
| Single frame (JPG) | 119 KB |
| First GIF | 126 KB |
| Shortened GIF | 77 KB |
| Scaled and FPS-limited GIF | 93 KB |

### Errors I Encountered

**Error 1: Unsupported output format**

- Error message: `Unable to choose an output format for 'frame.xyz'`
- What it means: FFmpeg could not identify a supported output format from the `.xyz` extension.
- What I learned: The output file extension helps FFmpeg determine the output format. I should use a supported extension.

**Error 2: Misspelled video filter**

- Error message: `Undefined constant or missing '(' in 'lanc2'`
- What it means: FFmpeg encountered an invalid or undefined filter expression.
- What I learned: Filter names and expressions must be written correctly. Even a small spelling mistake can cause an error.

---

## 2. qrencode

### What is qrencode?

qrencode is a command-line tool used to quickly generate QR codes that store information such as website links, contact details, and other text.

### Installation

**macOS:**

```bash
brew install qrencode
```

**Linux:**

```bash
sudo apt install qrencode
```

### Command Structure

```bash
qrencode [-o filename] [OPTIONS] [STRING]
```

### Commands I Practised

**1. Generate a QR code containing simple text:**

```bash
qrencode -o qrcode.png "Hello from learning!"
```

This generates a QR code containing the text and saves it as `qrcode.png`.

**2. Generate a QR code for a GitHub repository:**

```bash
qrencode -o qrcode.png "YOUR_GITHUB_REPOSITORY_URL"
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual GitHub repository URL.

### What I Learned

- The `-o` option specifies the output filename.
- The text or URL is provided as a string.
- URLs containing special characters such as slashes and colons should be enclosed in quotation marks.
- A generated QR code can be scanned using a smartphone to access the stored information.

---

## 3. The Five-Step Learning Method

The most important lesson from this session was learning how to explore an unfamiliar tool independently.

The five steps are:

| Step | Name | What It Means |
|---|---|---|
| 1 | What is this for? | Read the documentation and understand the tool's purpose in your own words. |
| 2 | Find the shape | Understand the command structure, its options, and the order of arguments. |
| 3 | Run the smallest thing that works | Start with the simplest possible command to verify that the tool works. |
| 4 | Change exactly one thing | Modify one option at a time, predict the result, execute it, and understand the difference. |
| 5 | Break it on purpose | Deliberately introduce an error and learn how to interpret the error message. |

This method helps me learn unfamiliar technologies without depending entirely on tutorials or other people.

---

## 4. What I Want to Explore Next

I want to explore more command-line tools and understand how they work through their official documentation.

My next goal is to learn another tool using the same five-step method and practise applying it to a small real-world task.

---

## 5. Repository Information

- **Repository Name:** learning-log
- **Date:** 14 November 2026
- **Tools Explored:** FFmpeg and qrencode
- **Commit Message:** `Add learning log for FFmpeg and qrencode`

**Repository URL:** [Add your GitHub repository URL here]

**Commit Hash:** [Add your commit hash here]

### Files to Commit

- `README.md`
- `frame.gif` (optional demonstration output)
- `qrcode.png` (optional demonstration output)

The original video file does not need to be committed because it is only an input file used for practising FFmpeg.

---

*This repository will serve as my personal technical reference, documenting the tools I learn, the commands I use, the errors I encounter, and the lessons I discover along the way.*