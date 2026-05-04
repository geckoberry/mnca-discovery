![](images/hero_img.png)
<br>
A tool for discovering and evolving patterns in a 6 channel MNCA rulespace.

## MNCA origins ([source](https://slackermanz.com/understanding-multiple-neighborhood-cellular-automata/))
MNCA (Multiple Neighborhood Cellular Automata) is a family of cellular automata, created by Slackermanz.
#### Conway's Game of Life
MNCA is built upon the principles of Conway's Game of Life, created by John Conway in 1970. To better understand MNCA, we can take a look at the simple rules that govern CGOL. For each cell in our grid, we take the number of "neighbors" (# of alive / filled cells in the 8 surrounding cells) and do the following at each frame / timestep (neighboring cells' updates not shown):
<table>
  <tr>
    <td align="center" width="20%">
      t = 0
    </td>
    <td align="center" width="20%">
      <img src="images/GOL0.png" width="200"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL2.png" width="200"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL3.png" width="200"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL5.png" width="200"><br>
    </td>
  </tr>
  <tr>
    <td align="center" width="20%">
      t = 1
    </td>
    <td align="center" width="20%">
      <img src="images/GOL1.png" width="200"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL2.png" width="200"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL4.png" width="200"><br>
    </td>
    <td align="center" width="20%">
      <img src="images/GOL6.png" width="200"><br>
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

# This rulespace

# Tool capabilities
