- Bass
stack(
  note ( "g1 ")
  .sound("sine")
  .room("3")
  .cpm(30)
  .pan(sine.slow(1)) 
)

- Drum & Chords
$: s("[bd sd | bd!4 | bd [sd hh | hh!2] sd hh | ht [mt ht mt] lt cr]")
  .bank("<9000>")
  //.gain(.07)
  .lpf(1000)
  .room(.07)
  .color("pink")

  let chords = chord("<Cm7 [FM7 | Am7] [Cm7 | EbM7] Bb7>")
  $: chords.struct("- x [- | x] x").voicing().sound("gm_fx_atmosphere").gain(.2).lpf(1000).room(1)
  
  
  sound banks :
  RolandTR808
  RolandTR909
  




- Visual
osc(8, 0.08, 0.7)
  .kaleid(4)
  .rotate(() => time * 0.03)
  .modulate(
    noise(3, 0.2)
      .scale(1.5)
      .scrollX(() => Math.sin(time * 0.1) * 0.1),
    0.25
  )
  .color(0.4, 0.7, 1.2)
  .contrast(1.4)
  .brightness(-0.15)
  .blend(
    osc(20, 0.02, 0.3)
      .color(1, 0.2, 0.4)
      .rotate(() => -time * 0.02),
    0.25
  )
  .out()

  
  kaleid(4)     // 3, 4, 6, 8
  osc(8...)     // low = slow、big；high = thin、spik
  color(...)    // emotion
  blend(...,0.25) // 0.1 to 0.5