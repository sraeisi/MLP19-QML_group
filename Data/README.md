Quantum Machine Learning Project
====

Data size was bigger than 25MB so it couldn't be uploaded on github, you can find the data on dropbox :

Data is a pandas DataFrame which should be imported via :

url = 'https://www.dropbox.com/s/zapb2jjm0ihp14a/data.gz?dl=1'

s=requests.get(url, stream=True).content

data=pd.read_pickle(io.BytesIO(s) , compression='gz')


DataFrame contains 500,000 records of random density matrices and contains following fields:

- 15 features for the density matrix, which is feature_i,j = tr(\rho * (sigma_i \ sigma_j)) where sigma_4 = I the identity operator,
and sigma_1 = sigma_x , sigma_2 = sigma_y , sigma_3 = sigma_z are the pauli matrices.

- the PPT criterion, which is the determinant of the partial transpose of the bi-partite system. The PPT criterion says that if this value is negative, then the density matrix is entangled and if positive, then it is seprable.

- the binary class of these matrices, where label '1' is for entangled matrices where '0' denotes the class of seprable matrices.

- in the Attached ".ipynb" File Ive **Prepared the Data** & **Data Analysis** & _Regression Methods_ or _Classification Methods_ to Analyse and Classifiy 
the **_Entagled_**  States over **_Separable_** States .

- Over Quite Some time that I ve run some Codes 
I think the **Decision Tree Regressor** can Provide a good Classification of Entangled States over Separable ones .

- Data is  Stored in a ".npy" Format which Contains 100000 Samples.
in order to successfully run the Code you need to put all of ".npy" Files in the Same Directory as the Code
or Generate your own Data (Which Will take a Longer Time to Run) 

- there is one Issue about the Data , which is that the Distribution Function of Features in  Denstiy Matrixes (Created by qutip) 
are not Symmetrical (Distribution Function changes when you Measure in  Z axis in relate to X axis or Y axis
 )


----
The code is jupyter notebook using python3 kernel.

The required packages to run the code are:

numpy

scipy

pandas

matplotlib

qutip

scikit-learn

Cython
