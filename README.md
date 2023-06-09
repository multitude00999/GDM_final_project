# Zero-Shot Evaluation of QuickVC in Multilingual Setting

## Developed By: 

### [Gautam Srinidhi Iruvanti](https://www.mccormick.northwestern.edu/artificial-intelligence/people/students/2022-2023/gautam-iruvanti.html)
(gautamiruvanti2024@u.northwestern.edu)
### [Surya Pratap Parmar](https://www.mccormick.northwestern.edu/artificial-intelligence/people/students/2022-2023/surya-parmar.html)
(suryaparmar2024@u.northwestern.edu)
### [Vishal Shrivastava](https://www.mccormick.northwestern.edu/artificial-intelligence/people/students/2022-2023/vishal-shrivastava.html)
(vishalshrivastava2024@u.northwestern.edu)

**********
## Course: [Deep Generative Models, CS 496 Spring 2023, Northwestern University](https://interactiveaudiolab.github.io/teaching/generative_deep_models.html#calendar)

### Professor: [Bryan Pardo](http://bryanpardo.com/)
### TA: [Patrick O’Reilly](https://oreillyp.github.io/)
*********** 

## <b>Background</b>
<p>
It is a commonly accepted fact in the AI community that the Automatic Speech Recognition (ASR) models can exhibit bias towards native speakers due to several factors. In one of the recent studies conducted at Washington University<sup>1</sup>, the researchers tried to examine discriminatory automatic speech recognition (ASR) performance as a function of speakers’ geopolitical orientation, specifically their first language. Unsurprisingly, they found that the ASR models were biased towards the native English speakers. We can see the results in the following graph where the X-axis represents a metric called “Word Information Lost” - the fraction of words that were changed, inserted, or deleted during the speech generation; and the Y-axis shows the first language of the respective speakers. As we can see in the graph, for all the three major ASR services, word information loss is lowest for native English speakers and it gets higher and higher for speakers from different backgrounds.

<span class="img_container center" style="display: block;">
    <img alt="test" src="./images/asr_bias.png?raw=true" style="display:block; margin-left: auto; margin-right: auto;" title="caption" />
    <span class="img_caption" style="display: block; text-align: center;">Figure 1: Mean word information lost (WIL) for ASR services vs. first language</span>
</span>
</br>
</br>
We believe that one of the primary reasons for this disparity is that the ASR models are typically trained on large amounts of data, which may consist predominantly of speech from native speakers. This happens due to a lack of labeled audio datasets of non-native speakers speaking a particular language. As a result, the ASR models struggle with recognizing and accurately transcribing non-native accents or variations in pronunciation.
This problem motivated us to think about some potential ways of generating high volumes of labeled audio data in multiple languages with diversified accents. Now, of course, we can generate high volumes of labled speech by using a text-to-speech system, but it doesn’t solve the problem of accented speech, which is the main issue with the low performance of ASR systems. Guo et. al<sup>2</sup> have recently introduced QuickVC - an any-to-many voice conversion framework using inverse short-time Fourier transforms. QuickVC is trained on English speech, but we wondered if we can use it for generating accented speech in other languages too. We believed that doing so would provide us with a viable option for generating high volumes of labeled audio data with diversified accents that can be used for training or fine-tuning ASR systems.
<span class="img_container center" style="display: block;">
    <img alt="test" src="./images/initial_flow_design.png?raw=true" style="display:block; margin-left: auto; margin-right: auto;" title="caption" />
    <span class="img_caption" style="display: block; text-align: center;">Figure 2:  Flow design for generating high volume of labeled audio with diversified accents<sup>1</sup></span>
</span>
</p>
&nbsp;

## <b>Dataset</b>
<p>
For the text-to-speech synthesis, we used Qi et. al’s massively multilingual (60 languages) data set derived from TED Talk transcripts<sup>3</sup>. We chose to work with ten of the most common languages around the world, which includes English, Hindi, Spanish, Portuguese, Turkish, Russian, Swedish, Hungarian, Indonesian, and German. For target audio samples, we chose ten different speakers from the VCTK corpus<sup>4</sup>, which contains recordings of speech from 110 English speakers with diverse accents. 
</p>

## <b>References</b>



<!DOCTYPE html>
<html>
  <figure>
    <figcaption>source audio:</figcaption>
    <audio
        controls
        src="audio/source.mp4">
            <a href="audio/source.mp4">
                Download audio
            </a>
    </audio>
</figure>
    
<figure>
    <figcaption>target speaker:</figcaption>
    <audio
        controls
        src="audio/target_speaker.mp4">
            <a href="audio/target_speaker.mp4">
                Download audio
            </a>
    </audio>
</figure>
    
<figure>
    <figcaption>output:</figcaption>
    <audio
        controls
        src="audio/output.mp4">
            <a href="audio/output.mp4">
                Download audio
            </a>
    </audio>
</figure>
</html>







