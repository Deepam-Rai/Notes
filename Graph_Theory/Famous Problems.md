----
## Four Color Problem

Relating to graph coloring.  
### Mathematical statement
> For loopless planar graph $G$, its chromatic number is $\chi(G) \le 4$.
- **Loopless:** that has no loop
- **Planar graph:** that can be embedded in a plane; it can be drawn such that no edges cross each other.
- **Chromatic number:** Minimum number of colors required to vertices of graph such that no two adjacent vertices have the same color.


### Layman statement
> **Four Color Theorem:** No more than four colors are required to color the regions of any map so that no two adjacent regions have the same color.
- Regions are adjacent if they share a common boundary segment.

### Constraints:
- Regions that share only isolated boundary points are not considered adjacent.
- Regions with finite area but infinite perimeter are not allowed
	- They may require more than 4 colors. *Four Colors Do Not Suffice by Hud Hudson in The American Mathematical Monthly*
- Each region must be contiguous / Exclaves are not allowed. Contiguous region(connected open subset of a place) are not same as exclaves in sense of country or regular maps.
	- Exclaves are the portion of the region geographically separated from the main part and is surrounded by alien territory.
	- Enclaves are allowed. They are regions surrounded totally by another region.
	- Exclaves which are enclaves are still not allowed.


### History
Origin:
1. 1852, October 23: Conjecture first proposed by Francis Guthrie.
	- While trying to color map of counties of England, whence he noted that just four colors were enough.
2. Francis asked his brother Frederick Guthrie who asked his teacher Augustus De Morgan at University of College London.
3. 1854: One of two brothers posed the question in Athenaeum, a British literary magazine published in London England.
4. 1860: De Morgan posed the same question again in the same magazine.

Proving the conjecture:
1. 1879 by Alfred Kempe; shown incorrect in 1890 by Percy Heawood.
2. 1880 by Peter Guthrie Tait; shown incorrect in 1891 by Julius Petersen.
3. 1890: Percy Heawood proved five color theorem.
4. 1976: Appel and Haken proved the conjecture.
5. 1989: They released *Every Planar Map is Four-Colorable* book with detailed proof.
6. 1996: Neil Robertson, Daniel P. Sanders, Paul Seymour and Robin Thomas created quadratic time algorithm ($O(n^2)$ where $n=$number of vertices) with checkings of only 633 reducible configurations. Appel-Haken proof was quartic-time.

### Proof
1976, June 21: Proved by Kenneth Appel and Wolfgang Haken at the University of Illinois, assisted by John A. Koch. The proof was computer assisted.
Logic:
1. If four-color conjecture were false $\implies$ these exists a map with smallest possible number of regions that requires five colors.
2. They showed that such a minimal counterexample cannot exist, using two concepts:
	1. An unavoidable set: 
	2. A reducible configuration: 
3. They found an unavoidable set of reducible configurations proving that a minimal counterexample to the four color conjecture could not exist.
4. They reduced infinitude of possible maps to 1,834 reducible configurations. Later reduced to 1,482.

Complete proof:
1. Early 1980s: Rumours of flaw in Appel-Haken proof spread.
	1. Ulrich Schmidt at RWTH Aachen examined Appel and Haken's proof and had found error in the discharging procedure.
2. 1986: Editor of Mathematical Intelligencer asked Appel and Haken to address rumours of flaws in proof.
3. 1989: *Every Planar Map is Four-Colorable* book with detailed proof was released with corrected errors found by Schmidt and several others.

#### Controversy of proof:
1. The proof required extensive computer assistance.
2. The proof actually didn't explain why it is so, but proved that it is so.
3. Thus proof was also taken controversially at the time.

----
## Three Houses and Three Utilities Problem

Relating to planar graphs.  

> There are three utilities(gas,water and electricity) that need to be connected to three houses by gas lines, water mains and electrical lines. Can this be done without any of the lines or mains crossing each other?

No, because the resulting graph $K_{3,3}$ is not planar.

----