# VibroScape

Matija Marolt<sup>1</sup>, Matevž Pesek<sup>1</sup>, Rok Šturm<sup>2</sup>, Juan José López Díez<sup>2</sup>, Behare Rexhepi<sup>2</sup>, Meta Virant-Doberlet<sup>2</sup>

<sup>1</sup> University of Ljubljana, Faculty of Computer and Information Science, Laboratory for Coumputer Graphics and Multimedia, Slovenia

<sup>2</sup> National Institute of Biology, Department of Organisms and Ecosystems Research, Slovenia

# The VibroScape Dataset

The repository contains the VibroScape dataset - an **annotated dataset of vibroscape recordings from meadow habitats**, containing insect vibrational signals categorized as pulses, harmonic signals, pulse trains and complex signals. 
<p align="center">
<img src="https://github.com/matijama/VibroScape/blob/main/T9.png" alt="T9 signal" width="500">
</p>

### Procedure
The dataset contains annotated laser vibrometry recordings that were collected over a period of several years. Most of them contain recordings of vibroscape in its natural environment (hay meadows), a subset also contains laboratory recordings of two species. 

Field recordings of vibroscape were conducted on a eutrophic lowland hay meadow located in Ljubljana Moors, Slovenia (coordinates: N 45°56’42.40’’, E 14°20’09.21’’) during the years 2016, 2017, 2018 and 2023. The vibroscape was recorded using a portable Doppler laser vibrometer (Polytec PDV 100) and stored on a laptop computer equipped with an external sound card (Sound Blaster SBX) and Raven Pro 1.5 software at the sampling rate 44 kHz and 16-bit resolution. To capture the vibroscape, we precisely point the laser beam at a small piece of reflective foil placed on a plant. Sound files in .wav format were automatically saved every 10 minutes. The recording site had access to the power grid, and electricity was supplied directly to the equipment via an extension cable. Recordings were conducted during stable weather conditions to prevent any damage to the equipment.

In contrast, laboratory recordings of leafhoppers from the genus *Aphrodes* were collected over several years at the National Institute of Biology in Slovenia. These recordings were obtained during behavioural trials using a portable Doppler laser vibrometer (Polytec PDV 100). The laser beam was directed at reflective foil placed on individual herbaceous plant cuttings with leafhoppers present. The laboratory recordings have a better signal to noise ration compared to those obtained in the natural environment.

### Annotations

The dataset was manually annotated by domain experts who marked the time/frequency ranges of each vibrational signal they encountered by listening to the recordings and inspecting the corresponding spectrograms. The experts classified the signals based on their distinct temporal and spectral characteristics [(Šturm et al. 2021)](https://doi.org/10.1016/j.isci.2021.103070). They identified four main vibrational signal categories: pulse (P), which contains short broadband or harmonic pulses, harmonic (F), which contains longer signals with a clear harmonic structure, train (T) with regularly repeating pulses or harmonic structures, and complex (C), which contains at least two of the previous types with a relatively well-defined structure. Some of the signals could be attributed to individual species i.e. leafhoppers *Aphrodes makarovi*, *A. bicincta* Dragonja (T1), *Anoscopus serratulae* (C2), *Megophthalmus scanicus* (T3), while others are identified only by their type and number (e.g. T9) because the species producing the signal is not known. 

Annotations include the start and end time of each vibrational signal, its low and high frequency and its label. Annotations may overlap in time. The labels used for annotations are:
* *CXX*: signal belonging to the complex category (*XX* is a number)
* *TXX*: signal belonging to the pulse train category (*XX* is a number)
* *FXX*: signal belonging to the harmonic category (*XX* is a number)
* *PXX*: signal belonging to the pulse category (*XX* is a number)
* *ZXX*: various noises, such as animal movements, wind etc. (*XX* is a number)
* *BG*: background, meaning no signal was annotated (background noise)
* *UNL*: unlabelled. In some recordings, the beginning or the end of a recordings was skipped during annotation, so it is marked as unlabelled.

### Dataset structure

The dataset is organized within several folders. The recordings are not included in the github repository and are available for download through the links below.

* **annotations/annotations.tsv**: the tab-separated file with annotations for all recordings. The columns are: *audio file name*, *start time*, *end time*, *start frequency*, *end frequency*, *label*.
* **audio**: contains recordings in the following sub-folders:
    * **Laboratory** contains laboratory recordings of C1 and T1 signals. Files are named as: *recording.1.XXX.wav* (*XXX* is a number).
    * **Field/C1T1** contains field recordings, where only the C1 and T1 signals have been labelled. The BG class in these recordings may thus contain other vibrational signals, as they were not annotated. Files, each with a maximum of ten minutes duration, are named as: *recording.date.hour_of_day.ch.XXX.wav*, where *date* and *hour_of_day* represent the date/time of the start of each recording, *ch* is the audio channel in the original recording and *XXX* a number.
    * **Field/CFPT** contains field recordings where C, F, P and T signals were annotated. Files, each with a maximum of ten minutes duration, are named as: *recording.date.hour_of_day.ch.XXX.wav*, where *date* and *hour_of_day* represent the date/time of the start of each recording, *ch* is the audio channel in the original recording and *XXX* a number.
    * **Field/24hour** contains unannotated field recordings of eight entire days. Files, each with a maximum of ten minutes duration, are named as: *recording.date.hour_of_day.ch.XXX.wav*, where *date* and *hour_of_day* represent the date/time of the start of each recording, *ch* is the audio channel in the original recording and *XXX* a number.

### Cite us
A paper describing the dataset and our first automatic classification methods is under review. Please cite our previous paper [(Šturm et al. 2021)](https://doi.org/10.1016/j.isci.2021.103070) if you use this dataset.

BibTex:
```
@article{Sturm2021,
   author = {Rok Šturm and Behare Rexhepi and Juan José López Díez and Andrej Blejec and Jernej Polajnar and Jérôme Sueur and Meta Virant-Doberlet},
   doi = {10.1016/j.isci.2021.103070},
   issn = {25890042},
   issue = {9},
   journal = {iScience},
   keywords = {Biological sciences,Interaction of plants with organisms,Plant biology,Plants},
   month = {9},
   publisher = {Elsevier Inc.},
   title = {Hay meadow vibroscape and interactions within insect vibrational community},
   volume = {24},
   year = {2021},
}
``` 

### Licensing
The dataset is published under the [CC-BY-NC-SA 4.0 license](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode). Feel free to use it for your research with necessary attributions. 

