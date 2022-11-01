title: "Format Normalization: Whitelist for Formats with good Preservation Properties"
date: Started on 2019-07-02 (published 2022-10)
categories: knowhow born-digital ingest formats


# Abstract

When preserving digital AV files, it is necessary to make the choice whether to
normalize (=change to a common set of formats/properties) a given file, or keep
its encoding, in order to "preserve well".

This article not only contains a list of audiovisual formats (codecs, containers, etc.)
that may be considered "good for preservation", but also a short insights on
which data formats may "preserve well".

This "whitelist" is intended to be used as a recommendation which formats can be
kept as-is and which are better converted to a different format (e.g. lossless
codec, uncompressed) to increase their chance of being accessible in the future.

The text assumes prior knowledge of digital audiovisual properties, as well as
some concept of what a container, a codec and long-term preservation thereof is.

The focus of use cases to be addressed or referred to are more with handling of
born-digital audiovisual material. With ingest of analogue sources, on the other
hand, a good preservation format/codec can be chosen in the first place.



# What are "preservation properties"?

Most of todays video recording settings are mostly defined by convenience of
use, speed, small data size, home editing and support on the web (e.g. browser
playback).

This means that it's common that vendors implement a video format in a way that
enables them to supply a product with a short time to market and if possible
apply some vendor dependency (e.g. proprietary formats, limited support = only
their applications, etc). It's not evil, it's business.

That's why proprietary formats are a problem - especially for preservation.
Without specification of a format (and/or its replayers), it is unclear whether
or whether not it can be made accessible in the future.

So good preservation properties are:

  * Technical specification available
  * Without artificial restrictions
  * Open Standard
  * FOSS implementation available
  * Widely adopted
  * Minimalistic Complexity


## Technical specification available

As mentioned above, technical specifications are the only means of providing
information of how to decode and use any format or machinery in existence.
Even with that information at hand, there are still a number of challenges to
handle in order to preserve things.

Without technical specifications, one cannot do anything with a format or
device unless the original vendor grants them to.

Since preservation use cases need to be addressed independent of current vendor
or market interests, tech-specs are a must for archives in order to do their
work.


### What about reverse engineering?

Indeed, many formats have been reverse-engineered due to the lack of accessible
tech-specs, but this is something that should not be necessary in the first
place (if avoidable). You'd rather like to have the clever people who are able
to "hack" a format, not having to waste their time and talent on this.


### Would source code suffice?

Kind of. See "FOSS implementation available" below.



## Without artificial restrictions

There are different kinds of restrictions that hinder free access to
specifications. A popular example are standards papers that can only be bought
for a fee, and are not allowed to be shared or published yourself.

Often, the price of the fee is adjusted to a market situation which is usually
quite expensive for non-profit organizations or private individuals - or not so
wealthy countries.

Other artificial restrictions might be:

  * legal restrictions (patents/licensing restricting free public access)
  * non-disclosure agreements
  * encryption (copy-protection, etc)


## Open Standard

If the specification of a format has undergone peer review and was published and
maintained in a proper way, that's great for preservability.


## FOSS implementation available

Having a Free and Open Source licensed implementation of a format specification
available is the preservation jackpot:

  * Source Code = This interpretation of a format specification
  * The implementation can be used, studied shared and improved

This makes a format virtually immortal by definition. Only obstacle to be
considered is that it may currently be illegal to own or use that implementation
in some cases. However, maybe it would be good to adapt the laws to encourage
preservability this way.


## Widely adopted

The larger the userbase of any technology (and data format), the more
involvement of different people, instituations, and scenarios - the better.
    
However, the "widely adopted" property is worth discussion and proper evaluation
in some cases, where the format better for preservation is less or not widely
adopted at all. This is often the case when the majority of business use cases
has too little overlap with preservation needs.

Wide adoption does not help you, if the format implementation is still a
(trade-)secret. You are not alone, as you may have more users suffering from the
same problems, but in the end it's still a bit of a hostage situation ;)



## Minimalistic Complexity

> "Is the format as simple as possible and as complicated as necessary?"

The "simpler" any data format (or technology in general) is, the easier it is to maintain and access.
It's a bit like a natural law.
Why? Because there's simply (a) less that can go wrong, and (b) easier to understand and get it to work.


There is an article related to ["Minimalistic Data Format - Open Standards" (by Bernhard Reiter)](https://fsfe.org/freesoftware/standards/minimalisticstandards.en.html), which addresses a different format choice challenge (mainly digital office document formats). Even though it doesn't relate to AV formats directly, it is a very good (and short) read giving insights into what makes formats "easier to handle/use" as vendor- and computing-environment-independent as possible. Basically, the same things we need to look out for when choosing formats for digital long-term preservation.

Take the following two questions in account when assessing a data format:

  * How well does the data-format solve the problem?
  * Is there a simpler format that could solve the problem just as well?


**But, what is "simpler" when it comes to a data format?**

In a nutshell, something like this:

  * Less features
  * Less lines of programming code
  * Less variants/versions to consider

So be careful if any format/program claims to do "everything".
This makes it more complex.
  * = harder to implement (fully/correctly).
  * = harder to support.
  * = harder to maintain.
  * = harder to preserve.

Brainstorm and write down which features of a data format you think you want/need.
Like: resolutions, framerates, color details, speed, size, timecode, (specific) metadata options, etc.
Anything that comes to your mind.

Then sort them to prioritize your needs into these categories:

  * Must have
  * Should have
  * Could have
  * Won't have (this time)

See "[MoSCoW method (Wikipedia)](https://en.wikipedia.org/wiki/MoSCoW_method)" for details on these categories, and this priorization technique in general.

Now, you can take this categorized (=priority) list and check which file format would serve which demands. Any format that does *not* cover the "MUSTs" is not an option and can be dismissed.
From the format options that are left, select the one that has the least features but still covers MUST and SHOULD. You decide how important "COULD" and "WON'T (=maybe next time)" are to your use case.



# Criteria for whitelisting

The list of "good preservation properties" of a data format from above can now
pragmatically be ordered and condensed down to two:

  1. FOSS implementation available?
  2. Without artificial restrictions?

Any data format that has "YES" to both of these questions, can be put on your
whitelist - and can be kept for preservation. Hooray!

If any part of your "AV file format stack" (container, codec, embedded data,
etc) has "NO" as answers to one of these questions, you may want to convert that
format to a "YES-YES" option.


## Why just these two criteria?

Because if you have the source code that can at least read (=decode) any given
AV data format, there is nothing to practically stop you from accessing the
content stored in that format - and, if necessary, translate (=transcode) to any
other format that seems more suitable at any later time.

And, "artifical restrictions" may include:

  * legal restrictions
  * encryption

Legal restrictions (format royalties, licenses, patents, etc) should not be
ignored, but in an end-of-days scenario, they may not be considered that
important anymore...

However, encryption definitely is an issue to be aware of. And to avoid for
preservation if possible, as it will only cause problems.

For example, copy-protection mechanisms (DVDs, Blu-Ray, M4P (MPEG-4 protected),
etc) may contain encryption methods.





# If not whitelisted: Rewrap and/or transcode.

What is "rewrapping" and "transcoding"?

  * **Rewrapping:**  
    Modifying only the container format.
    The AV streams inside stay as-is.
    No transcoding necessary.

  * **Transcoding:**  
    Re-encoding the actual AV data streams from one format to another.
    (eg Convert from codec A to codec B)

If you encounter a format that does not match the whitelist criteria, you can
either change "just the container" or "the audio/video codec" or both.

In some cases, it even makes sense to rewrap to the same container format as the
source was, simply to even out issues caused by different implementations
writing the original file.


## Rewrapping

Rewrapping may be used to keep the audio/video encodings untouched, while
completely re-writing the container format. It is often used to change from from
container to another, without any loss of audiovisual quality - even with
lossy-encoded streams (since they don't require re-encoding).

You could, for example take an "H.264/AAC in MOV" and rewrap it to MKV.
The H.264 (video) and AAC (audio) streams could be copied as-is, which not only
saves a great amount of (computing) time, but also keeps all your content
quality untouched.


## Transcoding

Transcoding means to re-encode the actual content stream(s) to (usually) a
different encoding format.

For digital video encodings, the default is that they are lossy-compressed.
Simply because digital video is considered still huge: ~1.4 GB/Minute
uncompressed 8bpc PAL *Standard Definition* (=old television resolution)

As cool as lossy-compression magic is, there's one downside:
Converting from lossy-to-lossy causes quality loss. You could call this a form
of "[generation loss](https://en.wikipedia.org/wiki/Generation_loss)".

Possibly also introducing [new compression artifacts](https://en.wikipedia.org/wiki/Compression_artifact).
For long-term preservation, avoiding any additional quality loss is preferred
(if reasonably possible).



# Normalize Audio to LPCM

It may be practical to simply transcode any and all source audio encoding format to
[LPCM (Linear Pulse Code Modulation)](https://en.wikipedia.org/wiki/Pulse-code_modulation).

Yes, the audio tracks may get much bigger (if their source format was
(lossy-)compressed), but doing so will possibly remove *all* format issues at
least for your audio tracks.

Why LPCM?
It's the most common uncompressed audio encoding, typically used in almost all
WAV files around the world: From profressional recording studios, audio CDs and
even non-pro consumer applications. There's hardly any application that deals
with audio and doesn't to WAV.

Of course your situation may be different. Then you can simply apply the
whitelist approach to your audio encodings as well, and only transcode if
considered necessary.



# List of Whitelisted Examples

## Video Encoding Formats

  * DV (Digital Video)
  * MPEG (1,2,4, etc)
  * FFV1

btw: Some broadcast/camera formats are actually settings-profiles for MPEG
encodings, defining fixed options for resolution, framerate, audio channels,
bit-rate, samplerate, etc.

Examples are:

  * [HDCAM SR](https://en.wikipedia.org/wiki/HDCAM#HDCAM_SR) = MPEG-4 Part 2 (Simple Studio Profile)
  * [AVCHD](https://en.wikipedia.org/wiki/AVCHD) = MPEG-4 AVC (H.264)


## Container Formats

Listed in order of "easiest to hardest" to handle:

  * AVI
  * MOV, MP4, MKV
  * MXF

AVI is still listed here, because it still is dead simple and (was) well
supported by actually all tools that handle AV since the 90s until now (2022).
Proper support for it may phase out in more recent tools in the future, due to
the lack of features and therefore interest in using this container anymore.

MOV/MP4 and MKV could be considered equally easy to handle. MOV and MP4 for the
time being, may have a slightly higher chance of being implemented in legacy-
and production AV-tools. Mainly because MOV/MP4 got big companies behind them,
and MKV originated from outside of "The Industry".
There are great changes in favor of MKV though in recent years, which may on the
long run cause it to even replace MOV/MP4 for most use cases. Google's "WebM"
container format (YouTube) is actually an MKV profile.

MXF is very powerful and most common in the production and broadcast world.
Unfortunately it is also very exclusively supported inside that "world" - which
makes it suffer from interoperability issues. Especially with almost all tools
that are not designed/used for the production/broadcast "bubble".



# Why analogue was different.

With analogue AV formats the vendor-induced excess of short-lived,
non-interoperable "variants" (as can be seen in the digital domain), was way
less. One theory of ours is that it was a bit similar to how analogue pirate
copies were limited: It simply took longer to do it.

Take VHS for example:
Tapes were expensive, and replayers crazy expensive. If you could only use it
for 3-5 years or tapes were not compatible with replayers from other vendors,
people wouldn't buy it.  Also the company had to make sure they delivered a
stable product (e.g. a replayer): They couldn't just do firmware updates
whenever they wanted to. Once it was out it had to work. And the public was used
to buying quality machinery that usually outlived the generation who bought it.

With digital, developers are able to release a product even if it's still
heavily under development: The vendors just supply updates. To download manually
or applied automatically.
Ever noticed how normal weekly (or even more frequent) updates are (often
automatically) applied to the tools we use daily? How short digital devices are
usable, or how quickly they become virtually obsolete - incompatible to the
updated surroundings?

This enables vendors to worldwide publish a new format - and stop supporting it
as they will. Same goes for interoperability and availability of specifications.
Even formats that are often considered "The Standard" by a wider audience of
users, it is currently still very common that such a defacto standard is a black
box. Trade secret. Believe it or not: Interoperability issues with file formats
are used by vendors to benefit from consumers being forced to buy theirs to
satisfy "the standard".

As I was taught at the university of economy: That's a great business
(role-)model.  This kind of business is good for quick innovation and brought us
really amazing things in a really short time. My personal opinion is though,
that it wouldn't have to be so fast and furious.
Why not let Full-HD resolution settle, stabilize and let the audience calm down
and enjoy their new home cinema? It was already hasty and expensive enough to go
from SD to HD-ready to mixed to Full-HD, from VHS to DVD to BluRay to Netflix to
end of broadcast as we knew it...

All in less than 1 generation. I'm not going to list the number of digital video
formats that came to existence in that same short time, as it would take too
long.

That's the reason why proprietary formats should be avoided for preservation
use. In order to improve preservability, it would therefore be good to create
less content in these formats in the first place.


