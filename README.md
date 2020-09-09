# MP0 Post Mortem

Overall, good job getting the basics of Go down. It can be a bit of a shift coming from most languages due to the Interface system replacing much of what type systems do in other languages. It is additionally a bit harder to find information about tasks that are more easily accessible for python or js. 

## Code Style

1. 
	Please everyone take 30 minutes out of your day and read the style guides for Go. It is *not* optional. 
	
	Either of the following are acceptable:
	
	- [Effective Go](https://golang.org/doc/effective_go.html)
	
	- [Practical Go](https://dave.cheney.net/practical-go/presentations/qcon-china.html)
	
	Going forward I will not explicitly mention stylistic errors and how to fix them, and will simply deduct those points. 

2. 
	MP0 was an *easy* pset. I think this let some of you get lazy and in combination with Go being a new language, you forgot many of the principles of good program design. This is covered extensively in both style guides as well.
	
	- You should *always* be refactoring your code to abstract reused sections. Even GoLand will tell you that you are repeating code and to abstract it. 
	
	- Each function should have one, easily defined purpose. Write functions like this. 
	
	-  Please abstract things to different packages as needed. The message struct should not be in the process package. They are separate ideas and need to be compartmentalized. 

	- Both style guides talk about handling errors. Read these sections. 
	
	- Use the [argparse](https://github.com/akamensky/argparse) package for command line parsing. 
	

## Documentation Style

Overall, things here were OK except for one area. Please continue to include exact instructions on how to run the code. I should be able to copy and paste what you have to get it running. 

#### Main gripe:

A lot of the documentation talked without saying much. I care far more about the decisions you made about the structure of your code and control flow than a long story about the steps in the control flow. I want to see that you are thinking critically about how you are approaching a problem. 

Many of you sent raw strings over the TCP socket. And many of you had implicit shortcomings like termination tokens and delimination tokens. This is easily solved with JSON or other serialization techniques, or with Gob which is pretty unique to Go and is likely the best choice for basic Go --> Go network communication. If you didn't use Gob or JSON, how did you design your program to figure out the format of the incoming data? Why? What are the shortcomings? Why did you or did you not use a message struct? Many of you only used a message struct on the server and not the client. Why? When we get to more complex designs, why did you break up the design into xyz components the way you did? If you can't answer these questions then it shows you don't understand what you are designing. 


## Conclusion

There are tons of resources online. I googled "Go network programming" and found this book, [Network Programming with Go](https://ipfs.io/ipfs/QmfYeDhGH9bZzihBUDEQbCbTc5k5FZKURMUoUvfmc27BwL/index.html) which is a pretty good resource for the network aspects of this class. You will need to put in the extra time to understand how TCP/UDP works and how Go works for this class. You can't fly by the seat of your pants copy and pasting from tutorials as many of these later MPs will not really be googleable like this one was. Take the time to first understand the problem and formulate a design, then implement it and adjust. 
