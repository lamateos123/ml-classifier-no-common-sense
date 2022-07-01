# ml-classifier-no-common-sense

Shows the big challenge for machine learning technologies

A simple classifier for digits '0' or '1' from MNIST fails to have common sense **IF the images from the training set with '1' are shifted to the left or to the right, then the classifier fails to give the correct answer** 

Here are some images from the training set (all digits are centered to the image and were correctly classified as '0's and '1's)
![image](https://user-images.githubusercontent.com/94204361/176938626-9458d2f9-81e1-4759-a068-60d5abd6112d.png)


- [**Starts with basic CNN**] - All shifted '1's (either to the left or right) are classified as '0's

![image](https://user-images.githubusercontent.com/94204361/176938776-dc5457a7-0eb0-4391-9634-4f9872946f34.png)
![image](https://user-images.githubusercontent.com/94204361/176938887-92827352-f025-4fd3-ac8a-d5aa08166832.png)


- [**Add to the classifier data augmentation**] - A few shifted '1's are correctly classified

![image](https://user-images.githubusercontent.com/94204361/176939029-d5ccb48a-e5ff-4261-b48d-5a29a6bfba32.png)
![image](https://user-images.githubusercontent.com/94204361/176939142-01f73cdc-71a8-48e8-afc9-c214baa1d74e.png)


- [**Add to the classifier data sugmentation + dropout**] - A few more shifted '1's are correctly classified

![image](https://user-images.githubusercontent.com/94204361/176939435-4e85a2c8-ee0f-46d0-a270-38669d1e9397.png)
![image](https://user-images.githubusercontent.com/94204361/176939471-1b1827f8-d211-41bf-a597-6463c4ccc45a.png)


- [**Change the model for a transfer learning**] - TBD


### Conclusion.

IF we can commensurate all data (lidars, radars, cameras, IMU, etc.) from an autonomous car in a sensor fusion logic, where images with digit '0' means GO and images with with digit '1' means STOP. Still, the autonomous car **will have a hard time figuring out cases it was not trained** and eventually fail at some point (that's why we don't have autonomous cars on the streets yet). The current ML as we know in 2022 is not ready ... for common-sense logic ... for critical decision making ... we need a higher level of intelligence.. a logic which combines Unsupervised + Supervised + Reinforcement learning - USRL
