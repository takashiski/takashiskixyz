## start gcode

```gcode
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops
;G1 Z15.0 F{speed_travel} ;move the platform down 15mm
;G92 E0 ;zero the extruded length
;G1 F200 E3 ;extrude 3mm of feed stock

;G1 Z7 F600 ;move Z to 7mm
G1 X5 Y5 F600 ;move to x5mm y5mm
;now move to a proper height. customize this based on your carriage/build plate setup.
G1 Z0.8 ;move z to 0.7mm
G92 E0 ;zero the extruded length
G1 F200 E2 ;extrude 15mm of filament in place. customize according to end-script retraction
G1 Z10 F200; move the extruder up by 10mm
G1 F200 E30 X40; extrude 30mm in a 4cm line
G1 Z18.00 F500 ; move up quickly the extruder to 18mm to break any strings from the blob
G1 X80 Y5 F4000; move away a bit to drag any remaining string of filament, useful for PETG
;G1 E-2 F600; retract a bit to stop oozing
;indiana jhones theme - curtesy of @saschaludwig
;M300 S1318 P240
;M300 S0 P120
;M300 S1396 P120
;M300 S1567 P120
;M300 S0 P120
;M300 S2093 P720
;M300 S0 P180

G92 E0 ;zero the extruded length again
G1 F{speed_travel}
G0 Y20 F{speed_travel}
M117 Printing...
G5
```

```
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops

G1 X10 Y10 F1000
G1 X150 E10 F1500
G1 E-3 F200
G1 Z30 F1500
G1 X10 F1500

G1 Z15.0 F{speed_travel} ;move the platform down 15mm
G92 E0 ;zero the extruded length
G1 F200 E3 ;extrude 3mm of feed stock
G92 E0 ;zero the extruded length again
G1 F{speed_travel}
G0 Y20 F{speed_travel}
M117 Printing...
G5
```

```
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 X0 Y0 ;move X/Y to min endstops
G28 Z0 ;move Z to min endstops

G1 X10 Y10 F1000
G1 X150 E20 F1500

G1 Z15.0 F{speed_travel} ;move the platform down 15mm
G92 E0 ;zero the extruded length
G1 F200 E3 ;extrude 3mm of feed stock
G92 E0 ;zero the extruded length again
G1 F{speed_travel}
G0 Y20 F{speed_travel}
M117 Printing...
G5
```

## end gcode

```
G4
M200 S100
M221 S100
G91 ;relative positioning
G1 E-1 F300 ;retract the filament a bit before lifting the nozzle, to release some of the pressure
G1 Z+0.5 E-5 ;X-20 Y-20 F{speed_travel} ;move Z up a bit and retract filament even more
G28 X0 ;Y0 ;move X/Y to min endstops, so the head is out of the way
G1 Y180 F2000
M104 S0 ; turn off extruder
M140 S0 ; turn off bed
M84 ; disable motors
M107
M106 S0 ; turn off cooling fan
M84 ;steppers off
G90
M300 P300 S4000
```


## 参考URL

https://www.thingiverse.com/groups/anycubic-i3-mega/forums/general/topic:46109
https://medium.com/@christianleber/anycubic-i3-mega-steps-for-good-minis-a393dfef76b1