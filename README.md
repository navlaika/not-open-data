# not-open-data

Tas, kas nav atvēries līdz galam.

## Latvijas Republikas administratīvi teritoriālais iedalījums (uz 2018.01.01)

Šie ir *Shapefile* formātā. [Reiz bija CSP lapā](https://www.csb.gov.lv/lv/statistika/kartes-un-telpiskie-dati). Tagad ir te. [*Shapefile* datņu skaidrojums](https://www.csb.gov.lv/sites/default/files/tile/Shapefile/2010/Shapefile_datnes_skaidrojums_teritorialas_vienibas.pdf).

* Territorial_units_LV_1.2m_(2018.01.01.) - mērogs 1:1 200 000 (atbilst A3 formātam)	
* Territorial_units_LV_1.7m_(2018.01.01.) - mērogs 1:1 700 000 (atbilst A4 formātam)	
* Territorial_units_LV_2.4m_(2018.01.01.) - mērogs 1:2 400 000 (atbilst A5 formātam)

Lai ieimportētu datubāzē, daram šādi:

```bash
# MySQL
ogr2ogr -f MySQL MySQL:dbname,host=hostname,user=username,password=password \ 
  Territorial_units_LV_1.2m_\(2018.01.01.\)/Territorial_units_LV_1.2m_\(2018.01.01.\).shp \ 
  -nln adm \ 
  -update \ 
  -overwrite
```
