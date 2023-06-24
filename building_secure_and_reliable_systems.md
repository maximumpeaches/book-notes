## Chapter 12

Basic idea for this chapter is that by using frameworks, libraries and languages developers can avoid classes
of vulnerabilities in their code. This can reduce the majority of software vulnerabilities that are out there today.

Some specifics are mentioned on which frameworks, libraries and languages to use, but you'd need to research solutions
for your own language / setup. 

Some special mention is given to memory and thread safety vulnerabilities, and language choice (not C++ for memory, 
and something like Rust is great for thread safety) makes a big difference there, although
there are also frameworks and static analyzers and stuff that can help reduce the risk even if you don't have a choice
of which language to use.

### Q&A
Should SREs or security engineers review code for security issues? What are pros and cons of this approach? Should
developers be responsible for security issues in their code?

Developers should definitely be educated about security issues and encouraged to write secure code. 
Having SREs and security engineers review the code can also help. Manual code reviews by SREs and security engineers 
won't catch every issue, and automated or no-op solutions like using frameworks, libraries or languages that are secure
by default is important, too.


