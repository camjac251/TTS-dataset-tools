# Automated-TTS-dataset-builder
Transcribe audio via Google Speech to Text API with speaker separation (diarization). Automatically generate TTS datasets using audio and associated text. Uses aeneas to force align text to audio. Create even more source text and audio by splitting entries and combining end and beginning halves. Quickly proofread and edit cuts.

Run dataset_gui.py for GUI tools. 

Current limitations are that you will need to adjust column width of the proofreading section and when navigating entries you must take the focus off the current and next input text boxes or the text box will not update. Next version of dearpy gui will solve these issues.

![Dataset GUI](https://github.com/youmebangbang/Automated-TTS-dataset-builder/blob/master/dataset_gui.png)


# Setup
Linux environment is recommended for the dataset builder as using windows aeneas will not be able to make longer cuts due to memory issues. 

wget https://raw.githubusercontent.com/readbeyond/aeneas/master/install_dependencies.sh

bash install_dependencies.sh

pip install numpy

pip install aeneas

test installation:  python -m aeneas.diagnostics

pip install pydub

pip install dearpygui

pip install google-cloud-speech

pip install google-cloud-storage

sudo apt install libasound2-dev

pip install simpleaudio

If you get libpython error: 
export LD_LIBRARY_PATH=[homepath]/anaconda3/envs/[yourenv]/lib

# Usage

Video tutorial coming soon!

# Recommendations

Several things will improve the quality of your cuts, although you should always proofread them before training. Currently this will only work with english language, but you can easily edit the aeneas command lines and character replacements to your need. Examine if things like chapter titles are included. Speakers with slow and even paced speech will make the cleanest cuts, while fast paced speakers tend to run words together and can cause some words, pieces of words, to be shifted into the next cut where it will have to be edited. Remove all music if able.
