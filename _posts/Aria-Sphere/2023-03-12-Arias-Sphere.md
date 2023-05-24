---
layout: post
title: Aria's Sphere
date: 2022-03-23 12:00:00-0400
description: an interesting problem from my friend's homework.
---

# The Problem
<div>
<img alt-text="A spherical surface, with four equally sized caps removed" src="/Book-N/assets/img/AS-surface.jpg" zoomable=true align="right" style="width:250px">

<p align="left">
	This is the most recent problem that I've had fun with. My friend Aria had a problem on her math homework that interested me: "A square hole with a cross length of 4 is cut symmetrically through a sphere of radius 2. Find the remaining surface area."
	Truthfully, the question was phrased slightly differently, but I am bad at web design, and the math formatting for the original question is disagreeing with the image to the right, so I've just rephrased the question. The image to the right shows the surface whose area we're trying to find.
	
</p>
</div>
# The Process

I kicked this problem around in my head for a few days. The "correct" way to solve it was to use multivariable calculus--which I have not yet learned. Still, I felt like there was some way to understand this problem without calculus. I was focused mostly on the parts *not* present in "Aria's Sphere." The four caps left over after cutting the square out are the complement of the surface area of the entire sphere, whose volume can be known by $$ 4\pi r^2 $$. I felt like there should be *some* easily calculable relationship between the radius of a cap (a portion of a sphere) and its surface area. Where $$ r_{cap} = r_{sphere} $$, the surface area is equal to $$ 2\pi r^2 $$, because at that point the cap is a hemisphere, so the surface area will be half that of a full sphere.


<p align="center">
	<img alt-text="The complement of the above sphere. Four equally sized caps arranged around a square" src="/Book-N/assets/img/AS-fourcaps.jpg" style="width:200px">

	<img alt-text="The top view of the above image" src="/Book-N/assets/img/AS-topview.jpg" style="width:200px">
</p>

I didn't have time to work on this for a while, but a recent camping trip gave me some time to think. The rest of the group left to get more water and access flushable toilets, but I was ready to have some alone-time. My friend and I stayed behind and I was able to spend some distraction-free time with my notebook. I drew out a top view of the complement of the Aria-sphere (4 caps of equal size, arranged so that there is a square hole in the middle). There I drew a diagram, and began to think about the relationship between arc length and angle. Of course, angle is defined by the arc length divided by the radius, or $$ \theta = \frac{AL}{r} $$. Thus, $$ {AL} = \theta{r} $$. Thinking about this relationship made me think about how it could be generalized to a 3D circle (a sphere). Rather than trying to find the surface area of the caps based on their maximum radius, perhaps I could find the surface area based on the angle at which the planecuts through the sphere. I drew a quick diagram of a top view of the sphere, and imagined the following animation:

<p align="center">
<iframe src="https://www.desmos.com/calculator/spxeailzov?embed" width="500" height="500" style="border: 1px solid #ccc" frameborder=0></iframe>
</p>

<img src="/Book-N/assets/img/AS-table.jpg" style="width:150px;float:right">
The plane remains parallel to the YZ-plane, and always intersects the XY polar point $$ (1,\theta) $$. The movement in the animation is defined by the constant increase of  $$ \theta $$. Imagining this segment of a sphere, growing and shrinking as $$ \theta $$ increased infinitely, I realized that the relationship between $$ \theta $$ and $$ SA $$ must be sinusoidal. The surface area of the cap I was looking for is defined by $$ f(\frac{\pi}{4}) $$, where $$ f(\theta) $$ is the wave function that returns the surface area of the segment of that sphere. That is obviously not easily intuited visually, but there are other values of $$ \theta $$ where the surface area is easily intuited. I constructed a table to show the relationship between the angle $$ \theta $$ and the **proportion** of the sphere's surface area remaining. 
<br style="clear:both">

I then began trying to find an equation for $$ {SA} $$ where:

 when $$\theta = 0 \| 2\pi $$,  $$ SA = 0 $$;

 when $$\theta = \frac{\pi}{2} \| \frac{3\pi}{2} $$,  $$ SA = 2\pi r^2 $$; 

 and when $$\theta = \pi$$,  $$SA = 4\pi r^2$$

This is the point at which I began making some logical leaps, and doing some guessing and checking. Although guess n' check is almost never the most efficient way to do math, I like allowing myself to "play with" the numbers. I feel like standard math education doesn't really encourage creative problem solving, and that has hindered my ability to see the beauty in math until recently. This isn't to say schools are bad at teaching math, I am able to learn math that took thousands of years of slow progress to discover in just a few months. Still, I take great joy in playing with the mathematical tools I've been given, even if there is a more efficient way to solve the problem. 

# The Solution 

After guessing and checking several equations for SA, I realized that the table of proportions above followed the equation $$ \sin^2(\frac{\theta}{2}) $$. So, for a unit sphere, the surface area of a segment would be given by $$ 4\pi \sin^2(\frac{\theta}{2}) $$; for a general sphere, $$ 4\pi (\sin(\frac{\theta}{2})r)^2 $$. Plugging in each of the values in the table, this seemed to be the correct equation for finding the surface area of a portion of a sphere.

So now, after all this time, I could finally calculate the surface area of the "Aria Sphere":

$$ 4\pi 2^2 - 4(4\pi (\sin(\frac{\frac{\pi}{4}}{2})2)^2) $$

$$ = 16\pi - 4(4\pi \sin^2(\frac{\pi}{8})4) $$

$$ = 16\pi - 64\pi \sin^2(\frac{\pi}{8}) $$

$$ = 16\pi(1-4\sin^2(\frac{\pi}{8})) $$

This is where I left the problem on the camping trip. I didn't have access to the internet to check. Upon returning home, I discovered that my answer could be further simplified to 

$$ 16\pi(\sqrt{2}-1) $$

# Oh wait, that's just a steradian

Before this, I had briefly encountered [steradians](https://en.wikipedia.org/wiki/Steradian), but the concept had not crossed my mind while trying to solve this problem. In summary, a steradian is the 3 dimensional analogy to a radian. While a radian is defined by the arc length divided by the radius, a steradian is defined by the equation $$ \Omega = (\frac{SA}{r})^2 $$. Finding the surface area of a portion of a sphere is just the same as finding the arc length of a portion of a circle. Scrolling to the bottom of the wikipedia article, the exact formula I found, $$ 4\pi (\sin(\frac{\theta}{2})r)^2 $$, was listed, along with a slightly more elegant equivalent: $$ 2\pi(1-\cos(\theta)) $$. 

I note this because I think it's really fun to "discover" a mathematical concept without formally learning about it. Something about finding a property or equation, only to discover that it is a well known concept with a name and notation is really fun to me. Playing with numbers, recognizing patterns, and discovering properties helps me appreciate the beauty of math in a way that's hard to explain. Geometric problems like this in particular are interesting. The concepts of sine waves, radians, steradians, and polar coordinates feel a little abstract when you first learn them. It isn't immediately clear how they're all connected. Unpacking problems like these, though, have helped me develop mathematical intuition and appreciate the connectedness of it all.
