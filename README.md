# Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning

Objective:
Process an image of the user's drawings and predict the possibility of Parkinson's disease.

This study involved applying multiple machine learning models to the data and then using the random forest method to predict.
The difference between the actual drawn shape and the main shape is saved in a CSV file stored in alldata.csv in Maincode Folder.
The CSV file is then used for predictive modeling in MachineLearning.ipynb to predict the outcome.
After testing, we have found that the solution provides promising results with a prediction accuracy of 74 percent and a precision of 90 percent. 

Details:
The data is collected from fc.unesp.br website. This data is collected at Botucatu Medical School, São Paulo State University - Brazil. 


The major assignment is filling up a form of four spirals and four meanders, cut out, and saved as a "jpg" image. Here are a few examples drawn from the dataset:

![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/023a8fcb-eb37-4b06-a2ca-44e7cff6fdeb)
![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/694a4373-e902-471b-bf7e-4c39ad45f7c7)
![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/29d480dd-3f68-4478-a2ae-b9e6b8708e14)

The dataset contains 92 individuals, divided into 18 healthy people (Healthy Group) and 74 patients (Patients Group).
Healthy Group: 6 male and 12 female individuals aged 19 to 79.
Patient Group: 59 male and 15 female individuals aged 38 to 78.
The dataset contains 526 images of healthy people and 947 of Parkinson's diagnosed patients.


After loading, the image looks like as follows:

![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/7b0231dd-2824-48b5-a234-67aad44ef4f6)

After loading the image, we find the hand-drawn part in the image using the lower and upper HSV bounds of the color. The mask was generated using the HSV values used to find the contours drawn in the picture.

![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/7a746e52-8bac-4e06-b60f-89cca305b71b)

The contour values are then divided into small parts to find the displacement and the distance covered. 

![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/7a22482e-8f11-4462-8514-cfc73309d900)

After getting the breakup points, the code calculates the contour length in the two points and the displacement between the points. And then calculates the ratio of the distance. We are dividing a single contour into 30 parts. And then, save the data in a CSV file with the label on it. 



Data saved in the CSV file then go for the preprocessing, and the following steps are implemented (MachineLearning.ipynb):
1.	Missing value Handling 
2.	Outlier detection and removal
3.	Feature Scaling 
4.	Label Encoding
5.	Modeling
6.	Saving the best accuracy model


GUI – Interface

![image](https://github.com/nikhilbaad1/Parkinson-Disease-Pre-Screening-using-Image-Processing-and-Machine-Learning/assets/47523576/0392a7ed-87dc-44a8-87d8-caf4cc0cbcc6)
Designed a simple and easy-to-use GUI using the pyqt5 Library. 

Random Forest:  This model gave us the reliable 
Results: 
Train set Accuracy: 74.81%
Test set Accuracy: 72.68%
Accuracy – 74.12%
Precision – 90.1%
Recall – 70.5%
