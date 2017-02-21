# 2nd W 2006
Attempt at writing a test that shows when t gets copied to v on the second write to 0x2006.

**simple**:  
Writes to 0x2006 have a ~12 dot variance and happen around dot 256.

**next level**:  
Through questionable code and blargg's nmi sync code, it's possible to time a write with a 1 dot variance.  
Press right or left to increase or decrease the dot offset by one, respectively.  
For example: the second "sta 0x2006" starts at dots 239-240 at offset 0, and dots 247-248 at offset 8 (max).  


The test will draw a row of triangles. If they appear as a pixel perfect staircase, the t->v transfer happened after the Y increment at dot 256. If not, it happened before.  
*Todo*: add explanation of output (on screen), better output
