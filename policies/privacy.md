---
title: Privacy policy
permalink: /privacy/
---

*people you know* is a private photo-sharing app for the people you actually
know. This page says what we hold about you, what we cannot see, and what
happens when you leave. It is written to be read, not skimmed; it is short
because there is not much to say.

**Last updated:** 8 September 2026. This policy covers the closed beta.

## The one-sentence version

Your photos, captions, comments, names and bios are encrypted on your phone
before they leave it, with keys we never have. We hold the encrypted files,
the list of who you are connected to, and the bookkeeping needed to deliver
things between you. We do not scan, read, rank, or sell any of it.

## What we cannot see

Everything you would call content is sealed on your phone under keys that
exist only on your phone and on the phones of the people you share with:

- photos, at every size we store them;
- captions;
- comments;
- your display name, your bio and your profile picture;
- the names of your albums.

We store these as ciphertext. We cannot open them, and neither can anybody
who obtains a copy of our servers. If you lose your recovery phrase and every
phone that holds your key, your photos are gone. We cannot recover them, and
this is deliberate: there is no copy that is ours to hand back.

## What we can see

To deliver a photo to the right people we hold, in the clear:

- your handle, and the email address you signed up with;
- who you are connected to, and when you connected;
- add requests you send and receive, and blocks you place;
- which of your groups a person is in (never shown to that person);
- who is in each album you are in;
- for every post: who made it, when, who it was addressed to, how many
  frames it has, how large the encrypted files are, and whether each
  recipient has looked at it;
- reactions, which are one emoji each and are stored in the clear because a
  single emoji from a known set cannot be meaningfully encrypted;
- the text of any report you file, because a report is a message to us and
  we have to be able to read it;
- the text of any bug report you send, and the one line shown to you before
  you send it: the version of the app, the version of Android and the model
  of your phone. Nothing else goes with it—no screenshot, no log, no file—
  and the app has no way to attach one;
- push tokens for phones you have signed in on;
- the moment you confirmed you were 18 or older (never your date of birth);
- counts of what your phone could and could not open, added to a total the
  moment they arrive and not kept against your account.

This is the honest boundary of the claim. It is metadata, and metadata
reveals who talks to whom. We keep it because the app cannot work without it,
we keep as little of it as we can, and we keep our access logs for 30 days
and no longer. Those logs record which kind of request was made and when, and
not who made it: no address of yours, no identifier, no page you asked for.

## Who else sees anything

Nobody, unless you share it with them. Only people you have both agreed to
connect with can see what you post, and only the people you address a post
to receive it. There is no public profile, no search by name, no
suggestions, and no way for a stranger to find you unless they already know
your exact handle or email address, and you have allowed requests from
people with no mutual in common.

What you share with someone, they can keep. The app does not stop screenshots
and cannot recall a photo from a phone that has already downloaded it, any
more than any other way of sending a photo can.

## What we do not do

- We do not sell, rent or share your data with anybody.
- We do not show advertising and do not build profiles for it.
- We do not scan content, because we cannot see it.
- We do not send you engagement notifications: there is no "you haven't
  posted in a while", no digest, no streak.
- We do not collect analytics about what you look at, and the app contains
  no crash-reporting or analytics library. If your phone is set to share
  usage and diagnostics with Google, Google tells us that the app crashed
  and where in our code; that report is Google's and contains none of your
  content.
- Your phone tells us how many photographs, captions, comments and album
  names it could or could not open since it last told us, and which version
  of the app and of Android it runs. Never which ones, and never whose. This
  is how we find out that something is broken before you would think to
  write to us, and it is on for everybody because it carries nothing that
  could be turned off.

## Third parties we use

- **Object storage** for the encrypted files. The provider holds ciphertext
  and never a key.
- **Push notifications**, through Google's Firebase Cloud Messaging, when you
  allow them. A push carries a type and nothing else: no names, no captions,
  no post identifiers.
- **Email** to send you a one-time sign-in code. The provider sees the
  address and the code, and nothing else about you.

## Deleting your account

*settings → delete my account*. Deleting is immediate and it is not
reversible. If you no longer have the app, [this page](/delete-account/) is how
to ask without it:

- every key that let anybody open your posts is destroyed at once, and so are
  the keys that let you open theirs;
- your posts, comments and reactions are gone for everyone straight away;
- your connections are severed and your groups are removed;
- albums you made are closed, and the people in them keep what they already
  had from each other;
- every phone you were signed in on is signed out;
- your handle and your email address are freed.

Eight days later the encrypted files are removed from storage. Those eight
days are not an undo: the keys were destroyed at the tap and nothing can
restore them. Signing in during that time with the same address starts a new,
empty account.

What we keep afterwards is a record that an account with that identifier
existed, blocks you placed or that were placed against you, and reports you
filed—without your name, address or key on any of it.

## Exporting your data

*settings → export my data* writes a folder to your phone containing your
posts at full size, your captions, the comments on your posts, and the
handles of the people you were connected to. It is decrypted on your phone,
because we could not produce it: we hold nothing readable to give you.

If you no longer have the phone, write to pykapp+privacy@proton.me from the
address on your account and we will send what we hold within a month: your
account record, the handles of your connections, and the encrypted files if
you want them. We cannot send readable photographs, because we cannot read
them.

## Children

You must be 18 or older to use *people you know*. We ask for your date of
birth once, at signup, compare it, and keep only the fact that you passed.

## Changes

If this policy changes we will say so in the app and here, with the date.

## Contact

pykapp+privacy@proton.me
