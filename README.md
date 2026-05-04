![](images/hero_img.png)
<br>
A tool for discovering and evolving patterns in a 6 channel MNCA rulespace.

## MNCA origins ([source](https://slackermanz.com/understanding-multiple-neighborhood-cellular-automata/))
MNCA (Multiple Neighborhood Cellular Automata) is a family of cellular automata, created by Slackermanz. Please check the source for a more in depth explanation of MNCA.
#### Conway's Game of Life
MNCA is built upon the principles of Conway's Game of Life, created by John Conway in 1970. To better understand MNCA, we can take a look at the simple rules that govern CGOL. For each cell in our grid, we take the number of "neighbors" (# of alive / filled cells among the 8 surrounding cells) and do the following at each frame / timestep (neighboring cells' updates not shown):
<table>
  <tr>
    <td align="center" width="20%">
      t = 0
    </td>
    <td align="center" width="20%">
      <img src="images/GOL0.png" width="150"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL2.png" width="150"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL3.png" width="150"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL5.png" width="150"><br>
    </td>
  </tr>
  <tr>
    <td align="center" width="20%">
      t = 1
    </td>
    <td align="center" width="20%">
      <img src="images/GOL1.png" width="150"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL2.png" width="150"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL4.png" width="150"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL6.png" width="150"><br>
    </td>
  </tr>
  <tr>
    <td align="center" width="20%">
    </td>
    <td align="center" width="20%">
      <2 neighbors: die
    </td>
    <td align="center" width="20%">
      2-3 neighbors: survive
    </td>
    <td align="center" width="20%">
      >3 neighbors: die
    </td>
    <td align="center" width="20%">
      3 neighbors: birth
    </td>
  </tr>
</table>

<table>
  <tr>
    <td align="center" width="100%">
      <img src="images/GOL.gif" width="750"><br>
    </td>
  </tr>
  <tr>
    <td align="center" width="100%">
      The rules in action
    </td>
  </tr>
</table>

#### Expansion to MNCA
MNCA makes two major expansions from Conway's Game of Life, those being larger neighborhoods and the use of two or more such neighborhoods, each with their own set of rules. Take the following example pair of neighborhoods:
<table>
  <tr>
    <td align="center" width="50%">
      <img src="images/neighborhoodA.png" width="300"><br>
    </td>
    <td align="center" width="50%">
      <img src="images/neighborhoodB.png" width="300"><br>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      Neighborhood A
    </td>
    <td align="center" width="50%">
      Neighborhood B
    </td>
  </tr>
</table>
The simplest way to implement MNCA is to apply a similar rule scheme to CGOL to each neighborhood (a 1/alive or 0/dead depending on the sum of neighbors for each neighborhood). However, we can also utilize a continous space by storing float values [0.0, 1.0] in each cell. We then have a float neighborhood sum as well as a fixed/parameterized weight we add to the target cell (rather than setting 1 or 0).

```
# Continuous MNCA Ruleset Skeleton Example

For each cell:
  If Neighborhood A sum between (a, b):
    cell += weight1
  If Neighborhood A sum between (c, d):
    cell += weight2
  If Neighborhood B sum between (e, f):
    cell += weight3
  If Neighborhood B sum between (g, h):
    cell += weight4
```
#### Selective MNCA
Selective MNCA (also by Slackermanz) is a variant of MNCA in which we calculate multiple "candidate" MNCA patterns/rulesets per cell per frame, and use some function to score each ruleset and pick one for that particular cell and frame. SMNCA massively increases the parameter space and expressive capability of MNCA. Here are some patterns I discovered while working in a single channel, continous SMNCA rulespace. The selection function for these patterns always awards the candidate pattern that changes the target cell's value the most.
<table>
  <tr>
    <td align="center" width="25%">
      <img src="images/smnca1.gif" width="200"><br>
    </td>
    <td align="center" width="25%">
      <img src="images/smnca2.gif" width="200"><br>
    </td>
    <td align="center" width="25%">
      <img src="images/smnca3.gif" width="200"><br>
    </td>
    <td align="center" width="25%">
      <img src="images/smnca4.gif" width="200"><br>
    </td>
  </tr>
</table>

## My rulespace

#### Neighborhoods

#### Thresholds

#### Channel mixing weights

## Tool capabilities

#### Pattern mutation

#### Parameter map

## Gallery
<table>
  <tr>
    <td align="center" width="33%">
      <img src="images/mnca01.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca02.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca03.gif" width="260"><br>
    </td>
  </tr>
    <tr>
    <td align="center" width="33%">
      <img src="images/mnca04.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca05.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca06.gif" width="260"><br>
    </td>
  </tr>
    <tr>
    <td align="center" width="33%">
      <img src="images/mnca07.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca08.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca09.gif" width="260"><br>
    </td>
  </tr>
    <tr>
    <td align="center" width="33%">
      <img src="images/mnca10.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca11.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca12.gif" width="260"><br>
    </td>
  </tr>
    <tr>
    <td align="center" width="33%">
      <img src="images/mnca13.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca14.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca15.gif" width="260"><br>
    </td>
  </tr>
    <tr>
    <td align="center" width="33%">
      <img src="images/mnca16.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca17.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca18.gif" width="260"><br>
    </td>
  </tr>
    <tr>
    <td align="center" width="33%">
      <img src="images/mnca19.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca20.gif" width="260"><br>
    </td>
    <td align="center" width="33%">
      <img src="images/mnca21.gif" width="260"><br>
    </td>
  </tr>
</table>
