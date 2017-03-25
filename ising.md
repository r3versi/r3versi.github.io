---
layout: math_page
title: 2D Lattice Field Theory - Ising
permalink: /ising/

---

# 2D Lattice Field Theory - Ising
L'hamiltoniana del modello di Ising (per campo magnetico nullo) risulta
$$
\mathcal{H} = -J\Sigma\sigma_i\sigma_j
$$
dove $$J$$ è la costante di accoppiamento fra spin.

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