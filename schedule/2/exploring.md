# Exploring Machine Learning with Edge Impulse
{:.no_toc}

* TOC
{:toc}

## Getting Started with Edge Impulse

1. First, create an account on Edge Impulse: [https://studio.edgeimpulse.com/signup](https://studio.edgeimpulse.com/signup)  
    <img src="/CRESTLEX3/schedule/2/ei/signup.png" alt="Edge Impulse Signup/Login Page" width="700px">
1. Validate your email by clicking the link in the email sent to your account’s email address

## Deploying Machine Learning Models to the Edge

### Hello World Keyword Spotting Model

1. Grab your phone, open up the Camera app and scan the QR code below by pointing your camera at your computer screen, then click on the link that appears on your phone:  
    <img src="/CRESTLEX3/schedule/2/ei/keyword-spotting-qr.png" alt="CRESTLEX QR code for stock keyword spotting model" width="300px">
1. Once you have scanned the QR code, your phone's web browser will appear loading the the "Data collection" web application. At the bottom of the page, click on the **Switch to classification mode** button:  
    <img src="/CRESTLEX3/schedule/2/ei/phone-data-collection.png" alt="Phone app: data collection screen" width="300px">
1. Once the project has finished building, click the **Give access to the microphone** button, then click **Allow**:  
    <img src="/CRESTLEX3/schedule/2/ei/phone-classification-mode.png" alt="Phone app: classification mode, building project" width="300px"><img src="/CRESTLEX3/schedule/2/ei/phone-permission-required.png" alt="Phone app: give access to the microphone" width="300px"><img src="/CRESTLEX3/schedule/2/ei/phone-microphone-access.png" alt="Phone app: allow microphone access" width="300px">
1. Now see the stock "Hello World" keyword spotting classifier in action!  
    <img src="/CRESTLEX3/schedule/2/ei/phone-audio-classification.png" alt="Phone app: classifying..." width="300px">
  
<details>
  <summary>Troubleshooting (Keyword Spotting)</summary>

<h4>Phone: Not connected</h4>

<img src="/CRESTLEX3/schedule/2/ei/error-connection-failed.png" alt="Edge Impulse web application, error: not connected" width="300px">  

<p>This error sometimes occurs when you leave your web browser app for a different app on your phone. Try refreshing your browser page, if that doesn't reconnect you, follow the <a href="#hello-world-keyword-spotting-model">Hello World Keyword Spotting Model</a> steps above to reconnect your phone to the Keyword Spotting classifer application.</p>

<h4>Phone: Failed to load</h4>

<img src="/CRESTLEX3/schedule/2/ei/error-failed-to-load.png" alt="Edge Impulse web application, error: failed to load" width="300px">  

<p>This error occurs when you don't give the web browser access to your microphone. Refresh your browser page and allow microphone access as seen in step 3 from the <a href="#hello-world-keyword-spotting-model">Hello World Keyword Spotting Model</a> steps above.</p>
</details>
  
### Person Detection Image Classification Model

1. Grab your phone, open up the Camera app and scan the QR code below by pointing your camera at your computer screen, then click on the link that appears on your phone:  
    <img src="/CRESTLEX3/schedule/2/ei/visual-wake-words-qr.png" alt="CRESTLEX QR code for stock person detection model" width="300px">
1. Once you have scanned the QR code, your phone's web browser will appear loading the the "Data collection" web application. At the bottom of the page, click on the **Switch to classification mode** button:  
    <img src="/CRESTLEX3/schedule/2/ei/phone-data-collection.png" alt="Phone app: data collection screen" width="300px">
1. Once the project has finished building, click the **Give access to the camera** button, then click **Allow**:  
    <img src="/CRESTLEX3/schedule/2/ei/phone-classification-mode.png" alt="Phone app: classification mode, building project" width="300px"><img src="/CRESTLEX3/schedule/2/ei/phone-camera-permission-required.png" alt="Phone app: give access to the camera" width="300px"><img src="/CRESTLEX3/schedule/2/ei/phone-camera-access.png" alt="Phone app: allow camera access" width="300px">
1. Now see the stock person detection image classifier in action!  
    <img src="/CRESTLEX3/schedule/2/ei/phone-image-classification.png" alt="Phone app: classifying..." width="300px">
  
<details>
  <summary>Troubleshooting (Person Detection)</summary>

<h4>Phone: Not connected</h4>

<img src="/CRESTLEX3/schedule/2/ei/error-connection-failed.png" alt="Edge Impulse web application, error: not connected" width="300px">  

<p>This error sometimes occurs when you leave your web browser app for a different app on your phone. Try refreshing your browser page, if that doesn't reconnect you, follow the <a href="#person-detection-image-classification-model">Person Detection Image Classification Model</a> steps above to reconnect your phone to the Keyword Spotting classifer application.</p>

<h4>Phone: Failed to load</h4>

<img src="/CRESTLEX3/schedule/2/ei/error-failed-to-load.png" alt="Edge Impulse web application, error: failed to load" width="300px">  

<p>This error occurs when you don't give the web browser access to your camera. Refresh your browser page and allow camera access as seen in step 3 from the <a href="#person-detection-image-classification-model">Person Detection Image Classification Model</a> steps above.</p>
</details>
