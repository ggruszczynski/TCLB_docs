

## Description
d2q9_plate

## Details
[Model description files](Model description) files for this model:
[Dynamics.c](https://github.com/llaniewski/TCLB/blob/(HEAD detached at c598d42)/src/d2q9_plate/Dynamics.c.Rt)
[Dynamics.R](https://github.com/llaniewski/TCLB/blob/(HEAD detached at c598d42)/src/d2q9_plate/Dynamics.R)

### [Zonal Settings](Settings)

| Name | Comment |
| --- | --- |
|`Velocity`|inlet/outlet/init velocity|
|`Density`|inlet/outlet/init density|
|`PX`|plate position X|
|`PY`|plate position Y|
|`PR`|plate angle|
|`ForceXInObj`|Weight of [reaction force X] in objective|
|`ForceYInObj`|Weight of [reaction force Y] in objective|
|`MomentInObj`|Weight of [reaction force X] in objective|
|`PowerXInObj`|Weight of [reaction force Y] in objective|
|`PowerYInObj`|Weight of [reaction force X] in objective|
|`PowerRInObj`|Weight of [reaction force Y] in objective|
|`PowerInObj`|Weight of [reaction force X] in objective|
|`Power2InObj`|Weight of [reaction force Y] in objective|


### [Global Settings](Settings)

| Name | Derived | Comment |
| --- | --- | --- |
|`tau0`|3*nu + 0.5|one over relaxation time|
|`nu`||viscosity|
|`Smag`||inlet density|
|`PDX`||plate diameter X|
|`PDY`||plate diameter Y|
|`SM`||smoothing diameter|
|`SM_M`||smoothing bias|
|`Descent`||Optimization Descent|
|`GradientSmooth`||Gradient smoothing in OptSolve|
|`Threshold`||Parameters threshold|

### [Exported Quantities](Quantities) (VTK, etc)

| Name | [Unit](Units) | Comment |
| --- | --- | --- |
|`Rho`|`kg/m3`|Rho|
|`U`|`m/s`|U|
|`Solid`|`1`|Solid|
|`RhoB`|`1`|RhoB|
|`UB`|`1`|UB|

#### [Exported Global Integrals](Globals) (CSV, etc)

| Name | [Unit](Units) | Comment |
| --- | --- | --- |
|`ForceX`|`1`|reaction force X|
|`ForceY`|`1`|reaction force Y|
|`Moment`|`1`|reaction force X|
|`PowerX`|`1`|reaction force Y|
|`PowerY`|`1`|reaction force X|
|`PowerR`|`1`|reaction force Y|
|`Power`|`1`|reaction force X|
|`Power2`|`1`|reaction force Y|
|`tau0_D`|`1`|Gradient of objective with respect to [one over relaxation time]|
|`nu_D`|`1`|Gradient of objective with respect to [viscosity]|
|`Smag_D`|`1`|Gradient of objective with respect to [inlet density]|
|`PDX_D`|`1`|Gradient of objective with respect to [plate diameter X]|
|`PDY_D`|`1`|Gradient of objective with respect to [plate diameter Y]|
|`SM_D`|`1`|Gradient of objective with respect to [smoothing diameter]|
|`SM_M_D`|`1`|Gradient of objective with respect to [smoothing bias]|
|`AdjointRes`|`1`|square L2 norm of adjoint change|
|`Objective`|`1`|Objective function|

### [Node Types](Node-Types)

| Group | Types |
| --- | --- |
|BOUNDARY|Wall, Solid, WVelocity, WPressure, WPressureL, EPressure, EVelocity|
|COLLISION|BGK, MRT|
|DESIGNSPACE|DesignSpace|
|NONE|None|
|SETTINGZONE|DefaultZone|

### [Solved fields](Fields)

| Name | Access pattern | Comment |
| --- | --- | --- |
|`f0`|![stencil](/images/st_a1p0p0p0p0p0p0.png)|f0|
|`f1`|![stencil](/images/st_a1n1p0p0n1p0p0.png)|f1|
|`f2`|![stencil](/images/st_a1p0n1p0p0n1p0.png)|f2|
|`f3`|![stencil](/images/st_a1p1p0p0p1p0p0.png)|f3|
|`f4`|![stencil](/images/st_a1p0p1p0p0p1p0.png)|f4|
|`f5`|![stencil](/images/st_a1n1n1p0n1n1p0.png)|f5|
|`f6`|![stencil](/images/st_a1p1n1p0p1n1p0.png)|f6|
|`f7`|![stencil](/images/st_a1p1p1p0p1p1p0.png)|f7|
|`f8`|![stencil](/images/st_a1n1p1p0n1p1p0.png)|f8|

### [Densities - default accessors](Densities)

| Name | [Field](Fields) | Pulling field from | Comment |
| --- | --- | --- | --- |
|`f0`|f0|![stencil](/images/st_a1p0p0p0p0p0p0.png)|f0|
|`f1`|f1|![stencil](/images/st_a1p1p0p0p1p0p0.png)|f1|
|`f2`|f2|![stencil](/images/st_a1p0p1p0p0p1p0.png)|f2|
|`f3`|f3|![stencil](/images/st_a1n1p0p0n1p0p0.png)|f3|
|`f4`|f4|![stencil](/images/st_a1p0n1p0p0n1p0.png)|f4|
|`f5`|f5|![stencil](/images/st_a1p1p1p0p1p1p0.png)|f5|
|`f6`|f6|![stencil](/images/st_a1n1p1p0n1p1p0.png)|f6|
|`f7`|f7|![stencil](/images/st_a1n1n1p0n1n1p0.png)|f7|
|`f8`|f8|![stencil](/images/st_a1p1n1p0p1n1p0.png)|f8|

### [Action stages](Stages)

| Name | Main procedure | Preloaded densities | Pushed fields |
| --- | --- | --- | --- |
|BaseIteration|Run|f0, f1, f2, f3, f4, f5, f6, f7, f8|f0, f1, f2, f3, f4, f5, f6, f7, f8|
|BaseInit|Init|_none_|f0, f1, f2, f3, f4, f5, f6, f7, f8|


### [Actions](Stages)

| Name | Stages |
| --- | --- |
|Iteration|BaseIteration|
|Init|BaseInit|

