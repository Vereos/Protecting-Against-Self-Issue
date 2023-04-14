# Practical Protection of Voice-Controllable Devices Against Self-Issued Voice Commands

This is the anonymous Github that supports the research paper _"Practical Protection of Voice-Controllable Devices Against Self-Issued Voice Commands"_. This repository is kept anonymous for the double-blind review process.

Voice spoofing attacks against smart devices issue a voice command using a synthesized voice from a speaker near the target device. An adversary may also leverage the target device to issue a voice command to itself, performing a self-issued voice command. In this paper, we propose a practical countermeasure against this attack, by training a Siamese Neural Network to recognize the differences between what is being played and what is being recorded by the voice-controllable device, as these audios are similar in case of voice command self-issue attacks and different in case of legitimate commands. Hence, our solution protects voice-controllable devices from self-issued commands while allowing usage of such devices to people who require a synthesized voice to communicate. We find that our solution correctly classifies commands in the benign and malign categories 97% of the times on average.

## Contents of this release

### Source Code
- `Release-SI-Mitigation.ipynb`, a notebook that contains the full source code of our solution. It performs the training of our Siamese Neural Network and then it validates such network against a different testing dataset. Instructions for use can be found within the notebook itself, which is best run on Google Colab.
- `Release-SI-MonoValidation.ipynb`, a notebook that contains only the portion of code that performs the validation. It can be used (i) for benchmarking purposes or (ii) to test a pretrained model quickly against a new sample. Instructions for use can be found within the notebook itself, which can be run on Google Colab, but can also be used as a Python script (just copy and paste the code within a `.py` file) on Windows and Raspbian. 

### Datasets
Instructions on how to use these datasets are contained within the aforementioned notebooks.
- `selfissue-dataset-public-v1.zip`, a dataset consisting of all the _played_ and _recorded_ samples, along with their respective Mel-Spectrograms. This dataset can be used if you want to compare another solution with ours, or if you want to use our solution and perform all the preprocessing steps from scratch. This dataset contains 140 .wav files and 140 .png files.
- `augmented-dataset.zip`, the full dataset after the preprocessing, consisting of all generated Mel-Spectrograms, including the augmented ones. This dataset can be used if you just want to run our solution without any extra step. This dataset does not include the .wav files as our solution only uses them for the preprocessing steps. This dataset contains 840 .png files.
- `augmented-dataset-structure.zip`, a directory tree that must be extracted before performing the preprocessing, so that Mel-Spectrograms that will be generated can be placed in the correct directory.
- `monotest-samples.zip`, an archive that contains files needed for the "MonoValidation" notebook to work (i.e., the pretrained model and one pair of samples).
