# lipsync-opensource-research
This document summarizes research on open-source methods for implementing lip-sync in video. We believe that Eleven Labs may offer the best high-quality voice replication, though it is not open source. Therefore, this research focuses on open-source lip-sync methods.

---------------------------------

## VideoRetalking
Based on the official page, I reviewed VideoReTalking’s results compared to ATVG, LipGAN, Wav2Lip, MakeItTalk, and PC-AVS. From the lip-sync video results, VideoReTalking stands out due to its structured approach, divided into three steps: 

- (1) face video generation with a canonical expression; 
- (2) audio-driven lip-sync;
- (3) face enhancement for improving photo-realism.

Page: https://opentalker.github.io/video-retalking/

Github: https://github.com/OpenTalker/video-retalking

To implement, we can use a VM, like on RunPod, and build an API with a Python framework (Flask, FastAPI, etc.). There are also models on Replicate: [chenxwh](https://replicate.com/chenxwh/video-retalking).

If we are ready to using this, i'll try to setup it on local for the rest api.

### Update - November 8, 2024
I found a video comparing wav2lip, wav2lip + GAN, videoretalking, and dinet:
the video: https://www.youtube.com/watch?v=lSODJt8Xqn0
- Dinet performs well, but it shows a noticeable square around the lips if the resolution is low or if the video has animations. Based on user feedback, it seems to deliver higher quality results with high-resolution inputs and less head movement.
- VideoReTalking performs well on average, even with low-resolution videos. However, it encountered errors in 4 out of 16 tests, as shown at 5:42 in the video. Still. But i think it’s the winner cause its better overall.

I also found this thread on Twitter! [Twitter Post Link](https://x.com/thibaudz/status/1713518876300857419). The SadTalker video looks quite realistic to me! [The SadTalker Video Link](https://x.com/thibaudz/status/1713518881304608904)

Other resources I’ve reviewed:
https://x.com/minchoi/status/1843395626199142521
https://www.reddit.com/r/StableDiffusion/comments/1fy63qy/the_best_opensource_lipsync_tools_as_of_right_now/
https://www.reddit.com/r/StableDiffusion/comments/1fy63qy/comment/lrjhrhp/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button

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

Update 8 Nov 2024
- 

---------------------------------

# reference:
- https://www.pragnakalp.com/best-ai-lip-sync-generators-open-source-free-in-2024-a-comprehensive-guide/
- https://github.com/Rudrabha/Wav2Lip/issues/493
- https://www.youtube.com/watch?v=ceHLnCveen4
- https://www.youtube.com/watch?v=kDlCUEsVzF8
- Chat GPT
