# version-beta
This is an project  for hackthon version beta from error_404 
# Screenshots
<p float="left">
  <img src="/Try Fit/ScreenShots/72322052_810218676059930_7368649405747953664_n.png" width="256" hspace="20"/>
  <img src="/Try Fit/ScreenShots/72343149_741909062953871_3776403506005540864_n.png" width="256" hspace="20"/> 
  <img src="/Try Fit/ScreenShots/72196412_400504493963568_6939379145478504448_n.png" width="256"/> 
</p>
<p float="left">
  <img src="/Try Fit/ScreenShots/72311459_2445192302366406_2332354953273671680_n.png" width="256" hspace="20"/>
  <img src="/Try Fit/ScreenShots/Screenshot from 2019-10-13 11-44-10.png" width="256" hspace="20"/> 
</p>
# [Try Fit]
### A virtual fitting room service!

<p float="left">
  <img src="Try Fit/inputs/example_person.jpg" width="256" hspace="20"/>
  <img src="Try Fit/inputs/example_clothing.jpg" width="256" hspace="20"/> 
  <img src="Try Fit/output/example_output.png" width="256"/> 
</p>

* [Important Note](#important-note)
* [Requisites](#requisites)
* [Setup](#setup)
  * [Test Example](#test-example)
* [Notebooks](#notebooks)
* [References](#references)

  
## Requisites

* [Conda](https://conda.io/docs/user-guide/install/index.html)
* [Octave 4.2+](https://www.gnu.org/software/octave/download.html) (with [image](https://octave.sourceforge.io/image/index.html) package)
  * Also compatible with MATLAB

## Setup

First clone the repository:

Next, run `source setup.sh`, which will create a conda environment and install the required packages via
```
conda create --name smartfit python=2.7 pip
source activate smartfit
pip install -r requirements.txt
```

### Test Example

To test whether the setup was successful, run the following command that should reproduce the clothing transfer shown at the top of the README:
```
./run_smartfit.sh inputs/example_person.jpg inputs/example_clothing.jpg
```
The corresponding output is `output/output.png` and should be similar to `output/example_output.png` (the right-most image above).

## Notebooks

This repo includes some jupyter notebooks (located in `notebooks/`) that may be useful for understanding the SmartFit pipeline and its inputs/outputs. Exact usage instructions are at the top of each notebook.

* `visualize_inputs.ipynb`
  * Explains and shows the main inputs to the clothing transfer model: body mask, face and pants, keypoint pose map, and clothing item.
* `visualize_output.ipynb`
  * Displays the output image.
* `skintone_check.ipynb`
  * Describes how the skintone check works. This is a check to make sure that the clothing transfer model did not change the skintone of the inputted person.

## References

This project builds from the work listed below:

* Human parsing
  * LIP_JPPNet ([repo](https://github.com/Engineering-Course/LIP_JPPNet), [paper](https://arxiv.org/abs/1804.01984))
* Pose estimation
  * Realtime Multi-Person Pose Estimation ([repo](https://github.com/ZheC/Realtime_Multi-Person_Pose_Estimation), [paper](https://arxiv.org/abs/1611.08050))
    * [Keras implementation](https://github.com/michalfaber/keras_Realtime_Multi-Person_Pose_Estimation)
* Virtual try-on
  * VITON ([repo](https://github.com/xthan/VITON), [paper](https://arxiv.org/abs/1711.08447))
