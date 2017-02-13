# 2nd W 2006
Attempt at writing a test that shows when t gets copied to v on the second write to 0x2006.

One idea:

1. know what cycle we are on by doing cpu-ppu syncing
2. perform a write right before dot 256. the t->v transfer should be delayed and avoid the Y inc



Currently the test has a timing variance of ~12 dots and is untested on hw. I should try reading blargg's syncing code but his code is generally really hard to read for me.
