- Erlang was created by Ericsson in mid 1980s with the goals of:
	+ reliability
	+ responsiveness
	+ scalability
	+ constant availability

- Erlang is a general purpose development platform. The above goals are tackled by providing:
	+ concurrency
	+ scalability
	+ fault-tolerance
	+ distribution
	+ high availability

- Today's systems are more intrinsic related to each other, meaning they need some requirements like:
	+ responsiveness regardless of the load
	+ impact of unexpected errors should be minimal
	+ should always be up and running

- The Erlang Virtual Machine BEAM (Bogdan/Bjorn Erlang Abstract Machine) has it's own schedulers and lightweight processes. Each scheduler is responsible for the work a single CPU core will do under BEAM execution. 
	+ The BEAM is a single OS process
	+ A scheduler is a OS thread
	+ Each BEAM process is a unit of concurrent execution

- Erlang processes shares no memory. This makes `fault tolerance` easier when an unexpected error occurrs, meaning impact is only local and a replacement process can be run.
- Locks, mutexes and semaphores are not needed for erlang processes synchronization. They share no memory and they communicate through async messages. This makes the system easier to scale.
- Communication between two Erlang processes in the same BEAM is not different of separated BEAM. This makes it easier to distribute the system onto different computers. Also making the system more resilient because of the possible cluster design
- System responsiveness is granted by the works of the schedulers. They run each erlang process in a small window of time, meaning that the work done by other erlang processes are not stopped. Giving a sense of pseudo paralelism. 
