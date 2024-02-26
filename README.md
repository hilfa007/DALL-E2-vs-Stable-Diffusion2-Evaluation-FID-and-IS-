<H3><b>A comparative Exploration of DALL-E-2 and Stable-Diffusion-2 based on the Frechet Inception Distance (FID) and Inception Score (IS)</b></H3>
<Big><b>DALL-E-2</b></Big><br>
DALL-E 2 is an image generation system created by OpenAI which can
generate high-resolution images that combine various concepts and art styles.
The project was built in PyTorch using ViT-H/16 text encounters with the
training data of 650M images scraped from the internet and aligned by
CLIP<br>
<Big><b>Stable-Diffusion-2</b></Big><br>
The Stable Diffusion 2.0 release includes robust text-to-image models trained using a brand new text encoder (OpenCLIP), developed by LAION with support from Stability AI, which greatly improves the quality of the generated images compared to earlier V1 releases. The text-to-image models in this release can generate images with default resolutions of both 512x512 pixels and 768x768 pixels. These models are trained on an aesthetic subset of the LAION-5B dataset created by the DeepFloyd team at Stability AI, which is then further filtered to remove adult content using LAION’s NSFW filter.<br>

<Big><b>Frechet Inception Distance(FID) Calculation:</b></Big><br>
To obtain the FID score first, preprocess the real and generated images.
Then, extract features from these images utilizing the Inception-v3 model.
After obtaining the features, calculate the FID score by computing the mean
and covariance matrices of the features and then using these matrices to de-
termine the distance between the distributions of real and generated images.<br>
FID = ∥μreal − μgenerated||2 + T r(∑ real + ∑ generated − 2(∑ real ∑ generated)1/2)
<br>
\item μreal and μgenerated are the mean feature representations of real and
generated images<br>
\item Σreal and Σgenerated are the covariance matrices of real and gener-ated image features<br>
\item Tr denotes the trace operation<br>

