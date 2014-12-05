NSTimer+Block
=============
Use blocks with NSTimer.

### Creating a timer

```
- (instancetype)initWithFireDate:(NSDate *)date interval:(NSTimeInterval)seconds 
                         repeats:(BOOL)repeats block:(void (^)(void))block;
```
Initializes a new NSTimer object using the specified block.

* **date:** The time at which the timer should first fire. 
* **seconds:** For a repeating timer, this parameter contains the number of seconds between firings of the timer. If seconds is less than or equal to 0.0, this method chooses the nonnegative value of 0.1 milliseconds instead.
* **repeats:** If YES, the timer will repeatedly reschedule itself until invalidated. If NO, the timer will be invalidated after it fires. 
* **block:** The block to be executed when the timer fire. The block should take no parameters and have no return value.

**Return:** The receiver, initialized such that, when added to a run loop, it will fire at date and then, if repeats is YES, every seconds after that.

--
```
+ (NSTimer *)scheduledTimerWithTimeInterval:(NSTimeInterval)seconds repeats:(BOOL)repeats 
                                      block:(void (^)(void))block;
```
Creates and returns a new NSTimer object and schedules it on the current run loop in the default mode.
 
* **seconds:** The number of seconds between firings of the timer. If seconds is less than or equal to 0.0, this method chooses the nonnegative value of 0.1 milliseconds instead.
* **repeats:** If YES, the timer will repeatedly reschedule itself until invalidated. If NO, the timer will be invalidated after it fires.
* **block:** The block to be executed when the timer fire. The block should take no parameters and have no return value.

**Return:** A new NSTimer object, configured according to the specified parameters.

--
```
+ (NSTimer *)timerWithTimeInterval:(NSTimeInterval)seconds repeats:(BOOL)repeats 
                             block:(void (^)(void))block;
```

Creates and returns a new NSTimer object initialized with the specified block.

* **seconds:** The number of seconds between firings of the timer. If seconds is less than or equal to 0.0, this method chooses the nonnegative value of 0.1 milliseconds instead.
* **repeats:** If YES, the timer will repeatedly reschedule itself until invalidated. If NO, the timer will be invalidated after it fires.
* **block:** The block to be executed when the timer fire. The block should take no parameters and have no return value.

**Return:** A new NSTimer object, configured according to the specified parameters.
