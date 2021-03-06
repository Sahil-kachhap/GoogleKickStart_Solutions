vote.cpp: let dp\[i]\[j] be the probability of, obtaining a sequence of length i with j number of As in it, and A is in the lead all the time. The base case is dp\[1]\[1]=N/M+N. Now for each dp\[i]\[j], we consider whether the last person is A or B. If the last person is A, we can safely let dp\[i]\[j]+=dp\[i-1]\[j-1]\*(probability of selecting A), because adding an A to an already valid seqence is still valid. On the other hand, if the last person is B, we could encounter scenarios where appending a B makes the sequence invalid. e.g. appending "B" to valid seqence "AAB" makes an invalid sequence "AABB". Thus we have to make sure the total number of As is at least greater than half of the current length. After that, we can let dp\[i]\[j]+=dp\[i-1]\[j]\*(probability of selecting B).

sitting.py: if the R is divisible by 3, we can divide the entire grid into 3\*1 strips. From each 3\*1 strip, we can take at most 2 grids to sit, according to pigeon-hole theorem. So the maximum we can reach is R\*C/3\*2. Similarly, if R%3==1, we can divide the entire grid into multiple 3\*1 strips and multiple 1\*3 strips, and we can always take the remaining 1 or 2 grids that do not form 1\*3 or 3\*1. Lastly, if R%3==2, if C%3==0 or C%3==1, we can take 2 out of 3 from each 1\*3 or 3\*1 strip, and take all remainders. If R%3==2 and C%3==2, the leftovers after assigning 1\*3 strip and 3\*1 strip is a 2\*2 grid. If C==2 or R==2, we can take the entire 2\*2 grid, otherwise we can take 3 out of 4. This is the end of the theoretical maximums. Here is a construction that reaches the maximum:<br />
XX.XX.XX.XX. and so on <br />
.XX.XX.XX.XX and so on <br />
X.XX.XX.XX.X and so on <br />

codejamonCipher.cpp: dp, the key optimization comes from the fact that each vocab word's length<=20.

stretchRope.cpp: knapsack dp. dp\[L]=min(dp\[L],dp\[L-B]...dp\[L-A]). Remember to properly initialize everything.
