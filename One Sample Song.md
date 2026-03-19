setcps(0.5)

stack(

  s("bd ~ bd [bd ~]")
  .gain(1)
  .room(0.2),

  s("bd*8")
  .gain(0.3)
  .speed(range(0.8,1.4).slow(6))
  .room(0.4),

  s("bd*16")
  .gain(range(0.1,0.6).slow(4))
  .speed(range(0.5,2).slow(8))
  .delay(0.25)
  .room(0.6),

  s("bd")
  .slow(4)
  .gain(1.2)
  .room(0.7)
)