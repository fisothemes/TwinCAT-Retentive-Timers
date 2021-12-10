# TwinCAT-Retentive-Timers
The Retentive Timer (RTO) is a function block that has been available on AB and Siemens PLCs but strangely has been missing on Beckhoff PLCs.
An RTO is extremely useful for applications like tracking the length of time a PLC has been running or retaining persistent time.

This project creates retentive variants of the standard library PLC timers:
* TON - Timer On-Delay
* TOF - Timer Off-Delay
* TP  - Pulse Timer 


**In this project the following will be implementated:**

* 👍 FB_RTON    - Retentive Timer On-Delay
* ⚡ FB_RTOF    - Retentive Timer Off-Delay 
* ⚡ FB_RTP     - Retentive  Pulse Timer
* ⚡ FB_Timer   - Pausable Timer
* ⚡ FB_RTimer  - Retentive Pausable Timer

- - - -
### FB_RTON

**Declaration:** 
```Pascal
(* <name of timer> : FB_RTON *)

// Declaring a Retentive Timer On-Delay
fbRTON : FB_RTON;
```

**Implimentation**
```Pascal
fbRTON(IN := bStart, PT := tSet_Time, Q => bElapsed_Time, ET => tElapsed_Time)
```

- - - -
### FB_RTOF
Work-In-Progress will update once finished

**Declaration:** 
```Pascal
(* WIP *)
```

**Implimentation**
```Pascal
(* WIP *)
```

- - - -
### FB_RTP
Work-In-Progress will update once finished

**Declaration:** 
```Pascal
(* WIP *)
```

**Implimentation**
```Pascal
(* WIP *)
```

- - - -
### FB_Timer
Work-In-Progress will update once finished

**Declaration:** 
```Pascal
(* WIP *)
```

**Implimentation**
```Pascal
(* WIP *)
```

- - - -
### FB_RTimer
Work-In-Progress will update once finished

**Declaration:** 
```Pascal
(* WIP *)
```

**Implimentation**
```Pascal
(* WIP *)
```
