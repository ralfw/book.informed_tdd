# The Self-Similar Software Development Process
I read, with interest, Robert C. Martin´s [comment](http://ht.ly/t2UdI) on Justin Searl´s [critique](http://blog.testdouble.com/posts/2014-01-25-the-failures-of-intro-to-tdd.html) of a common TDD teaching approach. Strange it was to see "the good uncle" to be so upset about Justin´s article. Why does he take it so personally, it seems, that someone is not content with the state of TDD-affairs? Why salting Justin´s earth?

Anyway... what I wanted to express is my disagreement with Robert C. Martin´s idea of a "Domain Discontinuity". He proposes there to be two levels in software system design: one, where thinking before implementing is good, and another one where it´s bad. The first being architecture, the second being "the problem domain".

Unfortunately, he does not define what he means by "architecture". And his definition of "problem domain" is shallow at best: business rules.

But why this dichotomy?

## It´s the requirements, stupid!

Strangely the term "requirements" occures only once in Robert C. Martin´s article. He associates it with tests. I completely agree with that. But why stop there?

Each and every trait of a software system -- the look of the UI, the performance of some calculation, the distribution of code across clients and servers, the choice of persistence technology, the number of classes, the interfaces of those classes etc. -- must be traceable to some requirement. This is true for coarse grained traits as well as fine grained traits.

The basic categories of requirements to me seem to be:

  * functional requirements or functionality for short
  * non-functional requirements or (primary) qualities for short, e.g. performance, scalability, security, usability etc.
  * evolvability, i.e. a special quality regarding the flexibility to adapt the software system to new requirements
  * production efficiency, i.e. a special quality regarding the ease and speed to implement requirements; it´s a quality of the development process

Software development thus is the art (or craft or disciplin) of making the right choices from a set of options to best fulfill the concrete requirements falling into those categories.

## Architecture for qualities

With requirements put first the question again is: What´s software architecture in particular about?

My simple answer to this perennial question is: Software architecture is about designing structures to fulfill non-functional requirements aka qualities.

I don´t care much about whether architects need to be top communicators in order to do this job. I don´t care much about whether they need to be top notch coders to do this job. I don´t care about their tools or the level of their architecture documentation. Just do whatever is necessary to transform requirements into "ideas" of structures for code (and other artifacts).

Architects don´t build, they design. That means they think -- before someone else implements. (Please get me right, when I say "architect" I don´t mean a person but a role. The same person can be an architect at one moment and something else in the next moment. I do not advocate special architect job positions. Right to the contrary: I think each and every developer should hone his architecture skills.)

Sure, architecting software is not easy. Not because so many paradigms and technologies need to be taken into consideration, but because of the need to balance. Qualities are contradictory at times. They can pull software structures into opposite directions. Designing for performance might impede evolvability. Designing for security might impede performance.

Architects thus need to deliberate much. They need to think.

Yes, not too much. I know. BDUF´s still bad. But some thinking is in order. All else would negate thousands of years of engineering success. Where the requirements are clear, up-front thinking leads to a solution -- however tentative that might be.

So when does thinking about qualities end? Does it end after choosing MVVM over MVC and encapsulating MongoDB access with some kind of adapter or moving business logic into stored procedures?

I won´t say so. Because architecture is whereever anybody decides anything with regard to qualities, especially when it´s pertaining to the software´s structure. That means, architecture is at work while (!) doing TDD. Because what drives the refactoring of a solution? It´s some quality, not functionality. Why extract a method, a class? Why segregate interfaces? Why follow IoC and do DI? That´s all architectural questions.

There´s nothing sacred or lofty about architecture. It´s simply about a couple of issues that need to be resolved, quality issues. Anybody with the right knowledge and capabilities can be an architect. In fact every developer is every day.

## Functionality for the problem domain

The second term Robert C. Martin uses is "problem domain". With the above categories of requirements I guess I know what he means by that: functionality. Not quality, but functionality. That´s fair enough.

And he says, tests should be used to formalize functional requirements (i.e. desired behavior) before the implementation. I agree with that, too.

What I don´t get, though, is: Why not continue to apply the human brain afterwards? Or even before? Why devalue thinking in the form of "thinking up a design"?

If (functional) requirements are clear enough to hard code tests, why aren´t they clear enough to at least come up with a solution sketch for the part of the problem domain in focus?

Again and again I have seen experienced developers fail at simple problem domains like "kata roman numerals". They don´t fail because they lack extraordinary TDD skills. No, they fail because they have little practice in actually "thinking about solutions before coding". Theír tool chest contains only a single tool: code.

So what to do about refactoring? Well, where should an idea of a better structure come from when you´re not used to thinking before coding? Refactoring as the third TDD step just defers thinking to the last possible moment -- and beyond, as the many TDD examples show where not much refactoring was done. Refactoring is optional. Nothing forces refactoring in TDD. That´s why Keith Braithwaite came up with ["TDD as if you meant it"](http://www.infoq.com/presentations/TDD-as-if-You-Meant-It).

But why then say, "They just haven´t gotten it! They need to learn to do better TDD!"? Why not question for a moment the "traditional" TDD approach? Why not -- as Justin does -- introduce at least some thinking before coding?

The cleanliness of code which TDD might aim at also is just one of many qualities -- which needs to be balanced against others, like production efficiency.

At least I´m happy to sacrifice some elegance and cleanliness for efficiency and readability. That´s why I think before I write the first test, no, even before I prioritize test cases. And I think about the design of the code. What functional (!) structure should it have to make it easy to understand? How does that collide or play together with testability?

So I´m an architect while doing TDD. I´m a problem solver. And more often than not I´m not surprised by the coded solutions, but see them to comply with my ideas of how a solution should look like. I know the steps of converting arabic numbers to roman numbers before (!) I start coding. In fact I´m writing code to match my conceptual (algorithmic) approach.

## Continuity in designing software on all levels

Architecture is thinking about structures, that is structures to deliver qualities. Solving the challenges of the problem domain ist about structures, that is structures to deliver functionality (in accordance with qualities).

Software is a self-similar system with many levels. It consists of wholes containing parts being wholes again for even smaller parts etc. "It´s [holons](http://en.wikipedia.org/wiki/Holon_(philosophy)) all the way down" to use a term Arthur Koestler has coined. And because of that the same principles apply on all levels, not just DRY, SRP etc., but also "thinking helps".

There is no discontinuity as Robert C. Martin suggest. Right to the contrary! Like there is strategic design, there is tactic design and situational design. And that means, there is thinking before doing. There is engineering before hammering and welding.

My interpretation of what Justin has written is: Use your head before you sling the code to make a test green. With that I agree wholeheartedly, even though I might disagree with some details of his approach.

The dichotomy Robert C. Martin suggests between architecture and problem domain does not warrant a fundamentally different approach to design on those different levels. Because design is about structure (and thus about options and decisions). And structure should not be an afterthought or be stumbled upon.

But before someone accuses me of advocating waterfall development: Yes, I do! :-) Because that´s how the world works. Before there is a man made structure, man better has thought about it. Design up-front is inevitable. Even if you want to you cannot avoid it. You just can hide it or deny it. But it´s there.

The question thus is not whether to design before coding or not. It´s not about waterfall or not. It´s just about the scope. If the scope encompasses so many requirements it would take you 3 months to design and 8 to implement, then that´s of course not gonna work. But if the scope is much, much smaller, say, 5 minutes of design and then 10 minutes of implementation... then that´s perfectly ok. The solution thus lies in ever smaller "waterfall iterations". And -- as always in life -- it helps to be humble. If you devise a solution design don´t deem it above new insights. Always be prepared to revise it.

Which brings me back to Justin: I haven´t seen any TDD demonstration where 5 or 10 minutes of "design thinking" have been applied before coding. That´s sad. Because it makes it harder than necessary to learn to appreciate the power TDD can have. It´s a great tool -- if not taken as the only one to come up with designs.