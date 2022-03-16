# IDAO-2022-stage1
Solution for the 5th International Data Analysis Olympiad : https://idao.world/.

Team "Variance killers"
___

## Data
* We replace the holes in the crystals by placeholders atoms (H)
* We delete Mo and S atoms because they do not bring any information

```
prepare_dataset()
```
* We translate on the x and y axis to have the smallest molecule that molecule 
is equivalent to all the translated ones because of the PBC 
````
get_minimal_dec()
````

For the augmentations we used rotations and flip on the Z axis
 (to switch 1st and 3rd layer)
 
## Training
We use the Megnet models with minors changes

## Retrain
After the primary training we retrain our models using cosine decay
the final models use the average of the 6 best retrain model weights.

We do that for each of the 10 splits 

At last, we used the median prediction of those 10 models