# How-to-Talk-Multivariate-Gaussian

December 25, 2020

I appreciate comments. Shoot me an email at noel_s_cruz@yahoo.com!

Hire me! 😊

- Now that we have linear algebra somewhat under control,
we can take a look at the Gaussian distribution
in arbitrary dimension.
So what we're gonna do today is to start by looking
at the density of the high dimensional Gaussian,
and getting some intuition for this,
and then move on to some widely used special cases.
So let's do a little bit of a rewind.
If you recall, and we've been looking at the wine data set,
we pulled out two features.
Alcohol level, and flavanoids.
And we fit a two-dimensional Gaussian to the data from
one of the wineries, and we got something like this.
Okay? So this is the 2-D Gaussian.
So it's a distribution over the entire plane,
over every possible pair x one x two.
So that's the density shown here.
So the density here is shown by the height
above the surface.
I personally find pictures like this a little
hard to understand.
So this is another depiction,
which just shows the contour lines drawn on the plane.
So the red dots here are the actual data points.
And the way we fit a Gaussian to them was to simply
compute the mean of each of the features.
So there's feature number one, alcohol level,
feature number two, flavanoids.
We computed the mean along each feature,
and the variance of each feature,
and then the covariance between the two features.
And this gave us a 2D Gaussian.
So the Gaussian parameters were the mean,
which is the two dimensional vector,
represented by the Greek letter mu,
which consists of the mean of x one and the mean of x two.
The other parameter of the Gaussian is a two by two
covariance matrix, which we denote
by the Greek letter sigma, capital sigma.
And it has only three distinct numbers in it.
It has the variance of x one,
up here, it has the variance of x two, down here,
and then it has the covariance between the two features.
Which are the off-diagonal numbers.
So this is the mean, mu is the center point over here.
And it's the point of highest density.
The ellipses show the contour lines of the density
and the reason that tilted upwards is because there is a
positive correlation between the two features.
So the two dimensional Gaussian is quite simple
and it turns out that this generalizes
in a straight forward way to d-dimensions.
So let's move to the higher dimensional case.
So now we're in d-dimension so we want a distribution of Rd,
and now instead of two features we have d features.
x one, x two, all the way to xd.
So in this case, the mean of the distribution, mu,
will be a d-dimensional vector.
It contains the mean along the first feature,
the mean along the second feature,
all the way to the mean along the d feature.
The covariance matrix, this time, is now a d by d matrix .
What does it consist of?
So it's a d by d matrix, and along the diagonal,
it has the variances of each of the individual features.
So these are d numbers, along the diagonal.
The numbers off the diagonals are covariances between all
possible pairs of features.
So in the first row for example,
we start with the variance of x one,
and then we have the covariance between x one and x two.
Followed by the covariance between x one and x three,
and so on.
In general, the i,j entry of this matrix
is the covariance between xi and xj.
So these are the parameters of the Gaussium.
And in terms of the density, it's highest at the mean,
as always, and as you move away from the mean,
the density folds off in these ellipsoidal contours.
The shape of the ellipsoid is given entirely
by the covariance matrix sigma.
And here is the exact equation for the density.
Let's take a brief look at this.
So in the...
So the first part of the density is just
a normalization tone.
That's only there to make sure
that the density integrates to one.
And that's nothing unusual and perhaps you remember
what this is.
That is the determinant of the matrix sigma.
So that's just a normalization term,
it's a constant in front.
The most important part of the density is the part
that's inside the exponent,
because that's the only part that depends on x.
So what does this thing mean?
What kind of function is this?
X minus mu transpose sigma inverse x minus mu.
Well to simplify it a little bit, let's just imagine
that mu equals zero.
So we have a Gaussian that is centered at the origin,
instead of being centered at some arbitrary point mu.
Okay? So mu is zero, let's see what we get.
So the first term over there, x minus mu just becomes x.
The second term also becomes x, and what is sigma inverse?
Well sigma is some d by d matrix
so its inverse is some other d by d matrix,
so let's just call it n.
So we get x transpose nx and that's
something that looks familiar.
That's a quadratic function, okay?
So the density depends only on a quadratic function of x.
And indeed, an ellipsoid is a kind of quadratic.
So now let's go and look at a special case
that's of particular interest.
So suppose these different features are independent.
What does the Gaussian look like then?
So we have d features that are independent of each other
and let's say that the variance of the I feature, xi,
is sigma sub I squared.
Let's figure out what the covariance matrix would be
in this case.
So we got the covariance matrix
which is always a d by d matrix,
and we know that its diagonal entries
are just the variances of the individual features.
And the off diagonal entries are covariances
between features, okay?
So let's see.
What is the covariance between xi and xj?
Well, in this case, the features are all
independent of each other, so they're uncorrelated,
which means that the covariance is zero.
So the off diagonal elements are all zero.
The covariance matrix is a diagonal matrix.
And we can fill in the variances, the variance of x one
is sigma one squared, then we have sigma two squared,
all the way to sigma d squared.
A nice short, form for this kind of matrix is just to say
the diagonal matrix whose entries are sigma one squared
all the say to sigma d squared.
Now, in order to compute the density,
we also need the inverse of this matrix.
What is that?
Well, it's easy to invert a diagonal matrix.
You just invert each element along the diagonal.
So the inverse is one over sigma one squared,
all the way to one over sigma d squared.
And that's it.
So because this covariance matrix is diagonal,
we sometimes call this a diagonal Gaussian.
And covariance matrix being simple
makes it rather easy to simplify the density.
We end up with something like this.
It turns out that each feature,
if you look at it just by itself,
is a Gaussian, it's the I feature, x sub i,
taken just by itself, is a Gaussian with mu sub i
and variant sigma i squared.
So this is what x sub i by itself looks like,
a one dimensional Gaussian.
And the density at a d dimensional point x
is just the one dimensional density at x one,
times the one dimensional density at x two,
all the way to the one dimensional density at xd.
The d features are all independent.
Now as always, the density if highest at the mean,
and folds off in these ellipsoidal contours,
what do the ellipsoids look like in this case?
Well, there are no correlations.
The covariance matrix is a diagonal matrix.
So because there is no correlation, positive or negative,
the ellipsoids are not tilted up or down.
So the ellipsoids are axis aligned, that is to say
that they are parallel to the coordinate directions.
They look something like this.
Now they are potentially stretched out differently,
along different directions.
The stretch along the x one direction is just
the standard deviation of x one, which is sigma one.
So that's the stretch in this direction.
The stretch in the x two direction is
the standard deviation of x two,
which is sigma two, and so on.
So it's a fairly simple distribution.
One of the very nice things about it
is that it can be specified using very few parameters.
So how many parameters do you need for a diagonal Gaussian?
Well, the mean is the d numbers because
it's a d-dimensional vector.
What about the covariance matrix?
Well, it's a diagonal matrix, so you only need d numbers.
So the total number of parameters is two d.
This is a huge savings over the general Gaussian,
which has a full covariance matrix, and therefore needs
something on the order of d squared parameters.
This can be a big convenience, and as a result,
the diagonal Gausian is often used
even when the features are not independent of each other.
Now let's look at an even more special case
that's also very popular.
This is when the features are independent as before,
but in addition, they all have the same variance.
So now the covariance matrix is a diagonal matrix
and in addition, the numbers along the diagonal
are all exactly the same.
In other words, the covariance is a multiple
of the identity matrix.
So the covariance matrix looks like this,
a multiple of the identity matrix.
In this case, the density can be simplified even further.
This is the density function, and as you can see,
the density at point x depends only
on the distance from x to mu.
It depends only on the distance
to the center of the Gaussian.
So the points of equal density
are points that lie on a sphere, centered at mu.
So as always, the density is highest at mu,
and as you move away from mu, the shells of equal density
are these concentric spheres.
So another popular Gaussian.
Okay, so we have a little bit of insight now into
multivariant Gaussians.
Let's turn to a somewhat more concrete and practical
question, which is how do you fit a Gaussian into data?
So we have a bunch of data points in d dimensional space,
let's call them x one through x m.
How would you go about fitting a Gaussian to them?
Well, it's quite simple.
Just compute the mean and covariance of these points.
And those are the parameters, mu and sigma of the Gaussian.
So, the mean of a bunch of data points
is often called an empirical mean.
So you take the points, these m data points,
and you just add them up, and you divide by m.
And this is some d dimensional vector that's the mean mu.
The covariance matrix, finding the empirical version of this
is also very simple.
You just apply the formula for covariance
to the data cell.
So how exactly does that work out?
Well, we now have this d to t by d matrix.
What is the ij entry of the matrix?
It's the covariance between xi and xj.
And what was the formula for covariance again?
Well, the covariance between xi and xj
is the expected value of xi times xj
minus the expected of xi times the expected value of xj.
What is the expected value of xi?
Well, we've already computed that, that's mu sub i.
What is the expected value of xj?
That's mu sub j,
So all we need to to do is compute the average value
of xi times xj in the data set,
and that's exactly what this term is over here.
So that's it for the multivariant Gaussian.
This is one of the absolutely most popular distributions
for modeling high dimensional data and it is
now part of your repertoire.

I included some posts for reference.

https://github.com/noey2020/How-to-Talk-Linear-Algebra-Review-3

https://github.com/noey2020/How-to-Talk-Linear-Algebra-Review-2

https://github.com/noey2020/How-to-Talk-Linear-Algebra-Review-1

https://github.com/noey2020/How-to-Talk-2D-Generative-Modeling

https://github.com/noey2020/How-to-Talk-Probability-Review-3

https://github.com/noey2020/How-to-Talk-Probability-Review-2

https://github.com/noey2020/How-to-Talk-Generative-Modeling-in-One-Dimension

https://github.com/noey2020/How-to-Talk-Probability-Review-1

https://github.com/noey2020/How-to-Talk-Generative-Approach-to-Classification

https://github.com/noey2020/How-to-Talk-of-Fitting-a-Distribution-to-Data-

https://github.com/noey2020/How-to-Talk-of-Host-of-Prediction-Problems

https://github.com/noey2020/How-to-Talk-of-Useful-Distance-Functions

https://github.com/noey2020/How-to-Talk-of-Improving-Nearest-Neighbor

https://github.com/noey2020/How-to-Talk-of-Prediction-Problems

https://github.com/noey2020/How-to-Talk-Matlab-Tricks-and-Tweaks

https://github.com/noey2020/How-to-Talk-Trading-and-Investing

https://github.com/noey2020/How-to-Work-in-Matlab-Development-Environment

https://github.com/noey2020/How-to-Talk-Vaccines

https://github.com/noey2020/How-to-Talk-Regression-in-Matlab

https://github.com/noey2020/How-to-Get-Started-in-Matlab

https://github.com/noey2020/How-to-Convert-Data-from-Web-Service-Using-Matlab

https://github.com/noey2020/Quote-for-the-Day

https://github.com/noey2020/How-to-Talk-Good-Investment-Strategy

https://github.com/noey2020/How-to-Talk-of-Good-Plan

https://github.com/noey2020/Thought-for-the-Day

https://github.com/noey2020/How-to-Talk-Stock-Watch-of-the-Day

https://github.com/noey2020/How-to-Talk-Data-Science

https://github.com/noey2020/How-to-Talk-Fundamental-Analysis

https://github.com/noey2020/How-to-Read-Company-Profiles

https://github.com/noey2020/How-to-Import-Data-from-Spreadsheets-and-Text-Files-Matlab-Without-Coding

https://github.com/noey2020/How-to-Talk-Model-of-Stock-Market-Prices-

https://github.com/noey2020/How-to-Talk-Digital-Wallets

https://github.com/noey2020/How-to-Talk-Investing

https://github.com/noey2020/How-to-Double-Your-Money-in-5years

https://github.com/noey2020/How-to-Talk-Matlab

I appreciate comments. Shoot me an email at noel_s_cruz@yahoo.com!
