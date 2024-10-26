---
title: 'Clash of Particles'
description: 'A basic simulation ot the movement of particles inside a box'
pubDate: '26 October 2024'
heroImage: ''
---

## Description
Clash of particles is a basic implementation of a simulation of the movement of particles confined in a box where we supposed that they are only subjected to the law of elastic collisions. This project was carried out as part of the IN101 course at ISAE-Supaero run by Christophe Garion. The complete project and instructions for use are available on its [repository](https://github.com/UnMoutonPerdu/clash-of-particles).

## Implementation
Two implementations are available for this project:
- The first one is a naive implementation of the management of the collisions between particles. This implementation isn't very useful for a large number of particles due to its low performance, but it did provide a nice warm-up for the second one and for testing the first functions.
- The second implementation involves the use of a binary heap data structure to reduce the time complexity of the simulation and improve the performance when increasing the number of particles. 

## A first naive implementation
The first approach we tested consists in calculating all possible collisions between all particles at each time step. Each particle must be checked to see if it collides with one of the other particles. Thus, for _N_ particles, this approach has a time complexity of  $\mathcal{O}(N^2)$. This time complexity allows us to produce a first simulation that works for small values of N but quickly becomes too slow when N becomes large as it is shown in the videos below:
<style>
    figure img {
        display: block;
        margin-left: auto;
        margin-right: auto;
        width: 350px;
    }
    figure figcaption {
        text-align: center;
    }

    .left, .right {
        display: inline-block;
        padding: 25px;
    }
</style>

<figure>
  <img src="/videos/cocn100.gif" alt="Naive simulation for 100 particles" style="border-radius:10px;">
  <figcaption>Naive simulation for 100 particles</figcaption>
</figure>

<figure class="left">
  <img src="/videos/cocn500.gif" alt="Naive simulation for 500 particles" style="border-radius:10px;">
  <figcaption>Naive simulation for 500 particles</figcaption>
</figure>

<figure class="right">
  <img src="/videos/cocn1000.gif" alt="Naive simulation for 1000 particles" style="border-radius:10px;">
  <figcaption>Naive simulation for 1000 particles</figcaption>
</figure>

We can clearly see a drop in performance of the naive implementation as _N_ becomes larger. This is due to the way in which we check whether or not a collision has occurred. To overcome this problem and allow a better collision management, we propose a second implementation using a data structure to efficiently store the collision events: the priority queue. 

## When binary heap comes into play
To implement this priority queue, we decided to use a *binary heap* which guarantees a worst case execution time complexity of $\mathcal{O}(log(N))$ to retrieve and store elements. The idea behind this implementation is to first make a first pass over all the particles to find out the dates of their next collision as in the first implementation (a quadratic number of operations but just this one time). Once these events have been generated and inserted into the structure, it's simply a matter of taking the nearest event in the future (which is done in $\mathcal{O}(log(N))$ time) and, if it includes particles, generating the future collisions involving those particles. It results a time complexity of $\mathcal{O}(Nlog(N))$ for this approach. 

The following videos show how the use of this data structure improves the performance of the simulation:

<figure>
  <img src="/videos/cocbh100.gif" alt="Simulation using a binary heap for 100 particles" style="border-radius:10px;">
  <figcaption>Simulation using a binary heap for 100 particles</figcaption>
</figure>

<figure class="left">
  <img src="/videos/cocbh1000.gif" alt="Simulation using a binary heap for 1000 particles" style="border-radius:10px;">
  <figcaption>Simulation using a binary heap for 1000 particles</figcaption>
</figure>

<figure class="right">
  <img src="/videos/cocbh2000.gif" alt="Simulation using a binary heap for 2000 particles" style="border-radius:10px;">
  <figcaption>Simulation using a binary heap for 2000 particles</figcaption>
</figure>

## Notes on the results
Even if the second implementation seems to perform much better than the first, we mustn't forget that we've only taken elastic collisions into account. Extending this simulation to include other types of forces would mean having to find a new data structure and rethink the algorithm. 

The current simulation also calculates $\pi$ to 6 decimal places, using the method exposed in this [video](https://www.youtube.com/watch?v=HEfHFsfGXjs) of _3Blue1Brown_. The code is also foundable on the same repository.