# Language

_What is the name of the language? Link the name to its webpage
(if appropriate)._

Despite putting a non-negligible amount of work into this, it doesn't actually
look like they named the language.

Here is the github link though: https://findlab.github.io/2020/11/15/music-layout-language/

# Domain

_Describe the language's domain in five words._

Easily manipulable notation for sheet music.

# Computational model

_We don't yet have a great definition of the term "computational model".
For now, try to come up with the clearest, most concise explanation of
what happens when a program in your DSL runs._


You will have a textual output that represents the sheet music, which can be
exported to other music languages (Lilypond, MusicXML, MEI). This textual output
can be compared to the likes of regular expressions because of how despite its
conciseness, it represents quite a lot. The key idea is that the music is
represented by measures, not by each staff which makes editing the whole music
easier. For an example, you can scroll down to the benefits section where I
describe a hypothetical scenario.

In the demo, the author also had an application  where you could type in the DSL in a
textbox and have it be directly translated into the host language.

# DSL-ness

_Fowler writes about a spectrum of languages, from general-purpose languages to
"purely" domain-specific. Where does the DSL you chose fall on this spectrum,
and why?_

This language seems to fall into a more purely domain-specific area. The DSL is
more interested in modeling sheet music, and thus avoids imperative control
structures. Though the DSL is model-heavy, this doesn't necessarily mean that
it is comprised only of variable assignments. The fluency comes from reading the
produced string left to right and "unpacking" it to reveal the full sheet
music. For example, suppose we have three measures, each which is represented by
1, 2, and 3. Suppose that at the end of measure 2, there is a repeat sign such
that you would go measure 1, measure 2, measure 1, measure 2, measure 3. This
would be represented in the DSL as 2 * [1, 2], 3. The first "2" multiples
measures 1 and 2 which represents repeating said measures twice. 

I will say that acquiring said fluency might be difficult because you'd have to
accustom yourself with notation that it isn't necessarily familiar to domain
experts. However, I feel like if people are put through regex, they can handle
this DSL. 

It is also very domain-specific because there is very little you can do with
this DSL outside of representing sheet-music; it is most certainly not
Turing-complete. It is specifically focused on generating a parseable string
which can be fed to other music programs.

# Internal or external?

_Is the language implemented as an internal or external DSL?
Justify your answer._

This is an external DSL because it is written in its own distinct language,
which can then be processed by other languages. In this case, the notation that
the DSL produces can be fed to other music programming languages such as Lilpond
and ABC notation.

# Host language

_What language(s) was (were) used to implement the DSL?_

Lilypond and/or ABC Notation which are both used to generate sheet music PDFs.
It can also be fed into other languages for deep learning tasks, such as OMR. 

# Benefits

_Identify one potential benefit of the DSL: how is a programmer's life made
easier by the existence of this language?_

From my understanding, the idea is that rewriting sheet music code can be
cumbersome. Suppose you have sheet music which has multiple voices, and that you
wanted to add a repeat sign to one of the staffs. Then, you'd also want the
other voices to have that repeat sign as well. It seems like this is painful to do
in the current music languages that we have because they require that you code
each different voice separately. So the edits you do to one voice will not apply
to another.

The DSL circumvents this by breaking up the music into measures that you can
easily manipulate, instead of having you edit each voice/staff. Let's go back to
the previous example where we have some music with 3 measures and 2 voices,
soprano and alto. We want to add a repeat sign to the end of the measure 2 for
the soprano voice. Without the DSL, we would have to go to the section of code
that refers to the soprano voice, add the repeat sign in, then go to the alto
voice, and add the repeat sign again. But with the DSL, we can use the notation
2 * [1,2], 3 to indicate that we want to take all the music at measures 1 and 2
and repeat it twice before continuing onto measure 3. 

# Drawbacks

_Identify one potential drawback of the DSL: what does a programmer
lose by using this DSL instead of a general-purpose language?_

The notation is very regex like; that is to say, you need to understand
different symbols in order to unpack the string you are reading/want to
write. Thankfully, the author tries to call on past conventions to make this
transition easier (Python also has the notation of multiplying a constant by an
array to represent repetition, like 2 * [1, 2]) but this requires some coding
knowledge. So in that sense, it may be inconvenient to learn a new language,
therefore making the programmer want to rely on a GPL that is more familiar to
them. 
