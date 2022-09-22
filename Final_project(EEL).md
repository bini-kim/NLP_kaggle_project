# Final_project-EEL-
<img width="1172" alt="스크린샷 2022-09-20 오후 6 05 35" src="https://user-images.githubusercontent.com/89832402/191216837-ac66715a-e6ff-4590-aa6d-91f05451e172.png">
<p>
    <b>Goal of the Competition</b><br>
The goal of this competition is to assess the language proficiency of 8th-12th grade English Language Learners (ELLs). Utilizing a dataset of essays written by ELLs will help to develop proficiency models that better supports all students.

Your work will help ELLs receive more accurate feedback on their language development and expedite the grading cycle for teachers. These outcomes could enable ELLs to receive more appropriate learning tasks that will help them improve their English language proficiency.
</p>

<pre>
<code>
#BASIC
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

import os
for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))
</code>
</pre>

## DATA
### 1. Import DATA
<pre>
<code>
train = pd.read_csv('../input/feedback-prize-english-language-learning/train.csv')
test = pd.read_csv('../input/feedback-prize-english-language-learning/test.csv')
submission = pd.read_csv('../input/feedback-prize-english-language-learning/sample_submission.csv')
</code>
</pre>

### TRAIN DATA
<pre>
<code>
train.head(10)
</code>
</pre>
<img width="866" alt="스크린샷 2022-09-19 오후 9 54 17" src="https://user-images.githubusercontent.com/89832402/191022013-0850ae53-d33a-4bf7-85a9-15886435efaa.png">

### TEST DATA
<pre>
<code>
test
</code>
</pre>
<img width="424" alt="스크린샷 2022-09-20 오후 6 04 14" src="https://user-images.githubusercontent.com/89832402/191216612-c25b746a-a1b8-4f45-8039-1d21f56826ba.png">

### SUBMISSION File
<pre>
<code>
submission
</code>
</pre>
<img width="565" alt="스크린샷 2022-09-20 오후 6 09 20" src="https://user-images.githubusercontent.com/89832402/191217640-10728963-ab05-4e2d-b790-ef61f36032ee.png">

### 2. EDA(train data)
#### 1) Shape
#### train data = 3911 , 8
#### test data = 3, 2
<pre>
<code>
print(train.shape, test.shape)
</code>
</pre>
(3911, 8) (3, 2)

#### 2) Train info
<pre>
<code>
#train info
train.info()
</code>
</pre>
<div>
<class 'pandas.core.frame.DataFrame'><br>
RangeIndex: 3911 entries, 0 to 3910<br>
Data columns (total 8 columns):<br>
 #   Column       Non-Null Count  Dtype<br>  
---  ------       --------------  -----<br>
 0   text_id      3911 non-null   object <br>
 1   full_text    3911 non-null   object <br>
 2   cohesion     3911 non-null   float64<br>
 3   syntax       3911 non-null   float64<br>
 4   vocabulary   3911 non-null   float64<br>
 5   phraseology  3911 non-null   float64<br>
 6   grammar      3911 non-null   float64<br>
 7   conventions  3911 non-null   float64<br>
dtypes: float64(6), object(2)<br>
memory usage: 244.6+ KB<br>
</div>    

#### 3) 6 cols have 9 data.
<pre>
<code>
train.nunique()
</code>
</pre>
<p>
text_id        3911<br>
full_text      3911<br>
cohesion          9<br>
syntax            9<br>
vocabulary        9<br>
phraseology       9<br>
grammar           9<br>
conventions       9<br>
dtype: int64
</p>
