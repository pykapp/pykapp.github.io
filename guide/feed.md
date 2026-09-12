---
title: The feed
permalink: /how-it-works/feed/
---

The feed is the screen *people you know* opens on. This page says what is in
it, what takes a post out of it, why it ends, and what the app does and does
not do beside it. Most of what follows is the opposite of how a feed usually
behaves, so it is worth reading before the app surprises you.

## It is a queue, and it empties

Your feed holds the posts other people addressed to you that you have not
looked at yet. That is the whole of the rule. Nothing is chosen for you and
nothing is added: no ranking, no scoring, no suggested posts, no advertising,
no "people you may know" row, no accounts to discover. A photograph is in
front of you because somebody addressed it to you: somebody you are connected
to, or somebody in an album you are both in.

So the feed has an end. When the queue runs out the app says *all caught up*,
and there is nothing more to scroll. Nothing is injected to keep you going,
because there is nothing here to keep you here: no reach to grow, no total to
inflate, no ranking to game.

The scrolling itself is ordinary. The app fetches more as you approach the
bottom and keeps fetching until the queue is genuinely exhausted, however many
pages that takes. What is different is that the last page is followed by a
line of text rather than by another page.

## Oldest first

The next row is always the oldest thing you have not seen. If Ana sent you a
photograph on Tuesday and Bruno sent one an hour ago, you open the app on
Tuesday's.

This is deliberate and it has a cost worth stating: the most recent thing is
not the first thing you see. What it buys is that the queue can actually be
finished. Newest-first fills a queue at the end you read from, so an arrival
lands on top of what you have not reached, the oldest unseen post sinks under
everything that came after it, and *all caught up* recedes as fast as you
approach it. Oldest-first inverts that exactly: an arrival sorts behind you,
nothing is ever inserted in front of you, and the end only gets closer.

The order is by when a post reached you, not by when it was taken or written.
A post somebody adds you to today arrives at the back of the queue today, even
if it was posted in March.

## What "seen" means, exactly

A post leaves your queue when you have looked at its first photograph. Three
things have to be true at once:

- the row is showing the first photograph, not the second or the third;
- the actual photograph has arrived and been decoded, not the blurred
  placeholder the app paints while it is fetching;
- that photograph is completely within the screen, or completely filling it,
  for one and a half continuous seconds. If it scrolls away, the clock starts
  again from nothing.

A post that leaves the queue does not come back, so the dangerous mistake is
marking something seen that nobody looked at. Every ambiguity is resolved
towards not-yet, which is why the rule is as strict as it is.

The first photograph is enough for the whole post. Requiring all of them would
strand a post of twenty photographs in the queue for ever, which is the thing
the feed exists to prevent.

**Only the feed marks a post seen.** Opening a post from your activity tab,
from a notification, or from somebody's profile does not take it out of your
queue. The row in the feed still has to be looked at.

**Nobody is told that you looked.** There is no seen-by list, no viewer count
and no read receipt anywhere in the app. The app does record that you saw a
post, because that is how your queue empties and how a set of photographs
reopens where you left it, and there is no screen, route or field that reports
it to the person who posted it. A version with seen-by was built once and
taken out again: a per-person read receipt turns looking at a photograph into
an act that gets reported, which is what this product is meant to be an escape
from.

## Nothing vanishes under your thumb

The moment a post is marked seen the server stops returning it. The app keeps
the row exactly where it is for the rest of the session. Rows do not disappear
mid-scroll, the list does not reshuffle, and nothing you are reading moves.
The photograph you had swiped to stays under your thumb for as long as the row
is on screen.

For the length of a session the app is deliberately holding rows the server
would no longer send it. The two are reconciled at the session boundary and
nowhere else.

## When the feed reloads, and when it does not

A feed session ends in exactly three ways:

- the app has been in the background for longer than 32 minutes;
- the app is started cold;
- you pull the feed down. The indicator is the app's own words, *pull to
  refresh* and then *refreshing*, rather than a spinner.

On the next session everything you have seen is gone and anything new is
there. Unseen posts stay where they are, in date order, however long they sit.

Nothing else reloads the feed. A notification arriving does not: a message is
the app's news, not yours, and it is not a fourth kind of session boundary.
There is no "new posts" pill, no timed refresh and no background reshuffle.
Tapping *home* while you are already on the feed does nothing at all, because
rebuilding the queue you are holding is the one thing the feed must not do.
Coming back from a post you opened returns you to the feed as you left it.

The pull is the only boundary that is a decision rather than a lapse, and it
exists because otherwise the only way to say "I am done with these" would be
to put the phone down for half an hour.

## All caught up, and posts you've seen

*all caught up* appears only when the server has said there is nothing after
the last row. It never appears because a page happened to be short.

Underneath it is one link, *posts you've seen*. That screen is the feed's own
past: everything that has been delivered to you and looked at, most recent
first by when you saw it, never re-surfaced, never automatically deleted, and
with no badges. Each row is the first photograph, the author, the date and the
caption. There is no swiping through photographs there, because paging frame
by frame through things you have already seen is browsing for its own sake.

It is worth knowing that this is the only door to that screen. It is not a row
in settings, and it cannot be reached from a tab that still has unseen posts
in it. If you were interrupted halfway through reading something and it has
already left your queue, there is no route back to it until a queue empties.
That gap is known, and it is recorded as an open question rather than
explained away.

## The tabs are your own filing

Across the top of the feed are your groups, with *everybody* first. A group
you have not put anybody in has no tab, so a new account sees one.

A group tab filters by **who wrote the post**, according to your own filing,
and not by how the author addressed it. Your *family* tab shows unseen posts
from the people you have filed under family, whatever audience they chose at
their end. Your groups are yours alone: they are not reciprocal, and nobody is
ever told which of your groups they are in, or that they are in one at all.
Putting Ana in *dinner table* does not put you in hers, and Ana cannot find
out.

The number beside a tab is the count of unseen posts in it. Apart from the
count of photographs on a row, it is the only number on the feed, and it is
allowed because it is yours, visible to nobody else, and it goes down as you
read. There is no comment count under a photograph, no reaction total, no view
count and no number anywhere that somebody else can make bigger.

## What is not in your feed

**Your own posts.** The feed is what other people sent you. There is no
delivery from you to yourself, so there is no row to put there; your own posts
live on your own profile, reached from the *profile* mark, and publishing
lands you there.

**Anybody's back catalogue.** When you connect to somebody and they share
their past posts with you, those photographs appear on their profile at their
original dates and never enter your queue: a thousand old posts arriving at
once leaves the feed empty. Being added to a single post that already exists
is a different thing—that delivery is stamped now, so it arrives at the back
of the queue as new, and your activity tab says who put it there.

**Anything that has been taken away.** A post deleted for everybody leaves
every feed at once, and disconnecting from somebody empties your feed of their
posts, because what goes is the key rather than a permission.

## What a row shows

A row is the author's picture and name, the date it was posted, the
photographs, and the caption. If people are named on it, a line reads *with
anna, bruno*. If it is a contribution to an album, a line reads *in Maine*. If
somebody reshared it, one line above the author's name reads *bruno reshared*,
and the row still wears the original poster's name and face.

Up to eight photographs are a swipeable set, with dots underneath as soon as
there is more than one. More than eight are shown as the first four in a grid
with a link reading *view all 24* into the full-screen viewer. The four are
the first four in the order the author put them, never a chosen best: picking
the best four would be this app ranking somebody's photographs.

Nothing somebody posted is ever cropped away. The box a photograph is drawn in
is bounded, so that one picture cannot take over the whole screen and push the
caption below the fold, and a picture that does not fit that box is fitted
inside it rather than trimmed. The one exception is the four-tile grid above,
which squares its tiles because a contact sheet with ragged edges is harder to
read, and the whole frame is a tap away. Tapping a photograph in the feed
opens the post at that photograph; tapping it again there opens the
full-screen viewer, which has no bound at all.

A caption is shortened to three lines in the list and never altered; the whole
of it is one tap away. A name in a row opens that person's profile, or, for
somebody named on the photograph you are not connected to, the
[card](/how-it-works/people/) that says who you both know. An author this
phone cannot name renders as the plain word *someone* and goes nowhere. In an
[album](/how-it-works/albums/) you may see a contribution from somebody you
have no connection to, because the album's membership is the audience: the row
names them, and the name is not a link, because there is no profile behind it.

A row in the feed always opens its photographs at the first one, including
when it scrolls out of view and back: a row that came back on the second could
never satisfy the seen rule, and the post would sit in your queue for ever.
The post screen behaves differently: a post you open resumes at the photograph
you were last looking at. Tapping a particular photograph in the feed beats
both and opens the post at that one.

## The activity tab

The bell on the bar is *activity*, and it holds the things that happen to you
that no other screen already names. Today that is seven: somebody reacted to
your post, somebody commented on it, somebody added you to a post, somebody
accepted your request, somebody added you to an album, somebody tagged you in
a post, and somebody reshared your post. Tapping a row opens the thing it is
about.

A post arriving is not in there, because a post arriving is the feed's. An add
request is not in there either, because it is at the top of your own profile.
The tab does not repeat what another screen already shows.

All of one post's reactions are a single row, naming whoever reacted most
recently, and it goes back to unread when somebody new reacts. It is not "anna
and three others", because that is a count of what other people did. Comments
keep a row each: three comments are three things somebody wrote.

**There is no unread count.** Not on the bell, not on the tab, not on the link
that opens it. A row that arrived since your last visit says the word *new*
beside its date, rows you have already read are drawn in a lighter ink, and
that is the whole of it. Every number in this app is your own, bounded and
shrinking; a tally of what other people have done to you grows while you do
nothing, which is the thing the app is trying not to be.

The bell can carry a plain dot, which has two values however many things have
happened. It asks whether the newest entry is unread, so looking answers it
and it goes out as the tab opens. The dot on the profile mark asks a different
question, whether anybody is waiting on a decision from you, so looking
answers nothing: it survives your visit and goes out only when the last
request has been accepted, declined or has expired.

## Notifications

The app is quiet by default, and it asks for permission to notify you on the
activity tab rather than at signup. The line there reads: "Nothing here has to
reach you. If you would like it to, this is where to say so."

Five things can put a notification on your phone:

- somebody asking to add you, in *settings → notifications* as *when somebody
  wants to add me*, which is the one switch that starts on;
- somebody commenting on your post, as *when somebody comments on my post*,
  off until you turn it on;
- a particular person posting, which is a switch on their profile reading
  *tell me when anna posts*, off for everybody until you ask;
- somebody adding photographs to a particular album, which is a switch on that
  album's own screen;
- somebody naming you in a photograph, which has no switch of its own under
  *notifications*. It rides on *let mutuals tag me*, which is on until you
  turn it off, so allowing the name allows the notification and refusing one
  refuses both.

One photograph is one interruption: a post that could satisfy several of those
switches at once sends exactly one notification. Being named is the clearest
case—the notification about the name arrives *instead of* the one you would
have had about the post, never beside it.

**A reaction can never notify anybody, and there is no setting that could make
it.** There is no notification type for it, no column in the database and no
route, and the settings screen says so in a line under the comment switch:
"Reactions never notify anybody, and cannot be made to." You can already see
who reacted by opening your own post, so the activity row saves you the
tapping; what is refused is the interruption. Having your post reshared is the
same: it writes a row in your activity tab and puts no notification on your
phone.

There is no "you haven't posted in a while", no digest, no streak and no
re-engagement message of any kind. This is not a policy somebody could relax:
a notification here is a single word naming what kind of thing happened, with
no field a sentence could be put into.

That word is all the notification carries. No name, no caption, and no
identifier for the post either, because two phones receiving the same post
identifier in the same second are two people in one audience, and repeated
often enough at a third party that is your social graph. The sentence you
read, "anna commented on your post", is written by your own phone out of a
profile we hold only as ciphertext and cannot open. The
[privacy policy](/privacy/) says what we can and cannot see.

Signing out on a phone stops that phone receiving anything for the account. It
is the server that does it, in the same step that ends the session, rather
than something the app has to remember on its way out.

---

The rest of the guide is at [how it works](/how-it-works/).
