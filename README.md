# ml-classifier-no-common-sense

IF we can commensurate all data (lidars, radars, cameras, IMU, etc.) from an autonomous car in a sensor fusion logic, where images with digit '0' means GO and images with with digit '1' means STOP. Still, the autonomous car **will have a hard time figuring out cases it was not trained** and eventually fail at some point (that's why we don't have autonomous cars on the streets yet). The current ML as we know in 2022 is not ready ... for common-sense logic ... for critical decision making ... we need a higher level of intelligence.. a logic which combines Unsupervised + Supervised + Reinforcement learning - USRL

## Playing with the MNIST set with only digits '1' and '0' shows the big challenge for machine learning technologies

A simple classifier for digits '0' or '1' from MNIST fails to have common sense **IF the images from the training set with '1' are shifted to the left or to the right, then the classifier fails to give the correct answer** 

Here are some images from the training set:(all digits are centered to the image)

![image](https://user-images.githubusercontent.com/94204361/176938626-9458d2f9-81e1-4759-a068-60d5abd6112d.png)


### - [**Starts with basic CNN**] - All shifted '1's (either to the left or right) are classified as '0's

![image](https://user-images.githubusercontent.com/94204361/176938776-dc5457a7-0eb0-4391-9634-4f9872946f34.png)
![image](https://user-images.githubusercontent.com/94204361/176938887-92827352-f025-4fd3-ac8a-d5aa08166832.png)


### - [**Add to the classifier data augmentation**] - A few shifted '1's are correctly classified

Here are some images from the data augmentation:

![image](https://user-images.githubusercontent.com/94204361/177024994-940ecd4e-8ae0-45e7-9c99-6ccfad1eb34f.png)

A few shifted '1's are correctly classified

![image](https://user-images.githubusercontent.com/94204361/176939029-d5ccb48a-e5ff-4261-b48d-5a29a6bfba32.png)
![image](https://user-images.githubusercontent.com/94204361/176939142-01f73cdc-71a8-48e8-afc9-c214baa1d74e.png)


### - [**Add to the classifier data sugmentation + dropout**] - A few more shifted '1's are correctly classified

![image](https://user-images.githubusercontent.com/94204361/176939435-4e85a2c8-ee0f-46d0-a270-38669d1e9397.png)
![image](https://user-images.githubusercontent.com/94204361/176939471-1b1827f8-d211-41bf-a597-6463c4ccc45a.png)


- [**Change the model for a transfer learning**] - INCEPTION V3 150x150x3

All shifted images are correctly classified (there are just a few examples ~30 images)

![image](https://user-images.githubusercontent.com/94204361/177025137-a616411d-bae7-4742-ba1b-1b5b2b74eef9.png)
![image](https://user-images.githubusercontent.com/94204361/177025153-e56df60b-d88d-43fb-8517-d57565be1a43.png)

The problem is when **retesting the training set of images. The model fails when classifying some of them** ...
(This also happens in the other models)

Images of digit '1' classified as zero (from training set)

![image](https://user-images.githubusercontent.com/94204361/177025477-3db529b5-1c15-48e2-ad2c-80f722fc9ad7.png)
![image](https://user-images.githubusercontent.com/94204361/177025484-eb5ba4e2-5962-4506-ba85-e07da6c9fa3d.png)

Images of digit zero classified as '1' (from training set)

![image](https://user-images.githubusercontent.com/94204361/177059130-f2dc8999-9a0b-4a6e-9cd8-5af98332a663.png)
![image](https://user-images.githubusercontent.com/94204361/177059156-65cb9f26-e629-4df4-9be3-fab62f6a0847.png)


### Conclusion.

ML technologies are great for **non critical applications**, such as: creating art, making predictions and classification in housing markets, activity recognition, etc. However, ML in **critical decision appliations** must integrate a '**watchdog**' or **other parallel process** to **corroborate** a  live / death decision.


## For more information read the book:

### <a href="url" target="_blank">[Adding common sense to AI: The big challenge in machine learning for critical decision making](https://www.amazon.com/dp/B0BGD1MKJJ)</a>

