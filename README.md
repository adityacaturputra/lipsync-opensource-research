# lipsync-opensource-research
This is a research for findings open source methods implementing lip-sync on video. We believe Eleven Labs is likely the best option for high-quality voice replication, but its not open source. So here we go the research for lipsync open source methods.

---------------------------------

## Wav2Lip
Github repo: https://github.com/Rudrabha/Wav2Lip

Web: https://sync.so/

Overview: Wav2Lip is a popular open-source solution that can sync any audio input to a given video. It uses deep learning to produce realistic lip movements aligned with speech.

Features:
- Works well for a variety of audio qualities.
- Can handle pre-existing videos and sync new or alternative audio tracks to them.
- Python-based
- Its support audio file, record, or by a text for the lipsync

<img width="447" alt="Screenshot 2024-11-04 at 20 53 07" src="https://github.com/user-attachments/assets/2348b42b-40b6-4bee-a620-7fd02207bbfb">

- I think we find this, it can be integrate with elevenlabs, and likely its requires api-key from Eleven Labs

<img width="1461" alt="Screenshot 2024-11-04 at 20 54 19" src="https://github.com/user-attachments/assets/9dc49796-ed65-466f-91c7-d44f88a41fd8">

- I try process the dog lipsync video, but default models result is not in expectations ...

https://github.com/user-attachments/assets/e05790db-2551-482d-b677-39685cae4a9b

But, we could fine-tune or retrain the model using a dataset of dog faces. By providing a collection of videos with dogs moving their mouths in sync with speech (or just barking), Wav2Lip’s network could adapt for dog animations.

https://github.com/Rudrabha/Wav2Lip/issues/493

Popularity:

<img width="423" alt="Screenshot 2024-11-04 at 20 48 13" src="https://github.com/user-attachments/assets/334bf36c-a3e6-40c5-81c6-478453dc3160">

Example generated video:
https://github.com/user-attachments/assets/6ec17f98-096e-45c1-80c3-c32399326c34

API Documentations: https://docs.sync.so/api-reference/endpoint/generate/post-generate

---------------------------------

# Live Portrait - I think it can be fit for dog lipsync
Github Repo: https://github.com/KwaiVGI/LivePortrait

Website: https://liveportrait.github.io

Example: https://www.youtube.com/watch?v=kDlCUEsVzF8

Overview: LivePortrait uses AI-powered facial motion capture and animation techniques to animate photos, including animals like dogs. This typically involves a reference video or an audio track that the system uses to animate the portrait by moving facial landmarks like the eyes, mouth, and nose in sync with speech or expression changes. I think its works properly by static image, then its generate a video with lip sync by that image.

---------------------------------

# Avatarify
Github Repo: https://github.com/alievk/avatarify-python

Overview: SyncNet is a lip-sync model that was originally designed for identifying and analyzing audio-visual sync in videos, which can be adapted for lip-sync applications. I think, its designed for Zoom, Skype and other video-conferencing apps.

Features:
- High accuracy for simple face tracking.
- Often used for synchronization checking and lip-sync transfer.
- Python-based.
- For spesific lipsync for animals (dogs), it requires training Avatarify with a custom dataset of dog faces.

notes: I haven't tried this yet on my local machines.

---------------------------------

# Conclusion
- It think the best for this is Wav2Lip, it has documented properly for the api. But currently i still find a way how to tune the models.
- For animals or dog lipsync, the best fot this is we can use Live Potrait.

---------------------------------

# reference:
- https://www.pragnakalp.com/best-ai-lip-sync-generators-open-source-free-in-2024-a-comprehensive-guide/
- https://github.com/Rudrabha/Wav2Lip/issues/493
- https://www.youtube.com/watch?v=ceHLnCveen4
- https://www.youtube.com/watch?v=kDlCUEsVzF8
- Chat GPT
