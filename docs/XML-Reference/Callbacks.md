#  Callbacks 
##  VTK 

```xml
<VTK Iterations="1000" what="U,Rho"/>
```

Export VTK data 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `what=` | List of Quantities and Geometry Components to export. | Value with unit (NULL) |
| `name=` | Name of the VTK file. | Value with unit (NULL) |

##  TXT 

```xml
<TXT .../>
```

Export data to TXT file 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `name=` | Name of the TXT file. | Value with unit (NULL) |
| `gzip=` | If to compress the TXT output | Value with unit (NULL) |

##  Catalyst 

```xml
<Catalyst script="vis1.py" Iterations="1000"/>
```

Run Catalyst co-processor 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `export=` | Select if to provide the Catalyst co-processor with VTK Cell of Point Data | Value with unit (NULL) |
| `script=` | Catalyst co-processing Python script | Value with unit (NULL) |
| `preprocess=` | If active, the Python script will be modified so that the files will be placed in the output directory | Value with unit (NULL) |

##  Log 

```xml
<Log .../>
```

 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `name=` |  | Value with unit (NULL) |

##  Stop 

```xml
<Stop FluxChange="1e-5" Times="5" Iterations="100"/>
```

Allows to stop the computatation if a change of some Global is small for a longer time 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `Unknown=` | Limit on change of a specific Global | Value with unit (NULL) |
| `Times=` | Numer of times the change have to be below the limit to stop the computation. | Value with unit (NULL) |

##  PID 

```xml
<PID Flux="10.0" control="ForceX" scale="0.01" DerivativeTime="100" IntegrationTime="10000" Iterations="10"/>
```

PID controller. Allows to achive a specified value of an Global, with tweaking of a Setting 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `Unknown=` | Target value for a specified Global | Value with unit (NULL) |
| `control=` | The setting to control (currently only zonal settings are supported) | Value with unit (NULL) |
| `scale=` | The proportional rate D in PID controller | Value with unit (NULL) |
| `DerivativeTime=` | The derivative time scale. D = P * DerivativeTime | Value with unit (NULL) |
| `IntegrationTime=` | The integral time scale. I = P / IntegrationTime | Value with unit (NULL) |

##  Sample 

```xml
<Sample Iterations="1000" what="U,P" ><Point dx="10" dy="20"/></Sample>
```

Effecient sampling of quantities on each iteration, without need for VTK 

| Attribute | Comment | Value |
| --- | --- | --- |
| `Iterations=` |  | Value with unit (int) |
| `Iterations=` | Iteration period after which the sampled data will be written to a file | Value with unit (NULL) |
| `what=` | List of Quantities to be sampled. By default all are sampled. | Value with unit (NULL) |

