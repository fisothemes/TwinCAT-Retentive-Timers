# TwinCAT-Retentive-Timers
Standard library timers on TwinCAT count time by taking the difference between the current time from system timer and start time from system timer.
While this is fine for most application, it is problematic for operations that require time to be retained even if the PLC is paused, stopped or turned off.
For example, if a `TON` (Timer On-Delay) Timer is running and you stop the PLC Boot Project for a period of time, the `TON` will not resume from the point it was stopped.
Instead it will skip time by the number of ms/secs/mins/hours it was stopped. 
This makes it useless for applications such as tracking the length of time a PLC has been running or retaining persistent time.

Retentive variants of the Standard library timers stop this from happen. They are based on PLC Task cycle time rather than system time. 
This means they will simply stop counting when the PLC Task Cycle is stopped and will resume from where they left-off as soon as the task cycle picks up.
All arguments behave in the same manner as those of the standard library. 

To see an example of the differences between Retentive Standard Library Timers and Normal Standard Library Timer, download this project, run it and follow the instructions in `P_Example_1_TONs()`

This project creates retentive variants of the standard library PLC timers:
* TON - Timer On-Delay
* TOF - Timer Off-Delay
* TP  - Pulse Timer 


**In this project the following will be implementated:**

* 👍 FB_RTON    - Retentive Timer On-Delay
* 👍 FB_RTOF    - Retentive Timer Off-Delay 
* 👍 FB_RTP     - Retentive  Pulse Timer
* 👍 FB_Timer   - Pausable Timer
* 👍 FB_RTimer  - Retentive Pausable Timer

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

**Declaration:** 
```Pascal
(* <name of timer> : FB_RTOF *)

// Declaring a Retentive Timer Off-Delay
fbRTOF : FB_RTOF;
```

**Implimentation**
```Pascal
fbTOF(IN := bStart, PT := tSet_Time, Q => bElapsed_Time_TOF, ET => tElapsed_Time_TOF)
```

- - - -
### FB_RTP

**Declaration:** 
```Pascal
(* <name of timer> : FB_RTP *)

// Declaring a Retentive Pulse Timer
fbRTP : FB_RTP;
```

**Implimentation**
```Pascal
fbRTP(IN := bStart, PT := tSet_Time, Q => bElapsed_Time_RTP, ET => tElapsed_Time_RTP);
```

- - - -
### FB_Timer

**Declaration:** 
```Pascal
(* <name of timer> : FB_Timer *)

// Declaring a Pausable Timer
fbTimer : FB_Timer;
```

**Implimentation**
```Pascal
fbTimer(bStart := bStart, bPause := bPause, tSet := tSet_Time, bElapsed => bElapsed_Time, tElapsed => tElapsed_Time);
```

- - - -
### FB_RTimer

**Declaration:** 
```Pascal
(* <name of timer> : FB_RTimer *)

// Declaring a Retentive Pausable Timer
fbRTimer : FB_RTimer;
```

**Implimentation**
```Pascal
fbRTimer(bStart := bStart, bPause := bPause, tSet := tSet_Time, bElapsed => bElapsed_RTime, tElapsed => tElapsed_RTime);
```
