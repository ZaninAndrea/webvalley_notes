# Spectroscopy and mass spectroscopy - an Introduction
## Keywords
- spectre
- wave-length
- emission and absorption spectrum
- Prediction vs Understanding
- correlation is not causation
- preprocessing
- reproducibility


## Spectroscopy
A spectrometer is an object that easures light, the properties of the light will bring memory of chemical characteristics about the fruit.

The wave-length tells you the size of the object the wave will interact with

> **Microwave**
> The microwave emits wave with the right wave-length to interact with water

The spectrum of the sun is a continuous spectrum, whereas different atoms emit different spectres when excited, and those are sparse.

We can also see an absorption spectrum, which is the spectrum of light remaining after a full spectrum light passes through a cloud of gas.

Overlapping the emission and absorption spectrum you get a continuous spectrum

The light coming from a star is partially absorbed by the outer layers of the star, this allows us to get information about the chemical composition of the star.
> **Issues**
> You have to consider that some wavelengths are blocked by the atmosphere or by objects in between the source and the spectrograph.

To understand the composition of a planet I can see the variation in the spectrum due to the crossing of the planet in front of the star and the absorption done by the atmosphere

> **Doppler effect**
> Depending on the relative speed of the stars to us the spectrum is shifted towards the red (if they are moving away) or the blue (otherwise)
> 
> We can see that almost all stars are moving away from us, because the universe is expanding.

Do not constrain yourself in just spectroscopy when you want to predict.

## Mass Spectroscopy
You have ionized molecules, and being charged you can spread them, producing a spectrum, that depends on the mass.
You get much more information with this technique, but I have to put the sample in a machine, it's not remote.

This technique is used to check if oil is similar to a known oil which is good.

Prediction and understanding are 2 different things: I can understand that a tree is a tree without knowing the mechanism of photosyntesis

Being able to predict something will not always lead to understanding how it works

## Preprocessing
The preprocessing needs to be reproducible, otherwise it's useless

Preprocessing has to tell noise and signal apart, the task is harder for weaker signals.

Issue list:
- background removal
    * I can find the local minima
    * choosing the window size is an issue
- peak picking
    * I can find a local maxima
    * choosing the window size is again an issue
- denoising
    * you can use a local average (again window size)
    * wavelet denoising
    * you have to smooth the right amount, so to remove noise, but not features
- alignment
    * peaks may be not aligned, due to issues with the machine or environment
- normalization
    * needed for quantitative measurements
    
## Spectrometry for medicine
With mass spectrometry you could use the spectra to identify the pathogen in minutes (nowadays it takes 2/3 days).

You can also use the data from mass spectrometry of the gases released when cutting with an electrical knife to classify the tissues. This technique can be used both for cancer sniffing and monitoring food processing.


I can find the local minima and then draw a smooth curve