---
layout: math_page
title: 2D Lattice Field Theory - Ising
permalink: /ising/
menu: false
---

Il modello di Ising descrive l'interazione di $$N$$ spin $$\sigma_i$$ su un reticolo. L'hamiltoniana del modello contiene un termine di interazione fra spin ed un termine di interazione con un campo magnetico esterno $$h$$:

$$
\mathcal{H} = -J\Sigma\sigma_i\sigma_j -h\Sigma\sigma_i
$$

La costante di accoppiamento $$J$$ descrive la natura magnetica del materiale: se $$J > 0$$ gli spin tendono ad allinearsi ed il materiale risulta ferromagnetico, diversamente, se $$J < 0$$ il reticolo avrà proprietà antiferromagnetiche.

Sia $${s} = (\sigma_1,..,\sigma_N)$$




{% highlight cpp %}
bool flip_spin(v2d &lattice)
{
	int dim = lattice.size();
	int N = dim*dim;

	int index = (double)rand()/RAND_MAX*(N-1);
	
	int x = index/dim;
	int y = index%dim;

	int sum = lattice[(x+1)%dim][y] + lattice[(x+dim-1)%dim][y] + lattice[x][(y+1)%dim] + lattice[x][(y+dim-1)%dim];
	int deltaE = 2*lattice[x][y]*sum;

	if (deltaE <= 0)
	{
		lattice[x][y] *= -1;
		return true;
	}
	else
	{
		double r = (double)rand()/RAND_MAX;
		if (r <= bmann_weigth(deltaE))
		{
			lattice[x][y] *= -1;
			return true;
		}

		// microstep rejected
		return false;
	}
}
{% endhighlight %}