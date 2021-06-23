# *Build it!* Creating your own application with Edge Impulse
{:.no_toc}

* TOC
{:toc}

Yesterday we analyzed a pre-trained keyword spotting model using the keyword "hello world" with audio samples uploaded from a small set of participants. Today we will see how machine learning becomes even more powerful when we train a model with it's potential biases in mind, such as the tone, pitch, accent, or even the language of the keyword itself.

## Creating a Crowdsourced Keyword Dataset

1. Grab your phone, open up the Camera app and scan the QR code below by pointing your camera at your computer screen, then click on the link that appears on your phone:  
    <img src="/CRESTLEX3/schedule/3/ei/30s_yaateeh_11KHz.png" alt="CRESTLEX QR code for crowd-sourced keyword collection" width="300px">
1. Your phone's web browser should open and connect successfully to the keyword collector application for our custom model:  
    <img src="/CRESTLEX3/schedule/3/ei/keyword-collector.png" alt="Keyword Collector" width="300px">
1. Click **Get started!** and give your phone's web browser access to your microphone by clicking **Allow**:  
    <img src="/CRESTLEX3/schedule/3/ei/kc-microphone-access.png" alt="Keyword Collector microphone access" width="300px">
1. Wait for audio recording to begin for a couple of seconds:  
    <img src="/CRESTLEX3/schedule/3/ei/kc-waiting.png" alt="Keyword Collector waiting to record" width="300px">
1. Once audio recording begins, repeat the keyword **"yáʼátʼééh"** over and over into your phone's microphone, leaving a pause of space between each iteration:  
    <img src="/CRESTLEX3/schedule/3/ei/kc-recording-data.png" alt="Keyword Collector recording data" width="300px">
1. Your keyword samples should now be successfully uploaded to the group's shared Edge Impulse Custom Keyword Spotting project!  
  
<details>
  <summary>Troubleshooting (Keyword Collection)</summary>

<h4>Phone: TypeError</h4>

<img src="/CRESTLEX3/schedule/3/ei/kc-failed-type-error.png" alt="Keyword Collector TypeError" width="300px"><img src="/CRESTLEX3/schedule/3/ei/kc-failed-empty-array.png" alt="Keyword Collector TypeError: empty array" width="300px">  

<p>These errors usually occur when you have switched applications on your phone mid-recording (for example, by swiping up and leaving the web browser), or you have lost connection to the internet. Try re-scanning the QR code from step 1 from the <a href="#creating-a-crowdsourced-keyword-dataset">Creating a Crowdsourced Keyword Dataset</a> steps above and re-recording your keyword samples.</p>
</details>
  
## Deploy a Custom Keyword Spotting Model

Now that we have collected our crowdsourced dataset and designed/trained our custom keyword spotting model, we can deploy this model to our phones for keyword spotting on the edge in real time.

**Note:** While Edge Impulse does allow you to deploy a trained model to any device via the QR code on the "Devices" tab (without needing to create an Edge Impulse account), today we are going to go through the steps required to create and build a project on your own Edge Impulse account for your future use!

1. Login to your Edge Impulse account: [https://studio.edgeimpulse.com/](https://studio.edgeimpulse.com/)  
1. Clone the CRESTLEX custom keyword spotting project to your own Edge Impulse account. Click the following link and then click the **Clone this project** button on the top right corner of the page: [https://studio.edgeimpulse.com/public/35699/latest](https://studio.edgeimpulse.com/public/35699/latest)  
    <img src="/CRESTLEX3/schedule/3/ei/clone-button.png" alt="Clone this project button" width="300px">
1. Change the name of your cloned project if you would like, then click the green **Clone this project** button:  
    <img src="/CRESTLEX3/schedule/3/ei/clone-this-project.png" alt="Clone this project dialog box" width="500px">
1. When the studio has finished cloning the project, select the "Devices" tab and click the **Connect a new device** button:  
    <img src="/CRESTLEX3/schedule/3/ei/devices.png" alt="Devices tab" width="700px">  
    <img src="/CRESTLEX3/schedule/3/ei/new-device-button.png" alt="Connect a new device button" width="300px">
1. From the "Collect data" pop-up box, click on the **Show QR code** button next to "Use your mobile phone":  
    <img src="/CRESTLEX3/schedule/3/ei/collect-data.png" alt="Collect data pop-up box" width="600px">
1. Grab your phone, open up the Camera app and scan the QR code that was generated for you by pointing your camera at your computer screen. An example of the QR code is shown below (this QR code is blurred out and unusable):  
    <img src="/CRESTLEX3/schedule/3/ei/collect-data-qr-code-blurred.png" alt="Collect data QR code box" width="600px">
1. Once you have scanned the QR code, your phone's web browser will appear loading the the "Data collection" web application. At the bottom of the page, click on the **Switch to classification mode** button:  
    <img src="/CRESTLEX3/schedule/3/ei/phone-data-collection.png" alt="Phone app: data collection screen" width="300px">
1. Once the project has finished building, click the **Give access to the microphone** button, then click **Allow**:  
    <img src="/CRESTLEX3/schedule/3/ei/phone-classification-mode.png" alt="Phone app: classification mode, building project" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-permission-required.png" alt="Phone app: give access to the microphone" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-microphone-access.png" alt="Phone app: allow microphone access" width="300px">
1. Now see our custom keyword spotting classifier in action!  
    <img src="/CRESTLEX3/schedule/3/ei/phone-audio-classification.png" alt="Phone app: classifying..." width="300px">
  
<details>
  <summary>Troubleshooting (Keyword Spotting)</summary>

<h4>Phone: Not connected</h4>

<img src="/CRESTLEX3/schedule/3/ei/error-connection-failed.png" alt="Edge Impulse web application, error: not connected" width="300px">  

<p>This error sometimes occurs when you leave your web browser app for a different app on your phone. Try refreshing your browser page, if that doesn't reconnect you, follow steps 5 through 8 from the <a href="#deploy-a-custom-keyword-spotting-model">Deploy a Custom Keyword Spotting Model</a> steps above to reconnect your phone to your Edge Impulse project.</p>

<h4>Phone: Failed to load</h4>

<img src="/CRESTLEX3/schedule/3/ei/error-failed-to-load.png" alt="Edge Impulse web application, error: failed to load" width="300px">  

<p>This error occurs when you don't give the web browser access to your microphone. Refresh your browser page and allow microphone access as seen in step 9 from the <a href="#deploy-a-custom-keyword-spotting-model">Deploy a Custom Keyword Spotting Model</a> steps above.</p>
</details>
  
## Deploy a Custom Image Classification Model

Similarly to the custom keyword spotting model, we can also create a personalized version of the person detection image classification model we saw yesterday.

1. Clone the person detection project to your own Edge Impulse account. Click the following link and then click the **Clone this project** button on the top right corner of the page: [https://studio.edgeimpulse.com/public/37001/latest](https://studio.edgeimpulse.com/public/37001/latest)  
    <img src="/CRESTLEX3/schedule/3/ei/clone-button.png" alt="Clone this project button" width="300px">
1. Change the name of your cloned project if you would like, then click the green **Clone this project** button:  
    <img src="/CRESTLEX3/schedule/3/ei/clone-this-project-person-detection.png" alt="Clone this project dialog box" width="500px">
1. When the studio has finished cloning the project, select the "Devices" tab and click the **Connect a new device** button:  
    <img src="/CRESTLEX3/schedule/3/ei/devices.png" alt="Devices tab" width="700px">  
    <img src="/CRESTLEX3/schedule/3/ei/new-device-button.png" alt="Connect a new device button" width="300px">
1. From the "Collect data" pop-up box, click on the **Show QR code** button next to "Use your mobile phone":  
    <img src="/CRESTLEX3/schedule/3/ei/collect-data.png" alt="Collect data pop-up box" width="600px">
1. Grab your phone, open up the Camera app and scan the QR code that was generated for you by pointing your camera at your computer screen. An example of the QR code is shown below (this QR code is blurred out and unusable):  
    <img src="/CRESTLEX3/schedule/3/ei/collect-data-qr-code-blurred.png" alt="Collect data QR code box" width="600px">
1. Once you have scanned the QR code, your phone's web browser will appear loading the the "Data collection" web application. Now start taking new images with the labels "person" and "non_person", click the **Collecting images?** button and wait for the Data collection application to load, and give access to the camera:  
    <img src="/CRESTLEX3/schedule/3/ei/phone-data-collection.png" alt="Phone app: data collection screen" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-dc-camera-permission-required.png" alt="Phone app: give access to the camera" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-dc-camera-access.png" alt="Phone app: allow camera access" width="300px">
1. Click on the **Label: unknown** button to change the label to "person" or "non_person" depending on the image that are you are taking, this will automatically upload your new images to your Edge Impulse person detection project:  
    <img src="/CRESTLEX3/schedule/3/ei/phone-capture-image.png" alt="Phone app: image collection" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-image-label.png" alt="Phone app: change image label" width="300px">
1. Open up your Edge Impulse project on your computer, since the model has already been trained before, and all we have done is added new data, click on the "Retrain model" tab, then click on the green **Train model** button.  
    <img src="/CRESTLEX3/schedule/3/ei/retrain-model-tab.png" alt="Retrain model tab" width="300px">  
    <img src="/CRESTLEX3/schedule/3/ei/retrain-model-page.png" alt="Retrain model page" width="600px">
1. Now wait for your project to finish building and training.
1. To deploy your newly trained model onto your phone, select the "Devices" tab again and click the **Connect a new device** button:  
    <img src="/CRESTLEX3/schedule/3/ei/devices.png" alt="Devices tab" width="700px">  
    <img src="/CRESTLEX3/schedule/3/ei/new-device-button.png" alt="Connect a new device button" width="300px">
1. From the "Collect data" pop-up box, click on the **Show QR code** button next to "Use your mobile phone":  
    <img src="/CRESTLEX3/schedule/3/ei/collect-data.png" alt="Collect data pop-up box" width="600px">
1. Grab your phone, open up the Camera app and scan the QR code that was generated for you by pointing your camera at your computer screen. An example of the QR code is shown below (this QR code is blurred out and unusable):  
    <img src="/CRESTLEX3/schedule/3/ei/collect-data-qr-code-blurred.png" alt="Collect data QR code box" width="600px">
1. Once you have scanned the QR code, your phone's web browser will appear loading the the "Data collection" web application. At the bottom of the page, click on the **Switch to classification mode** button:  
    <img src="/CRESTLEX3/schedule/3/ei/phone-data-collection.png" alt="Phone app: data collection screen" width="300px">
1. Once the project has finished building, click the **Give access to the camera** button, then click **Allow**:  
    <img src="/CRESTLEX3/schedule/3/ei/phone-classification-mode.png" alt="Phone app: classification mode, building project" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-camera-permission-required.png" alt="Phone app: give access to the camera" width="300px"><img src="/CRESTLEX3/schedule/3/ei/phone-camera-access.png" alt="Phone app: allow camera access" width="300px">
1. Now see your custom person detection image classifier in action!  
    <img src="/CRESTLEX3/schedule/3/ei/phone-image-classification.png" alt="Phone app: classifying..." width="300px">
  
<details>
  <summary>Troubleshooting (Image Classification)</summary>

<h4>Phone: Not connected</h4>

<img src="/CRESTLEX3/schedule/2/ei/error-connection-failed.png" alt="Edge Impulse web application, error: not connected" width="300px">  

<p>This error sometimes occurs when you leave your web browser app for a different app on your phone. Try refreshing your browser page, if that doesn't reconnect you, follow the <a href="#deploy-a-custom-image-classification-model">Deploy a Custom Image Classification Model</a> steps above to reconnect your phone to the Keyword Spotting classifer application.</p>

<h4>Phone: Failed to load</h4>

<img src="/CRESTLEX3/schedule/2/ei/error-failed-to-load.png" alt="Edge Impulse web application, error: failed to load" width="300px">  

<p>This error occurs when you don't give the web browser access to your camera. Refresh your browser page and allow camera access (steps above: <a href="#deploy-a-custom-image-classification-model">Deploy a Custom Image Classification Model</a>).</p>
</details>

