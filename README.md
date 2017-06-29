# boebots
' {$STAMP BS2sx}
' {$PBASIC 2.5}
HotOrCold VAR Byte
counter VAR Word
time VAR Word
isTrue VAR Word
irDetectRight VAR Word
irDetectLeft VAR Word
stops VAR Byte

DO
SERIN 15, 1200, [WAIT ("A!"), DEC3 HotOrCold]
 PULSOUT 6, 5
 PULSIN 6, 1, time
 DEBUG HOME, "time = ", DEC5 time
 PAUSE 100
IF time < 1000 THEN
  FOR counter = 1 TO 125
    PULSOUT 12, 860
    PULSOUT 13, 650
  NEXT
  FOR counter = 1 TO 325       'someone please tst
    PULSOUT 13, 650
    PULSOUT 12, 650
  NEXT
  FOR counter = 1 TO 1000
    PULSOUT 12, 860
    PULSOUT 13, 650
  NEXT
ELSE
  PULSOUT 12, 860
  PULSOUT 13, 650
ENDIF
LOOP
