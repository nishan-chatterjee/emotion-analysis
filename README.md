# emotion-analysis

**Description: Emotion Analysis of stuff?**

**List the relative path of the dataset:**


```python
import os
root_dir = "."
file_set = []

for dir_, _, files in os.walk(root_dir):
    for file_name in files:
        if file_name.endswith(".csv"):
            rel_dir = os.path.relpath(dir_, root_dir)
            rel_file = os.path.join(rel_dir, file_name)
            file_set.append("./" + str(rel_file))
print(file_set)
```

    ['././dataframe.csv', './UCI_ML_Drug_Review_dataset/drugsComTest_raw.csv', './UCI_ML_Drug_Review_dataset/drugsComTrain_raw.csv']


**Load datasets**


```python
import pandas as pd

df_test = pd.read_csv("./UCI_ML_Drug_Review_dataset/drugsComTest_raw.csv")
df_train = pd.read_csv("./UCI_ML_Drug_Review_dataset/drugsComTrain_raw.csv")

df_test.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>uniqueID</th>
      <th>drugName</th>
      <th>condition</th>
      <th>review</th>
      <th>rating</th>
      <th>date</th>
      <th>usefulCount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>163740</td>
      <td>Mirtazapine</td>
      <td>Depression</td>
      <td>"I&amp;#039;ve tried a few antidepressants over th...</td>
      <td>10</td>
      <td>28-Feb-12</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>206473</td>
      <td>Mesalamine</td>
      <td>Crohn's Disease, Maintenance</td>
      <td>"My son has Crohn&amp;#039;s disease and has done ...</td>
      <td>8</td>
      <td>17-May-09</td>
      <td>17</td>
    </tr>
    <tr>
      <th>2</th>
      <td>159672</td>
      <td>Bactrim</td>
      <td>Urinary Tract Infection</td>
      <td>"Quick reduction of symptoms"</td>
      <td>9</td>
      <td>29-Sep-17</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>39293</td>
      <td>Contrave</td>
      <td>Weight Loss</td>
      <td>"Contrave combines drugs that were used for al...</td>
      <td>9</td>
      <td>5-Mar-17</td>
      <td>35</td>
    </tr>
    <tr>
      <th>4</th>
      <td>97768</td>
      <td>Cyclafem 1 / 35</td>
      <td>Birth Control</td>
      <td>"I have been on this birth control for one cyc...</td>
      <td>9</td>
      <td>22-Oct-15</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>



**Create Random List of 15 to start annotation**


```python
random_list = df_test.sample(n=15)
random_list.to_csv (r'seed_test_dataset.csv', index = False, header=True)
random_list.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>uniqueID</th>
      <th>drugName</th>
      <th>condition</th>
      <th>review</th>
      <th>rating</th>
      <th>date</th>
      <th>usefulCount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6908</th>
      <td>32104</td>
      <td>Wellbutrin XL</td>
      <td>Major Depressive Disorde</td>
      <td>"Helped better than any other antidepressant I...</td>
      <td>6</td>
      <td>4-Nov-14</td>
      <td>59</td>
    </tr>
    <tr>
      <th>21896</th>
      <td>224119</td>
      <td>Budesonide</td>
      <td>Asthma, Maintenance</td>
      <td>"I have developed irritation of the throat and...</td>
      <td>2</td>
      <td>15-Sep-11</td>
      <td>22</td>
    </tr>
    <tr>
      <th>51002</th>
      <td>28132</td>
      <td>Lexapro</td>
      <td>Generalized Anxiety Disorde</td>
      <td>"Ok so a bit of backstory. I have had anxiety ...</td>
      <td>7</td>
      <td>4-Sep-15</td>
      <td>25</td>
    </tr>
    <tr>
      <th>53023</th>
      <td>26323</td>
      <td>Sprintec</td>
      <td>Endometriosis</td>
      <td>"I just start this pills this month and start ...</td>
      <td>6</td>
      <td>26-Dec-15</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10294</th>
      <td>165354</td>
      <td>Ethinyl estradiol / folic acid / levonorgestrel</td>
      <td>Birth Control</td>
      <td>"There are few good things with this birth con...</td>
      <td>7</td>
      <td>25-Mar-15</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>



**Annotation Guidelines**

**Link to Google Sheets For Annotation**

**Nishan's Worksheet:** https://docs.google.com/spreadsheets/d/16etO8GdeQBuGnyusqhDqqGwotmn6T8p0INM7b_YBKBo/edit?usp=sharing

**Isabelle's Worksheet:** https://docs.google.com/spreadsheets/d/1a9KmTZwXzDtnM8xvJ3e7AY4ApfngiNC2ibohnTCP71U/edit?usp=sharing*
