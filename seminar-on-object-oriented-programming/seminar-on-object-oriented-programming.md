## [Seminar on Object Oriented Programming](https://www.youtube.com/watch?v=QjJaFG63Hlo)
Note: This talk presents how Smalltalk group at PARC was thinking about OOP back then.

### First known form of OOP
I wrote my first program that I would call object-oriented in 1962 and people have been writing programs in that style even earlier than that. In my particular case I was a programmer in the Air Force at Air Training Command in 1962 there were no standardized operating systems of (course that's true today). But back then there was actually a reason for it nobody had gotten around to the idea of thinking it might be useful, and Air Training Command had a problem of moving tapes with records of various kinds on them from one Air Training Command base to another. The machines back then Burroughs 220, which were machines that have had about five thousand characters of storage and were about the size of this room and were great coffee warmers. My image of them is with this huge set of boxes with a row of pots on top trapping the heat as a came out.  Now the problem that they had was that there is no way to standardize on what the formats of the different records were. They changed and the operating system. It was usually just the kind of a loading program and so there was no way of standardizing on that and they wondered how can we actually read these data records if everything is constantly changing and nothing holds still. Somebody thought up a great idea. That idea was to have the records shipped in the following format. Each tape file had three sections to it: the front section was fairly short, it had a bunch of relative pointers into the second section which contained bunch of Burroughs 220 code and that code knew how to deal with a third section which had the actual data records. There are usually about 20 or 30 what we would call messages today. 20 or 30 entries in the first part and the code that came along with the tape records knew how to deal with all the data. **So in current day terms what the Air Training Command was doing (I think it was as far as the late 50s) was to ship an entire class of objects. The class was shipped with the protocol, with all of the code, and with all of the data in a form in which you did not have to penetrate any of it in order to make use of it.** That was used for a number of years as a technique until COBOL came in and the Air Force forced all of those good ideas to go away in order to standardize and COBOL which is a much weaker conception going back to the notion of data structures that are fragile.

### Encapsulation
our bodies have approximately a
9:27trillion cells in them and each cell is
9:31rather complex each cell has many
9:34millions of components in its own right
9:37so one of the ways nature discovered to
9:43control complexity and the kinds of
9:46interactions that are likely to happen
9:48is to try and incapsulate them in
9:52various ways this is a familiar
9:53principle to us it's something that we
9:55use in regular program
9:56as well trying to encapsulate and the
10:00question you're always asking when you
10:03encapsulate we're going to ask this
10:04quite a bit later is just what is
10:07encapsulated what kinds of things are we
10:10trying to control are usually in regular
10:13programming what we encapsulate are
10:15sections of programs that occasionally
10:19will try and encapsulate with regard to
10:21a protocol for dealing with some system
10:23we don't want to inquire about the
10:25internals of what biological systems
10:28encapsulate is the actual environment in
10:32which most important processing takes
10:35place there are very few object-oriented
10:38programming languages that go that far
10:40the average object-oriented programming
10:43language encapsulate snot the
10:45environment but in fact something like
10:50the state of a data structure along with
10:54the procedures that know how to
10:56intimately manipulate it and try and tie
10:58those two areas together in a way that
11:02they cannot be penetrated from the
11:05outside when people speak of an
11:09object-oriented programming language
11:11like Objective C or C++ they're talking
11:14about even less than that because
11:17they're the encapsulation is almost a
11:21convention it's done by means of macros
11:25the amount of protection at runtime that
11:29is delivered is rather low so there all
11:33of these gradations now biological
11:35systems encapsulate with a vengeance
11:37because nature discovered that if you
11:41give each cell its own little captured
11:44ocean and let it devote about 90% of its
11:49actual energies to simply protecting
11:53itself from the outside world as though
11:55the outside world were hostile then you
11:58get a situation where you can build very
11:59large structures rather safely and
12:03encapsulated is not just the saline
12:06solution not just the organic Moloch
12:10skills but also encapsulated and not
12:14just the programs that drive the cell
12:17but in fact encapsulated in biological
12:19organisms as many of you are aware is
12:21the entire plan for the entire structure
12:25okay now we don't generally do that when
12:29we write an object-oriented program but
12:31in fact people are starting to do that
12:33now in artificial intelligence and
12:36people who are interested can can bring
12:38this up later so my particular
12:52my particular motivation
12:59when I started thinking about objects
13:06was simply that of biological cells and
13:11one of the things that is difficult to
13:14escape when you look at biological cells
13:16is first the extent to which the outside
13:20world is kept away from the cell
13:22membrane and then the other thing is is
13:25that the cells aren't completely in
13:27isolation they communicate by means of
13:29sending messages to each other and again
13:32the way we way we translate that into
13:35computer terms is done in a much more
13:40restrictive way than biology does it
13:42biology generally communicates without
13:44wearing who's going to receive I'm going
13:47to talk a little bit later about a
13:49object-oriented strategy in which
13:52messages aren't sent at all they're only
13:54received you might think about what an
13:57object-oriented system might be like if
13:59you never sent a message but objects
14:00could receive what would they receive
14:04all I could do is receive the
14:07translation of this model into machine
14:13terms for me 25 years ago or so was that
14:19these biological cells acted a lot as
14:22though they're on a network you can
14:24think of it as a crossbar switch or a
14:28Ethernet type network in which every
14:31object can send to every other object
14:33and each one of these things is a lot
14:36like a little computer in fact is very
14:42difficult in a good object-oriented
14:44system to find out where the hardware
14:47stops and the software begins and the
14:52this notion of a little computer in the
14:56in the large here is something that is
14:59worthwhile considering when we think
15:00about making very small things now
15:03there's a principle in design that
15:07people came up with many years ago it's
15:11called the basic principle of recursive
15:13design and the idea is make the parts
15:16have the same power as the whole
15:20we know in the factorial example that a
15:25recursive program like factorial its
15:29charm is it's able to reinvest the
15:33conditional branches and so in some
15:36sense the program remains as long as
15:39that is true the program remains as
15:41strong as it was when you entered it
15:43because you can always reinter it
15:45instead of getting diluted away now
15:49another thing that that crossed my mind
15:51when I was pondering these ideas back in
15:54the 60s was why if that is such a
15:58powerful idea why is it that we take a
16:00very powerful idea like a computer and
16:04dilute it immediately in most
16:06programming languages divided by
16:08dividing it up into data structures and
16:10procedures data structures don't have
16:13the same power as a computer they're
16:14static can take on marks but they're
16:18once once you get a data structure it
16:21just sits there procedures don't have
16:24the same power as computers because they
16:27can't remember state they have to have
16:29something additional so what we did in
16:32the guise of following standard math
16:34mathematical notation in the 50s when
16:37Fortran was developed was to mimic
16:40standard mathematical notation without
16:42thinking about this basic principle of
16:44recursive design because people didn't
16:45write recursive programs back in the 50s
16:48and so the baby is thrown out with the
16:50bathwater almost immediately in a
16:52standard procedure and data structure
16:55language and it occurred to me and other
16:59people who are thinking about these
17:00ideas back then what if you didn't do
17:04that what if the only subdivision you
17:07ever made in a programming language was
17:10a subdivision of a computer into a
17:13computer you're never allowed to
17:15subdivide the computer into something
17:17that was less than the computer and what
17:19does that mean that means that each
17:21subdivision has to be something like a
17:23black box that has inside of it some
17:27mixture of State and process from the
17:31outside you
17:32can only invoke behavioral attributes
17:36rather than invoking method attributes
17:40and what I mean by that is this is
17:42something that was even in Fortran
17:44because the earlier designers of Fortran
17:46realized that there is a very funny
17:48correspondence between procedural things
17:50and data structure things so for
17:52instance when you say Si and parentheses
17:5630 close parentheses in Fortran you
18:00can't tell by looking at that whether
18:02you're invoking a function or whether
18:06you're accessing an array and that was
18:08not accidental back then because of
18:12course they thought of arrays as being a
18:13kind of a function and they wanted you
18:17to be able to write arrays huge tables
18:21still done today in order to do
18:25functional evaluation very quickly what
18:28they didn't realize is that you wanted
18:30to be able to trade-off between the two
18:31but that notion of just saying sine 30
18:36degrees without indicating how its to
18:38compete be computed is the essence of
18:41the kind of abstraction that that
18:43object-oriented programming is all about
18:46it's carried very far here by
18:55this strong membrane of the object so
18:58that what we're dealing with here are
19:00behaviors and there are two important
19:04implications that had to be worked out
19:07early on one of them is that messages in
19:11most cases can't be commands or you're
19:16violating the notion of the object as
19:18being in control now most
19:21object-oriented systems today when you
19:24do what is called sending a message you
19:26are issuing a command Objective C C++
19:30even small talk eighty all of those
19:33systems a message is actually something
19:38very very close to if not identical to a
19:41certain kind of procedure call okay but
19:45in fact in the original scheme and we
19:47can talk about the implications of why
19:49this is a good idea
19:50later in the original object oriented
19:54systems that were so successful messages
19:56aren't commands at all what they are are
19:59desires
20:01I'd like to have this happen just to
20:05give you an example of why imagine we
20:07have an object masquerading as a
20:10critical system file and the question is
20:14it should just anybody be able to come
20:17up and issue the command to it turn byte
20:205 to 0 now it's done all the time but in
20:25fact in an object-oriented system you
20:28would like the object to be able to
20:29protect itself so that even a person who
20:33has a pointer to it even a person who
20:35has the knowledge of which command is
20:38the right command that both of those do
20:42not imply that you have permission to
20:45actually change that file so in the when
20:49I talk about an object-oriented system I
20:51mean an object in which the worst you
20:55can do to an object is to simply
20:57indicate to it that you would like it to
21:00do something for you and the best that
21:03can happen is it will do that the worst
21:07that can happen
21:08to it internally as it will simply
21:10refuse it may put you may take your name
21:13and give it to the principal later if
21:17you've done something wrong but so this
21:20notion of absolute control that messages
21:23can't be commands and the other one is
21:27because the object is no longer a data
21:30structure in any sense that we regard it
21:32that assignment is something that can't
21:37be done from the outside either so the
21:40assignment statement has to go away in
21:42the form that we know it as an
21:44irrevocable change to a variable or a
21:49slot in a data structure an assignment
21:52has to be changed by something that we
21:53can think of as being advice or
21:56influence so again this notion of
22:01getting an object to to change its state
22:04is something that we normally don't do
22:07in object-oriented programming because
22:09normally in object-oriented programming
22:11we are not simply trying to imitate data
22:13structures now to be a data structure is
22:17that thing that if you send it to
22:21somebody else you're giving them
22:22permission to change it that's what I
22:25mean by a data structure so it's clear
22:28that some of the things that we call
22:29data structures in normal parlance in a
22:34system with an operating system that
22:36offers some protection are not strictly
22:39classical data structures by that means
22:41certain files usually have protections
22:44on them so that in a good operating
22:47system when we send a file from us to
22:51somebody else
22:52we are not can conveying to that person
22:55the same level of protection necessarily
22:58that we have been granted so in a good
23:01operating system this is this may be an
23:03operating system that you've never seen
23:05but there there have been operating
23:07systems in the past there exist
23:09operating systems now so that if you
23:11have a certain set of permissions for a
23:14file a and you wish to give it this file
23:19to your friend suppose you have the
23:22the magic permission to change the any
23:25byte in the system file because you're a
23:27honcho then you might wonder should I be
23:31able to pass on those permissions to the
23:36next person that I give this file to the
23:39answer to good operating system is no
23:41each person should get their own
23:44permission separately and when they
23:46receive this file a it's their
23:49permissions that are granted by the
23:51operating system that obtain not the
23:54permissions passed on to them by
23:56somebody who had the file before so you
23:59can think of taking this desperately
24:02important file passing it along and when
24:08it goes to somebody who is less to be
24:10trusted with it they have fewer
24:12permissions on that there are fewer
24:14things that they can do with it and then
24:16they passed it on to somebody again that
24:19may go back to a trusted person that
24:21person should be able to reintroduce
24:27that is called capability protection and
24:31capability protection is again another
24:33one of these old ideas from the 60s
24:35intertwined in a very strong way with
24:40object-oriented design that is now
24:42coming back capability is simply a
24:45technique for protecting objects in a
24:49stronger way than normal digital
24:51computers allow them to be done and
24:54again at the end of the at the towards
24:57the end of the talk we'll talk a little
24:58bit about this so to me there are lots
25:04of different ways of talking about
25:06objects but probably 90% of the reason
25:10to me for dealing with objects at all
25:13has to do with their abilities to
25:15protect in various ways protect by
25:20encapsulating various kinds of things
25:22almost always state less often control
25:27is encapsulated and so forth then about
25:3110 percent of the use of object-oriented
25:34programming to
25:35has to do with its ability in whispering
25:39to you how you might design a system
25:41better and just one more note about that
25:44before I get started on the on the talk
25:46proper and that is that the way objects
25:52are used today is a little bit confusing
25:55because they're intertwined with a
25:57another set of ideas that came out of
26:00the 70s that are very similar
26:03particularly in implementation these
26:05days and that's what's called data
26:07abstraction how many people are familiar
26:09with data abstraction as a idea okay so
26:13data abstraction looks a lot like
26:15object-oriented programming but its
26:17intent is different the intent of data
26:20abstraction is to take a system that
26:24you're familiar with like Pascal or
26:26Fortran that is starting to run into
26:30difficulties of various kinds difficult
26:33is usually a representational ones I
26:36think everybody's had the experience
26:38programming in a language with data
26:41structures you get this big system done
26:44you decide you need to change your
26:46representation and the next thing you
26:49know you're hunting down all of the
26:51procedures that think they knew about
26:52the old representation and the rule of
26:55the universe is that there's always one
26:57or two that you don't find so you slide
27:01in the new representation and a couple
27:03of months later one of those procedures
27:06is invoked and all of a sudden you have
27:08a crash and people wonder why the answer
27:11is the critical knowledge has actually
27:15been spread out in such a way that it
27:16can't be recovered it's like what you
27:19have to do after you do a multiplication
27:21in order to recover the the operands you
27:24have to do much more work like the
27:26difference between differentiation and
27:28integration the same thing is true is
27:31once you've lost information in a
27:32century in a system once the entropy has
27:36gone up then it's very hard to get it
27:38back so one of the things that you try
27:42and do with objects is to try and
27:44maintain the
27:46as much informational content as you
27:48possibly can
27:49in a smaller place as possible now data
27:52abstraction techniques use a similar way
27:55of wrapping an envelope around a data
27:59structure and invoke operations by means
28:02of procedures in order to try and get it
28:07to be a little bit more representation
28:08independent the difference though ADA
28:12for instance is a language that is a
28:15data abstraction language is not an
28:18object-oriented language and even the
28:21the people who actually understand ADA
28:22don't claim that but you can do certain
28:25kinds of things that are now today
28:27called object-oriented in Ada so this
28:32envelope of procedures is wrapped around
28:34the data structure in an effort to
28:37protect it but then what happens is that
28:40this new structure that's been created
28:42is then treated as a data structure by
28:44all the rest of the program the result
28:48is in particularly in ada is that the
28:53programs are not small the programs
28:56aren't any smaller than they were before
28:59and one of the hallmarks of
29:00object-oriented programming if you have
29:02any sense of whether you're doing it
29:05right or not is that the programs are
29:06remarkably smaller because there's a way
29:11of using the design that is not simply
29:15imitating a bad old idea which is data
29:18structures and trying to shore it up by
29:20putting it in an orthotic brace but in
29:23fact to go beyond the notion of data
29:25structures so for instance in in a NATO
29:28way of of doing object-oriented
29:30programming one typically comes out with
29:35something that looks very much like a
29:37data structure it has fields that are to
29:39be written to it has fields that data is
29:42to be taken out of the structure is
29:45static there's no actual process going
29:48on and it's essentially a slightly more
29:52abstract way of doing data typically in
29:55an object a good object will not
29:57actually permit you
29:59to write assignment statements to it at
30:02all because an object generally will not
30:07look at all like a data structure just
30:09to give you an example we can contrast a
30:12personnel record as it might be done in
30:16Ada in which we still wind up with
30:19fields as we had them before some of the
30:23fields might be a little bit more
30:24connected but it's still a large thing
30:27it's still passed around as a passive
30:29object we could contrast that with an
30:32object-oriented approach with which
30:33would be to try and turn the personnel
30:35record into something much more like the
30:38like a real person in other words this
30:41personnel record instead of sitting
30:45there on a file waiting to be
30:46manipulated would actually be trying to
30:48participate actively in some sort of
30:51simulation instead of changing the
30:54person's age from the outside the way
30:58you might do in a data record the age of
31:01the person would change dynamically as
31:03the birthday was passed because there
31:06was something in this object that was
31:07actively looking at the clock actively
31:10running in some sense the notion of
31:14being able to edit the object from the
31:16outside would be much less in the sense
31:19of editing the actual fields so objects
31:22even in a in a programming language in
31:25which everything is an object like small
31:28talk objects tend to be larger things
31:30than data structures they tend to be
31:34components active machines that fit
31:39together with other active machines to
31:40make a new kind of structure just to
31:43give you an example of a modern attempt
31:47at large scale object-oriented
31:49programming which hasn't been done very
31:51much for a long time the largest
31:52object-oriented system was small talk
31:55zone system which was even though it had
32:00its own user interface and its own
32:02operating system and its own sets of
32:07editors and facilities and file system
32:11and every other kind of thing the small
32:12talk ad system
32:13that is distributed by park play systems
32:15for instance is only about 40,000 lines
32:18of code which to me is is 10
32:22approximately 4 to 10 times as large as
32:25it actually needs to be it's actually
32:27kind of junky in various ways but when
32:32you consider that the UNIX kernel it's
32:33alone is 400,000 lines of C and that is
32:37thought to be a rather small kernel in
32:39the operating system domain you can see
32:41that most object-oriented programming
32:43historically the programs have been tiny
32:48the all of the stuff that we did at Parc
32:51that led to the Macintosh could be
32:54summed up this includes the equivalent
32:56of about 15 different Macintosh
32:58applications including mac draw and mac
33:00paint and all of those things were
33:03summed up by approximately 175 pages of
33:08code or approximately 8,000 lines of
33:13code that included the operating system
33:15the user interface and everything these
33:18programs are tiny when they're done
33:20right because of that people have been
33:23very suspicious of them in the world for
33:26instance that you come from you know
33:28does this idea really scale is it just
33:31for toy problems and so forth the most
33:34recent example of object-oriented
33:36programming in the large that I know has
33:39one done by Arthur Anderson consulting
33:41at the Brooklyn Union gas company over
33:44the last year now Arthur Anderson I
33:47don't know how large the jobs typically
33:49are at McDonnell Douglas but Arthur
33:52Andersen consulting typically and I
33:55think they do some work for McDonnell
33:56Douglas but typically when they get to
34:00work on a job their clients have already
34:02failed a couple of times and
34:03implementing it they're usually called
34:06in at the last moment they charge twenty
34:11to fifty million dollars a pop for one
34:15of these jobs and their jobs typically
34:17run to about one and a half million to
34:19two million lines of COBOL this this is
34:23done over a period of about a year and a
34:25half to two
34:25years by a highly trained group of
34:28people I think of as technological
34:30Marines they have a very rigorous
34:37high-spirited training facility called
34:39st. Charles they have a approximately
34:4127,000 people who do this kind of work
34:45and it's a fascinating fascinating set
34:47up I'm on their technical advisory board
34:49and I got on the board partly just
34:52because I was interested in the culture
34:53of this particular company I was really
34:56surprised that given how successful
34:58they've been that they have been
35:00shifting their entire set of operations
35:03over to objects over the last five years
35:06or so it's an enormous change for them
35:08because they have it's not the change in
35:12going from a non object-oriented
35:14language to an object-oriented language
35:15the change of going from one kind of
35:18culture to another kind of culture it's
35:20a change that as Koon mentioned about
35:22paradigms the reason the paradigm shifts
35:24take 25 years or more in science is in
35:28order to have a paradigm shift in
35:29science you generally have to let the
35:30old physicists die off once once people
35:35have learned a technique and have gotten
35:37comfortable with it is extremely
35:39difficult for them to go to something
35:40else the Macintosh user interface in its
35:43early stages had that difficult people
35:46had gotten so good with function keys
35:48that they actually felt diminished by
35:53using the mouse even after was shown to
35:55them that the mouse is four times more
35:58efficient in speed over what they've
36:01been doing with the function keys it
36:03didn't seem that way to them because
36:05they've gotten so adroit with it and the
36:07same thing is true with any technique
36:08that people use so Arthur Andersen has
36:12done a number of different pilot
36:14projects but last year they started the
36:17first large implementation this is a
36:20project that was a reimplementation of a
36:24system that had been done some years ago
36:26and it was originally designed to be
36:29done in the standard Arthur Anderson
36:31case tools and the estimate was 1.7
36:35million lines of COBOL and approximately
36:382 to
36:39two and a half years of implementation
36:41time to do this enormous system which is
36:44both both an accounting system and a
36:47management information system and as an
36:50experiment they decided to left a New
36:52York group which had been the pioneers
36:54in object-oriented programming do a
36:58implementation using object-oriented
37:00techniques now of course they didn't
37:02have an object-oriented language to work
37:04with for their end result this was to be
37:07done on IBM mainframes 30 90s there are
37:12no object-oriented languages extant on
37:18the 30 90 so they did a trial
37:20implementation to test out the design in
37:24small talk taking a few months to do it
37:27and then wrote a set of library routines
37:31and some pre-processing macros for PL 1
37:34and then we implemented this project
37:39with about 10 programmers in PL 1 so the
37:43results of that are now in the minor
37:47interesting thing was that they got done
37:49about 6 months early the major
37:53interesting thing was that the amount of
37:55code that actually had to be written to
37:57do this Amandla to 150,000 lines of this
38:01library is PL 1 as opposed to the 1.7
38:05million lines of COBOL that their
38:08estimates had done before so this is a
38:11factor of 11 less code and from their
38:14standpoint the six months was down in
38:16the noise because the the months that
38:19they're interested in are the 5 or 6
38:21years of maintaining the code from then
38:24on and being able to reuse those modules
38:27as they are going to be able to on other
38:303090 implementation so in some sense the
38:34the fact that you can program faster
38:36that you're you can save time and so
38:40forth in object-oriented programming in
38:42in the larger world is not nearly as
38:45interesting it as it is in research and
38:47research basically the ability to do
38:49quick prototyping dominates almost
38:52everything else
38:53in the large world the world that you
38:55come from the world that Arthur Andersen
38:57is in quick prototyping is something
38:58they'd like to do they're starting to do
39:00it but it's not nearly as important as
39:02maintainability reusability is the
39:07second thing if they can reuse a module
39:10as a component in some other system then
39:14they have saved themselves an enormous
39:17amount not of time although they have
39:21certainly done that but to them it's not
39:24time but it's designer skills the thing
39:28that all large companies are weak on is
39:31having enough designers to go around
39:33they're usually plenty of people to
39:34write code but the designers are few and
39:38far between and this notion that a
39:40successful design can actually be moved
39:43from one place to another in components
39:45is something that literally drives the
39:48Arthur Andersen people crazy with joy to
39:51to think about so they have now come up
39:52with an object-oriented repository and
39:55are starting to craft rather large
39:59useful objects that can be used as
40:01standard components and building blocks
40:03in various systems and we'll talk a
40:05little bit later about how one goes
40:07about to me this is what object-oriented
40:09programming is about it's not saving
40:13data structures from itself it's not
40:15making a slightly fancier data structure
40:18it's not even making a data structure
40:19that can implement certain kinds of
40:21constraints within itself and so forth
40:24it's thinking of those objects as
40:27independent machines going back to this
40:30whole biological notion that it's one
40:33thing to build cells and it's another
40:35thing to build tissues and for people
40:40who are just starting out in
40:41object-oriented programming they're
40:42usually thrilled that they can build
40:43cells but the real goal is to be had
40:46when you move from cells to thinking
40:48about what are the tissues what are the
40:50conglomerations of these atomic style
40:53objects into components that if you were
40:57to have three or four hundred of them in
41:00a repository usable by any programmer
41:04what would you be able to build
41:06could you be able to Tinkertoy things
41:08together could end-user programmers be
41:12able to do a considerable amount of the
41:14programming and retailer and so forth so
41:18the real change if there is one I think
41:22I think it's coming faster than we think
41:24that object-oriented programming is
41:26going to bring along is actually both a
41:29change in the way professional
41:31programmers do their work but even more
41:33so a change in the way these
41:35applications are designed another
41:37example for instance at Apple now we
41:40design all of the applications that we
41:43do as though they are going to be
41:46actually tailored not completed but
41:50tailored by an end-user a person who has
41:55programmed almost not at all
41:57person who's used HyperCard a few times
41:59so this is a really big change and it's
42:03something that has been talked about for
42:0520 years or more but it's something that
42:08just now is possible to actually do what
42:11does it mean well it means what you'd
42:13like when you get an application from
42:14somebody is to be able to use it right
42:19out of the box read them the manual
42:22understand what it is don't have to sit
42:27down and think about it as a kit or
42:29anything but just use it the way you're
42:30used to using it now it's a temporary
42:32solution to some set of problems you
42:34have right now also you wouldn't be
42:35using it but a month later your old
42:39attitude about this ad this application
42:41has changed completely month later now
42:44you're saying boy I wish this thing
42:46could do this and I wish this thing
42:47could do this everybody does that person
42:50who's never program before is only used
42:53the computer for a couple of weeks after
42:55a couple of weeks they'll say boy I wish
42:56this thing could do this and I wish it
42:58could do that and that's the point where
43:00you'd like to hit the hood latch button
43:02on the application and open it up and
43:05see something in there that was
43:07comprehensible right now if you open an
43:10application on the Macintosh you open it
43:12up it's sort of like looking into the
43:14hood of a Mercedes Benz or something
43:16there's this mass of tubing and if the
43:19thing had a carburetor you
43:20find it because it's a mass of spaghetti
43:23mostly machine code on desktop micros
43:26but doesn't matter whether it's machine
43:28code or Fortran it's a mess and on the
43:33other hand what the user wants to see
43:34when they open it up is something that
43:36looks like a Model T they want to see a
43:39schematic even if there's a Ferrari
43:42underneath the Model T they want to see
43:44a Model T they want to see a schematic
43:47engine of what makes that application
43:51tick because they've already got an
43:52intuitive notion about how that works
43:54and then they would like to be able to
43:56make changes at the level of that
43:59schematic engine there are a bunch of
44:01applications you can buy for the
44:02Macintosh now in which that's possible
44:05an example is focal point and most many
44:09other applications written in hyper card
44:11because hypercard is a an
44:12object-oriented language set up so that
44:16professional applications programmers
44:18can give you not just architectures not
44:21just a kit but working architectures
44:24working kids and then after you've used
44:26them for several months you can make the
44:28change that's going to change the whole
44:30way we go about designing things
44:32professional programmers won't be
44:34designing programs for each other or F
44:36at its worst professional programmers
44:39tend to design programs that will keep
44:41them in job security there's a class of
44:46programmer who delights in the obscure
44:48they love the fact that they are the
44:50only ones that can understand how this
44:52program works and there's a maxim that
44:55says if you're the only one who
44:56understands how it works you don't
44:57understand how it works and so progress
45:02is isn't to be made there so so I think
45:06I'm going to go into the the give you an
45:11idea about where some of these ideas
45:12came from the one thing I think you may
45:15be a little bit surprised to add is some
45:17of the earliest object-oriented ideas
45:19were some of the most sophisticated and
45:21it will be revisiting them in the next
45:24five and ten years to come one of the
45:27reasons for this is that because you
45:29couldn't make money in computing in the
45:3160s many of the people who
45:34had ideas about how computing should be
45:36done in the 60s had extremely pure
45:38conceptions those conceptions are
45:42powerful yet today and it's worthwhile
45:45showing you a few of them
46:01so just just as a reference point
46:09I like I always like to start off with
46:11this slide because this is my vote for
46:18the world's first personal computer this
46:23picture was taken at Lincoln labs in
46:251962 summer of 1962 and this is a
46:29machine called the link and it's
46:33especially appropriate to mention here
46:34since the person who invented this
46:36machine West Clarke had a research
46:38project at Washington University for
46:40many years
46:43sponsored by ARPA those things that look
46:46like Dec tapes over on the side he
46:48actually invented they were called link
46:50type tapes originally and this is kind
46:53of a metaphor for our talk which is the
46:59best that Dec could do with these ideas
47:02that came out of Lincoln labs as well
47:04when Dec saw this machine in the early
47:0660s it said boy what a great way of
47:08making a small mainframe and it
47:11immediately adapted the the architecture
47:15of the link to make many computers but
47:18Dec said well people aren't used to
47:21looking at displays let's make that an
47:23option so he took the display away and
47:27people didn't understand what was
47:32actually on the link tapes some obscure
47:35stuff so they said well let's put files
47:37on the link tape so I'll call him Dec
47:39tapes and out of this machine Dec was
47:44able to come up with the astounding idea
47:46of the mini computer whereas in fact
47:47about 2,000 of these were built in the
47:5160s and an astounding as far as I've
47:54been able to determine is an astounding
47:55900 of them seemed to be still working
47:58today now they were designed for
48:02biomedical labs for technicians who
48:07needed to do their own programming and
48:09needed to do real-time experiments and
48:11it was an almost perfect machine by the
48:13way what was on those original link
48:16tapes what was on there were the pages
48:17of the virtual memory this first
48:19personal computer
48:21had it's very hard to go out today and
48:25buy a personal computer that has a real
48:30virtual memory this machine had it back
48:32in 1962 so as an excellent idea but like
48:36many things thought of it it actually
48:40was so far ahead of its time that it
48:42took another decade or so for people to
48:44catch up to it
48:48one of the very first object-oriented
48:50software systems and one that's I think
48:52a particularly in this talk is Ivan
48:55Sutherland sketchpad which is also done
48:58at Lincoln labs on the tx2 computer
49:01which was the last computer in America
49:04large enough to have its own roof and in
49:07fact was it was about four times the
49:10size of this room and every Thursday
49:13they would take it down and change about
49:1610% of it because they were always
49:20putting new things it had some of the
49:21earliest core memory ever devised and
49:25it's quite a remarkable machine for its
49:27day it was used as a single user machine
49:29by Ivan Sutherland to invent sketchpad
49:33and you see him here he's working with a
49:37bridge truss sketchpad is very difficult
49:40to appreciate and just by looking at
49:44slides so I thought I would show you a
49:46videotape of it in operation so if we
49:48could run the first videotape take a
49:54look and see what this again is the
49:57summer of 62 is tape number one stop
50:08could you we I thought that was rewound
50:10could you rewind that please
50:20and then show it
51:02now back then they didn't really have
51:03computer displays as we know them today
51:06so that tx2 here is actually simulating
51:09the lines by drawing dots rubber band
51:13technique that you've seen before now
51:15here's something that I even invented
51:16which is he's pointing at the edges and
51:19telling sketchpad he wants them all to
51:22be mutually perpendicular and sketchpad
51:25just solved that problem we see the
51:27sketch pad is the first system to have a
51:29window the virtual paper he's drawing on
51:34is about a third of a mile on a side
51:38here the constraint was make the lines
51:40parallel now the constraint is
51:43collinearity so sketch pad wasn't just
51:48the first graphic system was also the
51:51first non procedural programming system
51:56so everything is controlled by non
52:01procedurally giving goals that the
52:03system has to figure out here he's
52:05making the guidelines invisible to get
52:08some dashed lines
52:16so he's made himself a flange now he
52:18wants to make a rivet and this is why it
52:21was called a sketchpad that you didn't
52:25want to have to be precise he wanted to
52:26be able to just sort of sketch things
52:29he's gonna use that as the center for an
52:30arc and now he's going to again point to
52:39those and say make them mutually
52:41perpendicular that pulls the center
52:43which pulls the arc which makes it
52:45symmetric which makes the rivet because
52:48of the way that program is implemented
52:50you can actually see it solve the
52:52problem there's actually quite
52:58sophisticated this is a nonlinear
52:59problem that's actually solving
53:12so no matter how he distorts it it comes
53:15up with the same general shape and he
53:16could constrain the ratios of the
53:19lengths if he wanted to now what he's
53:23been working on there was actually what
53:24we today would call a class he called it
53:26a master and this is an instance of that
53:31Rivet can make it larger or smaller
53:45so he wants to latch it into the flange
53:47here you can see that this program
53:52rapidly led to better display designs
53:59these are other instances of the rivet
54:02and now he goes back to the master and
54:07says well let's make those guidelines
54:08invisible so it looks more like a rivet
54:10and we see that the instances
54:12dynamically feel that change so these
54:16are not copies but actually dynamic
54:18instances
54:34okay and now he shows that any
54:36constructed thing can be a master so he
54:41had made the plan for the rivet into a
54:42master now he's pulling instances from
54:44it and rotating them and changing them
54:47and so forth
54:58okay if you stop that tape please so
55:03sketchpad even today is an amazing
55:05program you can't buy a graphics system
55:09that is nearly as as good today in the
55:14sense of it being a comprehensive system
55:16for allowing you to set up problems
55:23allowing you to solve problems its
55:26implementation not just its appearance
55:28was also object oriented and the style
55:33was something that Ivan settlin came up
55:35pretty much on his own because of the
55:39difficulty in dealing with many
55:42different kinds of objects and having
55:44them solve constraints and being able to
55:45make pictures for them of themselves and
55:49so forth so he got interested in this
55:50idea that each object could actually
55:53have its own drawing procedure embedded
55:56in it and all you had to do is be able
55:59to send the message draw to any of the
56:02objects and it would invoke the correct
56:04procedure although would be a different
56:06procedure each time and the same notions
56:08were later used for constraints now I
56:13once I asked to Ivan I said Ivan how how
56:17is it possible for you to in one year
56:20just by yourself come up with the
56:22world's first graphics system the first
56:25non procedural programming system and
56:27the first object-oriented software
56:29system and he said to me well I didn't
56:31know it was hard
56:35fortunately didn't and actually it has
56:38it has barely been improved on since
56:39there have been some improvements since
56:42the system called thing lab done at park
56:45about a decade ago or so was an
56:48improvement on it this whole area of
56:51constraint driven object-oriented
56:55programming is something that is a hot
56:57topic in research right now and I think
56:59for the first time in twenty years is
57:01actually going to yield some fruit over
57:03the next five to ten years the reason is
57:06is that people who do mechanical design
57:10particularly such as you do here at
57:13McDonnell Douglas require now for the
57:17first time serious simulation of the
57:21mechanical design particularly how it
57:23articulates with other parts of the
57:25design really want to have a simulation
57:28job-shop built into the design system so
57:32you can do a lot more than just finite
57:34element analysis but be able to do
57:37analysis of linkages and other kinds of
57:40situations that are too difficult to do
57:44simple in analytic solutions or do
57:46finite element analysis and the answer
57:49to this is a kind of constraint driven
57:52object-oriented design the sketchpad
57:55actually invented the first kind of so
57:58let me give you another example I'm
57:59going to go to the number four tape this
58:04time though
58:13okay okay I'll pause well had some
58:29interesting questions actually one of
58:36the things I should have mentioned at
58:37the beginning is I'm perfectly happy to
58:39entertain questions that at any point I
58:42believe that the the we have an hour and
58:47a half that the at least an hour of the
58:54hour and a half I think we should spend
58:56talking about issues that concern all of
59:01us about object-oriented programming I
59:03have some of my own people who are
59:06starting out on it may have some crap
59:08you the trepidation they may wonder
59:11where it's going what the actual
59:14leverage is I had a a question asked
59:19again about the difference between
59:20abstract data structures and what I
59:24think of as a real object-oriented style
59:26another question was asked about is
59:29there any way of preserving already
59:31written COBOL and Fortran code in an
59:34object-oriented fashion so it doesn't
59:38all have to be thrown away and maybe
59:43that last question is one that's worth
59:46while answering now a lot of companies
59:50are trying to figure out what to do
59:55about object-oriented programming
59:57particularly given that there don't
60:01exist any good object-oriented
60:03programming languages for programming in
60:05the large small talk is not a good
60:09language for programming in the large as
60:11it's currently distributed it's a great
60:14language for learning about
60:16object-oriented programming because it's
60:19written entirely in itself and so you
60:22can learn how an operating system how a
60:25user interface
60:26how applications how little things and
60:31larger things can be represented in an
60:33object-oriented form how inheritance
60:37subclassing and so forth all those
60:39things small talk is ideal the of the
60:43small talks around to look at the one
60:47that has the best manual is the one
60:49called small talk V and it runs on both
60:53the IBM PC and the Macintosh it's not
60:59the mote it's it's a rather complete
61:01system in in a number of ways the other
61:08system is called Park Place small talk
61:11small talk
61:128e and it is sort of the granddaddy of
61:15the small talks that that Xerox has
61:20released it has a even more complete set
61:25of system tools and some very ambitious
61:29applications written in it
61:32both of those are worthwhile looking at
61:35but for programming in the large objects
61:40aren't enough I don't believe and the
61:43reason is that at some point it's not
61:47simply a matter of piecing together
61:49something that is supposed to run it's a
61:53matter of being able to verify different
62:00sections different parts different
62:01modules independently to be able to
62:04unplug and replug and even I think in
62:08many cases it's desirable to allow
62:11different implementation languages to
62:14actually be used now if we look at the
62:20the standard
62:33so we have a glob and the main principle
62:36in object-oriented programming is to
62:38separate the outside from the inside so
62:43on the outside we have a variety of
62:48messages that we're willing to respond
62:50to and on the inside we have some
62:54methods oh sorry
63:01we have some methods the may or may not
63:06correspond to these things on the
63:09outside cuz whatever the idea is we're
63:10not supposed to understand what the
63:12inside looks at from looking at me on
63:15the outside and outside thing might even
63:18correspond to a little data structure
63:21inside a thing equally innocent might
63:25correspond to an enormous amount of code
63:27there might be code in here not directly
63:30connected to this and in fact some of
63:33the messages that the object may be able
63:35to receive aren't directly characterized
63:38in terms of some outside protocol lots
63:43of different variations here but the
63:45most important one here is that we're
63:48trying to separate a protocol
63:58from some methods
64:07at this level and then if we think about
64:09going a little bit more fine-grain where
64:12we started having zillions of objects
64:15interacting
64:24in a sea of messages
64:29in fact some of the
64:36some of the objects might not even be on
64:38the same machine they might actually be
64:40over here a good object-oriented system
64:46you shouldn't be able to tell what
64:47machine you're running on that's what
64:50messages are all about very quickly when
64:54we're starting to build a large system
64:56down here we've got something
64:58interesting we have absolute protection
64:59but we still have confusion right
65:03because it's you can have thousands of
65:08thousands of diamonds that are
65:11impervious to all normal wear and tear
65:15and still not be able to build the
65:17simplest structure out of them they may
65:19need to be too shiny may not be able to
65:21pile them up they may not fit together
65:23but by god they're perfect so what I'm
65:27trying to say is that the the protection
65:30issue is a critical one but it still
65:32doesn't guarantee that you actually have
65:34an architecture now in small talk in the
65:40most object-oriented systems how you
65:42come up with these guys is govern very
65:46much by convention there's a particular
65:50way like it's a convention in small talk
65:52systems that one of these guys will
65:53always be called print so that for every
65:58object in the system you're guaranteed
66:01that one of the messages you can send to
66:02it is print and theoretically what that
66:08means is this little patch of green in
66:12here that corresponds to print is
66:16supposed to print for you now there's
66:18nothing in small talk or any other
66:21object oriented system right now that
66:24guarantees that printing is going to be
66:28done now there was a strictly
66:31conventional it's something that
66:33everybody agrees to it's like
66:35overloading operators in Ada when you
66:39overload plus in order to give plus more
66:43meanings for different structures you're
66:45usually trying to adhere to something
66:50metaphorically similar to what plus
66:52originally stood for so for instance if
66:55you have a plus a plus it adds two
66:58numbers together you might overload it
67:00to apply two arrays so that the
67:03operation is some sort of point point
67:07point addition maybe vector addition
67:09sometimes you might overload strings -
67:15what could + mean and strings well one
67:18of the one of the ways of thinking about
67:19strings algebraically is that plus means
67:22concatenation because it's a way of
67:24adding two unary numbers together and so
67:27forth and at some point you started
67:29stretching it as you stretch the
67:32metaphor but generally you don't want
67:33Plus to go off and do some sort of
67:35multiply or something else but the only
67:38thing that controls that is some agreed
67:41on set of conventions and because of
67:45that what this protocol is how
67:48complicated it gets and so forth is the
67:51most important part in any kind of
67:54object-oriented design but it's also the
67:55most fragile the fact that there's
67:59nothing to protect print is absolutely
68:04critical let me let me give you an
68:05example of what we could do to protect
68:08print
68:17one of the things we could do is to have
68:22instead of having print just be code we
68:26could actually have a print class
68:38and its offspring its instances are
68:42actually structures that look like this
69:15okay in other words each offspring of
69:18print is a message method pair in which
69:28unrestricted code writing over here is
69:31not allowed does everybody understand
69:34why this is an interesting idea because
69:39so but if you could only if you can
69:41write anything here then J random
69:44programmer often will as you go as you
69:49go along and the fact that the system
69:51seems to be conventionalized at this
69:53protocol message level which is the very
69:57charm of object-oriented programming why
69:59object-oriented programs work so well
70:00why they fit together gets destroyed as
70:04the amount of generic information in the
70:09actual methods gets diluted but if
70:13another way of doing an object-oriented
70:15system is to actually make classes for
70:20each of the major code types that you're
70:22going to write and what you get here is
70:24something that would insert itself in
70:27here but in fact the only codes you're
70:33allowed to write are certain little
70:34restricted boxes in here and this thing
70:37guarantees that it's going to print for
70:39you it's not going to go off in zero
70:41byte five of some system file this thing
70:45because it came from a print class and
70:47because the print class does printing
70:49type things every piece of code that
70:52goes into a protocol actually is going
70:54to do something like printing and what
70:56you're allowed now is a certain amount
70:58of parameterization a certain amount of
71:00freedom but the meaning of print now has
71:04been nailed down because there's some
71:06actual code from the print class
71:09sticking behind here that you can't see
71:11that's going to make every effort to
71:14deliver a result that is what you want
71:16this is like types in type languages
71:21except it's stronger because it can
71:22controls the goal of the result the goal
71:27of the result not
71:28the shape of the result right in a typed
71:33language when you have a typed variable
71:35or type procedure what you can state is
71:39that might have some integer parameters
71:41and I'm going to deliver a
71:43floating-point result what you can't say
71:47in the type statement is what the intent
71:49of that procedure was the only intent
71:52that you could indicate is that's going
71:54to in it's going to give you some sort
71:55of floating-point result you can't say
71:58it was supposed to give you a sine or
72:01cosine or anything else that is up to
72:04the convention of the actual programmer
72:09itself so what I'm just pointing out
72:11here is that if you take a if you take a
72:16system in which there is a protocol you
72:20can get a lot out of it just by having
72:22the protocol be a convention agreed on
72:25by everybody as you go into a larger and
72:28larger system that that inside out
72:32outside Ness will protect against the
72:35inside getting dissolved by some hostile
72:40act action by the outside but what will
72:42get diluted as you go to a larger and
72:44larger system with more and more
72:46programmers is whether the protocol is
72:49going to have any meaning practical
72:52example in small talk has approximately
72:57Park Place small talk has approximately
73:025000 of these green things each one of
73:06them is there each one of them can be
73:08reused by inheriting it from somebody
73:11else the number of red things it has is
73:15on the order of twenty one hundred that
73:20means that the amount of how generic the
73:25code is with respect to the protocol is
73:27not much right it should the number
73:31should be more like 400 or so different
73:34red things four hundred concepts and say
73:38five thousand realizations of those
73:40concepts
73:41now print is the happy exam exception to
73:44that because if you have a 154 different
73:47kinds of objects than their 154
73:51different green guys and only but only
73:54one print concept so there's the same
73:58technique that people use overloading of
74:00operators for you want to reduce the
74:01concept space by making it more
74:03algebraic make take a concept make as
74:07metaphorical as you possibly can and
74:11like equal is a good one
74:13what does equal mean some systems that
74:17means we have I'm looking at exactly the
74:20same thing some systems it's okay for
74:23the same if the same things look the
74:24same some systems is if under some
74:28particular evaluation rule they evaluate
74:30to the same thing or they might evaluate
74:32to the same thing so equal is one of
74:34these very slippery notions because it
74:37very quickly becomes useful to think of
74:40equal as being very useful in terms of
74:44equivalent this is equivalent to that
74:48that's a generic notion so again you
74:51might imagine that one of the one of the
74:54things you might like to have be generic
75:00are comparisons equal equal is a much
75:04stronger one of course than greater than
75:05or less than because greater than less
75:07than involve some sort of sorting but
75:10again greater than and less than don't
75:12have to apply just two numbers in small
75:15talk there's a super class called
75:18magnitudes and anything that can be
75:21sorted in any way under any kind of
75:23sorting rule is underneath magnitudes
75:26and underneath magnitudes are things
75:30like less than and greater than
75:35so for instance dates are an example
75:39times time intervals anything that can
75:42be sorted in any in any form you can
75:46those what you might what you would call
75:48operators in a de or automatically
75:51overloaded now what happens in an
75:56object-oriented start off with a nice
75:58set of these and then as practical
76:02programmers chew on it the heat of
76:05debugging one of the things we
76:06discovered is that even good programmers
76:08don't make up generic operators for
76:14things what they do is they make up any
76:15old word think they can think of at the
76:17moment write a method for it and
76:19continue on the result is that what the
76:24object-oriented style was buying for you
76:27starts diluting it starts gradually
76:29diluting away the manuals get larger and
76:34all of a sudden you're back to something
76:36that is close to what you had before so
76:39I'm not I'm not sure if people didn't
76:41understand this explanation I'll be glad
76:46to go over it again because it's it's
76:50it's one of the important examples of
76:52something that you can actually do with
76:53an object-oriented system everybody more
76:56let's get what I was talking about that
76:58you can actually legislate one of the
77:00things you can do in an object-oriented
77:01system is to legislate to some extent
77:04even what the code that the programmer
77:07is going to write is going to deliver to
77:08you you can build in to these main
77:13concept classes the tests to see whether
77:17the code is it all behaving the way you
77:20think it is those tests can be run
77:22independently of the programmers who are
77:24writing the code now another thing you
77:27can do using these protocol ideas is
77:31horrible as it sounds there's no reason
77:34why you can't put some COBOL in here
77:38this is not something that people do in
77:42a typical object-oriented language like
77:43small talk because it's designed to to
77:48write all of the methods in itself but
77:51if you think about this whole notion
77:55here as a binding mechanism for a
77:58component not just as a way of
78:01protecting a data structure but a
78:03binding mechanism as a component then
78:05what you really are programming in terms
78:07with is the blue and the red what the
78:16green is is almost completely
78:18independent as long as it conforms to
78:24whatever this guy wants it to be able to
78:27do what I advise large companies when
78:31they are embarking on object-oriented
78:32programming is to do a few systems using
78:36something like small talk or preferably
78:39just to get an idea of what it's about
78:42but then think of all the things that
78:44you've already learned about controlling
78:46modules and systems and realize that the
78:50small sizes of the code of the small
78:51talks from the 70s don't have all the
78:54protections in there that you actually
78:55need what you really need is what these
78:58days is called a configuration language
79:00a C language configuration language
79:13and this language can be independent of
79:15all of your method languages it's it's
79:19something that is dealt with it the
79:21operating system-level it's something in
79:23which the protocols are chosen as much
79:26as possible ahead of time it's a
79:28standard vocabulary of concepts that
79:30you're going to use to write in it's one
79:32in which the protocols are controlled by
79:34active code the give you places to write
79:38code and insert other code that allow
79:41you to bring over a COBOL routine or a
79:43Fortran routine or whatever the heck you
79:45want and bind it in it's a binding
79:47mechanism it's a way of setting up
79:51environments for debugging modules
79:56independently of each other it's a way
79:58of assuring yourself that a module will
80:00be able to move from one place to
80:02another it's a way of discovering
80:04whether you want to use a module so at
80:08some point the ability for human to read
80:11this configuration language is going to
80:12be much more important than the ability
80:14to write it one of the embarrassments
80:18that you often find in an
80:20object-oriented language is you have all
80:22of us we have usable code and it's too
80:25hard to find the modules you want to
80:27reuse small talk has a lot of that
80:30flavor anybody who's ever tried
80:32programming and especially in small talk
80:3480 is bewildered by the fact that the
80:39system is completely written in itself
80:40there are tons of usable things in there
80:43and yet it is such a pain to find those
80:45things you wind up tandem out having to
80:48read other people's code and then in
80:51order to find out whether you actually
80:54want to use the stuff so the for
80:57instance what Arthur Andersen is doing
80:59right now is to try and come up with
81:04something that is completely independent
81:06just completely x-out forget about the
81:12interior stuff just come up with
81:14something that is basically modules in
81:17terms of blues and Red's making the the
81:21red message protocol be as powerful as
81:23possible controlled by other things and
81:25then using that
81:26as a dynamic binding mechanism for
81:30configuring programs it allows them to
81:34take large sections of database and
81:38sequel calls that they've already done
81:40and bind it into an object-oriented
81:42framework as an example yeah yeah
81:57so configuration
82:02let's start off with the things that you
82:04might want to have in it now the there's
82:08only I only know of one actually good
82:11configuration language that's been done
82:13as a language called C Mesa which was
82:17done by the Parc computer science lab
82:21about ten years ago and it served
82:25exactly this this purpose and here are
82:28some of the things can have it there are
82:31some things that you'd expect just from
82:34your previous experience you'd expect
82:36that there would be some sort of message
82:39name for something you'd expect that
82:45there would be I Oh parameters so that
82:53you would have input expectations
83:02output expectation
83:11a good configuration language has a an
83:13executable predicate you can think of as
83:19a goal that they may have a variety of
83:26them and I connect those with when I say
83:31input expectations I mean not just the
83:35types of the parameters that you expect
83:37to send to it and the types of the
83:40results but also these predicates sorry
83:47predicates you can think of
83:52preconditions on the input side and
83:54goals on the output side
84:04you can think of those as being
84:05executable there are environmental
84:17expectations
84:22one of the difficulties in most
84:25object-oriented programming languages is
84:26although you can protect an object what
84:30you don't have any sense of when you
84:32want to move an object is what the
84:34object itself expects to have as
84:36environment as a give you an example in
84:42small talk you can write an object move
84:49it for one place of a particular
84:50Smalltalk system to another but when you
84:54want to take it out of your small talk
84:55system and give it to somebody else a
84:57small talk system you often are
84:58unpleasantly surprised and it's not that
85:02the object has been solid in any way
85:04it's that it has some other assumptions
85:07about its environment that you weren't
85:09thinking about before in particular
85:13small talk allows you to do the somewhat
85:16obscene thing of allowing you to go and
85:20change existing super classes to make
85:23them more the way you like the benefit
85:26of this is that every class and the
85:28system feels this improvement and the
85:30problem with it is if that improvement
85:32is important then you've all of a sudden
85:34have done away with your portability so
85:37what I'm trying to point out here is
85:39that the modularity you get in
85:41object-oriented programming is slippery
85:43and one of the most critical things to
85:45do is to be able to pin down the amount
85:50of modularity that's actually there I'm
85:51gonna I'm going to go into that in a
85:54little more detail so the there are more
86:00things that are here people have design
86:06configurations languages in such a form
86:09that you can actually from the runnable
86:13parts of the stuff that you can actually
86:14derive an explanation
86:16mechanically of what the method and what
86:21the module itself is supposed to do
86:30okay so there are any number of things
86:34basically it's something a little bit
86:37more close closer in spirit to Parnas
86:40they've partners who did one of the
86:42original notions about information
86:44hiding although it wasn't
86:45object-oriented than what you might
86:47think of as straight object-oriented
86:49doctrine and that each one of these
86:52these things is part of
87:04this blue
87:10no Sheena that this forms a class from
87:17which we get the various instances that
87:21our system is actually made up of so
87:23each each a little instance
87:41now it is often the case that if these
87:47two predicates here are done correctly
87:49you can actually run you do your
87:53prototyping by running the blue thing
87:56essentially without any green things
88:00inside of it or you can think of it
88:04being just tiny little green things that
88:06come along because of what these are yes
88:17okay the this is it's similar to ADA
88:23except that ADA for instance doesn't
88:26have inheritance and so does everybody
88:30here understand what I'm not sure I
88:32didn't come to give a tutorial so I'm
88:34not sure what I'm what I was supposed to
88:36assume everybody knows about the thing
88:37but in most object-oriented languages is
88:40this notion of inheritance that you can
88:45define something very general and
88:47abstract like
88:55say a thing called a magnitude
89:02in a magnitude maybe something even more
89:07abs I mean let me use the fresh sheet of
89:08paper
89:14start off with something really abstract
89:17like a general object and then one of
89:25the operations and an object you might
89:27want to have for every object is
89:29equality then a little less abstract you
89:36might have something called a magnitude
89:40one of its operations might be less than
89:46but there still that might not be any
89:49notion of what addition is coming down a
89:52little bit further you might have
89:53something called a number and it might
89:59have a notion of plus and there might be
90:05a various specializations of numbers so
90:08you might have an integer a fraction
90:15these guys might have their own versions
90:17of plus the notion of inheritance is
90:21that very often you can get a compact
90:26sorry you can get a compact description
90:30of a wide variety of behaviors by
90:35factoring out behavior as abstract li as
90:39you possibly can you move it as high as
90:41you possibly can and occasionally you
90:44may have to give your own versions of
90:47things like integer may want its own
90:50version of what plus generally is it may
90:54even want to have its own version of
90:55what less than is or may be able to use
90:57this general one up here and but
91:02inheritance actually allows you to
91:06cascade descriptions and in a number of
91:10object-oriented systems particularly the
91:11AI ones you can actually blend them
91:14together in various ways so you can
91:16actually say this this thing is not just
91:20a number it is also a geometric object
91:22and inherit a bunch of things from the
91:25side as well so what
91:28go to when I talk about doing the
91:31configuration stuff I mean to imply all
91:38the things that you usually do in a
91:40typed language but also applied to a
91:46system that has inheritance because it's
91:48inheritance in object or any languages
91:50is how you share things the goal of
91:55release it has been the goal for the
91:57last 20 years of people who do this and
91:59write very small very reusable very
92:03compact code the goal goal is to make
92:07the things that are shared as abstract
92:11and inheritable as they possibly can be
92:15so you want the smallest number of
92:19maximally independent concepts that you
92:24can Tinkertoy together and have some
92:27confidence that the active Tinkertoy is
92:30going to give you something that also
92:32still works the whole idea in
92:35object-oriented style is to linearly
92:37combine things together not a native
92:39package allows you to subsume some of
92:45the details of a data structure it does
92:49not allow you for instance to define
92:53generic operations which are then
92:57inherited by subclasses because it
92:59simply doesn't allow you to subclass and
93:03what that we leaves you add is a single
93:06single layer of description for
93:08something which you can get instances
93:10from but you can't you generally Eneida
93:12do not write an abstract thing that
93:15you're going to get in instances from
93:17because usually these very abstract
93:20types like magnitude and so forth aren't
93:23things that you want to use directly
93:25they're really placeholders for general
93:27code and strategies and this is a
93:30foreign idea in the in the aid of
93:32programming world which is almost
93:34entirely concrete yes
93:37well I do to an actually ADA shouldn't
93:42even really call them generics from but
93:45it's yeah it's okay anybody can use a
93:47name for whatever they want but it's
93:48that's a it's a different way of
93:51thinking about what generic is than what
93:52I'm thinking about here the generic
93:54power in an object-oriented programming
93:56language is your ability to not just
94:00reuse a concept sideways but also to
94:02advance it abstractly the more you can
94:06advance it abstractly the more chance it
94:08has of being involved in in an abstract
94:12design the less probability you have of
94:15having to recode whole strategy here's
94:19is true is to avoid recoding remember we
94:23got off on this thing I'm just pointing
94:24out there's just really just an aside
94:27remark that you could make a very strong
94:36object-oriented programming language by
94:39being completely independent of whatever
94:43the methods are actually coded yet that
94:46was the whole point behind that
94:48digression that as you build yourself
94:51object-oriented tools you're much better
94:53off worrying about the integrity of the
94:57individual objects and then the next
94:59thing is can an object be a component
95:01and fit into some larger scale protocol
95:05when I say a component I mean something
95:07like let's say a paragraph of text or
95:11generic gear something that actually has
95:14a fair amount of meaning behind it might
95:15even have its own inference engine as
95:17part of it talking about something that
95:20can be used in a wide variety of cases
95:22in which the sharing is more than
95:24parametric you're really getting not
95:28just a class of things you're you're
95:31sharing a notion that somebody has come
95:34up a concept a set of concepts that
95:36somebody has come up with this obscure
95:43it's the hardest it's actually the
95:47hardest thing to explain simply because
95:50I'm gonna try another pass at it one of
95:55the reasons it's hard to explain is that
95:58the this notion because of ADA being
96:01called object oriented being taught in
96:03school as being object oriented actually
96:05has clouded the the issue considerably
96:08so it's very difficult to even explain
96:12why some of these ideas are more complex
96:15let me give you another completely
96:18different idea this has to do with
96:23another way of thinking about modularity
96:26now in most object-oriented systems the
96:35modularity that is gotten by them is one
96:40that is regard to the state that you put
96:44in each each object what isn't modular
96:46is the control
96:52this is another set of issues to talk
96:54about so for example one of the things
97:01that you may see when you're looking
97:02into an object-oriented programming is
97:04is you may see the state and each neatly
97:06encapsulated but you may see control
97:09going all over the place what happens
97:10when you send a message the answer is
97:12often I don't know
97:13goes here goes there and find somebody
97:16here talks to this guy dozens of things
97:19happen and I can't even tell whether
97:22control is ever going to get back to me
97:24that's often the state of affairs now
97:29what would happen if we actually made
97:31control modular
97:41we'd have something more like this where
97:46instead of control going through the
97:48objects the objects themselves are
97:50sitting in a sea of messages but they
97:54don't actually originate them themselves
97:56how is that possible well one way you
98:01can imagine for it to be possible is for
98:04the objects to simply say I need to know
98:10the following put needs in here
98:31now the object there are object-oriented
98:34system is one of the ones we've just
98:35developed at Apple one that we did at
98:37MIT is an object-oriented system in
98:40which you never send a message okay you
98:45only receive how is it possible well the
98:49system contrives to make the messages
98:51get to you by looking at your needs and
98:55looking around to see who might supply
98:57those needs
98:59okay is this obscure okay so an example
99:06is suppose your
99:17suppose you're a a button whose job it
99:24is to move the corner of a window so one
99:29of the ways of programming that is for
99:33you to be in a loop constantly looking
99:37to see if the mouse is coming into you
99:40okay it's a polling solution to the
99:43problem where somebody is polling
99:45somewhere but you're constantly looking
99:47to see whether the mouse is coming in
99:48when the mouse comes in then you say
99:50okay now I know what to do I'm going to
99:54latch on to the mouse's coordinates and
99:56I'm going to tell my window owner
100:00exactly how he should be moved around
100:02and so as we move around the corner the
100:04window corner moves around itself and so
100:10that's that's this kind of style of
100:11programming control is explicit we have
100:15to poll to find out things that are
100:16going on the other way of doing it is I
100:20could just say I need to know when the
100:23mouse comes in to me and then I can do
100:29my job this is like an on condition but
100:34it's an on condition that has to be
100:35scoped because we can't have it
100:40happening every time the princess the
100:42mouse button goes down but we can
100:45imagine that this guy can say okay I
100:47have a set of conditions I'm not going
100:50to explicitly look for it I'm just going
100:52to tell the world that if I had these
100:55conditions come true for me
100:57then I would be able to fulfill my
101:03obligations to the rest of the system
101:05I'd know what to do likewise the window
101:08that encloses this guy could also have a
101:12set of conditions that say well if the
101:14corner if my corner guy starts moving I
101:17should probably move too
101:19I'll change my size if he moves so if
101:23only if somebody would let me know that
101:24then I'll go along see what this is like
101:27this is like constraint programming okay
101:29we're going from
101:31a procedural style which controls past
101:35explicitly around to a declarative style
101:37in which were simply indicating needs
101:40and the system without having to do any
101:43problem-solving is picking up the slack
101:46by providing the actual information in
101:49the forms of messages HyperCard has this
101:51about half way it's a technique we've
101:54been experimenting with at Apple for the
101:56last couple of years and what it looks
102:00like it's able to do is to completely
102:04remove the necessity for actually being
102:07able to follow a control flow what does
102:09this mean when you move an object from
102:11one place to another
102:19when you move an object from some place
102:22into this kind of situation nothing is
102:26going to happen with sorry kind of a
102:30tiny screen isn't it and you put in when
102:33you move a new object in here in this
102:36kind of situation nothing is going to
102:38happen to that object unless you go in
102:40and recode somebody else in order to
102:42send it some messages right and so my
102:47modularity of being able to move an
102:49object from one place to another depends
102:52on me being able to do some kind of
102:54modification and the system is already
102:56there that's not so good it's good in
102:59the sense that this object is guaranteed
103:01not to hurt anybody and it's going to
103:04protect its own self from being moved
103:06around but in fact I still have to go in
103:08and make some sort of modification in
103:11order to get control the flow when I
103:19put in a new blue guy here
103:29and he has all his needs specified is he
103:34going to be able to run why
103:44because he doesn't have because the
103:47whole idea is that he's not intertwined
103:51with anybody else's control he's simply
103:54saying I know what I need god damn it
103:58then the question is can the system
104:00actually deliver those needs just
104:02because he's a new thing and the answer
104:04seems to be yes this is a peek into the
104:07object-oriented programming of the next
104:09couple of years in interesting you know
104:12if this the need to do things this way
104:14came out of yet another project with
104:16children all of the object-oriented
104:18stuff has developed at Park and the
104:21Macintosh user interface came from a set
104:25of designs to try and allow children to
104:30do serious programming on a computer
104:32that was what forced object-oriented
104:34programming out into the open the last
104:37set of stuff that we've been doing with
104:38children at Apple forced this out of the
104:41open because we wanted children younger
104:42than nine to be able to program and
104:45children younger than nine have a very
104:46hard time following control flow of
104:49course when we're thinking about that
104:51we're thinking well of course they have
104:52a hard time following control flow so do
104:54we except where you see the problem is
104:59adults are used to suffering so it's why
105:04I like why I like to design for children
105:06so designing this new programming
105:08language for children I'm going to give
105:10you a little example of some of the
105:11stuff programmed in it this notion of
105:17making control completely modular by
105:20going to a needs thing became apparent
105:23yes
105:27yes
105:33yeah well it's complicated because I'll
105:41give you I'll give you a simple example
105:44and then maybe we can generalize it a
105:47little bit the motivation came from a
105:50couple of years ago of you know
105:53wondering why it was so easy to program
105:55in spreadsheets and wondering what
105:58spreadsheets would be like if there are
105:59more object oriented I've always thought
106:01of the spreadsheet cells as being almost
106:03an object and spreadsheet cells have
106:06this nice characteristic that they they
106:09are these aren't they in other words the
106:13very act of writing the spreadsheet
106:15expression indicates to the rest of the
106:17spreadsheet system what your needs are
106:19now usually they're pretty simple needs
106:21they're just I need to know the values
106:23of so-and-so cells relative to where I I
106:26am but I got interested in generalizing
106:29that and started off with a spreadsheet
106:34system that I did in small talk that had
106:38a spreadsheet optimizer that first
106:41started off simply trying to look at
106:45places you wanted to get values from and
106:48building a propagation network rather
106:49than executing every cell every for
106:52every change in this especially I think
106:53most of you were aware that most
106:54spreadsheets today do not execute every
106:57cell there's a propagation network built
106:59by the spreadsheet compiler that you
107:01don't see that tries to find you the
107:06minimal number of things that have to be
107:08executed every time the change is made
107:11in the in the spreadsheet I started
107:13working on that and then the next thing
107:16is to go to billions where you're
107:19interested in whenever something like
107:21for instance whatever this is equal to
107:23that I would like to do something or
107:27whenever this is less than that I'd like
107:28to do something and the I'll just give
107:32you a hint of it
107:44so they start out with this fairly
107:50simple idea that if you have a variable
107:52somewhere one of the things that you can
107:57do is to link you can have a link to all
108:05of the different places that ever need
108:10the value of that variable and when this
108:15changes you simply fire off all of these
108:18guys and you get the desired result
108:24let's take an expression now so we take
108:30an expression like a is less than B or C
108:39is greater than equal to D and then ask
108:45what we'd have to do to that to make
108:47that efficient the answer is you make
108:50this thing into a little tree and at
108:53each stage each node of the tree you
108:59hold the very the value of the things so
109:03far
109:10so in this case the a value would be
109:13linked through here and you can think of
109:17the tree is pointing upwards
109:29okay and we can presume that this let's
109:33make this an just for the heck of it
109:42see that this is false and we assume
109:45that this is true and that this is false
109:50let's do it the other way I make this
109:52true
109:55this false so the idea is now if it
110:00changes the insight here is that all you
110:03have to do is compare it to whatever the
110:06current value of B is let's say this
110:09goes to to true you don't have to
110:12recompute this guy because it didn't
110:13change it's already part of this frozen
110:16result and then you come up and
110:18recompute this guy so you bait what you
110:21basically have done in this technique is
110:23to have sorted the actual computation
110:25that you have to make this this tech
110:28this way of doing things is called a
110:30continuously evaluating expression
110:41so it's a conglomerate of things it's
110:43actually a little computation engine
110:44designed to compute in parallel and only
110:48the stuff that needs to get computed
110:50gets computed so you the computation now
110:53the compiler instead of compiling
110:54machine code in a system like this is
110:56actually compiling a propagation people
111:00are interested in these techniques I
111:01refer you to the books on functional
111:03programming mostly being written in
111:07England these these days functional
111:10program is about this and well-behaved
111:14functional programming languages have
111:16the property that you can take any
111:17computation that has variables in it and
111:21through a fairly simple compilation
111:24change it into a network that has no
111:27variables whatsoever but simply routing
111:29x' for values does that sound please
111:33please interrupt me if that's it doesn't
111:36sound reasonable is that sound reason
111:38it's intuitively reasonable isn't it
111:41because what does a variable as a place
111:43you go to to get a value but of course
111:46you can what you really need in a
111:48computation is simply a value delivered
111:50you don't need the value to be anywhere
111:51except where the operator is so by using
111:56a combination of those techniques you
111:59can actually remarkably enough it's
112:07actually it's always surprising when
112:08these things work you can actually go to
112:12a thing that's an extreme generalization
112:14of a spreadsheet cell that does an
112:19enormous amount of parallel computation
112:22but in a way in which you see none of
112:24the interactions yourself
112:31now because of production production
112:34system it it's not at odds with the
112:37production system it's on this it's not
112:39like ops five as an example which is a
112:43production system I understand people
112:44use here it's basically it's orthogonal
112:50to whether there's a production system
112:52trying to do things or not
112:54ops five has an example in which the you
112:58have to order the rules yourself to a
113:01certain extent in order to in order to
113:03get efficiency and so forth and you can
113:08think of this as something which is
113:11independent of whether there are rules
113:12and I didn't say there are rules here
113:14what I said is that what we actually are
113:17interested in is whether there's whether
113:20there's a set of conditions that can
113:21deliver to me what I actually need one
113:24of the things you could implement with
113:26this idea is a production system I'm not
113:30but it doesn't lie it isn't particularly
113:32like a production system you could
113:34implement a production system using the
113:36idea though
113:37do you understand to say it just one it
113:42yeah because it because some production
113:44systems have to be executed in sorry
113:48we're getting killed for time we only
113:50have a half an hour so what I would like
113:52to suggest is that we just sit still
113:54while they change the tape is that okay
113:57should only take them 10 seconds
114:11I was brought up about what do you do
114:15with real time in fact what do you do
114:18with time and historically the first
114:28object-oriented programs that were done
114:30outside of machine code were done in a
114:33programming language called Simula and
114:36Simula had this way of looking at time
114:38the Simula he had
114:47a bunch of objects
114:53one for each entity that you're trying
114:57to model so the
115:05these guys might be modeling pipes
115:14and so forth and the blue the blue guys
115:16might be modeling reactors in a chemical
115:23plant or something like that but
115:27basically as far as seeing they're
115:28concerned they're all objects they're
115:31all trying to execute at once trying to
115:37get to the new trying to move advance
115:40the entire system time and they had this
115:44problem of if you have a system time the
115:46system clock that's going on
115:48how can you compute because you might
115:52actually run out of time for computing
115:57before you can actually advance to the
115:58next system time so what the similar
115:59people realize that they wanted to do
116:03was in between the system clock so
116:07system clock might be one and the next
116:13time any of these guys had to compute
116:17was two so what it would do is it would
116:23do all of the computing in between the
116:29ticks of the clock so the computing was
116:31actually outside the space of the
116:32simulation so Simula this is a non
116:36real-time situation simular running on a
116:39mainframe would compute an arbitrary
116:40amount in between each state change so
116:44guarantee that each as much as it could
116:46possibly do it would settle down the
116:48state of each one of these objects
116:50during this time when they were all in
116:53process as soon as that that had
116:55happened then it would say okay now I
116:57can go to the next time on the clock it
116:58is now - what do I have to do now then
117:02the clock could be frozen would compute
117:03like mad again advance the clock again
117:06now of course there's a huge conflict
117:10that's the way you generally do it when
117:12you're doing object-oriented program
117:14huge conflict between this and when you
117:16want to do real-time things because um
117:19real-time things you don't get to stop
117:21the clock the clock is moving along
117:25and of course one of the answers is if
117:29you don't have enough computing power to
117:31compute before the next time the clock
117:34ticks then you're dead anyway
117:36okay so let's assume that we have enough
117:38computing power and just to ask what we
117:42can do an object an object-oriented
117:44design to reconcile what time actually
117:49means and the way people generally think
117:54about time and object-oriented
117:55programming as time has entirely to do
117:57with who can view what when so it's a
118:02viewing operation so let's suppose we
118:04have our objects here and we have some
118:10views
118:18attached to the objects we can ask what
118:22is it like if one object is viewing
118:24another
118:30the first question I just should ask
118:32everybody this is absurdly simple once
118:37once you see it but the first question
118:40is when should I not be viewing the
118:42object when it's in transition right so
118:49it means I have to have at least a
118:51two-phase clock so the object really has
118:58two two states it's going in one is it's
119:00trying to settle itself to what it
119:02thinks as a stable state and the other
119:04one is one that's going to allow itself
119:06to be viewed
119:07okay so mmm let's we can do that and
119:11it's sort of a sort of a diagram here
119:19so here's the here's the object and
119:23here's the view so what we're saying is
119:27that when the object is computing we
119:30can't view and when the object is
119:34viewing we can't compute
119:45so we're gonna have a bunch of these
119:48little phases like this now that's not
119:53always useful sometimes this viewing
119:58thing is very long so the viewing can
120:02actually hold up the progress of the
120:04computation and so what can we do there
120:11this is suggested by actually this model
120:14so far just just curious to see if it
120:16suggests anybody what would be a good
120:17thing to do if to break this rigid
120:22synchrony we have what can you do yeah
120:27we could that's what's called slippage
120:30so we could actually arrange a slippage
120:32model so we let the as before as we had
120:37before we let the object compute and
120:41what we take is a copy of it that we let
120:47the viewer view
120:54and so the object in simulation can have
120:57an quite a number of phases as it goes
121:00along and every once in a while we get
121:07to view it
121:13we take let's say we take this guy right
121:15here okay now what's interesting is in
121:20an object-oriented system this slippage
121:23model is usually computed automatically
121:25by the the object in the view both of
121:29which are objects when you hook the view
121:31up to the object what they do is
121:34exchange information because one of the
121:36things that the object has some sense
121:37about is how long it takes it to settle
121:40it state typically the view has some
121:43sense about how long it takes to
121:44abstract the view and so they actually
121:46arrange and build a little buffer in
121:53between themselves and that buffer has
121:55the actual amount of information to
121:59allow the slippage to happen so the way
122:02this intertwines with doing real-time
122:03and deterministic computing is almost
122:06all real-time solutions to queuing
122:12problems knowing some sort of
122:15determinism they actually aren't
122:16completely deterministic what you
122:18usually do is you're saying I have some
122:20limits that I want to guarantee the
122:25computation is going to take place in
122:26between it I'm going to do enough
122:27buffering to make sure that those limits
122:30get down so for instance when you're
122:32doing real-time reading of records from
122:36Fast disks and so forth you set up
122:39buffer areas because you don't want to
122:42have to have real kind time constraints
122:44in every part of your real time
122:47computation in an object-oriented system
122:50these are usually handled by having
122:54what's called a viewing model small talk
122:57has one called models views and
122:58controllers which is quite general and
123:00has the facilities in it for generating
123:03all manner of slippage models in between
123:06by you putting on the outside what it is
123:09that you actually need to know from
123:11these objects at some point of course
123:13you can break it down there's no real
123:15time system you cannot break down but
123:18this gives you the maximum amount of
123:19automatic buffering that the system can
123:22generate without having to be explicitly
123:23programmed
123:27yeah very very large how can you well
123:51the way that's usually done is by trying
123:53to again it's that you know the stuff
123:57isn't a panacea but what you usually try
124:00and do is when you write a device driver
124:04in an object-oriented language what you
124:06try and do is ask what devices are
124:09likely to be like this device now what
124:12is this like so when you write when
124:17people do a user interface and an
124:19object-oriented language usually they
124:21don't write a driver for the mouse or
124:23for a tablet or anything else what they
124:25come up with is an abstraction of what
124:28it means to it's usually call a pick
124:30device it's an abstraction of what it
124:32means to be able to do selection and
124:35tracking and then one programmer at one
124:39time writes code for that and then if
124:42you come up in a system and it has a
124:44specific device you may have to write a
124:46line or two of additional code but it's
124:48written in a subclass below that the
124:51main driver is already written already
124:52been written in it's um it's not just
124:55doesn't just serve as the code for what
124:56you're doing it serves as the model for
124:59how you treat the actual devices when
125:01they're put in there so I'm part of the
125:04part of the the charm of the system is
125:07to be able to get away from the from the
125:10particular as much as possible and
125:13program as much as possible in the
125:15general case the whole act of
125:20subclassing is basically saying to
125:21something I want something just like you
125:23accept and the theory behind this which
125:28seems to work is that it is much easier
125:29to program differentially than it is to
125:32program from scratch it's much easier if
125:34you see something that is like what you
125:36want and you can get it
125:38in a way that um doesn't damage anything
125:42else then if all you could make have to
125:45make as incremental changes to it then
125:47you should be way ahead that's not
125:50always true you know there are always
125:53pathological cases always pathological
125:56cases but generally speaking like this
125:58is an example where the whole strategy
126:01once it was thought out was realized oh
126:04yeah this is something we can use it's
126:05not just for user interfaces we can use
126:07it for every kind of device drivers we
126:09can use it for every kind of real-time
126:11stuff where we have two different clocks
126:14going at two different rates and we're
126:15trying to synchronize in some way why
126:18should we have to write this over and
126:20over again why should some program we
126:21have to figure it out over and over
126:23again it's not that we have the solution
126:24to every possible problem but what we're
126:26saying is we've got a solution it's the
126:2980/20 rule get a solution to the
126:32eightieth you know 80% of all of the
126:34code you're ever going to have to write
126:35if you can put that into a superclass
126:39and then distribute it automatically as
126:42part of the solution so small so small
126:43that when you when you're doing a
126:46viewing operation and small talk you
126:48don't even have to think to yourself
126:49whether you should worry about
126:52synchronization or not until long after
126:56you may decide that you need it then you
126:58just have it oh it's already in here I
126:59just got it for free when I subclass the
127:01class view well try think like I say an
127:06ADA it's a little bit harder because you
127:08can't do those super classes that have
127:10all those goodies lying in there you
127:12have to you can do it with a macro
127:14operation people do to super classing
127:17and ADA by making macros that allow them
127:21to do a kind of copying and stuff
127:48No well in small talk no you can small
127:53talk allows you to dynamic basically
127:55small talk has no concept of loading
127:59code so everything is there
128:02dynamically into there and at any point
128:05you can go in examine any piece of code
128:08in the system you can rewrite any piece
128:09of code in a production case you really
128:12don't want to allow just anybody to go
128:15in and rewrite a superclass because of
128:19course the work it's really bad if they
128:21if the superclass starts doing something
128:24different
128:25generally when people go to rewrite a
128:26super classes to improve the algorithm
128:29that hundreds of applications are
128:32already using like you may go in and
128:34improve the sort algorithm yeah
128:51right that's why I was talking about the
128:55configuration so my belief is that in a
128:58production case you must have something
129:00like the configuration setup or else
129:05it's just too fragile it's not it's it's
129:09fragile in a funny way because in small
129:10talk we used to give $5 bills away to
129:15anybody who could crash the Smalltalk
129:17system it's very hard to crash an a good
129:21object-oriented system because there
129:22isn't anything you can get to that where
129:24you can actually hurt more than one
129:26layer of thing and then the system's
129:29says hey wait a minute what are you
129:30doing
129:30like in the small talk debugger as
129:34you'll discover I think there's a
129:35tutorial coming up has the anytime
129:38there's any kind of an error the system
129:42doesn't crash there was there's no
129:44concept of crashing the error is simply
129:47set aside as just another process and
129:50once when we were debugging the system
129:52we found 1,700 suspended errors waiting
129:57for somebody to take care of them and so
129:59I'll talk didn't care you know it's just
130:00an error comes up fine you know um set
130:04it aside it's right there you can go
130:06back to it anytime you want but keep on
130:07running it just keeps on running so the
130:11that's one of the reasons why we didn't
130:13do a configuration language because we
130:15were programming in the small and you
130:16couldn't hurt yourself
130:18so as the the worst he could have
130:20happened was something annoying they
130:23would come up but it wouldn't crash what
130:25you're doing so somebody who fixed it or
130:28make a note of it but I think that's
130:29intolerable in the production sense
130:33where you really don't well you have
130:36people who aren't part of the same group
130:38and so forth that you really have to
130:39have a configurations language and the
130:41super classes are the ones that you want
130:43to have most understood and most nailed
130:46down in particular the for instance in
130:53small talk it's often to make things
130:56like the sorting stuff parametric so
131:00you're actually sending in sorting
131:03objects that will do sorting for you
131:05as parameters rather than even putting
131:09that in embedding that into the the code
131:12just because you don't want somebody to
131:13try and change it that way you'd rather
131:14have it be something separate that you
131:17can dynamically bind in really good
131:20superclasses don't do much except act as
131:23really good binding mechanisms for other
131:27stuff that's going on
131:39yeah
131:43yes there is you can but again the the
131:48original the original small talk for
131:50example didn't use a kind of procedure
131:53call in order to send it really acted as
131:57though you're on a network and if you're
132:00interested in what order things had to
132:03be done in they they could actually be
132:06stamped and recued at the other end and
132:09people do do that when when you run
132:12small talk over the network people make
132:15the connection to the network by having
132:17what are called phantom objects and a
132:20phantom object is a stand-in from the
132:22object you're trying to send the net
132:23right because you're always sending a
132:24message to something
132:26so suppose yours suppose your
132:39so if you're over here and you think
132:45you're sending a message what you think
132:47you're doing is sending a message from
132:49object a to object B and but they may be
132:53on different machines and so what may be
132:55really going on is object a is sending a
133:01version of object B
133:11which is really going over the network
133:14to the real be again these are called
133:18Panem objects and usually there's just
133:21one class of them and whatever you're
133:24distributing a copy a computation
133:26usually the environment for the objects
133:31just consists of a few local objects and
133:35the rest of them are phantom objects the
133:36phantom objects take care of all the the
133:38network stuff and synchronizations and
133:43reorderings and other kinds of things
133:44that you have to do when you're going to
133:45slower slower media that's a
133:49well-established technique and any good
133:51object-oriented language you can set
133:53that up literally in an afternoon today
133:57oh it's quite instructive to think about
133:59what it means not to send just a message
134:02but to send an object from one place to
134:03another what part of its environment do
134:05you have to bring along with it in order
134:08for it to be understood see in theory
134:10sending an object let's say we send
134:14objects see across
134:20well si may not be terribly understood
134:24on the other side on the other hand it's
134:26still active so if your network has the
134:31rule as ours did it park that whatever
134:33an object shows up and its class isn't
134:36there its class a clone of its class
134:40gets sucked over with it so you compare
134:44that to sending a data structure which
134:45is sending bits and how fragile they are
134:50because you're not sure that there are
134:51procedures at the other end to know them
134:53here you're ensuring that either nothing
134:55at all happens or the right procedures
134:57are actually automatically sent along
134:59and so you can it's remember that story
135:02I told the beginning of the Vosges 220
135:04that's exactly how the training command
135:07protected their their tapes you just
135:09make sure the procedures go along with
135:11them and it's quite easy using these
135:13phantom objects to make that automatic
135:15so you can think of the network of
135:18objects as constantly rebalancing itself
135:21as to where the code actually is
135:35I think I believe that's true and from
135:42Park
135:43yeah it's written it's been written up
135:49yeah well my message to you is this is
135:52the same reason I told you the Arthur
135:53Andersen story is they have exactly the
135:56same you know their their attitude to me
136:01was kind of interesting they said they
136:03went to several phases and this is
136:05probably you're in one of these phases
136:07right now as well it went through one
136:09phase where the first phase with objects
136:12it was like magic God all the things you
136:14could do code is so small the second
136:16phase was complete disillusionment when
136:19they realize that for instance small
136:21talk which they were using as a model
136:23didn't scale they said you know what is
136:26you know is this the emperor's new
136:28clothes or what and I said no it's just
136:31because the part of the reason small
136:34talk wasn't built to scale was simply
136:36because we were able to do an enormous
136:39amount with very tiny programs and we're
136:43designing for children anyway and when
136:47you want to use these ideas and they're
136:48in the in the large I believe that you
136:51have to do a little bit more then you
136:53can go out on the street and buy that's
136:55what I'm my message to you is that and
137:00it was to Arthur Anderson that you know
137:02a lot about what it can once you've
137:05learned the object-oriented style which
137:07I believe is the right way a protecting
137:09state of the right way of making
137:12components the right way of making urns
137:14superclasses right way of sharing
137:16there's a whole bunch of right things
137:17about it in order to make it work in the
137:20large you then have to sit down and
137:23protect that by coming up with a
137:25configuration language and you can do
137:27yourself a lot of good by doing that
137:30carefully because the configuration
137:32language can include languages that you
137:34already have hundreds of programmers
137:36that know how to write in in other words
137:39the configuration language can be a way
137:41of protecting programs that are already
137:44written in COBOL and Fortran as well as
137:48new programs written in Ada it should be
137:49a really separate way you think of isn't
137:52and the architecture is opposed to the
137:54bricks of actually building the thing
137:57the architecture to me rules life is an
138:00architecture it wasn't
138:02as early as the turn of the century
138:04there are people that thought memory
138:05there's the stuff called protoplasm
138:07written about in books was supposed to
138:11be some special kind of material that
138:13you can build living things out of
138:14because people didn't believe that
138:16ordinary chemicals could bake you could
138:19make a living thing out of it wasn't
138:21really until 20 or 30 years ago that it
138:24was really shown quite definitively that
138:28we actually are just an architecture in
138:30fact we know now that the atoms in our
138:33body are actually recycled about every
138:35seven years so you and I as individuals
138:39are patterns in space the material is
138:42moving through we don't have the same
138:45atoms in our bodies that we had seven
138:47years ago we are a pattern and
138:50interesting things made out of the
138:53patterns you have - you know I have to
138:55have some understanding of the bricks
138:56and stuff which I think everybody is
138:58getting now but at some point you'll
139:00realize that the power of this stuff
139:02isn't from what the bricks do and that
139:04the bricks are have integrity the power
139:08of the stuff is from the architectures
139:11that you can create and the
139:12architectures have just been scratched
139:15now up until really a couple of years
139:19ago there probably been less than a god
139:21I don't know 100 or 200 people over two
139:24decades actually doing this stuff so
139:28it's the and the problems that have been
139:32worked on have tended to be small the
139:35reason I believe that object-oriented
139:36programming works well in the large is
139:38simply because it works well in the
139:40biological world and I see no reason why
139:42it is going to fall down in any way when
139:46we go large but in order to in order to
139:49make it work we have to either look at
139:51the biological world war which is the
139:55biological reason of urging can a
139:57configuration language or we have to go
139:59after for other reasons of just
140:01realizing hey this stuff gets fragile at
140:03this point what do we actually need and
140:06the answer is a configuration language
140:14but I think that there might be some
140:17immediate benefit these ideas of
140:20object-oriented design where you have
140:23existing systems that because it would
140:26nature
140:27the islands of automation approach have
140:29gotten tremendous ly complex and you
140:32need to be able to characterize various
140:35things possibly the concept of objects
140:38to help you do that and to help them
140:40understand what are the objects of one
140:43of the Linc
140:46right well I'm trying to think of it was
140:51Rudolph's irken that said you can't if
140:54you want to be a piano player you should
140:55spend half of your time reading books
140:57and his his point was is that if you
141:02spend all of your time just learning to
141:04move your fingers you have not absorbed
141:07any contact the context necessary to
141:09play any real piece of music that
141:11there's there's something else besides
141:13the practical application of the of the
141:16technique and I think that the somebody
141:18was asking me at the break it was a very
141:21good question actually which is and the
141:26it had to do with she doesn't sounds
141:30like objects make you do a lot of design
141:33and anyway but you know it wasn't said
141:37stupidly at all it's just said isn't
141:40that hard and I said yes it is hard and
141:43it's hard whether you've got objects or
141:45not the main reason is that objects
141:48provide both an excuse for designing and
141:51they also give you a framework for
141:52holding the design every little bit of
141:55design you do you get rewarded in an
141:57object-oriented system for having done
141:58it you really get rewarded where's it's
142:02hard to get rewarded in a in a procedure
142:04data structure system because often the
142:07design has nothing to hang itself on
142:10there can be local good things but you
142:12can't propagate the design forward the
142:15way you can in an object-oriented system
142:21I don't know because I haven't hung most
142:25you know Edward de Bono's says the
142:27problem with most American companies is
142:29that when they get in trouble they
142:30redouble their efforts so you know the
142:36idea is that we're basically too
142:37industrious for our own good and once we
142:39learn a technique we tend to put our
142:41head down and just fight like mad rather
142:43than trying to smart our way out of it
142:45like I said I particularly efference to
142:49me I had actually seen these techniques
142:50and actually programs using some of
142:52these techniques for five years for a
142:54period between 1961 and 1966 before
143:01Simula hit me on the head and hit me on
143:04the head just because at that point I
143:06had a problem that was much harder than
143:08I wanted to program it was the first
143:10time I was willing to actually see that
143:13was when I was going through insane
143:14minutes and I said to myself holy cow
143:17this is so you know there's just nothing
143:20here all I have to do is this and that
143:21I'm done you know all of these things
143:25fall in I was actually programmed in the
143:27game of space war you know which is one
143:30of the first video games but it wasn't
143:31even a video game back in the in the 60s
143:34and they're all of these it's very hard
143:35to do in an ordinary language because
143:37you have all of these spaceships and you
143:39have planets and you have torpedoes and
143:42when I was looking at Simula I was
143:44trying to get figure a way out of doing
143:48this I didn't want to do it in 30 pages
143:50of alcohol or so and I was trying to
143:53figure out a way and all of a sudden it
143:55occurred to me that every single thing
143:56in space war and Simula was the same
143:59thing the only thing was different was
144:01the costume they were wearing the
144:03planets were the same the spaceships
144:05were the same the torpedoes were the
144:07same there was like one line of code
144:08difference in each of their behavior and
144:11they all had to obey Newton's laws they
144:13all were interacting with each others in
144:15exactly the same way it was trivial and
144:17I wrote that program and a half a page
144:19of code and I never looked back since
144:21because the you know the that is the
144:25thing if you don't find this folding up
144:27of complexity into simplicity then
144:32either you're working on a truly hard
144:34problem
144:35which really really do exist
144:38or there's probably a rotation of the
144:40situation that you haven't examined yet
144:43you're probably still thinking the old
144:45way in thinking in terms of particulars
144:48rather than generalities we're so used
144:50to programming up each specific thing
144:52that's hard for us to think of avoiding
144:54that then we only have to to program up
144:57one general thing and then write a
144:59couple of lines of code for each of the
145:01particulars and we're done that's a
145:03really good test in this stuff and it
145:07accounts for the religious fervor of
145:09people who have had this happen to
145:11themselves as after pounding your head
145:12away on a system to have it fold up like
145:15like there was nothing there it is the
145:17most amazing thing they have an
145:20operating system go away to something
145:22that is practically a clock which is
145:25what it is in an object-oriented system
145:26because what do you need in an operating
145:27system well once you've got the ability
145:30to sustain objects and stuff like that
145:32you practically only need a clock you
145:34only need to get control routed around
145:36and everything else is written
145:37essentially as an application on top of
145:40that kernel that's a very modern way of
145:42looking at things and it's a terrific
145:44way of thinking about doing stuff
145:56okay yeah
146:00that's a very good question
146:03some of these idea a relational database
146:08everybody knows what a relational
146:09database is right okay so the the there
146:16are several things a relational data an
146:19item in a relational database has fields
146:24it has some of some of the things and
146:26depending on the data dictionary that
146:28the relational database wants to sustain
146:30you can occasionally do some integrity
146:33constraints the most relational database
146:35is friend for example is very difficult
146:37to do the following thing in a data
146:40record and that is make sure that Joe
146:42blows age is always the right one when
146:45you ask it because when you ask
146:47somebody's age in a relational database
146:49what it expects to do is to go to a
146:51field and find a number and bring it
146:54back to you right in an object system
146:58what you would have there is you'd sent
147:00the message age to the object and it
147:05could just go to a field and bring back
147:07a number but a smarter one would
147:09actually look at the guy's birthdate and
147:11compute his age for you right then and
147:15so you'd always get the right answer
147:16every time you asked aged you would
147:19always get the right answer from the
147:21object you would not get it from the
147:22relational database unless you're doing
147:24careful updates that's one difference
147:28the other difference is that in a in a
147:31relate in any kind of a relation it is
147:35extremely difficult to embed code
147:37although people sometimes do by
147:39embedding it on the outside of the
147:41database rather than on the inside with
147:44it so for doing a dynamic simulation for
147:47instance is quite difficult a good way
147:49of understanding where relational
147:51databases is going to go comes out of
147:53one of your own products and an industry
147:56that McDonnell Douglas is one of the
147:58leaders in Amanda's CAD CAM CAD cam
148:01can't be done on relational straight
148:05relational databases there simply aren't
148:07enough hooks in there to deal with all
148:09the things it's not you can't store the
148:11data so you can't deal with all the
148:13other things that the relational
148:14database database can't store that
148:18cad/cam requires so object-oriented
148:23servers like the gemstone or this the
148:27ontological rated servers are ones that
148:32the CAD cam industry is going towards
148:34now these allow you to do all the things
148:36that you're used to doing with
148:37relational database but also give you
148:39this extra level of abstraction that you
148:43get from objects what's nice about it I
148:46think for people worried about
148:48transitions is that there's a fairly
148:50reasonable transition almost everything
148:51gets better when you go to an
148:53object-oriented database server for
148:56instance I think most people would like
148:59for instance to have joins be real
149:03things rather than a made-up thing for
149:07the moment and they can be in an
149:09object-oriented database most people
149:11would like to have views be things that
149:14you can add it back through or views
149:15that you can view whereas a view in a
149:19relational database is an extremely weak
149:21notion of the whole notion of what view
149:24is where in an object-oriented system is
149:26extremely easy to have a view look like
149:29the set of stuff itself and so you can
149:31put another view on top of it and
149:33cascade them and so forth and all of
149:35those things are being done right at
149:38this moment with object-oriented servers
149:47excuse me yeah I think for also because
149:59the the tutorial it's going to happen in
150:01a couple of weeks is going to be one of
150:02the people from this digital company the
150:05company that does small talk V I want to
150:08just mention again that besides the fact
150:12that it's cheap small talk V I think is
150:15only $99 on the IBM PC and 150 on the
150:18Mac so it's the cheapest small talk they
150:21have by far the best manual none of the
150:24other manuals are even in second place
150:27because they actually don't believe that
150:30you understand about object-oriented
150:31programming in the beginning of the
150:34thing they actually write the manual
150:35there's a splendid tutorial hands-on
150:37tutorial for getting versed with all of
150:40the object-oriented lore and
150:42sub-classing and building a very
150:45powerful little application another
150:47thing that they give you for free in
150:51with small talk I don't have any stock
150:53in the company I haven't made a cent on
150:56small talk but what they do is they also
151:00give you for free a full-blown
151:03implementation of Prolog Edinboro Prolog
151:06written in small talk okay and just to
151:13give you an idea this whole
151:13implementation of Prolog written in
151:15small talk with its own user interface
151:17its own browser its own debugger and
151:19everything else is less than 20 pages of
151:21code okay and if you've ever tried doing
151:25anything like a programming language
151:27like this is a convince err okay and it
151:30uses object-oriented programming for
151:33what it's really it uses the fact for
151:35instance in small talk everything is an
151:37object everything is an object and
151:40protected including the things that you
151:42think of as stack frames and ordinary
151:44languages that you can't even get to how
151:46is it the bugger written in small talk
151:48well this stack frame is simply an
151:51object so you simply write a method that
151:53allows you to ask the guy well what do
151:56you what do you have here what do you
151:57have here can you advance your PC what
152:00see I mean I mean the debugger is like a
152:03page and a half long because it actually
152:05is part of it's just a subclass of class
152:09stack frame prologue is so simple in
152:12small type because they actually take
152:14the stack frame as an object and
152:17implement prologues control structure
152:19directly in using the small talk using
152:23small talk sone stack frames but using a
152:25non stack protocol which is what the
152:28Prolog backtracking requires this is
152:31gorgeous stuff and it's done completely
152:32without impinging on the integrity of
152:36small talk itself the two systems are
152:39integrated together and so you can do
152:41Prolog unifications into small talk
152:44variables and vice versa so it's a
152:47perfect example of what an embedded
152:49system in an object-oriented system
152:50looks like they give it to you for free
152:52you can do real work in it if you just
152:54want to use it but people are really
152:56interested in why this stuff is powerful
152:58that's an example of where the power of
153:02it is actually concentrated and used by
153:04some design thinking here's another one
153:08most object-oriented languages don't
153:12have a complete model so for instance
153:16when Simula for instance has classes so
153:21you have a class paragraph or a class
153:25string but Simula doesn't have classes
153:29be objects so if you have an
153:32object-oriented one of the choices you
153:34could make is to have everything in the
153:36language be an object why not that means
153:38if there are things called classes there
153:42must be a class class a class whose
153:45instances are the classes okay that
153:50sound shaky
153:53let me just let me just draw it cuz it's
154:09so I'm going to draw classes in red so
154:15this might be integer might be fraction
154:21might be paragraph this might be
154:24document this might be file and there
154:29are instances I'll draw in green this
154:32might be three and this might be for
154:34this might be three quarters this is a
154:40paragraph of text and so is this one
154:44this is a whole document this is a whole
154:47file here's another one they have lots
154:51of instances of these classes they've
154:53been on Simula these red things in an
154:56ADA these red things aren't around at
154:59runtime
154:59they're like macros they just help
155:02create the structures underneath that
155:04these green guys can work with but in
155:07small talk these are really objects and
155:11the question is is if they're objects
155:13what are they an instance of what is
155:16common to all of these things
155:19somebody tell me they're all a class so
155:23what what's common to all of these what
155:25do they do they all make instances right
155:30I mean they're the thing that holds all
155:32of the information that's necessary to
155:34make multiple instances and so you can
155:37imagine that there might be a thing
155:39called class class whose own instances
155:48are these guys
155:55okay that sound reasonable why not okay
156:03down remember I can subclass what do you
156:08think it might mean to sub class class
156:11class let me do that let me use another
156:16color here
156:23so I'm going to sub class class class
156:24here look just in general what is the
156:31sub class of class class going to be
156:33able to do it's going to no it's not
156:36gonna make some classes it's gonna make
156:38be able to make classes like these guys
156:40plus something else then I'm gonna add
156:43right there because anything that's of
156:48class class is going to make classes so
156:51any subclass of it is going to make
156:52classes now here's an example of
156:55something we did at parc many years ago
156:57we wanted to do a system in which every
157:02instance was data-driven okay in other
157:06words we wanted to do a data flow system
157:13inside of small talk in which the every
157:17thing that happened to some variable in
157:22an instance could be propagated to the
157:24next thing that meant that every
157:25instance had to have besides the places
157:29in it that an ordinary instance has
157:31here's what an ordinary instance looks
157:35like it's a thing that has slots in it
157:37for holding values and plus what we
157:41wanted to do was to tack onto that some
157:47pointer information that would link all
157:50of these guys together so we'd actually
157:51have a data-driven
157:53network here now how do you suppose we
157:56did that sub class class class
158:02right the various places I could do that
158:04but what if I did it up here and put
158:07that information in here and now every
158:14every class that this guy makes whatever
158:21it is is going to have the property that
158:24the instances of it regardless of what
158:27these guys are as I go along making up
158:29new classes for this kind of thing and
158:30that kind of thing every one of them is
158:32going to have the property that the
158:33instances are going to be instrumented
158:34this way see how high that change was
158:37made what I did is I actually change the
158:40meaning of what class this was in the
158:43system with one operation I just
158:45subclass a very very high-level guy and
158:49all of a sudden I got essentially a new
158:51small talk with a completely different
158:54strategy for how these things strategy
158:57independent of what the new classes are
158:58going to be okay that's the power of
159:02this stuff it's not the direct stuff
159:06that you can do that's so appealing now
159:08it's the meta stuff that you can do
159:10that's so incredibly powerful because
159:13you can literally when you have a new
159:16idea that's important you can literally
159:18distribute that idea over the entire
159:20universe with just a few changes in a
159:24system like this
159:25well let's I think we're about done let
159:28me let me give you a one of our favorite
159:33stories and as a winch and Winston
159:38Churchill story widget Winston Churchill
159:41jokes always have them at a party after
159:44a bunch of whiskeys
159:46and I'm sure everybody knows the one of
159:49the he was incredibly drunk and a woman
159:53came up to him at two o'clock in the
159:55morning and said mr. Churchill you're
159:57disgustingly drunk and he looked at her
160:01said and you Madame are indescribably
160:03ugly but in the morning I'll be
160:05indisputably sober
160:11so this particular this particular
160:14Churchill joke a little earlier on the
160:16party he hadn't had quite as many
160:18whiskey's and the hostess of the party
160:20came over to him quite agitated and said
160:23mr. Churchill I'm just really upset I
160:26don't know what to do I saw a famous
160:28Earl over there steal some of my silver
160:32salt shakers what should I do
160:33Churchill thought for a minute and stuck
160:35his cigar in his mouth and went over to
160:38the Earl along the way he took a salt
160:40shaker himself and put it in his pocket
160:42and we got over to the Earl took it out
160:45of his pocket and said I think we've
160:47been noticed perhaps we should put these
160:48back so that's my version for why we won
160:54World War two in other words if you want
160:57to get people to do something to go
161:00along with you you have to involve them
161:01in the same conspiracy and
161:04object-oriented programming is a kind of
161:07conspiracy that people are just finding
161:09out about it I hope I've been able to
161:10involve you in a little bit and I hope
161:12you will involve others thank you
161:14[Applause]