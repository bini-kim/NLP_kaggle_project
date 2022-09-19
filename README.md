# Final_project-EEL-

<pre>
<code>
#SETTING
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
### Import DATA
<pre>
<code>
train = pd.read_csv('../input/feedback-prize-english-language-learning/train.csv')
test = pd.read_csv('../input/feedback-prize-english-language-learning/test.csv')
submission = pd.read_csv('../input/feedback-prize-english-language-learning/sample_submission.csv')
</code>
</pre>

### Train DATA
<pre>
<code>
train.head(10)
</code>
</pre>
