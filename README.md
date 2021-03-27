# SwoLeios

This is a simple repository to select a short exercise to do for roughly 5 minutes every hour

List of things to do:
* Implement "heaps of heaps" to select exercise

Finicky things to think about:
* Determining whether set is in reps or duration is weird for `select_reps()`
* Can we just use `time` directly?
* if the dataframe is read in with a duration as the first row, it will assume everything is a "Date," which breaks things
* if no duration is present in exercises, dataframes assume that the column is for integers and things break
* by=x->x[2] for heaps?
* some sets do not fit on the image

Example run:
```
using SwoLeios
superset = SwoLeios.create_superset("exercises/core.dat", "exercises/mobility.dat", "exercises/arms.dat", "exercises/legs.dat")
set = SwoLeios.select_set!(superset)
reps = SwoLeios.select_reps(set)
```