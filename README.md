# 2nd W 2006
Attempt at writing a test that shows when t gets copied to v on the second write to 0x2006.

simple: Writes to 0x2006 have a ~12 dot variance. Should be stable on HW but shake on emulators if t->v happens instantly when a write cycle to 0x2006 happens right before dot 256. As there is some timing variance, the exact t->v delay can't be tested. Currently timed to be 1 cpu cycle too early for nintendulator, causing it to shake. This should in theory mean a real nes doesn't exhibit any shaking.

next level: Sync cpu-ppu to get a finer write timing around dot 256. There's just some loose ideas here, it doesn't actually work. This is why the simpler test exists, since I'm not a genius.

next level 2: Borrows nmi sync code from blargg. Starts sta $2006 on dots 240 and 241 in nintendulator.