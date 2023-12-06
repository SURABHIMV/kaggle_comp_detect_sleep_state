# 😴 Child Mind Institute - Detect Sleep States

Detect sleep onset and wake events from wrist-worn accelerometer data.

## 🛣️ Roadmap to reproduce the result

The dataset provided by the competition is very large. The above-mentioned notebooks are executed on Kaggle (with GPU P100). dataprepare.ipynb is the data preparation notebook, and the data extracted from this notebook is utilized during the training of the model in wavenet-train.ipynb (containing the WaveNet model) or cnn-rnn.ipynb (containing a CNN-RNN-based model). The output of wavenet-train.ipynb or cnn-rnn.ipynb notebook comprises the best-trained model. This trained model is then employed in the inference notebook to test the results using the test data provided by the competition.

## 📝Files

* `dataprepare.ipynb`: In the data preparation notebook includes code for data loading, cleaning, optimization, and storing each series_id of continuous data in a list and the events (onset and wakeup step) within that series_id in tuple format in another list.
  
* `wavenet-train.ipynb, cnn-rnn.ipynb`: In the data training notebook, new features are engineered as part of feature engineering. The given problem is considered as a regression task, two dependent variables are formed, one for the onset event and the other for the wakeup event. It is assumed that the data around the onset and wakeup transitioning time share a common pattern. The occurrence of these events is treated as a Gaussian pattern. If the model identifies this peak, it also finds its centroid. Once the dataset is prepared according to the WaveNet model(in notebook wavenet-train.ipynb) or CNN and RNN based model(in notebook cnn-rnn.ipynb) requirements, the model is trained, and the best model is stored.

* `wavenet-infr.ipynb, cnn-rnn-infr.ipynb`: In inference notebook contains code for how the trained model (WaveNet in notebook wavenet-infr.ipynb) or (CNN and RNN based model in notebook cnn-rnn.ipynb) is tested with test data and tried to extract the longest event in a day.

## 📚 Libraries and Versions

The dataset provided in the competition was very large, so all the notebooks were executed on Kaggle (with GPU P100). Kaggle has all the necessary built-in libraries.




  







