---
layout: post
title: "Scales App"
date: 2020-05-18 11:05 -0600
---

Recently I have been working on an application to help musicians learn the major scale and its modes. This application has a Rails API backend and a Javascript SPA frontend. As with many of my projects, I have chosen to use PostgreSQL as the database because it is a robust and fully featured database and because I plan to deploy my application soon to Heroku.

Over the past few years, I found a passion for the bass. It is due to that that I was inspired to create the Scales web application. Because the bass is an isomorphic instrument (i.e., the pattern of any scale is the same at any starting point), it is easy to get into a bad habit of learning a scale pattern or learning the intervals of a given scale/mode, but not knowing which notes are actually in that mode. So, in trying to learn the bass, although I can play in a given key, I often times don't know which notes I'm actually using which limits my understanding of the music. Amongst novice bassists like myself, this is a common issue.

Another issue which often ails many musicians is understanding the modes of a scale. Most readers (whether they are aware of it or not) would recognize a C major scale if they heard it. It is the most generic happy sounding relationship of Western music. It is also the key that most people would sing in if they sung "Twinkle Twinkle Little Star". Additionally, it is the scale you would play on a piano if you start on a C note and play every subsequent white key until the next C note. But here is where it gets weird: If you play a C Major scale staring on the third note of the scale from that C (i.e., start on the E) and then play to the next E, that generic Western tone fades into the distance and instead is replaced by an arabesque flamenco flair. No, you didn't use any different notes, you just changed which root you started on. It's mind bending, to say the very least. As a musician, it is important to know what modes you could use to change the flavor of your music. But with attributed Greek names like E Phrygian or G Mixolydian, it is not very easy for a beginner to latch onto the true meaning and beauty that modes can bring to your music.

As a result of this, I decided to make the Scales web application to help budding musicians learn not only the intervals, but also the notes which are associated with them and to help them to have a place where a community of musicians can share their experience with modes and what nuanced feel each one can give to their music.
