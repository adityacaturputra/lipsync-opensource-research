# lipsync-opensource-research
This document summarizes research on open-source methods for implementing lip-sync in video. We believe that Eleven Labs may offer the best high-quality voice replication, though it is not open source. Therefore, this research focuses on open-source lip-sync methods.

---------------------------------

## Wav2Lip
Github repo: https://github.com/Rudrabha/Wav2Lip

Web: https://sync.so/

Overview: Wav2Lip is a popular open-source solution that can sync any audio input to a given video. It uses deep learning to produce realistic lip movements aligned with speech.

Features:
- Works well for a variety of audio qualities.
- Can handle pre-existing videos and sync new or alternative audio tracks to them.
- Python-based
- Supports audio files, recordings, or text input for lip-syncing

<img width="447" alt="Screenshot 2024-11-04 at 20 53 07" src="https://github.com/user-attachments/assets/2348b42b-40b6-4bee-a620-7fd02207bbfb">

- Wav2Lip can potentially be integrated with Eleven Labs, likely requiring an API key from Eleven Labs.

<img width="1461" alt="Screenshot 2024-11-04 at 20 54 19" src="https://github.com/user-attachments/assets/9dc49796-ed65-466f-91c7-d44f88a41fd8">

- I attempted a dog lip-sync video, but the default models did not meet expectations.

https://github.com/user-attachments/assets/e05790db-2551-482d-b677-39685cae4a9b

However, we could fine-tune or retrain the model using a dataset of dog faces. By providing a collection of videos where dogs move their mouths in sync with speech (or barking), Wav2Lip’s network could adapt to dog animations.

https://github.com/Rudrabha/Wav2Lip/issues/493

Popularity:

<img width="423" alt="Screenshot 2024-11-04 at 20 48 13" src="https://github.com/user-attachments/assets/334bf36c-a3e6-40c5-81c6-478453dc3160">

Example Generated Video (with significant face shaking to challenge the lip-sync models):
https://github.com/user-attachments/assets/6ec17f98-096e-45c1-80c3-c32399326c34

API Documentations: https://docs.sync.so/api-reference/endpoint/generate/post-generate

---------------------------------

# Live Portrait - I think it can be fit for dog lipsync
Github Repo: https://github.com/KwaiVGI/LivePortrait

Website: https://liveportrait.github.io

Example: https://www.youtube.com/watch?v=kDlCUEsVzF8

Overview: LivePortrait utilizes AI-powered facial motion capture and animation techniques to animate photos, including those of animals like dogs. It typically uses a reference video or an audio track to animate the portrait, moving facial landmarks like the eyes, mouth, and nose in sync with speech or expression changes. This method works best with static images, generating a video with lip-sync from that image.

---------------------------------

# Avatarify
Github Repo: https://github.com/alievk/avatarify-python

Overview: Avatarify allows for real-time face animation, syncing audio and facial movements in real-time. It works with video calls and has been used for animated avatars. I think, its designed for Zoom, Skype and other video-conferencing apps.

Features:
- High accuracy for simple face tracking.
- Often used for synchronization checking and lip-sync transfer.
- Python-based.
- For specific lip-sync applications for animals (like dogs), Avatarify requires training on a custom dataset of dog faces.

Note: I haven’t yet tested this on my local machine.

---------------------------------

# Conclusion
- Wav2Lip seems the best option overall, with thorough documentation for its API and support for integration with Eleven Labs. However, I'm still exploring ways to fine-tune the models.
- Live Portrait appears to be the best option for lip-sync applications involving animals or dogs.

---------------------------------

# reference:
- https://www.pragnakalp.com/best-ai-lip-sync-generators-open-source-free-in-2024-a-comprehensive-guide/
- https://github.com/Rudrabha/Wav2Lip/issues/493
- https://www.youtube.com/watch?v=ceHLnCveen4
- https://www.youtube.com/watch?v=kDlCUEsVzF8
- Chat GPT
