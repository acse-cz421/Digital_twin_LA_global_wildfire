# IRP-ca421

## About The Project

The occurrence of forest fires can cause severe damage to the vegetation as well as to the soil in the ecosystem and can also indirectly affect the climate. The analysis of the interaction between wildfires and environmental factors is used to predict the occurrence of fires, which is the current JULES-INFERNO project. However, this prediction project uses mathematical methods to simulate vegetation and the environment, so that it can suffer from modelling difficulties and high computational costs. Deep learning models have an advantage in handling large amounts of data. They can reduce the computational cost of subsequent prediction models by extracting data features through Reduced Order Modelling (ROM) and compressing the data to a low-dimensional latent space. Therefore, this study proposes a JULES-INFERNO-based surrogate model based on ROM, deep learning prediction networks and Latent data Assimilation to improve the efficiency of physical wildfire prediction models.

## Getting Started

### Hardware requirement

*   Programming language: Python (3.5 or higher)
*   Platform: Google Colab Pro
*   GPU: P100
*   Google Drive space: 200GB

### Software requirement

| Package Requirement                        |
|--------------------------------------------|
| os                                         |
| pandas                                     |
| math                                       |
| numpy                                      |
| netCDF4                                    |
| seaborn                                    |
| matplotlib                                 |
| tensorflow                                 |
| keras                                      |
| sklearn                                    |


## Dataset
All data for this project are from the JULES-INFERNO project. URL:
(https://imperiallondon-my.sharepoint.com/:f:/r/personal/mk1812_ic_ac_uk/Documents/Data/JULES-INFERNO?csf=1&web=1&e=3YXM21)


Four climate variables from 1961 to 1990: 
temperature (``LGM/drive/climate/CRU-NCEP-v7-LGM-n96e/tair``), humidity (``LGM/drive/climate/CRU-NCEP-v7-LGM-n96e/qair``), rainfall (``LGM/drive/climate/CRU-NCEP-v7-LGM-n96e/rain``) and lightning (``LGM/drive/lightning``). Additionally, each dataset contaions 360 snapshot, each size of snapshot is 144*192.


Five wildfire (Grid box mean burnt area fraction) datasets from 1961 to 1990: P1(``LGM/output/p1``), P2(``LGM/output/p2``), P2(``LGM/output/p2``), P3(``LGM/output/p1``), P4(``LGM/output/p4``) and P5(``LGM/output/p5``). Each set was driven by the same climatic conditions (1961 to 1990). However, JULES-INFERNO applied different initial internal states to ensure the robustness of its model; the internal state of P_1 was randomized, and the initial internal states of the subsequent experimental results were all the last internal states of the previous one. Therefore, although each result was for 1961-1990, there was variability.  Additionally, each dataset contaions 360 snapshot, each size of snapshot is 112*192.


## Submission

In the repository, the final report is in `/reports`. 

The code to implement this project is in the `/source`.

Pre-processing for data: `/Source/JULES_Data_preprocessing.ipynb`.

The 20-dinmentional Convolutional Autoencoder (CAE) surrogaete model: `/Source/JULES_CAE_LSTM_20.ipynb`.

The 100-dinmentional CAE surrogaete model: `/Source/JULES_CAE_LSTM_100.ipynb`.

The 20-dinmentional Principal Component Analysis (PCA) surrogaete model: `/Source/JULES_PCA_LSTM_20.ipynb`.

The 100-dinmentional PCA surrogaete model: `/Source/JULES_PCA_LSTM_100.ipynb`.

Apart from that the, files for constructing CAEs on climate data are in the `/Source/Climate_CAE_construction` folder. The `/Source/JULES` folder holds the trained models for this project. The `/Source/output_figure` folder holds the output images for this project.

## License

MIT License. More information see `LICENSE`


## Contact

Caili Zhong - caili.zhong21@imperial.ac.uk<br>
Sibo Cheng - sibo.cheng@imperial.ac.uk<br>
Matthewm Kasoar - m.kasoar12@imperial.ac.uk<br>
