I think it's good to put together some high level objectives of what to monitor. See notes from Chapter 4 below. These high level objectives could help with the redesign as well, or Yokesh could read the book.
recommend to Yokesh to read Testing Alerting Logic for his work.

notes on the sre workbook

chapter 1

principles of devops:
change should be gradual (aka continuous integration),
accidents are normal and due to systemic reasons,
no more silos b/t ops, security, software, etc.,
measurement is critical

blur the lines b/t software engineer and sre... they can both work on overlapping stuff.
sre's main job is to automate away toil. this includes catching bugs earlier so that they are faster to fix.
At Google, teams lose SRE support if their product contains a ton of operations work that the SRE and team is not able to automate. SREs leave, so it motivates the team to reduce the toil.
there are a number of recommended books at the end of the first chapter which you could read to learn more about sre (maybe before going to mission control).

chapter 2

SREs need SLOs
SLO stands for service level objectives. SLI stands for service level indicator. I think SLO is a good term to use generally to refer to this concept.
SLOs can just be a reporting metric, but hopefully they are used to make decisions (should we try that new database, if it will impact our SLO in X way?)
At the end of the day it's all about user happiness, and SLOs provide a non-fuzzy way to measure user happiness. If your service is below the SLO, users will be unhappy. If it is above the SLO, users will be happy.
The correct language is "as measured by probers" not "as measured by probes". then again they refer to them as probes elsewhere "but setting up probes..."
A SLI can include a lot of things... in general it's the ratio of good user experiences to all user experiences. So this could be the number of successful requests that finished within 300 ms over the total number of requests.
the first attempt to get a SLI and SLO doesn't have to be correct. It's more important to get something up and running so you can improve the feedback loop. So define it as best you can and move on.
it'd be helpful to have past performance to define a good SLO. we don't have good metrics for past performance right now, so maybe we use Corp Eng's guide? or the one in the book.
availability and latency SLOs are pretty common... there are a few others like durability, freshness, correctness, etc.
SLOs can be on a gradient, they may say "90% of requests return within 100ms and 99.9% return within 500ms." Doesn't have to be a single number.
product managers need to agree the SLO is good enough for users, product developers need to agree to take the SLO seriously, and the team responsible for the production environment (OPS work) needs to agree the SLO is reasonable without burnout or Hurculean effort.
Workbook recommends writing a document that says what to do if having reached an error budget (search for "To make the error budget enforcement..."). Will need to write this document after coming up with SLO with product owners. there's a lot that follows this section and would be good to read for concrete action items to take when creating the SLOs.
it's important to revisit the SLO document you wrote (the one about which SLOs you'd pick) every so often. Maybe set a meeting once a month for a while, then once a quarter. You can review how hard it was to meet your SLO and what actions you can take or if you want to change your SLO. Also, importantly, you need to redefine your SLO often to reflect real-world user issues.
dashboards are helpful so you can see if you're trending toward reaching your SLO, and how SLIs are trending.
I didn't read Advanced Topics.

Chapter 4

So I should've known this, but couldn't describe it if asked... what's the difference b/t logs and metrics? Since rich, structured logs can be searched and queried, they are similar to metrics, right? The difference is that logs are usually not in real time (real time logs do exist though) and metrics contain much less granular information (exceptions exist, like high cardinality metrics).
they say that SLI metrics are important, and should be on your landing page for your service, but there are other metrics that are important to monitor for help in debugging. these include:

the version of the binary, command line flags, configuration data. they're saying this is monitored I think they're saying to link a graph / dashboard for these... I've never seen a dashboard like that but it does sound cool.

metrics from dependencies you rely on. specifically response size in bytes, latency, and response codes.

CPU, disk and memory usage, since you have a hard limit on them. Also  heap and metaspace size for Java, and number of goroutines for Go.

type of response code (they bring up an interesting point that even if it's a client error, it may indicate your page is doing something on the client side that's wrong. so you can't use these for alerting but they are informative.)

number of requests denied due to rate limiting