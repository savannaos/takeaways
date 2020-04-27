# Georgia Tech's Online Masters of Science in Computer Science

Aug 2019 - current

The main challenges with each class is the general coordination of work-work and school-work. During the first semester, I found myself "binging" life, being very social after work and out-and-about for up to 2 weeks at a time. Then I would bing school work: getting a lot done in a short period of time. The second semester, I practice better pacing and generally felt more confident with assignments. I worked on things with a buddy, using  going over to his place as a mental trigger for thinking about school-work. The class was well-organized, so I had to spend less time understanding what was being asked of me. It helped to draw the problem out and break up into smaller tasks. I would work on things up until the deadline, a habit I'd prefer to not carry-on to the next semester. I think I get used to having a break after one assignment, so I don't jump into the next thing immediately to give myself an emotional break. It got especially hard to coordinate work and school once quarentined. But there were times school needed more attention and others when I could balance the two fine.

## CS 6262 Network Security

Going in: virtually no experience with networking. High-level malware analysis background and experience from MITRE project.

| Project | Topic |
|---------|-------|
| 1       |       |
| 2       |       |
| 3       |       |
| 4       |       |

## CS 6200 Introduction to Operating Systems

January 2020 - May 2020

Supporting notes and code are found at: https://github.gatech.edu/ssmith456/gios.git.

### Background
Going in: no undergraduate course in OS, but systems programming primed me for C and for threading material.

### Projects
| Project | Goal  | Topics | Technologies |
|---------|-------|--------|--------------|
| 1       | Multi-threaded GetFile server that serves static files based on a Getfile protocol with a multi-threaded client as a load generator      | client-server communication, thread concurrency, boss-worker model | C, pthreads, sockets|
| 2       | System metrics and performance evaluation | workload request patterns, workload sizes, machine specifications  | C            |
| 3       | Part 1: Proxy server that translates Getfile requests to http requests Part2: A simple cache server that communicates with multiple proxy servers via shared memory. | interprocess communication, synchronization| C, libcurl, message queues, shared memory            |
| 4       | A simple distributed file system that handles both binary and text-based files between a single server and multiple clients     | remote procedure calls, cache consistency, distributed shared memory, message serialization      | C++, Protocol Buffers, gRPC (streams, synchronous and asynchronous requests), inotify|

The projects built off of one another. The first one was building a simiplified web-server, where I spent a good chunk of the time familiarizing with C: how to read from/write to files, how to send chunks of data over a socket, etc. The second project was extra credit and it was a written assignment to evaluate the design and performance of the first project. This one served as a nice lighter project, as well as applied evaluation skills demonstrated in a reading. The third builds by then adding a proxy server and cache server. The first part was a huge confidence boost since the implementation was straightforward since I was fmailiar with the callback design from project 1, and had to understand libcurl and how I could send the data back from that. The second part was more involved and benefited from drawing out the system. By having interconnected projects, it makes it apparent all the design decisions that go into creating a system. Perhaps we will be reaching out to a web-server, first checking if we have a cached copy, and then understanding how we could pass information between two processes. Continuing on with IPC, the final project implemented a distributed file system. I needed to understand the sharing and statefulness across all clients. A fun overlap was I was reversing protobufs for a project at work, and I got to use Protocol Buffers as my message serialization technique. On the client side, I implemented the sending of these requests and the packaging up of the related data, and the reading of the response data. On the server side, I implemented the reading of the request, and the necessary responses. For a file system, this meant implementing: Fetch, Store, Delete, and List. This was by-far my sloppiest code since I was throwing in more use-cases as I tested it out. It was interesting that we were essentially implementing OneDrive: syncing up files on a local client to those on the server, and vice versa.

### Lectures

I learned significanly more from the projects than from the lectures: I think the pertinence of the content to an actual problem (with a deadline) motivated me more than sitting down to read (which I do generally enjoy, just less-so when my attention is being pulled in school, work, and life directions). Other lecture content included: virtualization, i/o management, scheduling, and memory management. It was interesting learning about the different scheduling techniques and how i/o vs CPU bound tasks influence the time slice in round-robin. Meaning, you wanted to have a smaller time-slice for i/o tasks, to max the number you were addressing, since you're often dealing with the immediacy of a user. Lectures emphasized the general evolution of scheduling algorithms, virtualization, and of memory designs. I found it amusing that one of the early hiccups to virtualization was that there were a handful of operations that would not correctly generate an interrupt, so there was an in-between that just caught and skipped over those instructions. Polling vs. interrupts for i/o devices. In distributed there's replicated vs distributed: do we care more about the ability to recover if one of the nodes goes down, or about supported more files? In general, if I needed to re-visit this material, I would see the terms used in my notes, and lookup and refresh on those.

All in all, not bad for during a global pandemic.
