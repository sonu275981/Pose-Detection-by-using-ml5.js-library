
# Pose Detection in the Browser: PoseNet Model

Run real-time pose estimation in the browser using TensorFlow.js.
PoseNet can be used to estimate either a single pose or multiple poses, meaning there is a version of the algorithm that can detect only one person in an image/video and one version that can detect multiple persons in an image/video.

This is a Pure Javascript implementation of PoseNet. Thank you TensorFlow.js for your flexible and intuitive APIs.




  
## Installation

You can use this as standalone es5 bundle like this:

```bash
  <script src="https://unpkg.com/@tensorflow/tfjs"></script>
  <script src="https://unpkg.com/@tensorflow-models/posenet"></script>
```
Or you can install it via npm for use in a TypeScript / ES6 project.

~~~bash
npm install @tensorflow-models/posenet
~~~


  ## Usage

Either a single pose our multiple poses can be estimated from an image. Each methodology has its own algorithm and set of parameters.



| Id             | Part                                                                |
| ----------------- | ------------------------------------------------------------------ |
| 0 | nose |
| 1 | leftEye |
| 2 | rightEye |
| 3 | leftEar |
| 4 | rightEar |
| 5 | leftShoulder |
| 6 | rightShoulder |
| 7 | leftElbow |
| 8 | rightElbow |
| 9 | leftWrist |
| 10 | rightWrist |
| 11 | leftHip |
| 12 | rightHip |
| 13 | leftKnee |
| 14 | rightKnee |
| 15 | leftAnkle |
| 16 | rightAnkle |

## Single-Person Pose Estimation

Single pose estimation is the simpler and faster of the two algorithms. Its ideal use case is for when there is only one person in the image. The disadvantage is that if there are multiple persons in an image, keypoints from both persons will likely be estimated as being part of the same single pose—meaning, for example, that person #1’s left arm and person #2’s right knee might be conflated by the algorithm as belonging to the same pose.

### Inputs

- #### image
ImageData|HTMLImageElement|HTMLCanvasElement|HTMLVideoElement The input image to feed through the network.

- #### imageScaleFactor 
A number between 0.2 and 1.0. Defaults to 0.50. What to scale the image by before feeding it through the network. Set this number lower to scale down the image and increase the speed when feeding through the network at the cost of accuracy.

- #### flipHorizontal 
Defaults to false. If the poses should be flipped/mirrored horizontally. This should be set to true for videos where the video is by default flipped horizontally (i.e. a webcam), and you want the poses to be returned in the proper orientation.

- #### outputStride 
the desired stride for the outputs when feeding the image through the model. Must be 32, 16, 8. Defaults to 16. The higher the number, the faster the performance but slower the accuracy, and visa versa.


#### Returns
It returns a `pose` with a confidence score and an array of keypoints indexed by part id, each with a score and position.


## Developing the Model for demos
Details for how to run the model are included in the folder.
if anything worng please correct me.

## Credits
Credits for this code go to Google



  



  