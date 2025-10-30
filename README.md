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
The dataset contains annotated laser vibrometry recordings collected over a period of several years. Most of them contain recordings of vibroscape in its natural environment (hay meadows), a subset also contains laboratory recordings of two species.

Field recordings of vibroscape were conducted on a eutrophic lowland hay meadow located in Ljubljana Moors, Slovenia (coordinates: N 45°56’42.40’’, E 14°20’09.21’’) during the years 2016, 2017, 2018 and 2023. The vibroscape was recorded using a portable Doppler laser vibrometer (Polytec PDV 100) and stored on a laptop computer equipped with an external sound card (Sound Blaster SBX) and Raven Pro 1.5 software at the sampling rate 44 kHz and 16-bit resolution. To capture the vibroscape, we precisely point the laser beam at a small piece of reflective foil placed on a plant. Sound files in .wav format were automatically saved every 10 minutes. The recording site had access to the power grid, and electricity was supplied directly to the equipment via an extension cable. Recordings were conducted during stable weather conditions to prevent any damage to the equipment.

In contrast, laboratory recordings of leafhoppers from the genus *Aphrodes* were collected over several years at the National Institute of Biology in Slovenia. These recordings were obtained during behavioural trials using a portable Doppler laser vibrometer (Polytec PDV 100). The laser beam was directed at reflective foil placed on individual herbaceous plant cuttings with leafhoppers present. The laboratory recordings have a better signal to noise ration compared to those obtained in the natural environment.

### Annotations

The dataset was manually annotated by domain experts who marked the time/frequency ranges of each vibrational signal they encountered by listening to the recordings and inspecting the corresponding spectrograms. The experts classified the signals based on their distinct temporal and spectral characteristics [(Šturm et al. 2021)](https://doi.org/10.1016/j.isci.2021.103070). They identified four main vibrational signal categories: pulse (P), which contains short broadband or harmonic pulses, harmonic (F), which contains longer signals with a clear harmonic structure, train (T) with regularly repeating pulses or harmonic structures, and complex (C), which contains at least two of the previous types with a relatively well-defined structure. Some of the signals could be attributed to individual species i.e. leafhoppers *Aphrodes makarovi*, *A. bicincta* Dragonja (T1), *Anoscopus serratulae* (C2), *Megophthalmus scanicus* (T3), while others are identified only by their type and number (e.g. T9) because the species producing the signal is not known. 

The annotations include the start and end time of each vibrational signal, its low and high frequency and its label. The annotations may overlap in time. The labels used for the annotations are:
* *CXX*: Signal belonging to the complex category (*XX* is a number)
* *TXX*: Signal belonging to the pulse train category (*XX* is a number)
* *FXX*: Signal belonging to the harmonic category (*XX* is a number)
* *PXX*: Signal belonging to the pulse category (*XX* is a number)
* *ZXX*: Various noises, such as animal movements, wind, etc. (*XX* is a number)
* *BG*: Background, i.e. no signal was annotated (background noise)
* *UNL*: Unlabeled. For some recordings, the beginning or end of a recording was skipped during annotation, so it is marked as unlabeled.

### Dataset structure

The dataset is organized within several folders. The recordings are not included in the github repository and are available for download through the links below.

* **annotations/annotations.tsv**: the tab-delimited file with annotations for all recordings. The columns are: *audio filename*, *start time*, *end time*, *start frequency*, *end frequency*, *label*.
* **audio**: contains recordings in the following subfolders:
 * **Laboratory** contains laboratory recordings of C1 and T1 signals. The files are named as: *recording.1.XXX.wav* (*XXX* is a number).
* **Field/C1T1** contains field recordings in which only the signals C1 and T1 were labelled. The BG class in these recordings may therefore contain other vibrational signals as they have not been labelled. The files, which are each a maximum of ten minutes long, are named as follows: *recording.date.hour_of_day.ch.XXX.wav*, where *date* and *hour_of_day* denote the date/time of the start of the respective recording, *ch* denotes the audio channel in the original recording and *XXX* a number.
* **Field/CFPT** contains field recordings in which C, F, P and T signals were annotated. The files, which are each a maximum of ten minutes long, are named as follows: *recording.date.hour_of_day.ch.XXX.wav*, where *date* and *hour_of_day* denote the date/time of the start of the respective recording, *ch* the audio channel in the original recording and *XXX* a number.
 * **Field/24hour** contains unannotated field recordings of eight whole days. The files, which are each a maximum of ten minutes long, are named as follows: *recording.date.hour_of_day.ch.XXX.wav*, where *date* and *hour_of_day* denote the date/time of the start of each recording, *ch* detones the audio channel of the original recording and *XXX*  a number.

### Download audio

Zipped audio recordings can be downloaded with the following links. Unzip them in the root of the dataset repository.
* [Laboratory](https://drive.google.com/file/d/1Spf4S-nOytw5qS859yITIddRHy4q3lcq/view?usp=sharing) 2.25 GB
* [Field_C1T1](https://drive.google.com/file/d/1d0cSJIszzpTEto6ItaQqPhHVnU9_5rbW/view?usp=sharing) 2.7 GB
* [Field_CFPT](https://drive.google.com/file/d/1okoAbLhU4YyG0pBQMj22vZIlXnR7RUE9/view?usp=sharing) 11.3 GB
* [24 hour](https://drive.google.com/file/d/1wMB_T9pOcCtBIJH96z0GPy4twYtuQuRT/view?usp=sharing) 27.1 GB

### Cite us
The paper describing the dataset and our first automatic classification methods is published in Ecological Informatics. Please cite  [(Marolt et al. 2025)](https://doi.org/10.1016/j.ecoinf.2025.103003) if you use this code or dataset.

BibTex:
```
@article{Marolt2025,
   author = {Matija Marolt and Matevž Pesek and Rok Šturm and Juan José López Díez and Behare Rexhepi and Meta Virant-Doberlet},
   journal = {Ecological Informatics},
   keywords = {Vibroscape, Ecotremology, Deep learning, Automatic classification, Biotremology, Insects},
   publisher = {Elsevier Inc.},
   title = {Computational methods for detecting insect vibrational signals in field vibroscape recordings},
   year = {2025},
}
``` 

### Licensing
The dataset is published under the [CC-BY-NC-SA 4.0 license](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode). Feel free to use it for your research with necessary attributions. 

### Contact
For any questions, contact matija.marolt [at] fri.uni-lj.si
