Flowgramming 

So we have dozens of programming languages out there and they mostly cover the same terrain with a small difference. However, they also function as silos for most work. They all have data handling, memory management, procedures/functions, and some sort of UI set up in most of them. My idea was what if we separated these into separate systems and treated each one like a node in a workflow. 

The problem isn't having to learn programming. The problem I was having was having to learn programming over and over and over for different things. I started with Basic, then C, then C++ (which I hated), then Java (which I was trying to learn when it first came out and no one seemed to understand it then), then php, then javascript, then python. I started to realize it was just the same thing over and over. The problem was that something programmed in one language was locked up most of the time in that language. That is why they are trying to get COBOL programmers right now. The problem IS the languages. We are siloing all of our work over the years. We need to stop that.

How can we stop that? We need to break the problem into component parts. We need data that is independent of functions. We need Operating Systems that are independent of platform. We need components that are able to be put together in different ways instead of something that has to be programming in one way from start to finish or we have to start over in another language.

This is what this paradigm is about.
	
Data is like nouns. You have a set of nouns in a dataBlock. It would have all the data that you are working with. So hundreds of lines of code go there. Then you have functions or modules or programming code which I just call Actions. These are the verbs. This converts the data from one format to another and stores it back in the dataBlock or in a new dataBlock.

So you have one person who puts the dataBlock together from data that he collected or some API. This is the RAW dataBlock. Then you have to convert it to something else for your report so you have someone else create a Report dataBlock, or it could be an API to a dashboard. Every week you have to process this data by choosing certain Actions. One Action could be for materials. Another could be for profits. So you create a FlowScript to tie these three things Subject - Verb - Object into a program that you didn't have to write any of. Then you run it and the report is done. You could be in Sales, in Management, or just a secretary. You didn't program any of those blocks but you can use them all because Flowgramming isn't asking you to know anything complex to create and run a program.

My goal is to create an ecosystem of these modules so that we can have multiple uses for them. 

Applications - The first use would be for creating applications with more ease but be able to go back through at any point and upgrade any of the modules without having to refactor the whole system or find a programmer for because the application was written in a less popular language. 

IOT - Then take the same system of an application and strip it down to the smallest version to make IOT systems that are able to interconnect and you can program easily. 

Operating Systems - Then you can turn the same set up into an Operating System that can have incremental improvements without having to download a whole new version each time. It would have security built into it at all modules. 

Company - Then take all of those modules and make them function for a corporation. Integrate Access Control and Permissions with automatic auditing to notice when one person keeps producing problematic entries versus someone who keeps going above and beyond. 


Next Step

I want to start building these as workflows in Node Red in order to finalize the details of the first few modules. We can work out the problems for each system and block combination this way and then get them coded for long term use. I want to set up each system and block combination as something that can be dropped into a workflow as a new node and solve problems on its own. Eventually all of these nodes will be able to function as a whole system. 


It’s licensed under **MPL 2.0**, so it stays open but flexible for research or enterprise use.  
The documentation is being expanded weekly — early contributors are very welcome.
