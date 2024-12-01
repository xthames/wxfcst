# **wxfcst**
Repository to house processed weather forecast and observation data. Forecast data comes from the NWS API -- specifically the `api.weather.gov/gridpoints` set -- in 48 hour chunks; observations come from a backyard personal weather station (PWS). All efforts have been made to place the PWS in an optimal space for data collection, but close positioning of neighboring homes may slightly bias certain properties (ex: wind direction).

## **Data Variables**
#### **General**
- `DOY CYCLE`: the fractional day of the year in UTC mapped to a basic sinusoid to relate like seasonality. The exact formula is: `DOY CYCLE` $= - \cos(2\pi * \frac{\mathrm{DOY_{frac}}}{366})$, where $\mathrm{DOY_{frac}} = \mathrm{DOY_{int}} + \frac{\mathrm{HOUR}}{24}$
#### **FCST**
All variables with the `FCST` prefix are sourced from the NWS.
- `FCST AHEAD`: number of hours ahead the forecast is projecting from the `DOY CYCLE` timestamp
- `FCST TEMP`: forecasted temperature. Units are in \[ $^{\circ}\mathrm{C}$ \]
- `FCST RH`: forecasted relative humidity. Units are in \[ % \], $\in\ [0, 100]$
- `FCST SKYC`: forecasted sky coverage. Units are in \[ % \], $\in\ [0, 100]$
- `FCST WDIR`: forecasted wind direction. Units are in \[ $^{\circ}$ \], azimuthal from north
- `FCST WSPD`: forecasted wind speed. Units are in \[ $\mathrm{km\ hr^{-1}}$ \]
- `FCST WGST`: forecasted wind gusts. Units are in \[ $\mathrm{km\ hr^{-1}}$ \]
- `FCST PPCT`: forecasted precipitation chance. Units are in \[ % \], $\in\ [0, 100]$
- `FCST PRCP`: forecasted quantitative precipitation. Units are in \[ mm \]
- `FCST SNOW`: forecasted snow accumulation. Units are in \[ mm \]
#### **WX**
All variables with the `WX` prefix are sourced from the PWS.
- `WX TEMP`: observed temperature. Units are in \[ $^{\circ}\mathrm{C}$ \]
- `WX RH`: observed relative humidity. Units are in \[ % \], $\in\ [0, 100]$
- `WX WSPD`: observed wind speed. Units are in \[ $\mathrm{km\ hr^{-1}}$ \]
- `WX WGST`: observed wind gusts. Units are in \[ $\mathrm{km\ hr^{-1}}$ \]
- `WX WDIR`: observed wind direction. Units are in \[ $^{\circ}$ \], azimuthal from north
- `WX UV`: observed UV index. Units are \[ - \]
- `WX PRCP`: observed quantitative precipitation. Units are in \[ mm \]
- `WX RELP`: observed relative atmospheric pressure. Units are in \[ hPa \]
