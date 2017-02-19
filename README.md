# 2nd W 2006
Attempt at writing a test that shows when t gets copied to v on the second write to 0x2006.

**simple**:  
Writes to 0x2006 have a ~12 dot variance and happen around dot 256.

**next level**:  
Through questionable code and blargg's nmi sync code, it's possible to time a write with a 1 dot variance.  
Use up/down for +-1 dot, and left/right for +-3 dots. See table below, with timings for when "sta $2006" starts in nintendulator. Up/down changes y, left/right changes x.  

|     | x=0     | x=1     | x=2     |
|-----|---------|---------|---------|
| y=0 | 237-238 | 240-241 | 243-244 |
| y=1 | 238-239 | 241-242 | 244-245 |
| y=2 | 239-240 | 242-243 | 245-246 |

The test will draw a row of triangles. If they appear as a pixel perfect staircase, the t->v transfer happened after the Y increment at dot 256. If not, it happened before.  
*Todo*: Probably sync the starting point with the missed nmi.
