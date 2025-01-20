# Assignment Project.
<br>
Author: Rana Ahamed.
<br>
Task 1: Use the scattered plot with (X: Age), (Y: Fare) and provide different colors for male survived and female survived.
<br>
Task 2: Create 2 subplots for male and female passengers who survived. Visualize the age histogram for each plot.
<br>
(Using the titanic data.)


import numpy as np
import pandas as pd
import matplotlib.pyplot as plt


df = pd.read_csv("titanic.csv")
#print(df)
print(df.shape)

#Task-1
survived = df[df["Survived"] == 1]
male_survived = survived[survived["Sex"] == "male"]
female_survived = survived[survived["Sex"] == "female"]

plt.scatter(male_survived['Age'], male_survived['Fare'], color='r', label='Male Survived')
plt.scatter(female_survived['Age'], female_survived['Fare'], color='b', label='Female Survived')

plt.title('Scatter Plot of Age vs. Fare (Survived Passengers)')
plt.xlabel('Age')
plt.ylabel('Fare')
plt.legend()


plt.show()

#Task-2
plt.subplot(1, 2, 1)
plt.hist(male_survived["Age"], color = "r")
plt.title("Age Histogram for Male Survivors")
plt.xlabel("Age")
plt.ylabel("Frequency")

plt.subplot(1, 2, 2)
plt.hist(female_survived["Age"], color = "b")
plt.title("Age Histogram for Female Survivors")
plt.xlabel("Age")
plt.ylabel("Frequency")

plt.tight_layout()
plt.show()