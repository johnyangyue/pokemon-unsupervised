# Gotta Cluster 'Em All -  A Study of Pokémon with Unsupervised Learning

## Project Summary

In this project, we use k-means and Gaussian mixture algorithms to cluster pokemon images. Even with limited experience with the pokemon franchise, it is reasonable to suspect that there exist some commonalities (color, size, etc.) among pokemons with the same type. We are curious to find out if such commonalities can be identified by our unsupervised learning algorithms. 

The images and pokemon types information are scrapped from the Pokémon Showdown website using Selenium. The raw images are 96 by 96 in RGBA format. 

In the early stages of this project, we attempted to use the raw images and 32 by 32 resized images to implement the algorithms. The outcomes are disappointing. In both cases, we obtain 2 clusters with pokemon size being the primary separation criterion. To eliminate the size factor, we decide to crop the images and only keep the center 32 by 32 chunk. As shown in our report, while this decision successfully removes the size factor in the clustering, we are still not able to achieve a color-separated outcome. 

It is documented that distance in the RGB space does not translate well into perceived difference. An alternative that does a better job is YCbCr with Y representing the luminance, Cb representing the blue-difference, and Cr representing the red-difference. Distances in this color space do a much better job at representing differences in perceived color. With this change, our unsupervised learning algorithms are able to cluster the images based on their color palettes and demonstrate the correlation between pokemon types and colors. 

To get a sense of the relative performance of our unsupervised learning algorithms, we also implement a support vector machine model and a convolutional neural network to classify the images. Our k-means implementation yields an accuracy score on par with the support vector machine model. Unsurprisingly, the convolutional neural network achieves the best accuracy, although its lead over the other models is relatively moderate. 

## References

[1]. Pokémon Showdown. "Pokédex". [Online]. Available: https://pokemonshowdown.com/. [Accessed: 15-Apr-2022].

[2]. G. Holtes, "Extracting colour palettes with unsupervised learning," Medium, 08-Feb-2021. [Online]. Available: https://medium.com/analytics-vidhya/extracting-colour-palettes-with-unsupervised-learning-4399d5ca820c. [Accessed: 04-May-2022]. 

[3]. A. M. Aibinu, A. A. Shafie, and M. J. E. Salami, “Performance analysis of ANN based YCbCr skin detection algorithm,” Procedia Engineering, vol. 41, pp. 1183–1189, 2012. 
