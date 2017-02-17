# 2nd W 2006
Attempt at writing a test that shows when t gets copied to v on the second write to 0x2006.

simple: Writes to 0x2006 have a ~12 dot variance. Should be stable on HW but shake on emulators if t->v happens instantly when a write cycle to 0x2006 happens right before dot 256. As there is some timing variance, the exact t->v delay can't be tested. Currently timed to be 1 cpu cycle too early for nintendulator, causing it to shake. This should in theory mean a real nes doesn't exhibit any shaking.

next level: Through questionable code and blargg's nmi sync code, it's possible to time a write with a 1 dot variance. Use up/down for -+1 scanline and dot, and left/right for -+3 dots.
Todo: Output that makes sense and probably sync the starting point with the missed nmi.