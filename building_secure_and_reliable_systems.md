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

## Book Club

What is something many organizations, who wish to restore from backups, fail to do after backing up their systems?

A: Test they can restore from those backups successfully.

Security and reliability are both often managed by ___ ___ employees and brought up in ___ ___ review process.

A: the same

What are benefits of compliance regulations? What are some drawbacks?

Pros: Some organizations will allocate resources on security when they wouldn't've otherwise. It can incentivize
organizations whom otherwise would've had no incentives. These can facilitate change.
Cons: Some organizations will do "security by checkbox", meaning they meet the letter of the law but don't enact
meaningful change. Somtimes big organizations will lobby for compliance regulations as a way to inhibit competition
from smaller organizations which don't have the resources needed to be compliant.
Overall compliance regulations can get you part of the way to security, but you'll need to go beyond that 
(similar to code coverage metrics, or any other metric / checkbox).

If you want your login system to be secure, what is one thing you should do?

A: Monitor all of the logins that occur.

## Chapter 13

JUnit for Java, GoogleTest for C++, go2xunit for Golang, and unittest for Python are all examples of what unit testing paradigm?

A: xUnit. See https://en.wikipedia.org/wiki/XUnit for more context.

What is a hermetic test?

One which runs completely independently and in isolation from other tests.

What is mutation testing?

A: Injecting small faults into programs to see where code fails. I think basically you set a value to true, and then see
if a test would fail or not. If no test fails, you can give developers warnings.

I agree with their point that it's important to have a definition somewhere of what mocks, stubs and fakes mean, since
if someone proposes to build a fake, for instance, it's important to have a common understanding of what that proposal means.

What does unit testing pay off in the long-run, according to this book?

It leads to a higher-quality codebase and fewer edge cases to debug. You can also catch bugs earlier, often before even committing the code.

Why is it okay to use a production database in an integration test?

It's not! You should use test data. The reason for this is that you don't want to screw with customer data, and also
if an attacker gained access to your integration test you don't want that to imply access to your production data.
Also, having a test set of data makes the data easy to wipe between tests, which can reduce test flakiness.

How is dynamic analysis different from static analysis.

Dynamic analysis is similar to static analysis but is done while the software is running.

____ ____ and ___ ____ report generators are the best-known types of dynamic analysis.

Performance profilers and code coverage report generators

ASan is a C/C++ dynamic analysis tool. It builds a binary from source code, similar to a regular compiler, but adds
instructions which do extra stuff when the code runs which can help find memory bugs, like writing to unsafe locations.
Add instructions like this to the compiler is called what?

Instrumentation

Generating random numbers and passing them to software, to see if the software crashes, is called what?

Fuzzing

What is a seed corpus and how is it used in fuzz testing?

A seed corpus is example input that you want to send your program during fuzz testing. Fuzz engines commonly accept example input
and then mutate it in order to generate additional data to send to your programs.

There's a ton of info here on fuzzing. If you ever need to build a fuzzer, or perhaps even to select a fuzzer or set
one up, it'd be very useful to come read more about it.

Some teams run fuzzers continously in their continuous build pipeline. The fuzzers automatically find bugs and generate reports. What
is this practice called?

Continous fuzzing

Static analysis tools make tradeoffs between false positive (incorrect warnings) and false negatives (missed warnings).
What is one reason that this tradeoff is necessary?

Statically verifying any program is an undecidable program, that is, there is no algorithm that can determine whether any given
program will execute without violating any given property.

I found it interesting that many static analysis tools (such as those that would find common issues that make code less readable before a presubmit)
work by parsing the code into a AST tree (which is just a tree made up of the different code components, like one node might be a == sign, another node might be a variable)
and then checks if sections of the AST tree match the pattern the tool is looking for and if so, then they issue a warning.
It makes sense they are looking for code which matches a pattern, but I guess it is faster (and perhaps has fewer false positives)
if they use an AST tree to do this.

## Chapter 14

What should you verify before a deployment can occur? Give an example of a verification occurring before a deployment can
take place.

Both *who* deployed a change, and *what* is being deployed. An example of verifying what is being deployed is how
Google Kubernetes Engine allows you to only deploy images signed by your CI/CD system, and to receive notifications when
someone uses the breakglass feature to deploy a noncompliant image.
