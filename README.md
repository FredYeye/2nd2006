# 2nd W 2006
Attempt at writing a test that shows when t gets copied to v on the second write to 0x2006.  


Through epic code and blargg's nmi sync code, it's possible to time a write with a 1 dot variance.  
Press right or left to increase or decrease the dot offset by one, respectively.  
For example, in Mesen 0.9.7: the second "sta 0x2006" starts at dots 239-240 at offset 0, and dots 247-248 at offset 8 (max).  


The test draws a row of triangles. They can appear in three different ways:
1. Pixel perfect staircases: t->v happened before the Y increment at dot 256.
2. Broken: t->v happened after the Y increment at dot 256.
3. Shaking: t->v is happening before and after the Y increment at dot 256 (alternating).
  
*Todo*: add explanation of output (on screen), better output
