# Project proposal

## The user and a language

This section describes who the project would serve and why a language might be a
good way to meet their needs.


### What's the need?

_What need is met by your idea? Who are you helping? What is that person's
experience like now? What would their experience be like if you could help
them?_

Taiko is a percussive instrument usually found in Japanese festivals. A unique
feature about it is that there is typically no sheet music; it is taught almost
exclusively through oral instruction called kuchi-showa. Each note has its own
onomatopoeia (think of how in middle school choir, they made you read out notes
as "ta" or "titi") which instructs the player how they should hit the drum. It
is worth noting that this is not only by the duration of the note, but what part
of the drum you should hit. For instance, "don" refers to striking the middle of
the drum, and "ka" refers striking the edge. You can view all the sounds here:
http://taikosource.com/wp-content/uploads/2014/08/Kanji-West-Notation-090214.pdf
^ note that this isn't entirely standardized, though. Some places say things
differently.

Kuchi-showa has its own perks (personally, it's a lot more fun to chant out the
notes with your friends instead of silently pouring through pages of music) but
undoubtedly, a major downside is that songs are more easily misremembered -- or
worse, lost entirely. Thus, it would be useful to have some kind of sheet music
notation for taiko. One might think we can directly utilize music sheet for
regular drums, but I believe a lot of nuance would be lost. For instance, you
would want to specify which notes are dons and which notes are kas. Furthermore,
because taiko is a group performance, knowing what hand to strike with is also
very important. This makes regular drum notation a bit lacking for
translating taiko songs to sheet music.

### Why a language?

_Why is a DSL appropriate for your user(s)? How does it address the need?_

A DSL is appropriate because there is currently no specification for being able
to create taiko sheet music. Thus, it'd be useful for some kind of taiko
language to exist with the intent that the quirks that taiko has but other
percussion instruments don't are communicated clearly. Additionally, by creating
a language around taiko notes that can be written down, it may provide people
who find learning orally difficult a different, more effective medium to learn a
song.

You could always write it out physically without the need for a program, but having
a program that you can run has many benefits, including but not excluding easier
method of editing old sheet music, running sheet music through some interpreter
to play out the piece, and more.

### Why you?

_What excites you about this idea? How did you come up with it?_

I've been in the taiko club at the Claremont Colleges since sophomore year and
it's honestly one of the highlights of my week. Hitting drums relieves your
stress like nothing else. 

Our club is pretty small; there's only a handful of people from each grade and
when the seniors graduate, it's a major loss. One of these losses involve not
knowing how exactly a song goes because we were taught orally by the
seniors. There are videos of past performances we can look at, but the sound
quality isn't the greatest nor can we trust that the performers themselves did
it right. Additionally, we can't really google any of these because again, these
songs are passed down from instructor to student orally.

Just the other week, we had a minor incident where no one could agree how
exactly a song went. We ended up deciding on something, but it's very possible
that we were not correct and therefore altered how the song originally
went. Thus, I think it would be very helpful to have some kind of physical aid
to remember how a song goes instead of relying on faulty memory.


### Domain

_Describe the project's domain in five words._

Taiko songs into sheet music.

### Interface (syntax)

_How might the user interact with the language? What does programming look
like? Why is this the right way to interact with the problem domain?_

I want to make it somewhat similar to MuseScore so that people don't have to
learn entirely new controls. You would be presented with a GUI where you have a
sheet of empty staffs in front of you, and then you could click what notes you
want to put on it. The notes would be colored/shaped differently depending on
what hand you should play with and where you should hit the drum.

To make it more convenient, I could have a library of common rhythms (such as
the horse beat, which is a bit of a swing that sounds like a horse galloping)
that people could click to drop a collection of notes onto a measure, rather
than doing it one by one. 

Again, I believe this is the right way because musicians are already familiar
with GUIs like MuseScore and it clearly works well; there isn't really a need to
break the formula here except to introduce something that doesn't exist yet (the
taiko sheet music).

Another thought I have in mind, though, is a simple text input where you input
the rhythm (for example, writing don don don don would create 4 quarter notes)
and run the program to make it show up on sheet music. This might be more
convenient for taiko players specifically because that is how they are taught
the music. 

### Operation (semantics)

_What might happen when a program runs? How does a program interact with the
user? What kinds of errors might occur, and how might they be communicated to
the user?_

When the program runs, it should export the sheet music as a PDF that can then
be printed. The user can then read off of the sheet music. Another functionality
that might be explored in the future is playing back what the music would sound
like from the program directly. 

Some errors might be trying to fit more notes than there is space (in this case,
we just deny the user and prevent them from clicking until they delete notes to
make space). 

Because music is very free-form, though, I don't think there's a lot of errors
they could make aside from going beyond the constraints of the page.

### Expressiveness

_What should be easy to do in this language? What should be possible, but
difficult? What should be impossible or very difficult?_

It should be easy to create sheet music geared for taiko. You could possibly
adjust this to include other drums, but you'd have to readjust perception on
what different colors/symbols mean. For example, it wouldn't make sense for a
regular drum to have sheet music that indicates "dons" and "kas". It should be
impossible to have non-percussion notes represented because we're not dealing
with keys.

### Related work

_Are there any other DSLs in this domain? If not, describe how you know there
aren't and conjecture why not. If so, describe them and provide links. How well
do they address the need? Are there any particularly admirable qualities of the
language? Are there parts of the language you think could be improved?_

Given by the fact that taiko sheet music itself is not a thing, there are no
DSLs specific to taiko either. There do seem to be some music DSLs floating
around but again, those are not geared towards percussion instruments, let alone
taiko.

To be fair, it's entirely possible, though, that a Japanese programmer created a
DSL, and I just didn't find it because my Japanese isn't up to par.

In terms of documenting taiko in general, it seems like this site is trying to
collect a database of songs https://taikosource.com/song-database/

However, I'd like to make it easier for people to be able to create the sheet
music, because currently they just recommend copy pasting special characters
from their site. Additionally, their notation is a good start (I like how they
express dons as black circles, and kas as a note with a X instead of a circle)
but lacks some nuance. I think I'll try my best to incorporate their notation,
though, so that people who are familiar with theirs don't need to readjust to
mine.

(I'm going into a rabbit hole where this site actually has a lot of cool
contributions. Here is a site where you can make your own rhythms https://www.dokodon.com/#/)

## The Project

This section examines whether the idea makes for a good CS 111 project.

### Suitability

_If someone were to work on this project, what percentage of their time would be
spent directly engaging in the **language** aspects of this project (e.g.,
making language design decisions), as opposed to "systems" aspects of the
project (e.g., implementing a complicated semantics that doesn't require a lot
of language design)?_

I think you'd be able to engage with the language quite frequently because the
whole point is to create some way of transcribing taiko from something that is
only heard to something that can be written down. There are already conventions
in place that will make this easier, as shown in the link further above, but
adjustments must still be made to allow for a fluent transcription.

### Scope

_How big an idea is this? How ambitious is this project?_

Because taiko is percussive, it's a less complicated to deal with than other
instruments. I think it is very doable because it's a simple concept that I can
always add onto if I have more time such as including dynamics, standard sheet
music notation like repeats, and if I were really ambitious, trying to figure
out a way to include the dancing aspect of taiko (taiko is not a stationary art;
it is largely performance through dancing and shouting).

### Benefits and drawbacks

_Why might this be a good idea for a project? Why might this not be a good idea
project?_

It's good because I have a lot of personal stake in this, and I believe it's
fairly achievable. I would also have an ok pool of people I could ask feedback
from (the taiko club) who I would consider as better than domain amateurs.
However, this is a very, very, very domain-specific language that might not find
a lot of uses, which is a drawback. Additionally, this relies on having a GUI of
some sort for ease of use; building this GUI might take time away from designing
the language. 
