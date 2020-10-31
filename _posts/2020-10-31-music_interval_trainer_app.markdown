---
layout: post
title: "Creating an Interval Trainer for Guitarist and Bassists"
date: 2020-10-31 07:35
---

As many of you may know, in addition to being a software engineer, I am also an avid bassist.
When I first learned to play bass guitar, I struggled greatly to find materials to help me grow as a player and to develop a theoretical knowledge of the instrument and of music theory in general as it applies to the bass.
When learning to play any harmonic instruments, it is critical that one learn about intervals since it is the basis of chord theory (harmonic instruments are those instruments like the piano, guitar, and others which can play multiple notes simultaneously, as opposed to melodic instruments which only play one note at a time such as the flute).
Yet, when trying to learn the bass or guitar, most available learning resources focus on non-foundational techniques such as riffs, chords and basic phrases of a given style of music.
However, to advance as a musician and to be able to compose and even just perform, one needs to take time to learn the foundational knowledge of music theory. Yet, as a guitarist or a bassist the only resources which exist which present this information may seem to be out of the reach of the average player or too extensive to be tackled.

On my path to learn music theory as it related to bass, I found only two resources which truly helped me to advance my knowledge and to help me understand the foundation of arpeggiation, scales, and chord theory.
Intervals are the absolute basic foundation of all music and having a solid knowledge of naming conventions and being able to identify intervals is necessary to expand ones knowledge of her instrument beyond just memorizing fingering patterns on a fretboard or keyboard.
In that respect, I am very grateful to Ariane Cap for her indespensible [Music Theory for the Bass Player](https://www.amazon.com/Music-Theory-Bass-Player-Hands/dp/0996727604/) and to Adam Kadmon for his comprehensive [Bass Grimoire](https://www.amazon.com/Bass-Grimoire-Adam-Kadmon/dp/B006W1OVRY/). Both of these books are must-haves for any serious bass player who wishes to expand her knowledge of theory and become a better musician and composer.
These books cover intervals and scales in depth. However, when one does not have her instrument at hand, neither of these resoures allow one to practice identifying intervals and there is no way to measure ones progress.
As a result, I sought out a resource on ear training for intervals--an app which would allow me to practice identifying said intervals by ear and be able to relate them back to the bass and later the guitar; however, no such app currently exists for this purpose. There are a great many such apps which focus on ear training, but in the context of a piano keyboard. This does not immediately assist the bassist or the guitarist to relate this information back to her instrument without learning a completely different interface for this aspect of her learning.
This was very disappointing to me and I am sure that it is not only a frustration for other fellow bassists and guitarists, but it also has historically served as a senseless and an close to insurmountable barrier of entry to such players to advance their knowledge and abilities beyond a basic level or just learning songs without out knowing why they are composed as they are.

For the above reasons, I decided to make the first ear trainer/interval trainer which is specifically designed for bassists and guitarists.
My app (which is still under development) presents a segment of the fretboard of a bass or guitar (number of strings and tuning based on settings) and labels the intervals and corresponding notes.
Both the guitar and bass have self-repeating patterns of the freboard which apply when shifted anywhere on the instrument which helps the learner to understand that learning music theory as it relates to these instruments is not an unattainable goal, but rather the first steps they should take.

In my interval trainer app, each note on the fretboard also is liked to a sound which allows the student to practice the intervals and visually inspect where that would be on the fretboard.
To accomplish this, I utilized [Tone.js](https://tonejs.github.io/) which is perhaps the most advanced open source web audio framework.
Also, to preemptively bridge the chasm of learning to read music, I have included music notation for the scales shown by using the music notation rendering library [abcjs](https://www.abcjs.net/).
An advancing player should never be forced to rely on guitar or bass tabs as they do not include any information about rhythm, duration or phrasing of a given passage of music.
Relating the fretboard to the musical staff is one of the biggest challenges that a student of guitar or bass faces.
So, my app seeks to remove this as a barrier to advancement.

An example of the interval view for a five string bass presents the following information.

| :----: | :----: | :----: | :----: | :----: |
|   P12  |   ♭13  |   P13  |   ♯13  |   ♭15  |
|   M9   |   m10  |   M10  |   P11  |   ♯11  |
|   M6   |   m7   |   M7   |   O    |   m9   |
|   M3   |   P4   |   TT   |   P5   |   m6   |
|   M7   |   R    |   m2   |   M2   |   m3   |

For those without a music background, please see [this article](https://www.musiclearningworkshop.com/advanced-intervals/) to understand the notation above. My app will of course also include a short tutorial which will explain the meaning of thees symbols and the relationships they have to the root or tonic note.

As the development of my app progresses, I will be blogging additional information about how I solved some of the technical challenges associated with making such an app.
I hope this series of my blog to assist other developers and musicians of other instruments (violin, banjo, etc.) to develop such apps which will help the community of beginners and advancing students to learn their instruments.
Please stay tuned for future posts which will present screenshots and a live, deployed application which one can use for free.
