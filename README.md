# College Advisor Machine Learning 
[Link to PDF](Final%20Report%20(Team%20%231).pdf)
College Admission Advisor (CAA) is a data application designed to help students discover colleges and their neighborhoods across the United States. 

**Motivation:**
Higher education provides numerous benefits to individuals as well as to society. It is not only associated with higher income levels and better employment opportunities, but also plays a key role in the nation’s economic growth and social prosperity. With great opportunities come great challenges as prospective students start their journey to find the perfect school. 
On the path to securing college admission, students consider various aspects such as: fields of study, college ranking, study costs, location and cost of living. In this project, we aim to help students by developing a tool that collects, analyzes and visualizes critical college related data. This application will allow students to gauge how quantitative factors (SAT, GRE and GPA) is perceived by different colleges and help them make informed decisions to improve their admission chances.

**Goal:**
Develop a web-based data application to assist prospective students in finding the right school by examining college admission and location data in the United States.
Software Architecture:

**Application Components:**

**Google Firestore Cloud Database**:
Our first dataset is of colleges admissions data. the data was exported from IPEDS, the Integrated Postsecondary Education Data System. A cloud database has been setup on Firestore to maintain and manage application data (colleges dataset). 

**Numbeo API:**
Our second data source is Numbeo, a crowd-sourced global database of quality-of-life information. It is used to support our college admission data and provide general city information, such as, housing indicators, perceived crime rates, and quality of healthcare, among others. The data is fetched on demand utilizing Numbeo API through an academic license.

**Flask Web Service:**
A web service was created to connect the frontend with the data sources. It is aimed to fetch the data from both data sources and export it to the frontend ready to be displayed and visualized.

**Machine Learning Model:**
A Machine Learning model was developed to provide college recommendations based on a student’s academic standing. The model was developed using Scikit-learn package to conduct unsupervised learning and cluster out colleges by their standard exam scores (SAT and ACT) and their acceptance rate.
The model input includes standardized test scores (SAT and ACT), and the acceptance (a calculated value from dividing total admissions over total applicants), the lower the rate the more competitive a college’s admission. For example, if the acceptance rate of USC is 10%, it assumes students who are top 10% or exceed 90% of all applicants in academic performance and other backgrounds could get offers from USC. The measure of academic performance and backgrounds for undergraduate students is usually based on their GPA, AP, research or leadership experience, academic awards, and scholarships. Therefore, by calculating a student’s acceptance rate using the five factors, we could get an acceptance rate number which matches a ML cluster combined with his SAT or ACT score.

In order to build a ML model, first, by preprocessing the raw data, we standardized all inputs, such as replacing the blank values. Second, we normalized the data into range 0 to 1 by min-max scaler for better clustering. Also, we used K-means clustering (figure 1) and decided the cluster number 7 by the elbow method (figure 2). Finally, we built a ML model and saved the model locally for a faster operation.

https://drive.google.com/drive/folders/12PYv3KM0sIuOvpxbKmWIhCybd9ca-fw_?usp=sharing
