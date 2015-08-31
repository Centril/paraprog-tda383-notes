# Lecture 1:

## Some basic concurrency...

nbu 5000
nbe 5000

nbu 3000
nbe 2000

nbu 1000
nbe 5000

--------

buy	beer
e	5
6	10
9	15
12  ^
	|
15 --

--------

+ Some stuff about javax.swing interface actually posting messages to a different UI thread...
+ What if we need to post concurrently? 2 threads? => race condition :P
	* Message queue!
	* Sleep? Not? + Queue
	* Not deterministic.

--------

## Labs

+ FIRE, yay?!
+ points for the labs...
+ 1 & 3 labs more difficult (more time)...
+ less points per rejection.

## Intermission 1...

All slides are already up.

## Threads

+ Threads are logical computing unit.
+ 3 ways to make them in Java.
	* (if you dont while(true) it will quit when done, otherwise forever).
	* Using Thread & anonymous inner class.
	* Using a Runnable.
	* Equivalent!
+ Not very elegant...
+ Slight difference btw Runnable (reusable) & Thread (which has some nice stuff, e.g: .join(), etc.)
+ Concurrency in unicore CPU: threading is based on scheduling and interleaving execution units.
+ Switching & Scheduler:
	* runtime
	* OS
+ Cooperative Scheduling: thread releases control.
+ Preemptive Scheduling:
	* Erlang
+ Battle for resources & race condition:
	* Deadlock: both want the needle, so they get stuck.
	* Starvation: 2 are using needle, but third thread is not...
		- One process never gets to the queue.
	* Cooperating: Synchronization...
		- 3 threads are making parts, a fourth assembles (promises & joins)

## Atomicity:

+ Action is atomic if it can't be split into parts, e.g: in the middle of the sequence.
+ Guaranteed to execute w/o interuption.
+ 1 thread iterating list, 1 thread removing an element => BANG!
+ Java: synchronized => atomic.


counter = counter + 1;
counter++;

++counter;

INCA