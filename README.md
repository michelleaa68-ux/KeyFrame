
# KeyFrame
## What it does
KeyFrame watches a video of a piano from above and tells you which notes were played, like G2 -> C3.
It finds the fingertip, matches it to a key, and prints the notes in order.

## How it works
I used OpenCV and NumPy in Google Colab. There is no AI model.
1. Find the left edge of the keyboard.
2. Find the fingertip near the bottom of the frame.
3. Turn the fingertip position into a key number.
4. If the finger stays on a key for 0.2 seconds, it counts as a note.

## Data
I filmed 11 short clips of my keyboard (a Novation FLkey 37) from above with my phone.
8 were my first clips and 3 were recorded later with the camera farther back.
I wrote down the notes I played in each one to check the results.

## Results
My goal was 90% accuracy.

| Clips | Clips fully correct | Notes found |
|---|---|---|
| First 8 clips | 5 of 8 | 27 of 27 (but 7 extra wrong notes) |
| New 3 clips | 1 of 3 | 5 of 8 |

I did not reach my goal. I tuned the code on these clips, so this is not a clean test on new data.

## What went wrong
- It adds extra notes when my finger moves over other keys.
- It lost my finger when it was cut off at the bottom of the frame.
- The camera was handheld, and the key size changed when I moved it farther back, so I had to change a setting (`key_frac`).

## What changed from my Blueprint
- The camera was not fixed, so I find the keyboard again in every frame.
- I track the fingertip instead of watching the keys change.
- I only handle white keys, one finger, one note at a time.

## Next steps
Use a hand tracking model like MediaPipe, measure the key size automatically, and test on brand new clips.

## How to run
Open `notebooks/KeyFrame.ipynb` in Google Colab, upload the clips in the Files panel, and run the cells in order.
For the 3 newer clips, use `key_frac=0.043`.

## AI use
I used Claude for help with the code and planning. See `docs/AI_usage_log.md

