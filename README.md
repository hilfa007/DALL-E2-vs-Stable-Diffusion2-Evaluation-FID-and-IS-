![image](https://github.com/hilfa007/DALL-E2-vs-Stable-Diffusion2-Evaluation-FID-and-IS-/assets/88790993/8eda879d-e46b-4bde-a32f-168fdee6e04b)




<H3><b>A comparative Exploration of DALL-E-2 and Stable-Diffusion-2 based on the Frechet Inception Distance (FID) and Inception Score (IS)</b></H3>
<Big><b><u>DALL-E-2</u></b></Big><br>
DALL-E 2 is an image generation system created by OpenAI which can
generate high-resolution images that combine various concepts and art styles.
The project was built in PyTorch using ViT-H/16 text encounters with the
training data of 650M images scraped from the internet and aligned by
CLIP<br>
<Big><b><u>Stable-Diffusion-2</u></b></Big><br>
The Stable Diffusion 2.0 release includes robust text-to-image models trained using a brand new text encoder (OpenCLIP), developed by LAION with support from Stability AI, which greatly improves the quality of the generated images compared to earlier V1 releases. The text-to-image models in this release can generate images with default resolutions of both 512x512 pixels and 768x768 pixels. These models are trained on an aesthetic subset of the LAION-5B dataset created by the DeepFloyd team at Stability AI, which is then further filtered to remove adult content using LAION’s NSFW filter.<br>

<Big><b><u>Frechet Inception Distance(FID) Calculation:</u></b></Big><br>
To obtain the FID score first, preprocess the real and generated images.
Then, extract features from these images utilizing the Inception-v3 model.
After obtaining the features, calculate the FID score by computing the mean
and covariance matrices of the features and then using these matrices to de-
termine the distance between the distributions of real and generated images.<br>
FID = ∥μreal − μgenerated||2 + T r(∑ real + ∑ generated − 2(∑ real ∑ generated)1/2)
<br>
 • μreal and μgenerated are the mean feature representations of real and
generated images<br>
 • Σreal and Σgenerated are the covariance matrices of real and generated image features<br>
 • Tr denotes the trace operation<br>

<Big><b><u>Inception Score(IS) Calculation:</u></b></Big><br>
Utilize the Inception-v3 model to generate predictions
for the generated images. The predictions are then aggregated and used to
compute the entropy of the distribution. This process is repeated multiple
times to obtain a stable estimate of the IS. Finally, the mean and standard
deviation of the IS are calculated.<br>
IS = exp(Ex[KL(p(y | x) ∥∥ p(y))]) <br>
• p(y|x) is the conditional class probability given a generated image<br>
• x, p(y) is the marginal class probability<br>
• KL denotes the Kullback-Leibler divergence.<br>

<h6><b><u>Evaluation Result on the Selected Prompts</u></b></h6>
![image](https://github.com/hilfa007/DALL-E2-vs-Stable-Diffusion2-Evaluation-FID-and-IS-/assets/88790993/030a1d20-e888-4e05-bcbf-a10825258f56)

<h6><b><u>Final Results:</u></b></h6>
![image](https://github.com/hilfa007/DALL-E2-vs-Stable-Diffusion2-Evaluation-FID-and-IS-/assets/88790993/d3f0948d-de0b-410d-8136-839d7a173c7a)
