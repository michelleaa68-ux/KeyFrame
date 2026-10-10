# AI Usage Log

AI Tools Used

Log 1: Claude AI — Used for debugging and coding assistance.
Claude: how long a key must be held
What for: The code needs a rule for when a finger counts as pressing a note. Claude tested hold times from 0.1 to 0.5 seconds on my first clips.
What I kept or changed: I kept 0.2 seconds. Shorter times gave lots of extra notes from the finger passing over keys, and longer times missed notes.

Log 2: Claude AI: debugging wrong results
What for: When the predictions were wrong or had extra notes, Claude helped find the cause.
What I kept or changed: I checked every result against the notes I wrote down, and I did not change the code just to get a better score.

Log 3: Gemini — Used for velocity filtering and section setup.
Gemini: Finger speed tracking and notebook organization
What for: The code was picking up extra notes while the hand moved across the keyboard, and test videos were showing up in Step 3 early.
What I kept or changed: I kept the velocity filter set to max_velocity = 8.0 to ignore moving hands, and updated the video loops so each section only runs its own files.

Log 4: GitHub Copilot — Used for code refactoring and jitter fixes.
GitHub Copilot: Code cleanup and duplicate suppression
What for: Hand jitter caused duplicate note triggers, and different camera angles gave wrong note names on new test videos.
What I kept or changed: I kept the check that stops back-to-back duplicate notes and added key offset logic to handle zoomed-in test videos.

Log 5: Gemini — Used for ground truth verification and loop isolation.
Gemini: Step 3 ground truth fixes and test video separation
What for: Example 1 and Example 2 had swapped ground truth labels in the code, and test videos were running in the wrong notebook section.
What I kept or changed: I swapped the ground truth labels to match the real videos and added strict file filtering so Step 3 only runs baseline clips and Step 4 only runs test clips.
