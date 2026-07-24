# Dataframe: `YC:fed_yield_curve` - Federal Reserve Yield Curve Parameters

Daily Nelson-Siegel-Svensson yield curve parameters (BETA0-BETA3, TAU1, TAU2) estimated by Gurkaynak, Sack, and Wright, published by the Federal Reserve Board.


## DataFrame Glimpse

```
Rows: 16983
Columns: 31
$ SVENY01          <f64> 4.0611
$ SVENY02          <f64> 4.1005
$ SVENY03          <f64> 4.1503
$ SVENY04          <f64> 4.208
$ SVENY05          <f64> 4.2716
$ SVENY06          <f64> 4.3391
$ SVENY07          <f64> 4.4091
$ SVENY08          <f64> 4.4802
$ SVENY09          <f64> 4.5512
$ SVENY10          <f64> 4.6212
$ SVENY11          <f64> 4.6894
$ SVENY12          <f64> 4.7551
$ SVENY13          <f64> 4.8177
$ SVENY14          <f64> 4.8769
$ SVENY15          <f64> 4.9323
$ SVENY16          <f64> 4.9836
$ SVENY17          <f64> 5.0307
$ SVENY18          <f64> 5.0734
$ SVENY19          <f64> 5.1117
$ SVENY20          <f64> 5.1455
$ SVENY21          <f64> 5.1749
$ SVENY22          <f64> 5.1998
$ SVENY23          <f64> 5.2205
$ SVENY24          <f64> 5.2369
$ SVENY25          <f64> 5.2492
$ SVENY26          <f64> 5.2575
$ SVENY27          <f64> 5.262
$ SVENY28          <f64> 5.2628
$ SVENY29          <f64> 5.2601
$ SVENY30          <f64> 5.2541
$ Date    <datetime[ns]> 2026-07-17 00:00:00


```

## Dataframe Manifest

| Dataframe Name                 | Federal Reserve Yield Curve Parameters                                                   |
|--------------------------------|--------------------------------------------------------------------------------------|
| Dataframe ID                   | [fed_yield_curve](../dataframes/YC/fed_yield_curve.md)                                       |
| Data Sources                   | Federal Reserve                                        |
| Data Providers                 | Federal Reserve Board                                      |
| Links to Providers             | https://www.federalreserve.gov/data/nominal-yield-curve.htm                             |
| Topic Tags                     | Treasury, Yield Curve, Federal Reserve                                          |
| Type of Data Access            |                                   |
| How is data pulled?            | Web download via Python                                                    |
| Data available up to (min)     | None                                                             |
| Data available up to (max)     | None                                                             |
| Dataframe Path                 | C:\dev\hw3-marijajov65\_data\fed_yield_curve.parquet                                                   |


**Linked Charts:**

- None


## Pipeline Manifest

| Pipeline Name                   | Treasury Securities and the Yield Curve                       |
|---------------------------------|--------------------------------------------------------|
| Pipeline ID                     | [YC](../../../index.md)              |
| Lead Pipeline Developer         | Jeremiah Bejarano             |
| Contributors                    | Jeremiah Bejarano           |
| Git Repo URL                    |                         |
| Pipeline Web Page               | <a href="file://C:/dev/hw3-marijajov65/docs/index.html">Pipeline Web Page      |
| Date of Last Code Update        | 2026-07-24 01:24:24           |
| OS Compatibility                |  |
| Linked Dataframes               |  [YC:crsp_treasury_consolidated](../../dataframes/YC/crsp_treasury_consolidated.md)<br>  [YC:fed_yield_curve](../../dataframes/YC/fed_yield_curve.md)<br>  |


