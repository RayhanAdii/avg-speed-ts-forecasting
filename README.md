# avg-speed-ts-forecasting
Time Series Forecasting of Average Vehicle Speed for Ristek Datathon 2023 Competition

## Tujuan
Project ini bertujuan untuk melakukan time series forecasting tentang kecepatan rata-rata kendaraan pada suatu jalan. Project ini 

## Dataset
Dataset utama yang digunakan dalam project ini disediakan oleh [Ristek Datathon 2023](https://www.kaggle.com/competitions/ristek-datathon-2023). Dataset yang digunakan merupakan data time series untuk berbagai jalan dengan titik mulai dan titik akhir.

Selain dataset utama, digunakan pula data external tambahan yang diimport dari Open Street Map. Dataset berikut menyimpan beberapa feature yaitu highway, lanes, dan maxspeed. Dataset external yang telah diimport dapat diunduh pada link [berikut](https://drive.google.com/file/d/1c51EIcPUMZixans9Q1s1RASJca9Vbhh0/view?usp=share_link)

⚠️ Penting ⚠️
Harap unduh kedua dataset terlebih dahulu untuk dapat menjalankan project berikut. Unduh kedua file tersebut lalu letakkan dalam folder dataset/.

## Pendekatan
Model yang digunakan dalam Time Series Forecasting kali ini menggunakan dua pendekatan, yaitu menggunakan model Machine Learning Random Forest dan Timeseries AutoML Autogluon. 

## Evaluasi dan Hasil
Evaluasi pada pemodelan kali ini menggunakan metrics sMAPE. Implementasi sMAPE pada Python dapat ditunjukkan pada code berikut
```python
import numpy as np

def smape(actual, forecast):
    return 100 * np.mean(2 * np.abs(actual - forecast) / (np.abs(actual) + np.abs(forecast)))
```

Berikut merupakan hasil pemodelan menggunakan berbagai model

| Model | Public Test Score (30% test data) | Private Test Score (70% test data)
| -------- | -------  | ------ |
| Random Forest | 9.43 | 8.33 |
| Autogluon TimeSeries | 11.06 | 9.04 |

