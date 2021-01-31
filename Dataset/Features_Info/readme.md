This module contains the introduction of station information and data characteristics.



### StationInfo.csv

`StationInfo.csv`  covers a total of 159 stations in the target area (22°N -34°N, 98°E -107°E).

**Columns**

|    Column     |                         Description                          |
| :-----------: | :----------------------------------------------------------: |
|    `Title`    |                         Station name                         |
|  `StationID`  |                          Station ID                          |
|  `Longitude`  |                  East Longitude of station                   |
|  `Latitude`   |                  North Latitude of station                   |
|  `MagnData`   |            Station contains electromagnetic data             |
| `MagnUpdate`  | Station still updating electromagnetic data after Jan 1st, 2020 |
|  `SoundData`  |              Station contains geoacoustic data               |
| `SoundUpdate` | Station still updating geoacoustic data after Jan 1st, 2020  |

**remarks**

1. AETA stations are installed at different time, so the beginning time of data in each station is different.

2. During the past four years, some stations are moved or closed, and these stations no longer update their data.

3. In the past four years, short-term power outages or breakdown due to weather and environmental affection, so the timestamps of data may be discontinuous.

   

### DataFeatureInfo

Contains a compressed file of electromagnetic data ( `EM_20170101-20201130.zip` ) and a compressed file of geoacoustic data ( `GA_20170101-20201130.zip` ).

Take `EM_20170101-20201130.zip` as an example to introduce the contents of compressed files：

> 19_magn.zip（StationID_SignalType）
>
> >19_magn.csv（StationID_SignalType）
>
> 24_magn.zip
>
> ......
>
> 60251_magn.zip

There are two SignalType, magn represents EM signal and sound represents GA signal.

There are 51 types of electromagnetic features and 44 types of geoacoustic features.

**Feature description**

EMDTD : Electromagnetic disturbance time domain

EMDFD : Electromagnetic disturbance frequency domain

EMDWT : Electromagnetic disturbance wavelet transform

GAOTD : Geoacoustic original time domain

GAFD : Geoacoustic frequency domain

GAWT : Geoacoustic wavelet transform

|  Feature type   |        column         |                        description                         | number of EM features | number of GA features |
| :-------------: | :-------------------: | :--------------------------------------------------------: | :-------------------: | :-------------------: |
| `EMDTD`/`GAOTD` |          var          |                          Variance                          |           2           |           1           |
| `EMDTD`/`GAOTD` |         power         |                           Power                            |           2           |           1           |
| `EMDTD`/`GAOTD` |         skew          |                          Skewness                          |           2           |           1           |
| `EMDTD`/`GAOTD` |         kurt          |                          Kurtosis                          |           2           |           1           |
| `EMDTD`/`GAOTD` |         mean          |                            Mean                            |           0           |           1           |
| `EMDTD`/`GAOTD` |        abs_max        |                   Maximum absolute value                   |           2           |           1           |
| `EMDTD`/`GAOTD` |       abs_mean        |                    Mean absolute value                     |           2           |           1           |
| `EMDTD`/`GAOTD` |       abs_top_x       |                Absolute maximum x% position                |           4           |           2           |
| `EMDTD`/`GAOTD` |      energy_sstd      |            Short-term energy standard deviation            |           2           |           1           |
| `EMDTD`/`GAOTD` |      energy_smax      |                 Maximum short-term energy                  |           2           |           1           |
| `EMDTD`/`GAOTD` |      s_zero_rate      |             Mean short-term zero-crossing rate             |           0           |           1           |
| `EMDTD`/`GAOTD` |    s_zero_rate_max    |           Maximum short-time zero-crossing rate            |           0           |           1           |
| `EMDFD`/`GAFD`  |    power_rate_atob    |                        a~bHz power                         |          11           |          11           |
| `EMDFD`/`GAFD`  |   frequency_center    |                Center of gravity frequency                 |           1           |           1           |
| `EMDFD`/`GAFD`  | mean_square_frequency |                   Mean square frequency                    |           1           |           1           |
| `EMDFD`/`GAFD`  |  variance_frequency   |                     Frequency variance                     |           1           |           1           |
| `EMDFD`/`GAFD`  |   frequency_entropy   |                     Frequency entropy                      |           1           |           1           |
| `EMDWT`/`GAWT`  |    levelx_absmean     | Mean absolute value after reconstruction of the xth level  |           4           |           4           |
| `EMDWT`/`GAWT`  |     levelx_energy     |        Energy after reconstruction of the xth level        |           4           |           4           |
| `EMDWT`/`GAWT`  |  levelx_energy_svar   |  Variance of energy after reconstruction of the xth level  |           4           |           4           |
| `EMDWT`/`GAWT`  |  levelx_energy_smax   | Maximum energy value after reconstruction of the xth level |           4           |           4           |
|      total      |                       |                                                            |          51           |          44           |

**remarks**

1. The features extracted from the original signal are divided into three categories: time domain related features, frequency domain related features, and wavelet transform related features.
