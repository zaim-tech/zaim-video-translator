# Zaim Video Translator

Zaim Video Translator turns the spoken dialogue in a video into a translated voiceover. This guide is for people using the compiled Windows app; you do not need to install Python or use a command prompt.

## What you can do

- Translate dialogue into a selected language and create a new video file.
- Choose a video from your computer or download a TikTok video temporarily from its link.
- Preview the original and translated videos in the app.
- Select separate Edge TTS voices for speech detected as male or female. The app chooses between them as it processes the video.
- Optionally preserve detected music and skip subtitle cues that overlap it.
- See the current processing stage and progress in the app.
- Choose where the translated video is saved. Temporary work files are cleaned up after processing.

## Start the app

1. Open the folder where you saved the app and double-click `zaim-video-translator.exe`.
2. Wait for the workspace to load. The first translation may take longer because the selected Whisper model may need to download.
3. Make sure you have an internet connection. The app uses online services for translation, Edge TTS voices, and TikTok downloads. Internet access is also needed the first time the speech model is downloaded.

## Translate a video

1. Add a video in **Choose your video**:
   - Click **Choose video** to select a file on your computer. Supported formats include MP4, MOV, MKV, AVI, and WebM.
   - Or paste a TikTok link and click **Enter**. TikTok downloads are temporary and are removed after translation completes.
2. Use the preview controls to play, pause, or seek through the selected video.
3. In **Set language & destination**, search for and choose the language you want.
4. Choose a male and female voice. The app assigns voices based on detected speech regions. If the selected language does not have one voice type, the voice list falls back to voices that are available for that language.
5. Click **Browse** to choose the name and location for the translated video.
6. Click **Translate video**. The status area shows what the app is doing and its progress.
7. When processing finishes, the translated video opens in the preview. The original source video you selected from your computer is not deleted.

Not every language in the selector has an Edge TTS voice. If the app reports that no voice is available, choose another language.

## Preserve songs

Song preservation is **off by default**. To turn it on:

1. Open **Settings** from the side menu.
2. Turn on **Preserve detected songs**. The preference is saved automatically.
3. Start a translation as usual.

When enabled, the app skips subtitle cues that overlap music regions detected by its audio classifier and keeps the original audio in those regions. Other original audio is replaced by translated speech or silence. The detector identifies music generally, so it may also preserve instrumental music, and it can miss or misclassify sections. With the option off, the app does not preserve detected music; recognized lyrics may be translated like other dialogue.

## Customize settings

Open **Settings** to adjust:

- **Whisper model:** Tiny, Base, Small, Medium, or Large v3. Small is the default balance. Larger models can take longer and use more memory.
- **Processing device and precision:** CPU is the broad-compatibility default. CUDA options require a supported NVIDIA setup.
- **Voice speed:** Adjust the generated speech rate. The app also fits each voice line to the available timeline, which can make some lines faster when there is little time before the next cue.
- **Song detection:** Preserve detected music regions; off by default.

## What happens during translation

The app extracts the video's audio, transcribes speech with Whisper, translates the recognized text, generates speech with Edge TTS, aligns the voice lines to the video's timeline, and saves a new video with the translated audio. The translation and speech-generation stages need internet access. Audio extraction, transcription, alignment, and video rendering run on your computer. Whisper's model files are downloaded the first time the selected model is needed.

Your video file is processed locally. The recognized text is sent to MyMemory for translation, and translated text is sent to Edge TTS to generate speech. TikTok links are sent to the TikTok download service when you use that option.

## If something goes wrong

- **Voice list does not load:** Check your internet connection and try again.
- **Translation is rate-limited:** MyMemory may temporarily reject requests or reach a usage limit. Wait and retry later; the app stops the translation instead of repeatedly retrying a rate-limited request.
- **The first translation takes a long time:** Whisper may be downloading its model. Keep the app open and connected to the internet.
- **The output video cannot be saved:** Close the output video in the app preview or another media player, then try again.
- **A voice sounds too fast:** Choose a slower voice speed in Settings. Lines may still be sped up to fit the available time before the next cue.
- **A song was translated or not preserved:** Song preservation is off by default, and music detection is an estimate. Turn it on in Settings and try again; results can still vary by clip.

## Benefits

Zaim Video Translator gives you a straightforward way to make translated voiceovers without manually transcribing, translating, timing, and merging audio. It keeps the original video picture, provides selectable voices and a searchable language list, lets you preview the result, and cleans up its temporary processing files when it finishes.
