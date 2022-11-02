<!-- # Deep Neural Mel-Subband Beamformer for In-Car Speech Separation -->

<!-- ### *Vinay Kothapally, Yong Xu, Meng Yu, Shi-Xiong Zhang, Dong Yu* -->
### [SUBMITTED TO ICASSP 2023]

<h2 id = "1"><u>Abstract</u></h2>

While current deep learning (DL)-based beamforming techniques have been proved effective in speech separation, they are often designed to process narrow-band (NB) frequencies independently which results in higher computational costs and inference times, making them unsuitable for real-world use. In this paper, we propose DL-based mel-subband spatio-temporal beamformer to perform speech separation in a car environment with reduced computation cost and inference time. As opposed to conventional subband (SB) approaches, our framework uses a mel-scale based subband selection strategy which ensures a fine-grained processing for lower frequencies where most speech formant structure is present, and coarse-grained processing for higher frequencies. In a recursive way, robust frame-level beamforming weights are determined for each speaker location/zone in a car from the estimated subband speech and noise covariance matrices. Furthermore, proposed framework also estimates and suppresses any echoes from the loudspeaker(s) by using the echo reference signals. We compare the performance of our proposed framework to several NB, SB, and full-band (FB) processing techniques in terms of speech quality and recognition metrics. Based on experimental evaluations on simulated and real-world recordings, we find that our proposed framework achieves better separation performance over all SB and FB approaches and achieves performance closer to NB processing techniques while requiring lower computing cost.

<!-- ## Problem Statement

| **M-Microphone N-Speaker Separation with Low Computations and Faster Inference**                    |                                                              | 
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| <img src="./data/model/Overview.png" alt="flowtron_0.0" style="zoom: 50%;" /> | While current deep learning (DL)-based beamforming techniques have been proved effective in speech separation, they are often designed to process narrow-band (NB) frequencies independently which results in higher computational costs and inference times, making them unsuitable for real-world use. In this paper, we propose DL-based mel-subband spatio-temporal beamformer to perform speech separation in a car environment with reduced computation cost and inference time. As opposed to conventional subband (SB) approaches, our framework uses a mel-scale based subband selection strategy which ensures a fine-grained processing for lower frequencies where most speech formant structure is present | -->



<h2 id = "1"><u>Problem Statement</u></h2>

### [M-Microphone N-Speaker Separation with Low Computations and Faster Inference]
<img src="./data/model/Overview.png" alt="flowtron_0.0" style="zoom: 70%;" /> 

While current deep learning (DL)-based beamforming techniques have been proved effective in speech separation, they are often designed to process narrow-band (NB) frequencies independently which results in higher computational costs and inference times, making them unsuitable for real-world use. In this paper, we propose DL-based mel-subband spatio-temporal beamformer to perform speech separation in a car environment with reduced computation cost and inference time. As opposed to conventional subband (SB) approaches, our framework uses a mel-scale based subband selection strategy which ensures a fine-grained processing for lower frequencies where most speech formant structure is present 

<br><br><br><br>

<!-- <h2 id = "1"><u>Real-World Recording Setup for In-Car Speech Capture</u></h2>

| <img src="./data/model/Overview.png" alt="flowtron_0.0" style="zoom: 43%;" /> | <img src="./data/model/Overview.png" alt="flowtron_0.0" style="zoom: 43%;" /> | <img src="./data/model/Overview.png" alt="flowtron_0.0" style="zoom: 43%;" /> | <img src="./data/model/Overview.png" alt="flowtron_0.0" style="zoom: 43%;" /> | -->


<h2 id = "1"><u>Proposed Subband Beamforming -- All Neural Network Architecture</u></h2>

|  **Neural Architecture**                                     |
| :----------------------------------------------------------: |
| <img src="./data/model/Network.png" alt="flowtron_0.0" style="zoom: 180%;" /> |

|  **Tensor Dimensions for each step within the Network**      |
| :----------------------------------------------------------: |
| <img src="./data/model/Tensor_Chart_Subband_Beamformer.png" alt="flowtron_0.0" style="zoom: 150%;" /> |

<br><br><br><br>

<h2 id = "1"><u>Audio samples processed by various DL-based beamformers</u></h2>

### [Includes Narrow-band (NB), Full-band (FB), and Sub-band (SB) based approaches]

|       **Audio sample illustrated in the  paper**             |                                                              |                                                              |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture** <br><audio controls><source src="./data/with_reverb/example275/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **ConvTasNet (FB)** <br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **LSTM+Attention (FB)** <br><audio controls><source src="./data/with_reverb/example275/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (FB)** <br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **Tradition Subband (#64)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Proposed Mel-Subband (#64)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Time-Variant MVDR (NB)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (NB)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **[Reference Rev. Clean] Speaker-1 (In Zone-1)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-2 (In Zone-2)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-3 (In Zone-3)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-4 (In Zone-4)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |


<br><br><br><br>

<h2 id = "1"><u>Processed Audio Samples of Simulated Recordings (Test Set)</u></h2>

|       **One Available Speaker [S1]**                    | **Mixture SNR: -10 dB, PESQ: -10 dB**                         |                                                              |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture** <br><audio controls><source src="./data/audiofiles/1spk/mix_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **ConvTasNet (FB)** <br>  <audio controls><source src="./data/audiofiles/1spk/ConvTasNet_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **LSTM+Attention (FB)** <br><audio controls><source src="./data/audiofiles/1spk/LSTM_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (FB)** <br>  <audio controls><source src="./data/audiofiles/1spk/FB_GRNNBF_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/spectorgrams/mix_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/ConvTasNet_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/LSTM_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/FB_GRNNBF_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **Tradition Subband (#64)**<br>  <audio controls><source src="./data/audiofiles/1spk/SB_64_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Proposed Mel-Subband (#64)** <br> <audio controls><source src="./data/audiofiles/1spk/MelSB_64_Zone1_1.wav.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Time-Variant MVDR (NB)**<br>  <audio controls><source src="./data/audiofiles/1spk/MVDR_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (NB)** <br> <audio controls><source src="./data/audiofiles/1spk/NB_GRNNBF_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/spectorgrams/SB_64_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/MelSB_64_Zone1_1.png.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/MVDR_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/NB_GRNNBF_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **[Reference Rev. Clean] Speaker-1 (In Zone-1)**<br>  <audio controls><source src="./data/audiofiles/1spk/Ref_Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-2 (In Zone-2)** <br> <audio controls><source src="./data/audiofiles/1spk/Ref_Zone2_1" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-3 (In Zone-3)**<br>  <audio controls><source src="./data/audiofiles/1spk/Ref_Zone3_1" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-4 (In Zone-4)** <br> <audio controls><source src="./data/audiofiles/1spk/Ref_Zone4_1" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/spectorgrams/Ref_Zone1_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/Ref_Zone2_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/Ref_Zone3_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/spectorgrams/Ref_Zone4_1.png" alt="flowtron_0.0" style="zoom: 40%;" /> |



<!-- <br><br><br><br>




|       **One Available Speaker [S1]**                    | **Mixture SNR: -10 dB, PESQ: -10 dB**                         |                                                              |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture** <br><audio controls><source src="./data/audiofiles/1spk/mix_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **ConvTasNet (FB)** <br>  <audio controls><source src="./data/audiofiles/1spk/ConvTasNet_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **LSTM+Attention (FB)** <br><audio controls><source src="./data/audiofiles/1spk/LSTM_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (FB)** <br>  <audio controls><source src="./data/audiofiles/1spk/FB_GRNNBF_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **Tradition Subband (#64)**<br>  <audio controls><source src="./data/audiofiles/1spk/SB_64_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Proposed Mel-Subband (#64)** <br> <audio controls><source src="./data/audiofiles/1spk/MelSB_64_1.wav.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Time-Variant MVDR (NB)**<br>  <audio controls><source src="./data/audiofiles/1spk/MVDR_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (NB)** <br> <audio controls><source src="./data/audiofiles/1spk/NB_GRNNBF_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **[Reference Rev. Clean] Speaker-1 (In Zone-1)**<br>  <audio controls><source src="./data/audiofiles/1spk/Zone1_1.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-2 (In Zone-2)** <br> <audio controls><source src="./data/audiofiles/1spk/Zone2_1" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-3 (In Zone-3)**<br>  <audio controls><source src="./data/audiofiles/1spk/Zone3_1" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-4 (In Zone-4)** <br> <audio controls><source src="./data/audiofiles/1spk/Zone4_1" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |



<br><br><br><br>

<h2 id = "1"><u>Processed Audio Samples of Real In-Car Recordings</u></h2>

|       **Available Speakers [S1, S2, S3]**                    | **Mixture SNR: -10 dB, SER: -10 dB**                         |                                                              |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture** <br><audio controls><source src="./data/with_reverb/example275/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **ConvTasNet (FB)** <br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **LSTM+Attention (FB)** <br><audio controls><source src="./data/with_reverb/example275/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (FB)** <br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **Tradition Subband (#64)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Proposed Mel-Subband (#64)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Time-Variant MVDR (NB)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **GRNNBF (NB)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **[Reference Rev. Clean] Speaker-1 (In Zone-1)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-2 (In Zone-2)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-3 (In Zone-3)**<br>  <audio controls><source src="./data/with_reverb/example275/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Speaker-4 (In Zone-4)** <br> <audio controls><source src="./data/with_reverb/example275/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example275/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> | -->




<!-- <h3 id = "3"> case 2</h3>

|                          **case 2**                          |                                                              |                                                              |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy** <br><audio controls><source src="./data/with_reverb/example291/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/with_reverb/example291/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/with_reverb/example291/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/with_reverb/example291/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/with_reverb/example291/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/with_reverb/example291/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/with_reverb/example291/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/with_reverb/example291/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |



<h3 id = "3"> case 3</h3>

|                          **case 3**                          |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy**<br><audio controls><source src="./data/with_reverb/example5/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/with_reverb/example5/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/with_reverb/example5/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/with_reverb/example5/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/with_reverb/example5/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/with_reverb/example5/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/with_reverb/example5/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/with_reverb/example5/clean.png" alt="flowtron_0.0" style="zoom: 40%;" />** |



<h3 id = "3"> case 4</h3>

|                          **case 4**                          |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy**<br><audio controls><source src="./data/with_reverb/example63/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/with_reverb/example63/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/with_reverb/example63/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/with_reverb/example63/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/with_reverb/example63/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/with_reverb/example63/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/with_reverb/example63/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/with_reverb/example63/clean.png" alt="flowtron_0.0" style="zoom: 40%;" />** |









## Without Reverberation

<h3 id = "3"> case 1</h3>

|                          **case 1**                          |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy**<br><audio controls><source src="./data/no_reverb/example112/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/no_reverb/example112/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/no_reverb/example112/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/no_reverb/example112/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/no_reverb/example112/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/no_reverb/example112/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/no_reverb/example112/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/no_reverb/example112/clean.png" alt="flowtron_0.0" style="zoom: 40%;" />** |



<h3 id = "3"> case 2</h3>

|                          **case 2**                          |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy**<br><audio controls><source src="./data/no_reverb/example163/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/no_reverb/example163/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/no_reverb/example163/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/no_reverb/example163/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/no_reverb/example163/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/no_reverb/example163/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/no_reverb/example163/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/no_reverb/example163/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |



<h3 id = "3"> case 3</h3>

|                          **case 3**                          |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy**<br><audio controls><source src="./data/no_reverb/example82/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/no_reverb/example82/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/no_reverb/example82/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/no_reverb/example82/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/no_reverb/example82/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/no_reverb/example82/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/no_reverb/example82/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | **<img src="./data/no_reverb/example82/clean.png" alt="flowtron_0.0" style="zoom: 40%;" />** |





<h3 id = "3"> case 4</h3>

|                          **case 4**                          |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Noisy**<br><audio controls><source src="./data/no_reverb/example63/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **FullSubNet+**<br><audio controls><source src="./data/no_reverb/example63/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| **<img src="./data/no_reverb/example63/noisy.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <img src="./data/no_reverb/example63/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| **FullSubNet++**<br><audio controls><source src="./data/no_reverb/example63/fullsubnet++.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Clean**<br><audio controls><source src="./data/no_reverb/example63/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/no_reverb/example63/fullsubnet++.png" alt="flowtron_0.0" style="zoom: 40%;" /> | <img src="./data/no_reverb/example63/clean.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
 -->
