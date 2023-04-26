
Entry gate

19 camera

                   0 , 1 , looksatid , partiallooksatid , tags , entity-id 
entry 15 -> -1 -1 ,  0 , "row1racks" , "entry" , "gate 3"
entry 13 -> -1 -1 ,  0 , 1 , "row1racks" ,  "gate 4"
entry 14 ->  -1 -1 , 0 , kiosk , "entry" , "gate 4"
entry 21 ->  -1 -1 , 0 , kiosk , "entry" , "gate3 & gate4"

exit 17  -> "gate2"
exit 22 -> "gate 1 & gate 2" -- this will be identified first then on with x or y next camera will be identified whose x or y will be same. 
exit 18 -> "gate 2"
exit 20 -> "gate 1"

rack and tracking --- tilt < 5 -> tracking most time


Gates - tag("entry")

target fictures - gate 1 & 2
1. Entry gates

target ficture - gate 3 & 4
1. Exit gates



Non-Gates - tag("non entry")

entity_id("kiosk")
4. kiosk

non-kiosk

1. Facing cameras
2. Top-down cameras

