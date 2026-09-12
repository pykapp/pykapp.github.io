---
title: Connecting with people
permalink: /how-it-works/people/
---

This page is about how two people become connected in *people you know*: how
you find somebody, how you ask, what they are told at each step, and what
happens when you remove or block them. A good deal of it is not what other
apps do, and where that is true the reason is given rather than assumed.

## There is one kind of connection

No follows, no followers, no subscribers, no one-way links, no close-friends
tier. There is one relationship—a **mutual**—and it exists only because both
people agreed to it: one asks, the other accepts. Either side can end it at
any moment, alone, without the other's agreement and without telling them. The
signup screen says it in four words: *no follows—only mutuals*.

Everything else rests on that. When you post, your phone encrypts the
photograph with a key of its own and wraps a copy of that key for each person
you addressed it to. Being a mutual is what makes such a copy possible, and
ending the connection destroys the copies that exist. That is why removing
somebody here takes photographs away rather than hiding them, and why nothing
about connecting is retroactive in either direction.

## Getting an account at all: invites

During the closed beta we issue invite codes by hand. There is no invite
screen in the app, nothing to share and no quota: you cannot invite anybody
yet. Keeping the only way in in one pair of hands means a controlled start for
the graph, and no accounts belonging to people nobody knows.

A code is twelve characters, drawn at random, without the letters and digits
that look like one another. It is checked on the screen where you type it
rather than at the end of signup, so a mistyped code is caught immediately.
Unknown, expired and already-used all give one sentence—"That invite code
cannot be used."—because three different answers would tell somebody guessing
which of their guesses was close. Codes expire, and nothing reserves one for
you between checking it and using it.

### Redeeming an invite sends a request to whoever invited you

This is the part people do not expect. When your account is made, your phone
sends an add request to the person whose code you used, on its own, the first
time it launches. Signup says so on the step where the code is typed: *The
person who invited you will get a request from you.*

It happens without a tap, so it is said in advance; finding it out afterwards
would be the app acting on your behalf and not mentioning it.

It exists because otherwise nobody could make a first connection at all. A new
account has no mutuals, so it shares none with anybody, and the rule below
would refuse a request in both directions for ever. The invite carries a
standing permission to ask that one person, and that is all it carries.

It buys exactly one introduction. The permission is spent by the request it
allows, so if they decline, or you cancel, there is nothing left to send and
you are a stranger to them on the same terms as anybody else. It works in one
direction only: you may ask them. They get nothing in return, and need
nothing, because your request is already on its way to them.

## Finding somebody

By exact handle, exact email address or exact phone number, and no other way.
The field's label is *handle, email or phone*, the line under it reads *Search
finds people by their exact handle, email or phone.*, and at most one person
comes back. A partial handle finds nobody. So does a near miss.

There is no directory to page through, no suggestions, no "people you may
know", no friend-of-friend list, no ranked near-matches and no browsing of any
kind. That is the product rather than a feature cut for time: a surface on
which strangers can be discovered is a surface on which strangers accumulate,
and there is meant to be nothing here worth farming.

A search that finds nobody says *no one by that name*, and it says exactly
that for an unknown handle, for your own handle, for a deleted account, and
for somebody who blocked you or whom you blocked. None of them can be told
apart, and the exclusion is inside the database query rather than a filter
over its answer: the row is never read at all, so there is nothing afterwards
for the answer to differ by.

Searching is rationed: 32 searches per account per hour, counted over a
sliding window, charged whether or not they find anybody. Nobody adds
thirty-two people in an hour, so the limit is generous for a person and
useless for enumeration: 768 guesses a day is a rounding error against the
space of possible handles. The refusal says "Too many searches. Try again
later." and never recites the number. Renaming yourself draws on the same
budget, because "is this handle taken" and "does this account exist" are the
same question.

Being findable is what a handle is for, and it can be changed from *settings →
your handle*. The old one is not held for you: people who knew it will not
find you afterwards, and somebody else may take it.

Sign-in codes go to an email address at the moment, because we can send an
email and cannot yet send a text message. Searching by phone number still
works—finding somebody and being sent a code were never the same question.

## Asking to add somebody

Tap *add*. Your phone wraps your profile key for the person you asked, which
is what lets their phone open your display name and your picture; we hold
ciphertext throughout and can read neither. The request expires after sixteen
days, and both sides see the date rather than a countdown.

On their side it arrives at the top of their own profile under *asked you*,
above who they know and above what they have made, with a dot on the profile
mark on the bar while anybody is waiting. The dot is never a number, and
looking at it does not clear it—it goes out when the last request is accepted,
declined or expires. It is deliberately not also on the people screen, and a
request arriving writes nothing to the activity tab: one thing, in one place.

A request also sends a notification. It is one of only two the app sends
without being asked: the other is somebody putting your name on a photograph,
which you can stop at *settings → let mutuals tag me*. You can turn this one
off at *settings → notifications → when somebody wants to add me*. Everything
else that interrupts you is something you asked for. The words are written by
the receiving phone from a name only that phone can read; what we send is a
single token saying what kind of thing happened.

Their row shows your face, your name, *accept*, *decline* and *more*—which
holds *block* and *report*, because a stranger's request is the one place
abuse can arrive from somebody who is on no other screen, and declining alone
lets them ask again. Under the row is *you both know anna, carla*, and then
*expires on 17 september*.

### What you see while you wait is almost nothing

Your own outgoing request sits on the people screen under *you asked*, and it
shows their handle, *cancel*, and the date. No face. No display name. No
"seen". The row has no field that could say whether they opened it, and there
is no such field anywhere.

The asymmetry is the whole gate. The person asking offers a face and a name so
they can be recognised; the person being asked reveals nothing at all until
they say yes. That is also why your own *you both know* line is empty on
somebody you asked and who has not answered: which of your people know them is
a fact about their connections, not yours.

### Accepting hands over no history

Accepting creates the connection and moves no photographs. Their profile
starts empty—*nothing shared with you yet*—and fills only as they share with
you, and yours does the same. There is no back catalogue to open, because a
profile here is not a page somebody maintains: it is simply the posts of
theirs you were sent.

Sharing what you posted before you met is a separate offer you answer on
purpose—*Share your past posts with anna?*—unless you have turned *settings →
share past posts with new mutuals* on, which is off to begin with and skips
the question. Either way, what it shares lands on your profile rather than in
their feed. The [posting page](/how-it-works/posting/) covers it.

### Declining, cancelling, expiring

All three are silent. Declining destroys the wrapped profile key in the same
transaction that settles the request, and the requester is told nothing: their
outgoing row is simply not there any more. Cancelling removes the row from the
other person's profile with no notification. Expiry is swept rather than only
filtered, so a request nobody ever opened does not leave your profile
decryptable by them for ever.

One honest limit, since it is easy to read as stronger than it is: destroying
that key stops future decryption. It does not unsee what was already shown.

If you each ask the other at the same time, both requests sit there and the
first accept creates the connection and clears both.

## Who may ask you

By default, only people who share a mutual with you. This is on for every
account, and it is the one rule in the product that a stranger runs into.

It is said at signup, under the handle field, because a handle is what makes
you findable and this is the answer to the question that raises: *Only people
with a mutual in common can ask to add you. You can change that in settings.*
It is shown and not chosen: one more decision at signup, about a default
nobody can have an opinion about yet, would be one more thing standing between
somebody and the app.

The switch is *settings → requests from anyone*. It is off, and its line reads
*only people with a mutual in common*; turned on, it reads *anyone can ask*.
Turning it on only ever makes you easier to reach, and turning it off only
ever makes you harder to reach, so nothing else in the app can pin it either
way.

Somebody with no mutual in common is told so, plainly: "You need a mutual in
common to send a request." That is the one refusal in the app that explains
itself. Everywhere else a denial is an ordinary not-found, because saying "you
are not allowed" confirms that the thing exists. Here it confirms nothing:
they already knew your handle, so an invented not-found would be a lie that
helps nobody.

The two exceptions to the rule are the target's own switch and the invite
above. There is no third.

## Who you both know

Where the app can show it—under an incoming request, at the top of a mutual's
profile, on a person card—it reads *you both know anna, carla*, and each name
opens that person's profile.

It is names and never a count. "3 mutuals in common" is a figure other people
grow, which this product refuses everywhere, and *which* three is the whole of
what decides anything. Every name on the line is already one of your own
mutuals—the overlap between two sets of people is inside both—so the line
tells you nothing about anybody you do not already know.

It is empty in one case, on purpose: a card for somebody you asked who has not
answered.

## Somebody a friend named in a photograph

There are two ways to arrive at a person you have never met, and neither is a
search. If a mutual of yours names somebody in a photograph they showed you,
that name is tappable; and if a mutual passes on somebody else's photograph,
the row carries the name of whoever originally made it. Both open the same
card: their face, their name with their handle under it, *you both know …*,
and *add*.

Two consents stand behind a name on a photograph. The person's own, in a
setting that is on until they turn it off, and the poster's, in the act of
naming them. A passed-on photograph is the same shape: the original poster had
to turn on *tagged people may reshare this*, which is off to begin with, and
one of the people they named had to choose to pass it on. It is the mechanism
that already exists offline—"who is that in your picture?"—and it is the
opposite of "people you may know": nothing is computed, ranked or suggested,
and the person in the middle is on the hook for the introduction.

The card answers for a mutual, for somebody with a live request between you
either way, for somebody named on a photograph you still hold, and for whoever
originally made a photograph that was passed on to you. For anybody else it is
the same not-found an account that never existed gets, byte for byte. And what
it shows you depends on what you were given: for somebody who asked you it
shows a face, for a mutual it shows a face, and for somebody *you* asked it
shows a handle, the words *request sent*, and nothing else.

## The limit is 128

You may have 128 mutuals. It is a hard limit: there is no appeal, nothing to
buy that raises it, and nothing to ask us for. When you reach it the refusal
names the number, because it is your own count—"You already have 128 mutuals.
Remove someone to add anyone new."—and removing somebody is the only remedy.

The number is what it is because you can raise a cap and you cannot lower one:
lowering it strands everybody above the new limit with no good answer, so the
asymmetry argues for starting tight. It also sits just under Dunbar's number
of about 150, which is the claim this product is actually making.

Your own count is on your own profile, under *who you know*, reading *mutuals
12 of 128*, and the count is itself the way to the people screen. It is the
only number of its kind in the app, and it survives the rule against totals
because it is none of the things that make a total corrosive: it is bounded,
it is visible to nobody but you, and it answers a question you genuinely
have—am I near the limit—which you would otherwise discover by being refused
in the middle of adding somebody.

Your count is never consulted when somebody sends you a request. Telling a
stranger "that person is full" would hand out a fact about somebody else's
connections. The request is made, and the limit is enforced when you accept,
where the person who learns it is the person whose count it is. If they are
the full one, the accepter is told: "They cannot take any more mutuals."

## What the other person is told, step by step

- **You search for them.** Nothing, ever. Searching is invisible to the person
  searched for.
- **You send a request.** A notification unless they turned it off, a row
  under *asked you* on their own profile, and a dot on their profile mark. No
  activity entry.
- **They open it.** You are never told they looked.
- **They decline.** You are told nothing; your outgoing row is simply gone.
- **It expires.** Nothing. You saw the date on the row.
- **You cancel.** Nothing.
- **They accept.** You get an activity row: *anna accepted your request*.
- **You remove them.** Nothing. Both sides quietly stop being able to open
  what the other shared.
- **You block them.** Nothing. Every door answers exactly what it would answer
  for an account that never existed.
- **You report them.** Nothing. No route tells a reported person that a report
  exists or who filed it.
- **You are at 128.** Only you are told, and the number is named.
- **They are at 128.** You are never told when you ask. Only the person
  accepting learns it, about their own count.

## Removing somebody

From their row on the people screen, beside *block*. That is the only door: a
profile's *more* holds *block* and *report*, and nothing else. One dialog, and
it says what will happen rather than asking whether you are sure: *They will
not be told. You will both stop seeing anything the other has shared.*

In one transaction it destroys the connection and, with it:

- every wrapped key that let either of you open the other's posts, in both
  directions—so the photographs stop being readable rather than being hidden;
- both profile grants, so neither can open the other's display name or picture
  any more;
- their membership of your groups, and yours of theirs;
- their membership of any [album](/how-it-works/albums/) you created, and
  their copies of the keys for everything in it—and yours of any album they
  created;
- the per-person "tell me when they post" subscriptions, both ways;
- any reshare either of you made of the other's posts.

Two things it does not do. It does not reach into an album a third person
made: if you are both in Carla's album you go on receiving each other's
contributions there, because an album delivery rests on being in the room
rather than on the connection between you. And it cannot un-download: anything
already on their phone stays theirs, exactly as with any photograph you have
ever sent anybody by any means. What stops is anything new.

A removal is undone by adding each other again, and the past-posts offer can
hand back what they used to hold. That is the difference between it and a
block.

## Blocking somebody

Reachable beside *remove* on their row, under *more* on their profile, and
under *more* on an incoming request—because a decline alone lets somebody ask
again. A stranger can be blocked, and nothing ever stands in the way of
blocking somebody.

The dialog: *They will not be told. This also removes them, and they will not
be able to ask again.*

Everything a removal does, and then:

- **Every delivery between you goes, album photographs included.** This is the
  one act that reaches into a room somebody else made: their photographs stop
  arriving through Carla's album, and nothing of either of yours is ever
  wrapped for the other again.
- **Your words come out of each other's posts, both ways.** Reactions deleted,
  comments taken down, permanently. After a block neither of you can reach the
  other's posts, so a comment left there would be a comment its own author can
  never delete—and words you cannot take back are words you did not agree to
  leave behind.
- **Pending requests in either direction are cancelled**, or a block would
  leave a live invitation from somebody you had just blocked.

What a block deliberately does not do is remove either of you from a third
person's album. The room is theirs, being in it is a fact about the room
rather than about the two of you, and a block is not a power over somebody
else's album. Both names stay on its member list—but no photograph passes
between you there any more.

### What the blocked person sees

One not-found, everywhere. Search, sending a request, your profile, a post of
yours, a photograph's address, your key, your picture, your person card: every
one of them answers exactly what it answers for an account that does not
exist, and nothing they can fetch contains anything identifying you. They
cannot tell a block from an account that was never made, and that is the
point.

### Undoing one

The people you blocked are at the foot of the people screen under *blocked*,
each a handle and *unblock*. The name is not a link, because nothing opens
their profile any more and a link to a not-found is worse than a word.

The dialog is honest about what unblocking is and is not: *They will be able
to find you and ask again. Nothing that was taken away comes back.*

There is no list of who blocked you, and there cannot be one: it would be the
signal the 404 exists to withhold.

## Reporting somebody

*more → report*, on a profile or on an incoming request row. We hold
ciphertext and cannot see the photograph or the words, so what reaches us is a
pointer and the paragraph you write, which travels in the clear—the dialog
says so. The person reported is never told that a report exists or who filed
it, and you are given no reference number to chase, because a queue that
promises an answer is a queue that owes one. Everything we can do acts on the
account rather than on a photograph. The [moderation policy](/moderation/) is
the long version.

Nothing about the state of your own account stops you reporting, a suspension
included: somebody being harassed must always be able to say so. The one limit
is a rate—sixteen reports an hour, which is a person having a bad evening
rather than a script—and, like the search limit, the refusal does not recite
the number.

## What is not here

- **No directory and no suggestions.** Nothing pages through accounts, nothing
  computes who you might know, nothing is ranked.
- **No public profile.** Asking for the posts of somebody you are not
  connected to is a not-found and not an empty page—the same answer for a
  stranger, for yourself, and for an identifier belonging to nobody. There is
  no profile URL, no QR code and no "share my profile".
- **No follower or following counts**, and no post counts. Nothing totals what
  you have made, and nothing counts who saw it. What is counted instead is
  small and private: your mutual count against the limit, how many people are
  in a group you made, and how many unseen posts a feed tab or an album is
  holding.
- **No way to see anybody else's connections.** The most you ever learn is
  *you both know …*, and every name on that line is already yours.
- **No way to see who blocked you**, and no way to learn which of somebody's
  groups you are in—group membership is invisible even to the people in a
  group.
- **Nobody is told who looked.** Not at a request, not at a photograph. A
  per-person read receipt was built once and taken out again.
- **No invite to hand out.** During the beta, codes come from us and there is
  nothing in the app that mints one.

The [privacy policy](/privacy/) says exactly what we hold about your
connections and what we cannot see, and [how it works](/how-it-works/) is the
rest of these pages.
