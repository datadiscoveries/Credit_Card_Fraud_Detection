```python
# data has already been aggregated, cleaned and transformed, and column headers are masked to hide identifying information

# read in credit card transaction data
import pandas as pd
df = pd.read_csv('C:\\Users\\todda\\Desktop\\Desktop\\Career General\\My Companies\\BlockWatch\\credit_fraud_detection\\creditcard.csv')
df
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
      <th>Time</th>
      <th>V1</th>
      <th>V2</th>
      <th>V3</th>
      <th>V4</th>
      <th>V5</th>
      <th>V6</th>
      <th>V7</th>
      <th>V8</th>
      <th>V9</th>
      <th>...</th>
      <th>V21</th>
      <th>V22</th>
      <th>V23</th>
      <th>V24</th>
      <th>V25</th>
      <th>V26</th>
      <th>V27</th>
      <th>V28</th>
      <th>Amount</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.0</td>
      <td>-1.359807</td>
      <td>-0.072781</td>
      <td>2.536347</td>
      <td>1.378155</td>
      <td>-0.338321</td>
      <td>0.462388</td>
      <td>0.239599</td>
      <td>0.098698</td>
      <td>0.363787</td>
      <td>...</td>
      <td>-0.018307</td>
      <td>0.277838</td>
      <td>-0.110474</td>
      <td>0.066928</td>
      <td>0.128539</td>
      <td>-0.189115</td>
      <td>0.133558</td>
      <td>-0.021053</td>
      <td>149.62</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.191857</td>
      <td>0.266151</td>
      <td>0.166480</td>
      <td>0.448154</td>
      <td>0.060018</td>
      <td>-0.082361</td>
      <td>-0.078803</td>
      <td>0.085102</td>
      <td>-0.255425</td>
      <td>...</td>
      <td>-0.225775</td>
      <td>-0.638672</td>
      <td>0.101288</td>
      <td>-0.339846</td>
      <td>0.167170</td>
      <td>0.125895</td>
      <td>-0.008983</td>
      <td>0.014724</td>
      <td>2.69</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1.0</td>
      <td>-1.358354</td>
      <td>-1.340163</td>
      <td>1.773209</td>
      <td>0.379780</td>
      <td>-0.503198</td>
      <td>1.800499</td>
      <td>0.791461</td>
      <td>0.247676</td>
      <td>-1.514654</td>
      <td>...</td>
      <td>0.247998</td>
      <td>0.771679</td>
      <td>0.909412</td>
      <td>-0.689281</td>
      <td>-0.327642</td>
      <td>-0.139097</td>
      <td>-0.055353</td>
      <td>-0.059752</td>
      <td>378.66</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1.0</td>
      <td>-0.966272</td>
      <td>-0.185226</td>
      <td>1.792993</td>
      <td>-0.863291</td>
      <td>-0.010309</td>
      <td>1.247203</td>
      <td>0.237609</td>
      <td>0.377436</td>
      <td>-1.387024</td>
      <td>...</td>
      <td>-0.108300</td>
      <td>0.005274</td>
      <td>-0.190321</td>
      <td>-1.175575</td>
      <td>0.647376</td>
      <td>-0.221929</td>
      <td>0.062723</td>
      <td>0.061458</td>
      <td>123.50</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2.0</td>
      <td>-1.158233</td>
      <td>0.877737</td>
      <td>1.548718</td>
      <td>0.403034</td>
      <td>-0.407193</td>
      <td>0.095921</td>
      <td>0.592941</td>
      <td>-0.270533</td>
      <td>0.817739</td>
      <td>...</td>
      <td>-0.009431</td>
      <td>0.798278</td>
      <td>-0.137458</td>
      <td>0.141267</td>
      <td>-0.206010</td>
      <td>0.502292</td>
      <td>0.219422</td>
      <td>0.215153</td>
      <td>69.99</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>284802</th>
      <td>172786.0</td>
      <td>-11.881118</td>
      <td>10.071785</td>
      <td>-9.834783</td>
      <td>-2.066656</td>
      <td>-5.364473</td>
      <td>-2.606837</td>
      <td>-4.918215</td>
      <td>7.305334</td>
      <td>1.914428</td>
      <td>...</td>
      <td>0.213454</td>
      <td>0.111864</td>
      <td>1.014480</td>
      <td>-0.509348</td>
      <td>1.436807</td>
      <td>0.250034</td>
      <td>0.943651</td>
      <td>0.823731</td>
      <td>0.77</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284803</th>
      <td>172787.0</td>
      <td>-0.732789</td>
      <td>-0.055080</td>
      <td>2.035030</td>
      <td>-0.738589</td>
      <td>0.868229</td>
      <td>1.058415</td>
      <td>0.024330</td>
      <td>0.294869</td>
      <td>0.584800</td>
      <td>...</td>
      <td>0.214205</td>
      <td>0.924384</td>
      <td>0.012463</td>
      <td>-1.016226</td>
      <td>-0.606624</td>
      <td>-0.395255</td>
      <td>0.068472</td>
      <td>-0.053527</td>
      <td>24.79</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284804</th>
      <td>172788.0</td>
      <td>1.919565</td>
      <td>-0.301254</td>
      <td>-3.249640</td>
      <td>-0.557828</td>
      <td>2.630515</td>
      <td>3.031260</td>
      <td>-0.296827</td>
      <td>0.708417</td>
      <td>0.432454</td>
      <td>...</td>
      <td>0.232045</td>
      <td>0.578229</td>
      <td>-0.037501</td>
      <td>0.640134</td>
      <td>0.265745</td>
      <td>-0.087371</td>
      <td>0.004455</td>
      <td>-0.026561</td>
      <td>67.88</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284805</th>
      <td>172788.0</td>
      <td>-0.240440</td>
      <td>0.530483</td>
      <td>0.702510</td>
      <td>0.689799</td>
      <td>-0.377961</td>
      <td>0.623708</td>
      <td>-0.686180</td>
      <td>0.679145</td>
      <td>0.392087</td>
      <td>...</td>
      <td>0.265245</td>
      <td>0.800049</td>
      <td>-0.163298</td>
      <td>0.123205</td>
      <td>-0.569159</td>
      <td>0.546668</td>
      <td>0.108821</td>
      <td>0.104533</td>
      <td>10.00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284806</th>
      <td>172792.0</td>
      <td>-0.533413</td>
      <td>-0.189733</td>
      <td>0.703337</td>
      <td>-0.506271</td>
      <td>-0.012546</td>
      <td>-0.649617</td>
      <td>1.577006</td>
      <td>-0.414650</td>
      <td>0.486180</td>
      <td>...</td>
      <td>0.261057</td>
      <td>0.643078</td>
      <td>0.376777</td>
      <td>0.008797</td>
      <td>-0.473649</td>
      <td>-0.818267</td>
      <td>-0.002415</td>
      <td>0.013649</td>
      <td>217.00</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>284807 rows × 31 columns</p>
</div>




```python
# The data set is imbalanced. This will be addressed later as the models are trained
df['Class'].value_counts()
```




    Class
    0    284315
    1       492
    Name: count, dtype: int64




```python
# check feature distributions. All features are roughly normal except Time (bimodal distribution addressed below with rescaling and multicollinearity check)
df.hist(bins=30, figsize=(30, 30))
```




    array([[<Axes: title={'center': 'Time'}>, <Axes: title={'center': 'V1'}>,
            <Axes: title={'center': 'V2'}>, <Axes: title={'center': 'V3'}>,
            <Axes: title={'center': 'V4'}>, <Axes: title={'center': 'V5'}>],
           [<Axes: title={'center': 'V6'}>, <Axes: title={'center': 'V7'}>,
            <Axes: title={'center': 'V8'}>, <Axes: title={'center': 'V9'}>,
            <Axes: title={'center': 'V10'}>, <Axes: title={'center': 'V11'}>],
           [<Axes: title={'center': 'V12'}>, <Axes: title={'center': 'V13'}>,
            <Axes: title={'center': 'V14'}>, <Axes: title={'center': 'V15'}>,
            <Axes: title={'center': 'V16'}>, <Axes: title={'center': 'V17'}>],
           [<Axes: title={'center': 'V18'}>, <Axes: title={'center': 'V19'}>,
            <Axes: title={'center': 'V20'}>, <Axes: title={'center': 'V21'}>,
            <Axes: title={'center': 'V22'}>, <Axes: title={'center': 'V23'}>],
           [<Axes: title={'center': 'V24'}>, <Axes: title={'center': 'V25'}>,
            <Axes: title={'center': 'V26'}>, <Axes: title={'center': 'V27'}>,
            <Axes: title={'center': 'V28'}>,
            <Axes: title={'center': 'Amount'}>],
           [<Axes: title={'center': 'Class'}>, <Axes: >, <Axes: >, <Axes: >,
            <Axes: >, <Axes: >]], dtype=object)




    
![png](Credit_Card_Fraud_V6_files/Credit_Card_Fraud_V6_2_1.png)
    



```python
# no output => multicollinearity does not exist

correlation_matrix = df.corr()

threshold = 0.6  # correlation threshold
correlated_features = set()  # store correlated feature pairs

# Iterate through the correlation matrix
for i in range(len(correlation_matrix.columns)):
    for j in range(i):
        if abs(correlation_matrix.iloc[i, j]) > threshold:
            colname_i = correlation_matrix.columns[i]
            colname_j = correlation_matrix.columns[j]
            correlated_features.add((colname_i, colname_j))

# print any correlated feature pairs 
for pair in correlated_features:
    print(pair)
```


```python
# check feature summary statistics. "Amount" has outliers (addressed below with rescaling)
df.describe()
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
      <th>Time</th>
      <th>V1</th>
      <th>V2</th>
      <th>V3</th>
      <th>V4</th>
      <th>V5</th>
      <th>V6</th>
      <th>V7</th>
      <th>V8</th>
      <th>V9</th>
      <th>...</th>
      <th>V21</th>
      <th>V22</th>
      <th>V23</th>
      <th>V24</th>
      <th>V25</th>
      <th>V26</th>
      <th>V27</th>
      <th>V28</th>
      <th>Amount</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>284807.000000</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>...</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>2.848070e+05</td>
      <td>284807.000000</td>
      <td>284807.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>94813.859575</td>
      <td>1.759061e-12</td>
      <td>-8.251130e-13</td>
      <td>-9.654937e-13</td>
      <td>8.321385e-13</td>
      <td>1.649999e-13</td>
      <td>4.248366e-13</td>
      <td>-3.054600e-13</td>
      <td>8.777971e-14</td>
      <td>-1.179749e-12</td>
      <td>...</td>
      <td>-3.405756e-13</td>
      <td>-5.723197e-13</td>
      <td>-9.725856e-13</td>
      <td>1.464150e-12</td>
      <td>-6.987102e-13</td>
      <td>-5.617874e-13</td>
      <td>3.332082e-12</td>
      <td>-3.518874e-12</td>
      <td>88.349619</td>
      <td>0.001727</td>
    </tr>
    <tr>
      <th>std</th>
      <td>47488.145955</td>
      <td>1.958696e+00</td>
      <td>1.651309e+00</td>
      <td>1.516255e+00</td>
      <td>1.415869e+00</td>
      <td>1.380247e+00</td>
      <td>1.332271e+00</td>
      <td>1.237094e+00</td>
      <td>1.194353e+00</td>
      <td>1.098632e+00</td>
      <td>...</td>
      <td>7.345240e-01</td>
      <td>7.257016e-01</td>
      <td>6.244603e-01</td>
      <td>6.056471e-01</td>
      <td>5.212781e-01</td>
      <td>4.822270e-01</td>
      <td>4.036325e-01</td>
      <td>3.300833e-01</td>
      <td>250.120109</td>
      <td>0.041527</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>-5.640751e+01</td>
      <td>-7.271573e+01</td>
      <td>-4.832559e+01</td>
      <td>-5.683171e+00</td>
      <td>-1.137433e+02</td>
      <td>-2.616051e+01</td>
      <td>-4.355724e+01</td>
      <td>-7.321672e+01</td>
      <td>-1.343407e+01</td>
      <td>...</td>
      <td>-3.483038e+01</td>
      <td>-1.093314e+01</td>
      <td>-4.480774e+01</td>
      <td>-2.836627e+00</td>
      <td>-1.029540e+01</td>
      <td>-2.604551e+00</td>
      <td>-2.256568e+01</td>
      <td>-1.543008e+01</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>54201.500000</td>
      <td>-9.203734e-01</td>
      <td>-5.985499e-01</td>
      <td>-8.903648e-01</td>
      <td>-8.486401e-01</td>
      <td>-6.915971e-01</td>
      <td>-7.682956e-01</td>
      <td>-5.540759e-01</td>
      <td>-2.086297e-01</td>
      <td>-6.430976e-01</td>
      <td>...</td>
      <td>-2.283949e-01</td>
      <td>-5.423504e-01</td>
      <td>-1.618463e-01</td>
      <td>-3.545861e-01</td>
      <td>-3.171451e-01</td>
      <td>-3.269839e-01</td>
      <td>-7.083953e-02</td>
      <td>-5.295979e-02</td>
      <td>5.600000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>84692.000000</td>
      <td>1.810880e-02</td>
      <td>6.548556e-02</td>
      <td>1.798463e-01</td>
      <td>-1.984653e-02</td>
      <td>-5.433583e-02</td>
      <td>-2.741871e-01</td>
      <td>4.010308e-02</td>
      <td>2.235804e-02</td>
      <td>-5.142873e-02</td>
      <td>...</td>
      <td>-2.945017e-02</td>
      <td>6.781943e-03</td>
      <td>-1.119293e-02</td>
      <td>4.097606e-02</td>
      <td>1.659350e-02</td>
      <td>-5.213911e-02</td>
      <td>1.342146e-03</td>
      <td>1.124383e-02</td>
      <td>22.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>139320.500000</td>
      <td>1.315642e+00</td>
      <td>8.037239e-01</td>
      <td>1.027196e+00</td>
      <td>7.433413e-01</td>
      <td>6.119264e-01</td>
      <td>3.985649e-01</td>
      <td>5.704361e-01</td>
      <td>3.273459e-01</td>
      <td>5.971390e-01</td>
      <td>...</td>
      <td>1.863772e-01</td>
      <td>5.285536e-01</td>
      <td>1.476421e-01</td>
      <td>4.395266e-01</td>
      <td>3.507156e-01</td>
      <td>2.409522e-01</td>
      <td>9.104512e-02</td>
      <td>7.827995e-02</td>
      <td>77.165000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>172792.000000</td>
      <td>2.454930e+00</td>
      <td>2.205773e+01</td>
      <td>9.382558e+00</td>
      <td>1.687534e+01</td>
      <td>3.480167e+01</td>
      <td>7.330163e+01</td>
      <td>1.205895e+02</td>
      <td>2.000721e+01</td>
      <td>1.559499e+01</td>
      <td>...</td>
      <td>2.720284e+01</td>
      <td>1.050309e+01</td>
      <td>2.252841e+01</td>
      <td>4.584549e+00</td>
      <td>7.519589e+00</td>
      <td>3.517346e+00</td>
      <td>3.161220e+01</td>
      <td>3.384781e+01</td>
      <td>25691.160000</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 31 columns</p>
</div>




```python
# rescale Amount and Time to address overshadowing other features, outliers (Amount), and bimodal distribution (Time)

#Amount
from sklearn.preprocessing import RobustScaler
new_df = df.copy()
new_df['Amount'] = RobustScaler().fit_transform(new_df['Amount'].to_numpy().reshape(-1, 1))

#Time
time = new_df['Time']
new_df['Time'] = (time - time.min()) / (time.max() - time.min())
new_df
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
      <th>Time</th>
      <th>V1</th>
      <th>V2</th>
      <th>V3</th>
      <th>V4</th>
      <th>V5</th>
      <th>V6</th>
      <th>V7</th>
      <th>V8</th>
      <th>V9</th>
      <th>...</th>
      <th>V21</th>
      <th>V22</th>
      <th>V23</th>
      <th>V24</th>
      <th>V25</th>
      <th>V26</th>
      <th>V27</th>
      <th>V28</th>
      <th>Amount</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.000000</td>
      <td>-1.359807</td>
      <td>-0.072781</td>
      <td>2.536347</td>
      <td>1.378155</td>
      <td>-0.338321</td>
      <td>0.462388</td>
      <td>0.239599</td>
      <td>0.098698</td>
      <td>0.363787</td>
      <td>...</td>
      <td>-0.018307</td>
      <td>0.277838</td>
      <td>-0.110474</td>
      <td>0.066928</td>
      <td>0.128539</td>
      <td>-0.189115</td>
      <td>0.133558</td>
      <td>-0.021053</td>
      <td>1.783274</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.000000</td>
      <td>1.191857</td>
      <td>0.266151</td>
      <td>0.166480</td>
      <td>0.448154</td>
      <td>0.060018</td>
      <td>-0.082361</td>
      <td>-0.078803</td>
      <td>0.085102</td>
      <td>-0.255425</td>
      <td>...</td>
      <td>-0.225775</td>
      <td>-0.638672</td>
      <td>0.101288</td>
      <td>-0.339846</td>
      <td>0.167170</td>
      <td>0.125895</td>
      <td>-0.008983</td>
      <td>0.014724</td>
      <td>-0.269825</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.000006</td>
      <td>-1.358354</td>
      <td>-1.340163</td>
      <td>1.773209</td>
      <td>0.379780</td>
      <td>-0.503198</td>
      <td>1.800499</td>
      <td>0.791461</td>
      <td>0.247676</td>
      <td>-1.514654</td>
      <td>...</td>
      <td>0.247998</td>
      <td>0.771679</td>
      <td>0.909412</td>
      <td>-0.689281</td>
      <td>-0.327642</td>
      <td>-0.139097</td>
      <td>-0.055353</td>
      <td>-0.059752</td>
      <td>4.983721</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.000006</td>
      <td>-0.966272</td>
      <td>-0.185226</td>
      <td>1.792993</td>
      <td>-0.863291</td>
      <td>-0.010309</td>
      <td>1.247203</td>
      <td>0.237609</td>
      <td>0.377436</td>
      <td>-1.387024</td>
      <td>...</td>
      <td>-0.108300</td>
      <td>0.005274</td>
      <td>-0.190321</td>
      <td>-1.175575</td>
      <td>0.647376</td>
      <td>-0.221929</td>
      <td>0.062723</td>
      <td>0.061458</td>
      <td>1.418291</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.000012</td>
      <td>-1.158233</td>
      <td>0.877737</td>
      <td>1.548718</td>
      <td>0.403034</td>
      <td>-0.407193</td>
      <td>0.095921</td>
      <td>0.592941</td>
      <td>-0.270533</td>
      <td>0.817739</td>
      <td>...</td>
      <td>-0.009431</td>
      <td>0.798278</td>
      <td>-0.137458</td>
      <td>0.141267</td>
      <td>-0.206010</td>
      <td>0.502292</td>
      <td>0.219422</td>
      <td>0.215153</td>
      <td>0.670579</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>284802</th>
      <td>0.999965</td>
      <td>-11.881118</td>
      <td>10.071785</td>
      <td>-9.834783</td>
      <td>-2.066656</td>
      <td>-5.364473</td>
      <td>-2.606837</td>
      <td>-4.918215</td>
      <td>7.305334</td>
      <td>1.914428</td>
      <td>...</td>
      <td>0.213454</td>
      <td>0.111864</td>
      <td>1.014480</td>
      <td>-0.509348</td>
      <td>1.436807</td>
      <td>0.250034</td>
      <td>0.943651</td>
      <td>0.823731</td>
      <td>-0.296653</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284803</th>
      <td>0.999971</td>
      <td>-0.732789</td>
      <td>-0.055080</td>
      <td>2.035030</td>
      <td>-0.738589</td>
      <td>0.868229</td>
      <td>1.058415</td>
      <td>0.024330</td>
      <td>0.294869</td>
      <td>0.584800</td>
      <td>...</td>
      <td>0.214205</td>
      <td>0.924384</td>
      <td>0.012463</td>
      <td>-1.016226</td>
      <td>-0.606624</td>
      <td>-0.395255</td>
      <td>0.068472</td>
      <td>-0.053527</td>
      <td>0.038986</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284804</th>
      <td>0.999977</td>
      <td>1.919565</td>
      <td>-0.301254</td>
      <td>-3.249640</td>
      <td>-0.557828</td>
      <td>2.630515</td>
      <td>3.031260</td>
      <td>-0.296827</td>
      <td>0.708417</td>
      <td>0.432454</td>
      <td>...</td>
      <td>0.232045</td>
      <td>0.578229</td>
      <td>-0.037501</td>
      <td>0.640134</td>
      <td>0.265745</td>
      <td>-0.087371</td>
      <td>0.004455</td>
      <td>-0.026561</td>
      <td>0.641096</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284805</th>
      <td>0.999977</td>
      <td>-0.240440</td>
      <td>0.530483</td>
      <td>0.702510</td>
      <td>0.689799</td>
      <td>-0.377961</td>
      <td>0.623708</td>
      <td>-0.686180</td>
      <td>0.679145</td>
      <td>0.392087</td>
      <td>...</td>
      <td>0.265245</td>
      <td>0.800049</td>
      <td>-0.163298</td>
      <td>0.123205</td>
      <td>-0.569159</td>
      <td>0.546668</td>
      <td>0.108821</td>
      <td>0.104533</td>
      <td>-0.167680</td>
      <td>0</td>
    </tr>
    <tr>
      <th>284806</th>
      <td>1.000000</td>
      <td>-0.533413</td>
      <td>-0.189733</td>
      <td>0.703337</td>
      <td>-0.506271</td>
      <td>-0.012546</td>
      <td>-0.649617</td>
      <td>1.577006</td>
      <td>-0.414650</td>
      <td>0.486180</td>
      <td>...</td>
      <td>0.261057</td>
      <td>0.643078</td>
      <td>0.376777</td>
      <td>0.008797</td>
      <td>-0.473649</td>
      <td>-0.818267</td>
      <td>-0.002415</td>
      <td>0.013649</td>
      <td>2.724796</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>284807 rows × 31 columns</p>
</div>




```python
# shuffle rows before splitting data
new_df = new_df.sample(frac=1, random_state=1)      # use random_state for reproducibility
new_df
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
      <th>Time</th>
      <th>V1</th>
      <th>V2</th>
      <th>V3</th>
      <th>V4</th>
      <th>V5</th>
      <th>V6</th>
      <th>V7</th>
      <th>V8</th>
      <th>V9</th>
      <th>...</th>
      <th>V21</th>
      <th>V22</th>
      <th>V23</th>
      <th>V24</th>
      <th>V25</th>
      <th>V26</th>
      <th>V27</th>
      <th>V28</th>
      <th>Amount</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>169876</th>
      <td>0.693938</td>
      <td>-0.611712</td>
      <td>-0.769705</td>
      <td>-0.149759</td>
      <td>-0.224877</td>
      <td>2.028577</td>
      <td>-2.019887</td>
      <td>0.292491</td>
      <td>-0.523020</td>
      <td>0.358468</td>
      <td>...</td>
      <td>-0.075208</td>
      <td>0.045536</td>
      <td>0.380739</td>
      <td>0.023440</td>
      <td>-2.220686</td>
      <td>-0.201146</td>
      <td>0.066501</td>
      <td>0.221180</td>
      <td>-0.282401</td>
      <td>0</td>
    </tr>
    <tr>
      <th>127467</th>
      <td>0.453377</td>
      <td>-0.814682</td>
      <td>1.319219</td>
      <td>1.329415</td>
      <td>0.027273</td>
      <td>-0.284871</td>
      <td>-0.653985</td>
      <td>0.321552</td>
      <td>0.435975</td>
      <td>-0.704298</td>
      <td>...</td>
      <td>-0.128619</td>
      <td>-0.368565</td>
      <td>0.090660</td>
      <td>0.401147</td>
      <td>-0.261034</td>
      <td>0.080621</td>
      <td>0.162427</td>
      <td>0.059456</td>
      <td>-0.279746</td>
      <td>0</td>
    </tr>
    <tr>
      <th>137900</th>
      <td>0.476770</td>
      <td>-0.318193</td>
      <td>1.118618</td>
      <td>0.969864</td>
      <td>-0.127052</td>
      <td>0.569563</td>
      <td>-0.532484</td>
      <td>0.706252</td>
      <td>-0.064966</td>
      <td>-0.463271</td>
      <td>...</td>
      <td>-0.305402</td>
      <td>-0.774704</td>
      <td>-0.123884</td>
      <td>-0.495687</td>
      <td>-0.018148</td>
      <td>0.121679</td>
      <td>0.249050</td>
      <td>0.092516</td>
      <td>-0.294977</td>
      <td>0</td>
    </tr>
    <tr>
      <th>21513</th>
      <td>0.183556</td>
      <td>-1.328271</td>
      <td>1.018378</td>
      <td>1.775426</td>
      <td>-1.574193</td>
      <td>-0.117696</td>
      <td>-0.457733</td>
      <td>0.681867</td>
      <td>-0.031641</td>
      <td>0.383872</td>
      <td>...</td>
      <td>-0.220815</td>
      <td>-0.419013</td>
      <td>-0.239197</td>
      <td>0.009967</td>
      <td>0.232829</td>
      <td>0.814177</td>
      <td>0.098797</td>
      <td>-0.004273</td>
      <td>-0.084119</td>
      <td>0</td>
    </tr>
    <tr>
      <th>134700</th>
      <td>0.468326</td>
      <td>1.276712</td>
      <td>0.617120</td>
      <td>-0.578014</td>
      <td>0.879173</td>
      <td>0.061706</td>
      <td>-1.472002</td>
      <td>0.373692</td>
      <td>-0.287204</td>
      <td>-0.084482</td>
      <td>...</td>
      <td>-0.160161</td>
      <td>-0.430404</td>
      <td>-0.076738</td>
      <td>0.258708</td>
      <td>0.552170</td>
      <td>0.370701</td>
      <td>-0.034255</td>
      <td>0.041709</td>
      <td>-0.296793</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>21440</th>
      <td>0.183261</td>
      <td>-2.986845</td>
      <td>-8.663978</td>
      <td>-1.910863</td>
      <td>0.664058</td>
      <td>-3.934875</td>
      <td>0.861269</td>
      <td>1.647511</td>
      <td>-0.480963</td>
      <td>-1.546866</td>
      <td>...</td>
      <td>1.252092</td>
      <td>-0.993085</td>
      <td>-2.173147</td>
      <td>0.145570</td>
      <td>-0.235062</td>
      <td>-0.227411</td>
      <td>-0.382702</td>
      <td>0.404045</td>
      <td>32.002515</td>
      <td>0</td>
    </tr>
    <tr>
      <th>117583</th>
      <td>0.432480</td>
      <td>0.937083</td>
      <td>-0.849673</td>
      <td>0.524186</td>
      <td>-0.020031</td>
      <td>-0.606327</td>
      <td>0.692302</td>
      <td>-0.463724</td>
      <td>0.148857</td>
      <td>0.785062</td>
      <td>...</td>
      <td>-0.143322</td>
      <td>-0.479981</td>
      <td>-0.237902</td>
      <td>-0.715247</td>
      <td>0.251418</td>
      <td>0.975406</td>
      <td>-0.060168</td>
      <td>0.023771</td>
      <td>2.086495</td>
      <td>0</td>
    </tr>
    <tr>
      <th>73349</th>
      <td>0.318852</td>
      <td>-1.149963</td>
      <td>1.696462</td>
      <td>1.637114</td>
      <td>2.658991</td>
      <td>-0.021502</td>
      <td>0.192287</td>
      <td>0.205204</td>
      <td>0.588754</td>
      <td>-1.187820</td>
      <td>...</td>
      <td>0.025147</td>
      <td>0.086506</td>
      <td>-0.262748</td>
      <td>0.321538</td>
      <td>0.341667</td>
      <td>0.210343</td>
      <td>-0.162047</td>
      <td>0.031193</td>
      <td>-0.201495</td>
      <td>0</td>
    </tr>
    <tr>
      <th>267336</th>
      <td>0.941757</td>
      <td>1.754554</td>
      <td>-0.699398</td>
      <td>-0.076332</td>
      <td>0.443915</td>
      <td>-0.672082</td>
      <td>0.389061</td>
      <td>-0.807534</td>
      <td>0.202915</td>
      <td>0.858635</td>
      <td>...</td>
      <td>0.141950</td>
      <td>0.358412</td>
      <td>0.259748</td>
      <td>0.746839</td>
      <td>-0.560808</td>
      <td>0.104636</td>
      <td>-0.005853</td>
      <td>-0.019622</td>
      <td>1.017257</td>
      <td>0</td>
    </tr>
    <tr>
      <th>128037</th>
      <td>0.454743</td>
      <td>-0.707635</td>
      <td>0.493302</td>
      <td>2.648089</td>
      <td>1.064807</td>
      <td>-0.680271</td>
      <td>1.183838</td>
      <td>0.169413</td>
      <td>0.074553</td>
      <td>1.247988</td>
      <td>...</td>
      <td>-0.102350</td>
      <td>0.323975</td>
      <td>-0.172601</td>
      <td>0.126965</td>
      <td>-0.001998</td>
      <td>-0.398741</td>
      <td>-0.385589</td>
      <td>-0.205589</td>
      <td>0.500245</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>284807 rows × 31 columns</p>
</div>




```python
# split data into train, test, and validation sets
train, test, val = new_df[:240000], new_df[240000:262000], new_df[262000:]
train['Class'].value_counts(), test['Class'].value_counts(), val['Class'].value_counts()
```




    (Class
     0    239589
     1       411
     Name: count, dtype: int64,
     Class
     0    21955
     1       45
     Name: count, dtype: int64,
     Class
     0    22771
     1       36
     Name: count, dtype: int64)




```python
# convert each set into a numpy array
import numpy as np
train_np, test_np, val_np = train.to_numpy(), test.to_numpy(), val.to_numpy()
train_np.shape, test_np.shape, val_np.shape
```




    ((240000, 31), (22000, 31), (22807, 31))




```python
# split each set into inputs and outputs (to reference later in models)
x_train, y_train = train_np[:, :-1], train_np[:, -1]
x_test, y_test = test_np[:, :-1], test_np[:, -1]
x_val, y_val = val_np[:, :-1], val_np[:, -1]
x_train.shape, y_train.shape, x_test.shape, y_test.shape, x_val.shape, y_val.shape
```




    ((240000, 30), (240000,), (22000, 30), (22000,), (22807, 30), (22807,))




```python
# create logistic regression model
from sklearn.linear_model import LogisticRegression
logistic_model = LogisticRegression()
logistic_model.fit(x_train, y_train)
logistic_model.score(x_train, y_train)
```

    c:\Users\todda\Desktop\Desktop\Career General\My Companies\BlockWatch\credit_fraud_detection\myvenv\lib\site-packages\sklearn\linear_model\_logistic.py:458: ConvergenceWarning: lbfgs failed to converge (status=1):
    STOP: TOTAL NO. of ITERATIONS REACHED LIMIT.
    
    Increase the number of iterations (max_iter) or scale the data as shown in:
        https://scikit-learn.org/stable/modules/preprocessing.html
    Please also refer to the documentation for alternative solver options:
        https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression
      n_iter_i = _check_optimize_result(
    




    0.9992375




```python
# logistic regression performance: not as good as other models
from sklearn.metrics import classification_report
print(classification_report(y_val, logistic_model.predict(x_val), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       1.00      1.00      1.00     22771
           Fraud       0.73      0.53      0.61        36
    
        accuracy                           1.00     22807
       macro avg       0.87      0.76      0.81     22807
    weighted avg       1.00      1.00      1.00     22807
    
    


```python
# create shallow neural network model
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import InputLayer, Dense, BatchNormalization
from tensorflow.keras.callbacks import ModelCheckpoint        

shallow_nn = Sequential()
shallow_nn.add(InputLayer((x_train.shape[1],)))
shallow_nn.add(Dense(2, 'relu'))
shallow_nn.add(BatchNormalization())       
shallow_nn.add(Dense(1, 'sigmoid'))        

checkpoint = ModelCheckpoint('shallow_nn', save_best_only=True)      
shallow_nn.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
shallow_nn.summary()
```

    Model: "sequential"
    _________________________________________________________________
     Layer (type)                Output Shape              Param #   
    =================================================================
     dense (Dense)               (None, 2)                 62        
                                                                     
     batch_normalization (BatchN  (None, 2)                8         
     ormalization)                                                   
                                                                     
     dense_1 (Dense)             (None, 1)                 3         
                                                                     
    =================================================================
    Total params: 73
    Trainable params: 69
    Non-trainable params: 4
    _________________________________________________________________
    


```python
# train the data
shallow_nn.fit(x_train, y_train, validation_data=(x_val, y_val), epochs=5, callbacks=checkpoint)
```

    Epoch 1/5
    7462/7500 [============================>.] - ETA: 0s - loss: 0.0525 - accuracy: 0.9814

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    7500/7500 [==============================] - 9s 1ms/step - loss: 0.0522 - accuracy: 0.9815 - val_loss: 0.0055 - val_accuracy: 0.9991
    Epoch 2/5
    7465/7500 [============================>.] - ETA: 0s - loss: 0.0035 - accuracy: 0.9993

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    7500/7500 [==============================] - 9s 1ms/step - loss: 0.0034 - accuracy: 0.9993 - val_loss: 0.0047 - val_accuracy: 0.9990
    Epoch 3/5
    7456/7500 [============================>.] - ETA: 0s - loss: 0.0033 - accuracy: 0.9994

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    7500/7500 [==============================] - 9s 1ms/step - loss: 0.0033 - accuracy: 0.9994 - val_loss: 0.0044 - val_accuracy: 0.9991
    Epoch 4/5
    7458/7500 [============================>.] - ETA: 0s - loss: 0.0033 - accuracy: 0.9994

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    7500/7500 [==============================] - 9s 1ms/step - loss: 0.0033 - accuracy: 0.9994 - val_loss: 0.0042 - val_accuracy: 0.9989
    Epoch 5/5
    7486/7500 [============================>.] - ETA: 0s - loss: 0.0032 - accuracy: 0.9994

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    INFO:tensorflow:Assets written to: shallow_nn\assets
    

    7500/7500 [==============================] - 9s 1ms/step - loss: 0.0032 - accuracy: 0.9994 - val_loss: 0.0039 - val_accuracy: 0.9991
    




    <keras.callbacks.History at 0x26b5b4cfeb0>




```python
# create function to use when printing classification reports for different models
def neural_net_predictions(model, x):
  return (model.predict(x).flatten() > 0.5).astype(int)
neural_net_predictions(shallow_nn, x_val)
```

    713/713 [==============================] - 1s 744us/step
    




    array([0, 0, 0, ..., 0, 0, 0])




```python
# shallow neural network performance: not as good as it could be
print(classification_report(y_val, neural_net_predictions(shallow_nn, x_val), target_names=['Not Fraud', 'Fraud']))
```

    713/713 [==============================] - 1s 762us/step
                  precision    recall  f1-score   support
    
       Not Fraud       1.00      1.00      1.00     22771
           Fraud       0.69      0.75      0.72        36
    
        accuracy                           1.00     22807
       macro avg       0.85      0.87      0.86     22807
    weighted avg       1.00      1.00      1.00     22807
    
    


```python
# Random Forest performance: not as good as other models (fraud recall very low)
from sklearn.ensemble import RandomForestClassifier
rf = RandomForestClassifier(max_depth=2, n_jobs=-1)
rf.fit(x_train, y_train)
print(classification_report(y_val, rf.predict(x_val), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       1.00      1.00      1.00     22771
           Fraud       0.77      0.47      0.59        36
    
        accuracy                           1.00     22807
       macro avg       0.89      0.74      0.79     22807
    weighted avg       1.00      1.00      1.00     22807
    
    


```python
# gradient boosting classifier performance: not as good as shallow neural network model
from sklearn.ensemble import GradientBoostingClassifier
gbc = GradientBoostingClassifier(n_estimators=50, learning_rate=1.0, max_depth=1, random_state=0)
gbc.fit(x_train, y_train)
print(classification_report(y_val, gbc.predict(x_val), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       1.00      1.00      1.00     22771
           Fraud       0.67      0.67      0.67        36
    
        accuracy                           1.00     22807
       macro avg       0.83      0.83      0.83     22807
    weighted avg       1.00      1.00      1.00     22807
    
    


```python
# support vector machine performance: comparable to shallow neural network but not quite as good
from sklearn.svm import LinearSVC
svc = LinearSVC(class_weight='balanced')
svc.fit(x_train, y_train)
print(classification_report(y_val, svc.predict(x_val), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       1.00      1.00      1.00     22771
           Fraud       0.64      0.75      0.69        36
    
        accuracy                           1.00     22807
       macro avg       0.82      0.87      0.85     22807
    weighted avg       1.00      1.00      1.00     22807
    
    

    c:\Users\todda\Desktop\Desktop\Career General\My Companies\BlockWatch\credit_fraud_detection\myvenv\lib\site-packages\sklearn\svm\_base.py:1244: ConvergenceWarning: Liblinear failed to converge, increase the number of iterations.
      warnings.warn(
    


```python
train.head()
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
      <th>Time</th>
      <th>V1</th>
      <th>V2</th>
      <th>V3</th>
      <th>V4</th>
      <th>V5</th>
      <th>V6</th>
      <th>V7</th>
      <th>V8</th>
      <th>V9</th>
      <th>...</th>
      <th>V21</th>
      <th>V22</th>
      <th>V23</th>
      <th>V24</th>
      <th>V25</th>
      <th>V26</th>
      <th>V27</th>
      <th>V28</th>
      <th>Amount</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>169876</th>
      <td>0.693938</td>
      <td>-0.611712</td>
      <td>-0.769705</td>
      <td>-0.149759</td>
      <td>-0.224877</td>
      <td>2.028577</td>
      <td>-2.019887</td>
      <td>0.292491</td>
      <td>-0.523020</td>
      <td>0.358468</td>
      <td>...</td>
      <td>-0.075208</td>
      <td>0.045536</td>
      <td>0.380739</td>
      <td>0.023440</td>
      <td>-2.220686</td>
      <td>-0.201146</td>
      <td>0.066501</td>
      <td>0.221180</td>
      <td>-0.282401</td>
      <td>0</td>
    </tr>
    <tr>
      <th>127467</th>
      <td>0.453377</td>
      <td>-0.814682</td>
      <td>1.319219</td>
      <td>1.329415</td>
      <td>0.027273</td>
      <td>-0.284871</td>
      <td>-0.653985</td>
      <td>0.321552</td>
      <td>0.435975</td>
      <td>-0.704298</td>
      <td>...</td>
      <td>-0.128619</td>
      <td>-0.368565</td>
      <td>0.090660</td>
      <td>0.401147</td>
      <td>-0.261034</td>
      <td>0.080621</td>
      <td>0.162427</td>
      <td>0.059456</td>
      <td>-0.279746</td>
      <td>0</td>
    </tr>
    <tr>
      <th>137900</th>
      <td>0.476770</td>
      <td>-0.318193</td>
      <td>1.118618</td>
      <td>0.969864</td>
      <td>-0.127052</td>
      <td>0.569563</td>
      <td>-0.532484</td>
      <td>0.706252</td>
      <td>-0.064966</td>
      <td>-0.463271</td>
      <td>...</td>
      <td>-0.305402</td>
      <td>-0.774704</td>
      <td>-0.123884</td>
      <td>-0.495687</td>
      <td>-0.018148</td>
      <td>0.121679</td>
      <td>0.249050</td>
      <td>0.092516</td>
      <td>-0.294977</td>
      <td>0</td>
    </tr>
    <tr>
      <th>21513</th>
      <td>0.183556</td>
      <td>-1.328271</td>
      <td>1.018378</td>
      <td>1.775426</td>
      <td>-1.574193</td>
      <td>-0.117696</td>
      <td>-0.457733</td>
      <td>0.681867</td>
      <td>-0.031641</td>
      <td>0.383872</td>
      <td>...</td>
      <td>-0.220815</td>
      <td>-0.419013</td>
      <td>-0.239197</td>
      <td>0.009967</td>
      <td>0.232829</td>
      <td>0.814177</td>
      <td>0.098797</td>
      <td>-0.004273</td>
      <td>-0.084119</td>
      <td>0</td>
    </tr>
    <tr>
      <th>134700</th>
      <td>0.468326</td>
      <td>1.276712</td>
      <td>0.617120</td>
      <td>-0.578014</td>
      <td>0.879173</td>
      <td>0.061706</td>
      <td>-1.472002</td>
      <td>0.373692</td>
      <td>-0.287204</td>
      <td>-0.084482</td>
      <td>...</td>
      <td>-0.160161</td>
      <td>-0.430404</td>
      <td>-0.076738</td>
      <td>0.258708</td>
      <td>0.552170</td>
      <td>0.370701</td>
      <td>-0.034255</td>
      <td>0.041709</td>
      <td>-0.296793</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 31 columns</p>
</div>




```python
# return counts of frauds and not frauds to see how imbalanced the data set is
not_frauds = new_df.query('Class == 0')
frauds = new_df.query('Class == 1')
not_frauds['Class'].value_counts(), frauds['Class'].value_counts()
```




    (Class
     0    284315
     Name: count, dtype: int64,
     Class
     1    492
     Name: count, dtype: int64)




```python
# create a balanced data set
balanced_df = pd.concat([frauds, not_frauds.sample(len(frauds), random_state=1)])
balanced_df['Class'].value_counts()
```




    Class
    1    492
    0    492
    Name: count, dtype: int64




```python
# view balanced data set
balanced_df = balanced_df.sample(frac=1, random_state=1)
balanced_df
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
      <th>Time</th>
      <th>V1</th>
      <th>V2</th>
      <th>V3</th>
      <th>V4</th>
      <th>V5</th>
      <th>V6</th>
      <th>V7</th>
      <th>V8</th>
      <th>V9</th>
      <th>...</th>
      <th>V21</th>
      <th>V22</th>
      <th>V23</th>
      <th>V24</th>
      <th>V25</th>
      <th>V26</th>
      <th>V27</th>
      <th>V28</th>
      <th>Amount</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>18372</th>
      <td>0.170309</td>
      <td>-1.762593</td>
      <td>0.256143</td>
      <td>1.683125</td>
      <td>-1.279233</td>
      <td>-1.902762</td>
      <td>1.004210</td>
      <td>-1.009748</td>
      <td>-2.432546</td>
      <td>0.458860</td>
      <td>...</td>
      <td>2.493579</td>
      <td>0.320829</td>
      <td>-0.535481</td>
      <td>0.499401</td>
      <td>-0.915196</td>
      <td>-0.423434</td>
      <td>0.107049</td>
      <td>0.175922</td>
      <td>2.906449</td>
      <td>0</td>
    </tr>
    <tr>
      <th>96341</th>
      <td>0.380388</td>
      <td>1.227614</td>
      <td>-0.668974</td>
      <td>-0.271785</td>
      <td>-0.589440</td>
      <td>-0.604795</td>
      <td>-0.350285</td>
      <td>-0.486365</td>
      <td>-0.010809</td>
      <td>-0.794944</td>
      <td>...</td>
      <td>-0.026055</td>
      <td>-0.295255</td>
      <td>-0.180459</td>
      <td>-0.436539</td>
      <td>0.494649</td>
      <td>-0.283738</td>
      <td>-0.001128</td>
      <td>0.035075</td>
      <td>1.062111</td>
      <td>1</td>
    </tr>
    <tr>
      <th>248296</th>
      <td>0.890522</td>
      <td>-0.613696</td>
      <td>3.698772</td>
      <td>-5.534941</td>
      <td>5.620486</td>
      <td>1.649263</td>
      <td>-2.335145</td>
      <td>-0.907188</td>
      <td>0.706362</td>
      <td>-3.747646</td>
      <td>...</td>
      <td>0.319261</td>
      <td>-0.471379</td>
      <td>-0.075890</td>
      <td>-0.667909</td>
      <td>-0.642848</td>
      <td>0.070600</td>
      <td>0.488410</td>
      <td>0.292345</td>
      <td>-0.307413</td>
      <td>1</td>
    </tr>
    <tr>
      <th>264328</th>
      <td>0.933932</td>
      <td>-0.011624</td>
      <td>0.640413</td>
      <td>0.868046</td>
      <td>-0.505279</td>
      <td>0.261938</td>
      <td>0.223098</td>
      <td>0.239049</td>
      <td>0.150877</td>
      <td>0.225142</td>
      <td>...</td>
      <td>0.069401</td>
      <td>0.268024</td>
      <td>0.261459</td>
      <td>0.683742</td>
      <td>-1.567901</td>
      <td>-0.816674</td>
      <td>0.185781</td>
      <td>0.283021</td>
      <td>-0.272619</td>
      <td>0</td>
    </tr>
    <tr>
      <th>208904</th>
      <td>0.794730</td>
      <td>-0.679341</td>
      <td>1.217389</td>
      <td>-0.316778</td>
      <td>-1.086725</td>
      <td>0.855349</td>
      <td>-0.980760</td>
      <td>0.970589</td>
      <td>0.133116</td>
      <td>-0.357671</td>
      <td>...</td>
      <td>-0.083048</td>
      <td>-0.137032</td>
      <td>-0.238920</td>
      <td>-0.617244</td>
      <td>0.039020</td>
      <td>-0.081848</td>
      <td>0.234633</td>
      <td>0.128382</td>
      <td>-0.307273</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>81557</th>
      <td>0.341393</td>
      <td>-4.502731</td>
      <td>-3.876484</td>
      <td>1.341248</td>
      <td>0.113400</td>
      <td>0.189428</td>
      <td>-0.560985</td>
      <td>-0.140478</td>
      <td>0.684651</td>
      <td>0.475363</td>
      <td>...</td>
      <td>-0.140218</td>
      <td>0.049411</td>
      <td>2.313731</td>
      <td>0.252330</td>
      <td>0.307219</td>
      <td>0.859051</td>
      <td>0.184033</td>
      <td>-0.308269</td>
      <td>4.227625</td>
      <td>0</td>
    </tr>
    <tr>
      <th>276071</th>
      <td>0.965803</td>
      <td>2.091900</td>
      <td>-0.757459</td>
      <td>-1.192258</td>
      <td>-0.755458</td>
      <td>-0.620324</td>
      <td>-0.322077</td>
      <td>-1.082511</td>
      <td>0.117200</td>
      <td>-0.140927</td>
      <td>...</td>
      <td>0.288253</td>
      <td>0.831939</td>
      <td>0.142007</td>
      <td>0.592615</td>
      <td>-0.196143</td>
      <td>-0.136676</td>
      <td>0.020182</td>
      <td>-0.015470</td>
      <td>-0.028645</td>
      <td>1</td>
    </tr>
    <tr>
      <th>175971</th>
      <td>0.709373</td>
      <td>1.972989</td>
      <td>0.157281</td>
      <td>-1.715078</td>
      <td>1.207451</td>
      <td>0.681612</td>
      <td>-0.615282</td>
      <td>0.601791</td>
      <td>-0.291935</td>
      <td>-0.132265</td>
      <td>...</td>
      <td>0.098640</td>
      <td>0.467533</td>
      <td>-0.078973</td>
      <td>-0.371882</td>
      <td>0.486038</td>
      <td>-0.490665</td>
      <td>-0.018374</td>
      <td>-0.070911</td>
      <td>0.075735</td>
      <td>0</td>
    </tr>
    <tr>
      <th>27738</th>
      <td>0.200727</td>
      <td>-2.439237</td>
      <td>2.591458</td>
      <td>-2.840126</td>
      <td>1.286244</td>
      <td>-1.777016</td>
      <td>-1.436139</td>
      <td>-2.206056</td>
      <td>-2.282725</td>
      <td>-0.292885</td>
      <td>...</td>
      <td>1.774460</td>
      <td>-0.771390</td>
      <td>0.065727</td>
      <td>0.103916</td>
      <td>-0.057578</td>
      <td>0.242652</td>
      <td>-0.268649</td>
      <td>-0.743713</td>
      <td>1.443443</td>
      <td>1</td>
    </tr>
    <tr>
      <th>156988</th>
      <td>0.632535</td>
      <td>0.745153</td>
      <td>2.809299</td>
      <td>-5.825406</td>
      <td>5.835566</td>
      <td>0.512320</td>
      <td>-0.615622</td>
      <td>-2.916576</td>
      <td>0.776710</td>
      <td>-1.878832</td>
      <td>...</td>
      <td>0.284841</td>
      <td>-0.874383</td>
      <td>-0.083995</td>
      <td>-0.651442</td>
      <td>0.454594</td>
      <td>0.050376</td>
      <td>0.756953</td>
      <td>0.383869</td>
      <td>-0.307413</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>984 rows × 31 columns</p>
</div>




```python
# total number of rows
492*2
```




    984




```python
# split balanced data

# convert to numppy
balanced_df_np = balanced_df.to_numpy()

# split data
x_train_b, y_train_b = balanced_df_np[:700, :-1], balanced_df_np[:700, -1].astype(int)
x_test_b, y_test_b = balanced_df_np[700:842, :-1], balanced_df_np[700:842, -1].astype(int)
x_val_b, y_val_b = balanced_df_np[842:, :-1], balanced_df_np[842:, -1].astype(int)
x_train_b.shape, y_train_b.shape, x_test_b.shape, y_test_b.shape, x_val_b.shape, y_val_b.shape
```




    ((700, 30), (700,), (142, 30), (142,), (142, 30), (142,))




```python
# find distribution of Class for each set
pd.Series(y_train_b).value_counts(), pd.Series(y_test_b).value_counts(), pd.Series(y_val_b).value_counts()
```




    (1    353
     0    347
     Name: count, dtype: int64,
     0    73
     1    69
     Name: count, dtype: int64,
     0    72
     1    70
     Name: count, dtype: int64)




```python
# logistic regression model performance (using balanced data): very good at both capturing total frauds (fraud recall) and making accurate fraud predictions (fraud precision)
logistic_model_b = LogisticRegression()
logistic_model_b.fit(x_train_b, y_train_b)
print(classification_report(y_val_b, logistic_model_b.predict(x_val_b), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       0.96      0.93      0.94        72
           Fraud       0.93      0.96      0.94        70
    
        accuracy                           0.94       142
       macro avg       0.94      0.94      0.94       142
    weighted avg       0.94      0.94      0.94       142
    
    


```python
# create shallow neural netowrk model with 2 relus
shallow_nn_b = Sequential()
shallow_nn_b.add(InputLayer((x_train.shape[1],)))
shallow_nn_b.add(Dense(2, 'relu'))
shallow_nn_b.add(BatchNormalization())
shallow_nn_b.add(Dense(1, 'sigmoid'))

checkpoint = ModelCheckpoint('shallow_nn_b', save_best_only=True)
shallow_nn_b.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
shallow_nn_b.fit(x_train_b, y_train_b, validation_data=(x_val_b, y_val_b), epochs=40, callbacks=checkpoint)
```

    Epoch 1/40
     1/22 [>.............................] - ETA: 13s - loss: 0.5935 - accuracy: 0.5938

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 2s 45ms/step - loss: 0.5395 - accuracy: 0.7443 - val_loss: 0.5253 - val_accuracy: 0.6972
    Epoch 2/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5897 - accuracy: 0.6875

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.5074 - accuracy: 0.7986 - val_loss: 0.4865 - val_accuracy: 0.7958
    Epoch 3/40
     5/22 [=====>........................] - ETA: 0s - loss: 0.4946 - accuracy: 0.8250

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 38ms/step - loss: 0.4876 - accuracy: 0.8214 - val_loss: 0.4640 - val_accuracy: 0.8310
    Epoch 4/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4997 - accuracy: 0.7812

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.4713 - accuracy: 0.8386 - val_loss: 0.4486 - val_accuracy: 0.8662
    Epoch 5/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4370 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.4586 - accuracy: 0.8486 - val_loss: 0.4370 - val_accuracy: 0.8944
    Epoch 6/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4199 - accuracy: 0.8125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.4394 - accuracy: 0.8500 - val_loss: 0.4262 - val_accuracy: 0.8944
    Epoch 7/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4986 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.4343 - accuracy: 0.8529 - val_loss: 0.4145 - val_accuracy: 0.8944
    Epoch 8/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4148 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.4115 - accuracy: 0.8729 - val_loss: 0.4024 - val_accuracy: 0.8944
    Epoch 9/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4671 - accuracy: 0.8125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.4050 - accuracy: 0.8800 - val_loss: 0.3929 - val_accuracy: 0.8944
    Epoch 10/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3837 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.3862 - accuracy: 0.8757 - val_loss: 0.3825 - val_accuracy: 0.9014
    Epoch 11/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3406 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 40ms/step - loss: 0.3849 - accuracy: 0.8786 - val_loss: 0.3721 - val_accuracy: 0.8944
    Epoch 12/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4771 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.3809 - accuracy: 0.8843 - val_loss: 0.3604 - val_accuracy: 0.8873
    Epoch 13/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2701 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.3546 - accuracy: 0.8943 - val_loss: 0.3500 - val_accuracy: 0.8873
    Epoch 14/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3281 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.3437 - accuracy: 0.8800 - val_loss: 0.3396 - val_accuracy: 0.8873
    Epoch 15/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3083 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.3358 - accuracy: 0.8971 - val_loss: 0.3297 - val_accuracy: 0.8944
    Epoch 16/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3327 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.3317 - accuracy: 0.8857 - val_loss: 0.3192 - val_accuracy: 0.9014
    Epoch 17/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5765 - accuracy: 0.7500

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.3162 - accuracy: 0.8986 - val_loss: 0.3095 - val_accuracy: 0.9014
    Epoch 18/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2843 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2995 - accuracy: 0.9071 - val_loss: 0.2993 - val_accuracy: 0.9014
    Epoch 19/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2878 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.2966 - accuracy: 0.9100 - val_loss: 0.2920 - val_accuracy: 0.9014
    Epoch 20/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1992 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.2784 - accuracy: 0.9200 - val_loss: 0.2861 - val_accuracy: 0.9014
    Epoch 21/40
    20/22 [==========================>...] - ETA: 0s - loss: 0.2821 - accuracy: 0.9187

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.2825 - accuracy: 0.9157 - val_loss: 0.2757 - val_accuracy: 0.9014
    Epoch 22/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4165 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 39ms/step - loss: 0.2696 - accuracy: 0.9100 - val_loss: 0.2668 - val_accuracy: 0.9085
    Epoch 23/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3015 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2600 - accuracy: 0.9229 - val_loss: 0.2569 - val_accuracy: 0.9155
    Epoch 24/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2037 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.2532 - accuracy: 0.9171 - val_loss: 0.2519 - val_accuracy: 0.9155
    Epoch 25/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2821 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.2464 - accuracy: 0.9157 - val_loss: 0.2415 - val_accuracy: 0.9085
    Epoch 26/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1643 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2406 - accuracy: 0.9157 - val_loss: 0.2358 - val_accuracy: 0.9225
    Epoch 27/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1865 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.2304 - accuracy: 0.9286 - val_loss: 0.2322 - val_accuracy: 0.9155
    Epoch 28/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1776 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2279 - accuracy: 0.9271 - val_loss: 0.2238 - val_accuracy: 0.9225
    Epoch 29/40
    21/22 [===========================>..] - ETA: 0s - loss: 0.2230 - accuracy: 0.9241

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.2304 - accuracy: 0.9243 - val_loss: 0.2175 - val_accuracy: 0.9225
    Epoch 30/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2401 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.2179 - accuracy: 0.9300 - val_loss: 0.2083 - val_accuracy: 0.9155
    Epoch 31/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1493 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2098 - accuracy: 0.9243 - val_loss: 0.1973 - val_accuracy: 0.9437
    Epoch 32/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1886 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2064 - accuracy: 0.9271 - val_loss: 0.1924 - val_accuracy: 0.9366
    Epoch 33/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2628 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 42ms/step - loss: 0.1884 - accuracy: 0.9371 - val_loss: 0.1895 - val_accuracy: 0.9366
    Epoch 34/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1475 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.1973 - accuracy: 0.9357 - val_loss: 0.1858 - val_accuracy: 0.9366
    Epoch 35/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1065 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.1878 - accuracy: 0.9343 - val_loss: 0.1845 - val_accuracy: 0.9366
    Epoch 36/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1977 - accuracy: 0.9357 - val_loss: 0.1846 - val_accuracy: 0.9366
    Epoch 37/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1455 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.1971 - accuracy: 0.9357 - val_loss: 0.1818 - val_accuracy: 0.9366
    Epoch 38/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1629 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.1782 - accuracy: 0.9329 - val_loss: 0.1817 - val_accuracy: 0.9366
    Epoch 39/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2361 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.1856 - accuracy: 0.9300 - val_loss: 0.1788 - val_accuracy: 0.9437
    Epoch 40/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1892 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.1801 - accuracy: 0.9314 - val_loss: 0.1781 - val_accuracy: 0.9437
    




    <keras.callbacks.History at 0x26b5ba58190>




```python
# train the data
shallow_nn_b.fit(x_train_b, y_train_b, validation_data=(x_val_b, y_val_b), epochs=40, callbacks=checkpoint)
```

    Epoch 1/40
    22/22 [==============================] - 0s 4ms/step - loss: 0.1693 - accuracy: 0.9371 - val_loss: 0.1781 - val_accuracy: 0.9437
    Epoch 2/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1794 - accuracy: 0.9329 - val_loss: 0.1782 - val_accuracy: 0.9437
    Epoch 3/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1999 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.1820 - accuracy: 0.9300 - val_loss: 0.1758 - val_accuracy: 0.9437
    Epoch 4/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1671 - accuracy: 0.9357 - val_loss: 0.1764 - val_accuracy: 0.9366
    Epoch 5/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1813 - accuracy: 0.9257 - val_loss: 0.1767 - val_accuracy: 0.9366
    Epoch 6/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1662 - accuracy: 0.9343 - val_loss: 0.1765 - val_accuracy: 0.9437
    Epoch 7/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1606 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.1777 - accuracy: 0.9371 - val_loss: 0.1749 - val_accuracy: 0.9437
    Epoch 8/40
    22/22 [==============================] - 0s 4ms/step - loss: 0.1606 - accuracy: 0.9286 - val_loss: 0.1775 - val_accuracy: 0.9366
    Epoch 9/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1764 - accuracy: 0.9271 - val_loss: 0.1776 - val_accuracy: 0.9366
    Epoch 10/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1762 - accuracy: 0.9357 - val_loss: 0.1769 - val_accuracy: 0.9366
    Epoch 11/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1773 - accuracy: 0.9329 - val_loss: 0.1760 - val_accuracy: 0.9437
    Epoch 12/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1648 - accuracy: 0.9314 - val_loss: 0.1762 - val_accuracy: 0.9366
    Epoch 13/40
    22/22 [==============================] - 0s 4ms/step - loss: 0.1646 - accuracy: 0.9357 - val_loss: 0.1755 - val_accuracy: 0.9366
    Epoch 14/40
    22/22 [==============================] - 0s 4ms/step - loss: 0.1561 - accuracy: 0.9471 - val_loss: 0.1754 - val_accuracy: 0.9366
    Epoch 15/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1557 - accuracy: 0.9386 - val_loss: 0.1770 - val_accuracy: 0.9296
    Epoch 16/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1762 - accuracy: 0.9229 - val_loss: 0.1780 - val_accuracy: 0.9296
    Epoch 17/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1554 - accuracy: 0.9357 - val_loss: 0.1770 - val_accuracy: 0.9296
    Epoch 18/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1623 - accuracy: 0.9329 - val_loss: 0.1769 - val_accuracy: 0.9296
    Epoch 19/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1622 - accuracy: 0.9329 - val_loss: 0.1771 - val_accuracy: 0.9296
    Epoch 20/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1698 - accuracy: 0.9257 - val_loss: 0.1787 - val_accuracy: 0.9225
    Epoch 21/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1518 - accuracy: 0.9400 - val_loss: 0.1786 - val_accuracy: 0.9225
    Epoch 22/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1490 - accuracy: 0.9429 - val_loss: 0.1753 - val_accuracy: 0.9366
    Epoch 23/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1633 - accuracy: 0.9400 - val_loss: 0.1758 - val_accuracy: 0.9366
    Epoch 24/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1516 - accuracy: 0.9343 - val_loss: 0.1764 - val_accuracy: 0.9366
    Epoch 25/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1435 - accuracy: 0.9386 - val_loss: 0.1763 - val_accuracy: 0.9296
    Epoch 26/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1722 - accuracy: 0.9286 - val_loss: 0.1758 - val_accuracy: 0.9296
    Epoch 27/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1461 - accuracy: 0.9386 - val_loss: 0.1773 - val_accuracy: 0.9296
    Epoch 28/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1570 - accuracy: 0.9400 - val_loss: 0.1786 - val_accuracy: 0.9225
    Epoch 29/40
    22/22 [==============================] - 0s 6ms/step - loss: 0.1541 - accuracy: 0.9400 - val_loss: 0.1790 - val_accuracy: 0.9225
    Epoch 30/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1509 - accuracy: 0.9400 - val_loss: 0.1794 - val_accuracy: 0.9296
    Epoch 31/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1553 - accuracy: 0.9371 - val_loss: 0.1793 - val_accuracy: 0.9366
    Epoch 32/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1585 - accuracy: 0.9386 - val_loss: 0.1789 - val_accuracy: 0.9225
    Epoch 33/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1503 - accuracy: 0.9457 - val_loss: 0.1814 - val_accuracy: 0.9225
    Epoch 34/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1496 - accuracy: 0.9386 - val_loss: 0.1828 - val_accuracy: 0.9225
    Epoch 35/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1479 - accuracy: 0.9471 - val_loss: 0.1840 - val_accuracy: 0.9225
    Epoch 36/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1587 - accuracy: 0.9429 - val_loss: 0.1830 - val_accuracy: 0.9225
    Epoch 37/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1529 - accuracy: 0.9471 - val_loss: 0.1831 - val_accuracy: 0.9225
    Epoch 38/40
    22/22 [==============================] - 0s 4ms/step - loss: 0.1526 - accuracy: 0.9343 - val_loss: 0.1833 - val_accuracy: 0.9225
    Epoch 39/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.1508 - accuracy: 0.9429 - val_loss: 0.1818 - val_accuracy: 0.9225
    Epoch 40/40
    22/22 [==============================] - 0s 2ms/step - loss: 0.1609 - accuracy: 0.9371 - val_loss: 0.1826 - val_accuracy: 0.9225
    




    <keras.callbacks.History at 0x26b5ad5b340>




```python
# shallow neural network (with 2 relus) performance: as good as the logistic regression model at capturing total frauds, but not as good at making accurate fraud predictions, which is
    # likely more mportant. So in this use case, the logistic regression model is better.
print(classification_report(y_val_b, neural_net_predictions(shallow_nn_b, x_val_b), target_names=['Not Fraud', 'Fraud']))
```

    5/5 [==============================] - 0s 998us/step
                  precision    recall  f1-score   support
    
       Not Fraud       0.96      0.89      0.92        72
           Fraud       0.89      0.96      0.92        70
    
        accuracy                           0.92       142
       macro avg       0.92      0.92      0.92       142
    weighted avg       0.92      0.92      0.92       142
    
    


```python
# create shallow neural netowrk model with only 1 relu
shallow_nn_b1 = Sequential()
shallow_nn_b1.add(InputLayer((x_train.shape[1],)))
shallow_nn_b1.add(Dense(1, 'relu'))
shallow_nn_b1.add(BatchNormalization())
shallow_nn_b1.add(Dense(1, 'sigmoid'))

checkpoint = ModelCheckpoint('shallow_nn_b1', save_best_only=True)
shallow_nn_b1.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
shallow_nn_b1.fit(x_train_b, y_train_b, validation_data=(x_val_b, y_val_b), epochs=40, callbacks=checkpoint)
```

    Epoch 1/40
     1/22 [>.............................] - ETA: 13s - loss: 0.8334 - accuracy: 0.3125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 2s 41ms/step - loss: 0.7941 - accuracy: 0.3357 - val_loss: 0.7222 - val_accuracy: 0.3099
    Epoch 2/40
     1/22 [>.............................] - ETA: 0s - loss: 0.7884 - accuracy: 0.2500

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 50ms/step - loss: 0.7775 - accuracy: 0.3343 - val_loss: 0.7171 - val_accuracy: 0.3310
    Epoch 3/40
    19/22 [========================>.....] - ETA: 0s - loss: 0.7648 - accuracy: 0.3388

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 41ms/step - loss: 0.7625 - accuracy: 0.3443 - val_loss: 0.7131 - val_accuracy: 0.3521
    Epoch 4/40
     1/22 [>.............................] - ETA: 0s - loss: 0.7734 - accuracy: 0.3438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 35ms/step - loss: 0.7567 - accuracy: 0.3529 - val_loss: 0.7050 - val_accuracy: 0.4014
    Epoch 5/40
     1/22 [>.............................] - ETA: 0s - loss: 0.7811 - accuracy: 0.3438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.7457 - accuracy: 0.3600 - val_loss: 0.6938 - val_accuracy: 0.4155
    Epoch 6/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6741 - accuracy: 0.5000

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 39ms/step - loss: 0.7347 - accuracy: 0.3757 - val_loss: 0.6851 - val_accuracy: 0.4225
    Epoch 7/40
     1/22 [>.............................] - ETA: 0s - loss: 0.7726 - accuracy: 0.2500

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.7209 - accuracy: 0.4014 - val_loss: 0.6785 - val_accuracy: 0.4366
    Epoch 8/40
    17/22 [======================>.......] - ETA: 0s - loss: 0.7217 - accuracy: 0.4062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 43ms/step - loss: 0.7178 - accuracy: 0.4100 - val_loss: 0.6734 - val_accuracy: 0.4437
    Epoch 9/40
    21/22 [===========================>..] - ETA: 0s - loss: 0.7073 - accuracy: 0.4137

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.7059 - accuracy: 0.4229 - val_loss: 0.6669 - val_accuracy: 0.4718
    Epoch 10/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6848 - accuracy: 0.5000

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.6933 - accuracy: 0.4557 - val_loss: 0.6622 - val_accuracy: 0.4859
    Epoch 11/40
     1/22 [>.............................] - ETA: 0s - loss: 0.7017 - accuracy: 0.3125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.6839 - accuracy: 0.4786 - val_loss: 0.6584 - val_accuracy: 0.4930
    Epoch 12/40
    17/22 [======================>.......] - ETA: 0s - loss: 0.6822 - accuracy: 0.5092

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 50ms/step - loss: 0.6856 - accuracy: 0.5043 - val_loss: 0.6549 - val_accuracy: 0.5141
    Epoch 13/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6540 - accuracy: 0.6562

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 50ms/step - loss: 0.6757 - accuracy: 0.5329 - val_loss: 0.6514 - val_accuracy: 0.5423
    Epoch 14/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6849 - accuracy: 0.4375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.6720 - accuracy: 0.5514 - val_loss: 0.6482 - val_accuracy: 0.5634
    Epoch 15/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6437 - accuracy: 0.6875

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 35ms/step - loss: 0.6663 - accuracy: 0.5729 - val_loss: 0.6442 - val_accuracy: 0.5986
    Epoch 16/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6545 - accuracy: 0.5938

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 40ms/step - loss: 0.6617 - accuracy: 0.5971 - val_loss: 0.6415 - val_accuracy: 0.6127
    Epoch 17/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6396 - accuracy: 0.6562

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 42ms/step - loss: 0.6555 - accuracy: 0.6129 - val_loss: 0.6367 - val_accuracy: 0.6268
    Epoch 18/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6338 - accuracy: 0.7188

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.6487 - accuracy: 0.6529 - val_loss: 0.6308 - val_accuracy: 0.6831
    Epoch 19/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6427 - accuracy: 0.6250

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.6409 - accuracy: 0.6800 - val_loss: 0.6238 - val_accuracy: 0.7042
    Epoch 20/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6104 - accuracy: 0.7812

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.6345 - accuracy: 0.6871 - val_loss: 0.6144 - val_accuracy: 0.7394
    Epoch 21/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6463 - accuracy: 0.6562

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.6268 - accuracy: 0.7071 - val_loss: 0.6043 - val_accuracy: 0.7606
    Epoch 22/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6132 - accuracy: 0.7500

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.6133 - accuracy: 0.7257 - val_loss: 0.5925 - val_accuracy: 0.8169
    Epoch 23/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5997 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.6054 - accuracy: 0.7414 - val_loss: 0.5820 - val_accuracy: 0.8451
    Epoch 24/40
     1/22 [>.............................] - ETA: 0s - loss: 0.6089 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 45ms/step - loss: 0.5955 - accuracy: 0.7657 - val_loss: 0.5717 - val_accuracy: 0.8803
    Epoch 25/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5635 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.5843 - accuracy: 0.7714 - val_loss: 0.5618 - val_accuracy: 0.8944
    Epoch 26/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5927 - accuracy: 0.6875

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.5747 - accuracy: 0.7771 - val_loss: 0.5519 - val_accuracy: 0.8944
    Epoch 27/40
    15/22 [===================>..........] - ETA: 0s - loss: 0.5628 - accuracy: 0.7833

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 41ms/step - loss: 0.5686 - accuracy: 0.7900 - val_loss: 0.5419 - val_accuracy: 0.8944
    Epoch 28/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5844 - accuracy: 0.7812

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 42ms/step - loss: 0.5550 - accuracy: 0.8000 - val_loss: 0.5324 - val_accuracy: 0.8944
    Epoch 29/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5095 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.5452 - accuracy: 0.8029 - val_loss: 0.5226 - val_accuracy: 0.8944
    Epoch 30/40
    18/22 [=======================>......] - ETA: 0s - loss: 0.5385 - accuracy: 0.8160

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.5351 - accuracy: 0.8157 - val_loss: 0.5130 - val_accuracy: 0.8944
    Epoch 31/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5082 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 39ms/step - loss: 0.5263 - accuracy: 0.8186 - val_loss: 0.5032 - val_accuracy: 0.8944
    Epoch 32/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5190 - accuracy: 0.7812

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 39ms/step - loss: 0.5157 - accuracy: 0.8214 - val_loss: 0.4932 - val_accuracy: 0.8944
    Epoch 33/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5036 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.5121 - accuracy: 0.8271 - val_loss: 0.4837 - val_accuracy: 0.8944
    Epoch 34/40
     1/22 [>.............................] - ETA: 0s - loss: 0.5602 - accuracy: 0.7188

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.4969 - accuracy: 0.8243 - val_loss: 0.4743 - val_accuracy: 0.8944
    Epoch 35/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4816 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 47ms/step - loss: 0.4898 - accuracy: 0.8429 - val_loss: 0.4641 - val_accuracy: 0.8944
    Epoch 36/40
    19/22 [========================>.....] - ETA: 0s - loss: 0.4811 - accuracy: 0.8257

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 42ms/step - loss: 0.4800 - accuracy: 0.8357 - val_loss: 0.4546 - val_accuracy: 0.8944
    Epoch 37/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4448 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 49ms/step - loss: 0.4661 - accuracy: 0.8529 - val_loss: 0.4451 - val_accuracy: 0.8944
    Epoch 38/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4332 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 37ms/step - loss: 0.4626 - accuracy: 0.8486 - val_loss: 0.4363 - val_accuracy: 0.8944
    Epoch 39/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4063 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.4558 - accuracy: 0.8457 - val_loss: 0.4276 - val_accuracy: 0.9014
    Epoch 40/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4412 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.4403 - accuracy: 0.8629 - val_loss: 0.4186 - val_accuracy: 0.9014
    




    <keras.callbacks.History at 0x26b5ab507c0>




```python
# train the data
shallow_nn_b1.fit(x_train_b, y_train_b, validation_data=(x_val_b, y_val_b), epochs=40, callbacks=checkpoint)
```

    Epoch 1/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4227 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.4340 - accuracy: 0.8571 - val_loss: 0.4106 - val_accuracy: 0.9014
    Epoch 2/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4175 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.4229 - accuracy: 0.8543 - val_loss: 0.4026 - val_accuracy: 0.9085
    Epoch 3/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3446 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 35ms/step - loss: 0.4068 - accuracy: 0.8657 - val_loss: 0.3944 - val_accuracy: 0.9014
    Epoch 4/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3630 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.3928 - accuracy: 0.8671 - val_loss: 0.3864 - val_accuracy: 0.9085
    Epoch 5/40
     1/22 [>.............................] - ETA: 0s - loss: 0.4183 - accuracy: 0.8125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.3975 - accuracy: 0.8586 - val_loss: 0.3791 - val_accuracy: 0.9085
    Epoch 6/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3747 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 41ms/step - loss: 0.3810 - accuracy: 0.8714 - val_loss: 0.3719 - val_accuracy: 0.9085
    Epoch 7/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3936 - accuracy: 0.7812

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.3634 - accuracy: 0.8857 - val_loss: 0.3659 - val_accuracy: 0.9014
    Epoch 8/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2901 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 38ms/step - loss: 0.3574 - accuracy: 0.8771 - val_loss: 0.3597 - val_accuracy: 0.9014
    Epoch 9/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2692 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.3411 - accuracy: 0.8914 - val_loss: 0.3543 - val_accuracy: 0.9085
    Epoch 10/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3711 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.3435 - accuracy: 0.8857 - val_loss: 0.3491 - val_accuracy: 0.8944
    Epoch 11/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3373 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 40ms/step - loss: 0.3368 - accuracy: 0.8843 - val_loss: 0.3440 - val_accuracy: 0.9014
    Epoch 12/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2787 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 43ms/step - loss: 0.3213 - accuracy: 0.8986 - val_loss: 0.3392 - val_accuracy: 0.9085
    Epoch 13/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2747 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.3063 - accuracy: 0.8943 - val_loss: 0.3337 - val_accuracy: 0.9014
    Epoch 14/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3974 - accuracy: 0.7500

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 38ms/step - loss: 0.3073 - accuracy: 0.9000 - val_loss: 0.3273 - val_accuracy: 0.9155
    Epoch 15/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2876 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2963 - accuracy: 0.9100 - val_loss: 0.3207 - val_accuracy: 0.9155
    Epoch 16/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3604 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2904 - accuracy: 0.9100 - val_loss: 0.3106 - val_accuracy: 0.9155
    Epoch 17/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3826 - accuracy: 0.8125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 42ms/step - loss: 0.2946 - accuracy: 0.8986 - val_loss: 0.3000 - val_accuracy: 0.9155
    Epoch 18/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2659 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 36ms/step - loss: 0.2788 - accuracy: 0.9100 - val_loss: 0.2921 - val_accuracy: 0.9155
    Epoch 19/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2789 - accuracy: 0.8125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2749 - accuracy: 0.9043 - val_loss: 0.2800 - val_accuracy: 0.9085
    Epoch 20/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2632 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.2783 - accuracy: 0.9043 - val_loss: 0.2764 - val_accuracy: 0.9085
    Epoch 21/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3101 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2579 - accuracy: 0.9214 - val_loss: 0.2715 - val_accuracy: 0.9085
    Epoch 22/40
    17/22 [======================>.......] - ETA: 0s - loss: 0.2521 - accuracy: 0.9136

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.2718 - accuracy: 0.9029 - val_loss: 0.2638 - val_accuracy: 0.9155
    Epoch 23/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3557 - accuracy: 0.8125

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2639 - accuracy: 0.9171 - val_loss: 0.2599 - val_accuracy: 0.9155
    Epoch 24/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2547 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.2583 - accuracy: 0.9200 - val_loss: 0.2578 - val_accuracy: 0.9085
    Epoch 25/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2510 - accuracy: 0.9375

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.2545 - accuracy: 0.9171 - val_loss: 0.2512 - val_accuracy: 0.9155
    Epoch 26/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2387 - accuracy: 0.8750

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2470 - accuracy: 0.9171 - val_loss: 0.2487 - val_accuracy: 0.9155
    Epoch 27/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2435 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2583 - accuracy: 0.9129 - val_loss: 0.2444 - val_accuracy: 0.9225
    Epoch 28/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.2509 - accuracy: 0.9157 - val_loss: 0.2453 - val_accuracy: 0.9155
    Epoch 29/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1759 - accuracy: 1.0000

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 39ms/step - loss: 0.2391 - accuracy: 0.9186 - val_loss: 0.2394 - val_accuracy: 0.9155
    Epoch 30/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2019 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 31ms/step - loss: 0.2364 - accuracy: 0.9200 - val_loss: 0.2389 - val_accuracy: 0.9155
    Epoch 31/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2531 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 34ms/step - loss: 0.2321 - accuracy: 0.9200 - val_loss: 0.2350 - val_accuracy: 0.9155
    Epoch 32/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3025 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2279 - accuracy: 0.9300 - val_loss: 0.2305 - val_accuracy: 0.9155
    Epoch 33/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1406 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2315 - accuracy: 0.9229 - val_loss: 0.2288 - val_accuracy: 0.9155
    Epoch 34/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3463 - accuracy: 0.8438

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.2274 - accuracy: 0.9257 - val_loss: 0.2269 - val_accuracy: 0.9155
    Epoch 35/40
     1/22 [>.............................] - ETA: 0s - loss: 0.3256 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 33ms/step - loss: 0.2171 - accuracy: 0.9286 - val_loss: 0.2256 - val_accuracy: 0.9225
    Epoch 36/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2342 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.2359 - accuracy: 0.9186 - val_loss: 0.2223 - val_accuracy: 0.9225
    Epoch 37/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.2190 - accuracy: 0.9329 - val_loss: 0.2231 - val_accuracy: 0.9225
    Epoch 38/40
    22/22 [==============================] - 0s 3ms/step - loss: 0.2252 - accuracy: 0.9200 - val_loss: 0.2243 - val_accuracy: 0.9155
    Epoch 39/40
     1/22 [>.............................] - ETA: 0s - loss: 0.1931 - accuracy: 0.9688

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 30ms/step - loss: 0.2259 - accuracy: 0.9286 - val_loss: 0.2169 - val_accuracy: 0.9155
    Epoch 40/40
     1/22 [>.............................] - ETA: 0s - loss: 0.2404 - accuracy: 0.9062

    WARNING:absl:Found untraced functions such as _update_step_xla while saving (showing 1 of 1). These functions will not be directly callable after loading.
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    INFO:tensorflow:Assets written to: shallow_nn_b1\assets
    

    22/22 [==============================] - 1s 32ms/step - loss: 0.2169 - accuracy: 0.9243 - val_loss: 0.2144 - val_accuracy: 0.9155
    




    <keras.callbacks.History at 0x26b5abc7490>




```python
# shallow neural network (with 1 relu) performance: fraud predictions are more accurate than the neural network with 2 relu's, but it is not as good at capturing total frauds, which
    # is likely more important. So the neural network with 2 relu's is better for this use case.
print(classification_report(y_val_b, neural_net_predictions(shallow_nn_b1, x_val_b), target_names=['Not Fraud', 'Fraud']))
```

    5/5 [==============================] - 0s 1ms/step
                  precision    recall  f1-score   support
    
       Not Fraud       0.89      0.94      0.92        72
           Fraud       0.94      0.89      0.91        70
    
        accuracy                           0.92       142
       macro avg       0.92      0.92      0.92       142
    weighted avg       0.92      0.92      0.92       142
    
    


```python
# random forest performance: all predicted frauds were correct, but the model is pretty bad (nearly 50/50) at capturing total frauds, which is important 
rf_b = RandomForestClassifier(max_depth=2, n_jobs=-1)
rf_b.fit(x_train_b, y_train_b)
print(classification_report(y_val_b, rf.predict(x_val_b), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       0.69      1.00      0.82        72
           Fraud       1.00      0.54      0.70        70
    
        accuracy                           0.77       142
       macro avg       0.85      0.77      0.76       142
    weighted avg       0.84      0.77      0.76       142
    
    


```python
# gradient boosting classifer performance: better than random forest, but still not good at capturing total frauds
gbc_b = GradientBoostingClassifier(n_estimators=50, learning_rate=1.0, max_depth=2, random_state=0)
gbc_b.fit(x_train_b, y_train_b)
print(classification_report(y_val_b, gbc.predict(x_val_b), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       0.81      1.00      0.89        72
           Fraud       1.00      0.76      0.86        70
    
        accuracy                           0.88       142
       macro avg       0.90      0.88      0.88       142
    weighted avg       0.90      0.88      0.88       142
    
    


```python
# support vector machine performance: better than both random forest and gradient boosting classifer, but still not good at capturing total frauds
svc_b = LinearSVC(class_weight='balanced')
svc_b.fit(x_train_b, y_train_b)
print(classification_report(y_val_b, svc.predict(x_val_b), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       0.88      1.00      0.94        72
           Fraud       1.00      0.86      0.92        70
    
        accuracy                           0.93       142
       macro avg       0.94      0.93      0.93       142
    weighted avg       0.94      0.93      0.93       142
    
    

    c:\Users\todda\Desktop\Desktop\Career General\My Companies\BlockWatch\credit_fraud_detection\myvenv\lib\site-packages\sklearn\svm\_base.py:1244: ConvergenceWarning: Liblinear failed to converge, increase the number of iterations.
      warnings.warn(
    


```python
# We will choose the *logistic regression model* as the final model since it performed the best, as it captured the largest percentage of total fraud transactions (96% of fraud
    # transactions were captured) and made the most accurate fraud predictions (93% of fraud predections were correct).
print(classification_report(y_val_b, logistic_model_b.predict(x_val_b), target_names=['Not Fraud', 'Fraud']))
```

                  precision    recall  f1-score   support
    
       Not Fraud       0.96      0.93      0.94        72
           Fraud       0.93      0.96      0.94        70
    
        accuracy                           0.94       142
       macro avg       0.94      0.94      0.94       142
    weighted avg       0.94      0.94      0.94       142
    
    
