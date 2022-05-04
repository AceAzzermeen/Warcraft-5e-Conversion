<style>
/* GLOBAL FORMATTING  */

  /* Resize page to international A4 */
  .phb {
    width: 210mm;
    height: 296.8mm;
    background-image: url('https://www.gmbinder.com/images/RVaHjr8.png');
    background-size: cover;
  }
  .phb:after { 
    content: "";
  }
  /* Workaround fix for the line height displacement that GM Binder is
    experiencing right now thanks to under the hood Chromium changes */
  .phb p{ line-height: 15px; } 
  .phb blockquote p{ line-height: 14px; } 
  .phb h2{ line-height: 26px; } 
  .phb h3{ line-height: 19px; } 
  .phb h4{ line-height: 15px; padding-bottom: 3px; } 
  .phb h5{ line-height: 17px; } 
  th, td { line-height: 14px; }

/* FRONT PAGE STYLES */

  .cover-header-container {
    display: block;
    position: absolute;
    width: 100%;
    top: 80px;
    left: 0;
    right: 0;
    clear: both;
  }
  .cover-header-logo {
    display: block;
    width: 700px;
    margin: auto;
  }
  .cover-header-divider {
    display: block;
    width: 580px;
    margin: -12px auto -6px;
  }
  .cover-header-title {
    display: block;
    width: 700px;
    margin: auto;
    color: white;
    font-family: NodestoCaps,nodesto,sans-serif;
    font-weight: normal;
    font-size: 72px;
    line-height: 72px;
    text-align: center;
    text-shadow: 2px 2px 4px #000, -2px 2px 4px #000, 2px -2px 4px #000, -2px -2px 4px #000;
  }
  .cover-footer-container {
    display: block;
    position: absolute;
    width: 100%;
    bottom: 28px;
    left: 0;
    right: 0;
    clear: both;
  }
  .cover-footer-subtitle,
  .cover-footer-version {
    display: block;
    width: 500px;
    margin: auto;
    color: white;
    font-family: NodestoCaps,nodesto,sans-serif;
    font-weight: normal;
    text-align: center;
    text-shadow: 1px 1px 2px #000, -1px 1px 2px #000, 0px 0px 2px #000;
  }
  .cover-footer-subtitle {
    font-size: 28px;
    line-height: 28px;
  }
  .cover-footer-version {
    margin-top: 16px;
    font-size: 20px;
    line-height: 20px;
  }


/* TABLES AND BLOCKS */

  /* Adjust table colors inside noteblocks */
  .phb blockquote table tr:nth-child(odd) td { 
    background-color: #FFF0f5; 
  }
  .phb hr+section blockquote tr:nth-child(odd) td { 
    background-color: transparent;
  }
  /* Clear internal padding and add gap above for green note blocks*/
  .phb blockquote {
    padding-left: 0px;
    padding-right: 0px;
  }
  .phb blockquote { 
    margin-top: 1em;
  }
  /* Clear internal padding in creature statblocks */
  .phb hr+section blockquote {
    padding-left: 0px;
    padding-right: 0px;
  }  
  /* Use black tones for statblock backgrounds */
  .phb blockquote {
    box-shadow: 1px 4px 14px rgba(0,0,0,0.42);
  }
  /* Normalize space above Attributes */
  .phb hr+section blockquote hr+table {
    padding-top: 4px;
  }

/* TABLE OF CONTENTS  */

  /* toc specifically wants black text. This resets the headers*/
  .toc a {
    color: inherit !important;
  }
  /* Allow dot leaders to fill remaining space but not overlap */
  .toc li span:nth-child(2) {
    width: auto;
    overflow: hidden;
    white-space: nowrap;
    display: block;
  }
  .toc li span:nth-child(2):after {
    font-family: BookSanity;
    font-size: 0.317cm;
    font-weight: normal;
    color: black;
    content:
      " ........................................"
      "........................................."
      ".........................................";
    }

  /* Style TOC page numbers*/
  .toc li span:first-child {
    float: right;
    font-family: BookSanity;
    font-size: 0.317cm;
    font-weight: normal;
    color: black;
    margin-left: 1px;
  }

  /* Adjust TOC H3 styles */
  .toc li h3 span:nth-child(2):after {
    content: " ";
  }
  .toc li h3 {
    margin-bottom: 4px !important;
    margin-top: 10px !important;
    line-height: initial !important;
  }
  .toc li h3 span:first-child {
    line-height: 1.8em !important;
  }

  /* Reduce TOC list indentation*/
  .toc ul ul {
    margin-left: 10px !important;
  }
  .toc>ul>li {
    margin-bottom: initial !important;
  }


/* DOUBLE WIDE STATBLOCKS */

  /* For double-wide creature statblocks that we want to have anchored to the
  bottom of the page regardless of content flow. */
  .statblock-bottom-wide {
    position:absolute;
    bottom:63px;
    right:1.7cm;
    left:1.7cm;
    margin-top:1200px;
  }

/* INK BLOT STYLES */

  /* Root style for inkblots. Use alone, or together with
  one of the inkb lotstyle classes below. Essentially:
  <img url='{url}' class='inkblot inkblot-blue' />
  */
  .inkblot {
    position: absolute;
    mix-blend-mode: multiply;
    opacity: 0.6;
  }
  .inkblot-blue {
    filter: hue-rotate(190deg) saturate(120%)
  }
  .inkblot-green {
    filter: hue-rotate(120deg)
  }

/* FOOTER */

  /* Footnotes */
  .phb .pageNumber {
    color: #7e735c;
    z-index: 1000;
  }
  .phb .footnote { 
    color: #7e735c;
  }
  /* On odd pages before the bestiary, have just the page tear */
  .phb:nth-child(odd):nth-of-type(n+2):after {
    content: '';
    height: 125px;
    background-image: url(https://www.gmbinder.com/images/PB8On0U.png), url('https://gmbinder.com/images/YWardeu.png');
    background-size: 120px 120px, 816px 55px;
    background-repeat: no-repeat, no-repeat;
    background-position: bottom right -10px, bottom;
  }
  /* Reversed for alternating pages */
  .phb:nth-child(even):nth-of-type(n+2):after {
    content: '';
    height: 125px;
    background-image: url(https://www.gmbinder.com/images/PB8On0U.png), url('https://gmbinder.com/images/YWardeu.png');
    background-size: 120px 120px, 816px 55px;
    background-repeat: no-repeat, no-repeat;
    background-position: bottom right -10px, bottom;
    -webkit-transform: scaleX(-1);
    transform: scaleX(-1);
  }
  /* On odd bestiary pages, have the Monster Manual page tear and lettering */
  .phb:nth-child(odd):nth-of-type(n+11):nth-of-type(-n+123):after {
    content: '';
    height: 125px;
    background-image: url(https://gmbinder.com/images/lLWeevR.png), url('https://gmbinder.com/images/YWardeu.png');
    background-size: 120px 120px, 816px 55px;
    background-repeat: no-repeat, no-repeat;
    background-position: bottom right -10px, bottom;
  }
  /* Reversed for alternating pages */
  .phb:nth-child(even):nth-of-type(n+11):nth-of-type(-n+123):after {
    content: '';
    height: 125px;
    background-image: url(https://gmbinder.com/images/lLWeevR.png), url('https://gmbinder.com/images/YWardeu.png');
    background-size: 120px 120px, 816px 55px;
    background-repeat: no-repeat, no-repeat;
    background-position: bottom right -10px, bottom;
    -webkit-transform: scaleX(-1);
    transform: scaleX(-1);
  }
  /* The page number position */
  .phb .pageNumber {
    right: 0px;
  }
  /* The page number position for alternating pages */
  .phb:nth-child(even) .pageNumber {
    left: 0px;
  }
  /* The letter in the Monster Manual page tear */
  .pageLetter {
    position: absolute;
    right: 15px;
    bottom: 87.5px;
    color: #905727;
    z-index: 1000;
    font-size: 135%;
  }
  /* Reversed for alternating pages */
  .phb:nth-child(even) .pageLetter {
      left: 15px;
  }

/* MONSTER MANUAL SPECIFIC */

  /* Adds the surrounding framing for the big, bold monster letter headings */
  .letterheader {
    position: absolute;
    top: 30px;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    background-image: url(https://gmbinder.com/images/YH3aESG.png);
    background-size: cover;
    width: 775px;
    height: 133px;
  }

  /* Base component for the actual letter in the heading */
  .mmletter {
      position: absolute;
      top: 20px;
      left: 0;
      right: 0;
      margin-left: auto;
      margin-right: auto;
      background-size: cover;
      width: 163.2px;
      height: 163.2px;
  }

  /* Monster Manual alphabetical chapter letters */
  .mml-a {background-image: url(https://gmbinder.com/images/fVVv93s.png);}
  .mml-b {background-image: url(https://gmbinder.com/images/21X6N0B.png);}
  .mml-c {background-image: url(https://gmbinder.com/images/MvnpOWF.png);}
  .mml-d {background-image: url(https://gmbinder.com/images/AFbLU4P.png);}
  .mml-e {background-image: url(https://gmbinder.com/images/28NVNf9.png);}
  .mml-f {background-image: url(https://gmbinder.com/images/Oyrhmqy.png);}
  .mml-g {background-image: url(https://gmbinder.com/images/fRyiQn4.png);}
  .mml-h {background-image: url(https://gmbinder.com/images/N8NamlT.png);}
  .mml-i {background-image: url(https://gmbinder.com/images/xWI93aa.png);}
  .mml-j {background-image: url(https://gmbinder.com/images/GgIzsun.png);}
  .mml-k {background-image: url(https://gmbinder.com/images/OcObsWl.png);}
  .mml-l {background-image: url(https://gmbinder.com/images/B7AUyR6.png);}
  .mml-m {background-image: url(https://gmbinder.com/images/q4wXoxt.png);}
  .mml-n {background-image: url(https://gmbinder.com/images/OJtC4w9.png);}
  .mml-o {background-image: url(https://gmbinder.com/images/adeRr5d.png);}
  .mml-p {background-image: url(https://gmbinder.com/images/EEhcrSR.png);}
  .mml-q {background-image: url(https://gmbinder.com/images/O1AhfzL.png);}
  .mml-r {background-image: url(https://gmbinder.com/images/w66eIuZ.png);}
  .mml-s {background-image: url(https://gmbinder.com/images/YEoe0PP.png);}
  .mml-t {background-image: url(https://gmbinder.com/images/7Bk9D35.png);}
  .mml-u {background-image: url(https://gmbinder.com/images/uVJZYUg.png);}
  .mml-v {background-image: url(https://gmbinder.com/images/gKjngey.png);}
  .mml-w {background-image: url(https://gmbinder.com/images/14WWpsC.png);}
  .mml-x {background-image: url(https://gmbinder.com/images/ojIYjh0.png);}
  .mml-y {background-image: url(https://gmbinder.com/images/Gi1ePwY.png);}
  .mml-z {background-image: url(https://gmbinder.com/images/0ZTFNVs.png);}
 
/* APPENDIX STYLES */

  /* Avoid upscaling first letter on an appendix page */
  .phb:nth-of-type(n+100):nth-of-type(-n+200) h1+p::first-letter {
    font-family: BookSanity;
    font-size: .317cm;
    text-rendering: optimizeLegibility;
    float: initial;
  }  
</style>

<div class='cover-header-container'>
  <img class='cover-header-logo' src='https://www.gmbinder.com/images/0fKd9bC.png' />
  <img class='cover-header-divider' src='https://www.gmbinder.com/images/SGYtcP2.png' />
  <span class='cover-header-title'>
    Manual of Monsters
  </span>
</div>

<div class='cover-splotch'></div>

<div class='cover-footer-container'>
  <span class='cover-footer-subtitle'>
    An assortment of monsters and races
    <br />
    for your adventurers to face in the world of Azeroth
    <br />
  </span>
  <span class='cover-footer-version'>
    Major Version 3, Book Release 1
  </span>
</div>

<style> .phb#p1:after { display:none; } </style>
<img src='https://www.gmbinder.com/images/v1OE3Fq.jpg' style='position:absolute; top:-3px; right:-5px; width:810px' />

\pagebreak

## Foreword

We've made this book in an attempt to bring the beloved Warcraft franchise into the 5th edition of Dungeons & Dragons. It is a task that has taken us months to do, and it'll likely take many more still. Everyone involved are working this in their spare time, aiming to bring a genuine recreation of *Warcraft* as a D&D 5th Edition tabletop RPG.

This book is made to compliment official D&D 5th edition books, including the **Player's Handbook, Dungeon Master's Guide**, and **Monster Manual**. It has been built on the framework set by those books, and designed to be brought in as any supplement book would. Without any more work than to just use the material presented.

It has been written with the intention of always being a free resource for everyone to use. Never to be bought or paid for. We've made this because we want others to enjoy the Warcraft universe under D&D 5th Edition rules. Not for any monetary gain.

With each coming update, all changes will be noted in the Changelog — Link is provided below.
<div style='margin-top:-5px;'></div>
<div style="text-align:Center">

#### [ChangeLog](https://drive.google.com/open?id=1487fO7RPdUbloD7NY6mdCC-yFwsU4yFHOUQ4CBqX9mE)
</div>

## Project Links

**Other Warcraft 5E books**
<br><span style="margin-left:12px"></span> We've been working creating both player material and
<br><span style="margin-left:12px"></span> dungeon master material for playing Warcraft in
<br><span style="margin-left:12px"></span> D&D 5th Edition. You can check them all out here:

<div style="text-align:center">

#### [Warcraft 5E on GDrive](https://drive.google.com/drive/folders/1kVoAMR8TiO3CXFYcigFN2B6zk62xcnv9)

</div>

<br> **Want to join our community?**
<br><span style="margin-left:12px"></span> We're a relatively small group working together on this,
<br><span style="margin-left:12px"></span> and we think it's fun to hear the thoughts and opinions
<br><span style="margin-left:12px"></span> of people who have played with it. If you want to share
<br><span style="margin-left:12px"></span> your stories with us, suggest changes, or just join our
<br><span style="margin-left:12px"></span> Warcraft RPG community, we have both a Discord
<br><span style="margin-left:12px"></span> server and a subreddit going.

<div style="text-align:center">

#### [Discord Server](https://discord.gg/dKMJmmD) <span style="margin-left:40px"></span> [Subreddit](https://www.reddit.com/r/wc5e/)

</div>


\columnbreak


## Contributor Credits

*Contributors listed by community usernames.*
<div style='margin-top:-10px;'></div>

<br> **Original project authors** 
<br><span style="margin-left:12px"></span> Jih, Tangerine

<br />**Current core team**
<br><span style="margin-left:12px"></span> Ace Azzermeen, Geamros, Lorestalker Nemzal,
<br><span style="margin-left:12px"></span> MagusRogue MythMaker, Nagash, Llamadom,
<br><span style="margin-left:12px"></span> Tangerine, Tyloris

<br />**Inactive & former team members**
<br><span style="margin-left:12px"></span> 123jrf, ApolloLumina, Artipo, Auvreannia, Christinekn,
<br><span style="margin-left:12px"></span> ClockWorkTank, Elenus, Jih, Prometheus, Reiga,
<br><span style="margin-left:12px"></span> Silverblade, Tseims, Wyken

<br />**Big thanks to** 
<br><span style="margin-left:12px"></span> Everyone at our community Discord and Subreddit,
<br><span style="margin-left:12px"></span> whose engagement with the material and conversations
<br><span style="margin-left:12px"></span> with us make this project a ton of fun to work with.

<br> **Based on the original D&D game created by**
<br><span style="margin-left:12px"></span> E. Gary Gygax and Dave Arneson, as well as
<br><span style="margin-left:12px"></span>Brian Blume, Rob Kuntz, James Ward and Don Kaye.

<br> **Based on the Warcraft franchise by**
<br><span style="margin-left:12px"></span> © Blizzard Entertainment


## Other Thanks 

**Other projects we really like and want to give thanks to**
- [World of Warcraft 5E](https://www.thepiazza.org.uk/bb/viewtopic.php?t=13979) by Arrius Nideal
- [Champions of Azeroth](https://drive.google.com/drive/folders/1f07sWuQJ_MBJxKbToalevudGQ8hjnma7) by Silverblade#9212
- [These WoW Dungeon modules](https://www.gmbinder.com/profile/wyken) by Wyken
- All of the awesome homebrew that has been shared within the community, it's super cool to see it all! <br /> You can see a lot of it on our Discord, and in this [Theme of the Month](https://drive.google.com/drive/folders/1_inQbI4jjd6WF3ghzhr_9RYBFygAkVK1) collection.


## Made with GM Binder

This entire book was made using GM Binder. It is an amazing tool for creating authentic-looking homebrew material for 5th Edition Dungeons and Dragons.  Without it, this project would've likely never been considered.


<div style='margin-top:24px'></div>
<div style="text-align:Center">

<img src='https://www.gmbinder.com/images/yiRpC5m.png' style='width:150px' />

##### [www.GmBinder.com](https://www.gmbinder.com/)

</div>

\pagebreakNum

## Legal Stuff

In accordance with [statements presented by Blizzard Entertainment](https://www.blizzard.com/en-us/legal/28d5ebbf-c245-4408-8ba9-043dd5f056bf/legal-faq), for use of Blizzard trademarks in the creation of "total conversions", we the providers of the Dungeons & Dragons 5th Edition material presented in here make it all available for free.

There will never be a cost required to access any of it. This project will always remain free.

Depending on viewpoint, this project could be viewed as an "adaption" rather than a "total conversion" of Blizzard Entertainment's intellectual property. 

We have however seen a number of long-lived and still going conversion projects, adopting properties such as *Warcraft* and *Diablo* to other games -- including other tabletop RPG conversions of such. The common denominator between is that they are all creative endeavours and not marketed products.

We understand that our ability to work on this project may be revoked should Blizzard Entertainment find it an infringement of their End User License Agreement.

##### Wizards of the Coast Legal
DUNGEONS & DRAGONS, D&D, Wizards of the Coast, Forgotten Realms, Ravenloft, Eberron, the dragon ampersand, Ravnica and all other Wizards of the Coast product names, and their respective logos are trademarks of Wizards of the Coast in the USA and other countries.

Permission to copy, modify and distribute the files collectively known as the System Reference Document 5.1 ("SRD5") is granted solely through the use of the Open Gaming License, Version 1.0a.

##### Blizzard Entertainment Legal

©2004 Blizzard Entertainment, Inc. All rights reserved. World of Warcraft, Warcraft and Blizzard Entertainment are trademarks or registered trademarks of Blizzard  Entertainment, Inc. in the U.S. and/or other countries.


\pagebreakNum

<div style='margin-top:1000px;'></div> <br><br> <div style='margin-top:150px;'></div>

# Contents

<div class='toc wide'; style='column-count:3'>

 - [<span>4</span><span>**Ch. 1: Bestiary**                    </span>](#p4)
 - [<span>4</span><span> Preface                               </span>](#p4)
 - [<span>116</span><span>**App. A: Miscellaneous Creatures**  </span>](#p116)
</div>

<div class='wide'>

## Index of Monster Stat Blocks
</div>

<div class='toc wide'; style='column-count:3'>

 - [<span>10</span><span> Ancients                      </span>](#p10)
 - [<span>13</span><span> Basilisk                      </span>](#p13)
 - [<span>14</span><span> Bog Beasts                    </span>](#p14)
 - [<span>17</span><span> Centaurs                      </span>](#p17)
 - [<span>20</span><span> Core Hounds                   </span>](#p20)
 - [<span>22</span><span> Dinosaurs                     </span>](#p22)
 - [<span>24</span><span> Dragonhawks                   </span>](#p24)
 - [<span>25</span><span> Dust Devil                    </span>](#p25)
 - [<span>26</span><span> Dwarves: Dark Iron            </span>](#p26)
 - [<span>30</span><span> Elementals                    </span>](#p30)
 - [<span>34</span><span> Faceless Ones                 </span>](#p34)
 - [<span>36</span><span> Fleshbeast                    </span>](#p36)
 - [<span>37</span><span> Furbolg                       </span>](#p37)
 - [<span>38</span><span> Ghosts                        </span>](#p38)
 - [<span>46</span><span> Gnolls                        </span>](#p46)
 - [<span>50</span><span> Golems                        </span>](#p50)
 - [<span>52</span><span> Grell                         </span>](#p52)
 - [<span>53</span><span> Harpies                       </span>](#p53)
 - [<span>55</span><span> Kobolds                       </span>](#p55)
 - [<span>57</span><span> Kodos                         </span>](#p57)
 - [<span>58</span><span> Lashers                       </span>](#p58)
 - [<span>60</span><span> Leper Gnome                   </span>](#p60)
 - [<span>61</span><span> Makrura                       </span>](#p61)
 - [<span>62</span><span> Mana Wyrms                    </span>](#p62)
 - [<span>63</span><span> Mechanicals                   </span>](#p63)
 - [<span>67</span><span> Murlocs                       </span>](#p67)
 - [<span>69</span><span> Naga                          </span>](#p69)
 - [<span>73</span><span> Ogres                         </span>](#p73)
 - [<span>75</span><span> Owlbeasts                     </span>](#p75)
 - [<span>77</span><span> Quilboars                     </span>](#p77)
 - [<span>80</span><span> Ravagers                      </span>](#p80)
 - [<span>82</span><span> Sabercats                     </span>](#p82)
 - [<span>84</span><span> Satyrs                        </span>](#p84)
 - [<span>86</span><span> Scourge                       </span>](#p86)
 - [<span>92</span><span> Shale Spider                  </span>](#p92)
 - [<span>93</span><span> Shredder                      </span>](#p93)
 - [<span>94</span><span> Silithids                     </span>](#p94)
 - [<span>98</span><span> Skeletons                     </span>](#p98)
 - [<span>100</span><span> Treant                       </span>](#p100)
 - [<span>101</span><span> Troggs                       </span>](#p101)
 - [<span>104</span><span> Trolls                       </span>](#p104)
 - [<span>108</span><span> Thunder Lizard               </span>](#p108)
 - [<span>109</span><span> Whale Shark                  </span>](#p109)
 - [<span>110</span><span> Wind Serpents                </span>](#p110)
 - [<span>112</span><span> Wretched                     </span>](#p112)
 - [<span>113</span><span> Worgen: Feral                </span>](#p113)
 - [<span>114</span><span> Yetis                        </span>](#p114)
</div>

<img src='https://www.gmbinder.com/images/fePJKiQ.jpg' style='position:absolute; top:0px; right:-750px; width:2100px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:40px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:350px;'></div>

# Chapter 1: Bestiary
THERE IS A BIG WORLD OUT THERE. From the familiar shores of Azeroth and the torn reaches of Draenor, across the Twisting Nether to a thousand worlds within the great cosmic planes. It's no wonder so many take to the call for adventure and seek out on the&shy;ir own, and no surprise to hear of the dang&shy;ers they've found along the way.

This chapter presents creatures found throughout the Warcraft universe. Some of the statistics have been brou&shy;ght over or otherwise adopted from the D&D System Reference Document (SRD) under the Open Gaming License (OGL), while the majority were written by the fans and contributors to this project -- without whom this book would likely be a long way away still.

Here you will find statistics for many classic fantasy RPG staples -- skeletons, yetis, owlbeasts, harpies, gnolls, basi&shy;lisks, ghosts, and more -- as well as numerous creatures iconic to Warcraft; such as the insidious murlocs, the lumbering woodland ancients, and the ever-looming threat of the undead Scourge.

If you are looking for material to run a campaign set within the Warcraft universe, whether with material of your own or with material taken from the *Heroes' Handbook* also written as part of this project, we hope this book will provide you with enough material to keep your players on their toes as they venture through Azeroth and beyond.

### This chapter is not yet finished

As of this first release of our *Manual of Monsters*, this book contains statistics for 179 monsters and miscellaneous creatures suitable for a Warcraft campaign.

In the long run, our full goal is a book of statistics for approximately 600 (and perhaps later, even more) monsters, creatures, and NPCs. From mundane beasts to the great Dragonflights and the infernal armies of the Burning Legion, as well as legendary figures.

## Statistics
A monster's statistics, sometimes referred to as its **stat block**, provide the essential information that you need to run the monster.

### Size
A monster can be Tiny, Small, Medium, Large, Huge, or Gargantuan. The Size Categories table shows how much space a creature of a particular size controls in combat. See the 5th edition *Player's Handbook* for more information on creature size and space.

\columnbreak

##### Size Categories
|&nbsp; Size       | Space | Examples |
|:-----------------|:-----------|:-:|
|&nbsp; Tiny       | 2½ by 2½ ft. | Bat, spider
|&nbsp; Small      | 5 by 5 ft. | Kobold, murloc
|&nbsp; Medium     | 5 by 5 ft. | Gnoll, human
|&nbsp; Large      | 10 by 10 ft. | Kodo, ogre
|&nbsp; Huge       | 15 by 15 ft. | Ancient protector, devilsaur
|&nbsp; Gargantuan | 20 by 20 ft. or larger | Brutosaur, whale shark

> ##### Modifying Creatures
> Despite the versatile collection of monsters in this book, you might be at a loss when it comes to finding the perfect creature for part of an adventure. Feel free to tweak a creature to make it into something more useful for you, perhaps by borrowing a trait or two from a different monster or by using a **variant** or **template**, such as the ones in this book. Keep in mind that modifying a monster, including when you apply a template to it, might change its challenge rating.

### Type
A monster's type speaks to its fundamental nature. Certain spells, magic items, class features, and other effects in the game interact in special ways with creatures of a particular type. For example, an *arrow of dragon slaying* deals extra damage not only to dragons but also other creatures of the dragon type, such as drakonids and drakeadons.

The game includes the following monster types, which have no rules of their own.

**Aberrations** are utterly alien beings. Many of them have innate magical abilities drawn from the creature's alien mind rather than the mystical forces of the world. The quin&shy;tessential aberrations are forgotten ones, nerubians, and the creations of the old gods.

**Beasts** are nonhumanoid creatures that are a natural part of the fantasy ecology. Some of them have magical powers, but most are unintelligent and lack any society or language. Beasts include all varieties of ordinary animals, dinosaurs, and giant versions of animals.

<div class='footnote'>CHAPTER 2 | INTRODUCTION </div>
<img src='https://www.gmbinder.com/images/aVVaaY1.jpg' style='position:absolute; top:-150px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/epoShfv.png' style='position:absolute; top:50px; right:0px; width:900px; transform:scaley(-1)' />

\pagebreakNum

&nbsp;&nbsp;&nbsp; **Constructs** are made, not born. Some are programmed by their creators to follow a set of instructions, while others are imbued with sentience and capable of independent thought. Golems are the iconic constructs.

**Dragons** are reptilian creatures of ancient origin and tremendous power. The dragonflights are highly intelligent and have innate magic. This category also includes distant relatives of the dragonflights; such as the less powerful and less magical  dragonspawns and proto-drakes.

**Elementals** are creatures native to the elemental plane. Some creatures of this type are little more than animate masses of their respective elements. Others have biological forms infused with elemental energy. The races of elemen&shy;tal creatures include ascendants, bound and unbound elementals, and revenants.

**Fey** are magical creatures closely tied to the forces of nature. They dwell in twilight groves and misty forests. They are closely tied to the Emerald Dream. Fey include dryads, faerie dragons, and wisps.

**Fiends** are creatures of wickedness native to worlds beyond Azeroth. Many originate from the Great Dark Beyond and its Twisting Nether, others were corrupted on planets far away. Fiends all serve Sargeras the Dark Titan, and in turn the Void Lords themselves. Fiends include demons, infernals, and the Eredar.

**Giants** tower over humans and their kind. They are enor&shy;mous creatures created by the titans, many of whom still show the stone shapes of their makers. Giants include sea giants, ogres, breakers, and the vrykul.

**Humanoids** are the main people of Azeroth, both civilized and savage, including humans and a tremendous variety of other species. They have language and culture, few if any innate magical abilities (though most humanoids can learn spellcasting), and a bipedal form. The most common humanoid races are the ones most suitable as player characters: humans, orcs, trolls, and dwarves.

A variety of humanoids appear throughout this book, but the races detailed in the *Heroes Handbook* are dealt with in appendix B. That appendix gives you a number of stat blocks that you can use to make variations of those races.

**Monstrosities** are monsters, frightening creatures that are not ordinary, not truly natural, and almost never benign. Some are the results of magical experimentation gone awry, and others are the product of terrible curses. They defy categorization, and in some sense serve as a catch-all category for creatures that don't fit into any type.

**Oozes** are gelatinous creatures that rarely have a fixed shape. They adapt to their environment, taking on aspects of their surroundings.

**Plants** in this context are vegetable creatures, not ordinary flora. Most of them are ambulatory, and some are carnivorous. The quintessential plants are the ancients and treants. Fungal creatures such as sporelings and the mandragora also fall into this category.

**Titans** are beings made by titans themselves. Many resemble constructs, being massive creatures made of stone or other inanimate materials. Titans include titan constructs, titanforged, and titanic watchers.

**Undead** are once-living creatures brought to a horrify&shy;ing state of undeath through the practice of necromantic magic or some unholy curse. Undead include walking corpses, such as zombies and the San’layn, as well as bodi&shy;less spirits, such as ghosts and specters.

\columnbreak

#### Tags
A monster might have one or more tags appended to its type, in parentheses. For example, an orc has the human&shy;oid (orc) type. The parenthetical tags provide additional categorization for certain creatures. The tags have no rules of their own, but something in the game, such as a magic item, might refer to them. For instance, a spear that is especially effective at fighting demons would work against any monster that has the demon tag.

### Alignment
A monster's alignment provides a clue to its disposition and how it behaves in a roleplaying or combat situation. For example, a chaotic evil monster might be difficult to reason with and might attack characters on sight, while a neutral monster might be willing to negotiate. See the *Heroes Handbook* for descriptions of the different alignments.

The alignment specified in a monster's stat block is the default. Feel free to depart from it and change a monster's alignment to suit the needs of your campaign. If you want a good-aligned doomguard or an evil keeper of the grove, there's nothing stopping you.

Some creatures can have **any alignment**. Meaning, you can choose the monster's alignment. Some monster's alignment entry indicates a tendency or aversion toward law, chaos, good, or evil. For example, a berserker can be any chaotic alignment (chaotic good, chaotic neutral, or chaotic evil), as befits its wild nature.

Many creatures of low intelligence have no comprehen&shy;sion of law or chaos, good or evil. They don't make moral or ethical choices, but rather act on instinct. These creatures are **unaligned**, which means they don't have an alignment.

### Armor Class
A monster that wears armor or carries a shield has an Armor Class (AC) that takes its armor, shield, and Dexterity into account. Otherwise, a monster's AC is based on its Dexterity modifier and natural armor, if any. If a monster has natural armor, wears armor, or carries a shield, this is noted in parentheses after its AC value.

### Hit Points
A monster usually dies or is destroyed when it drops to 0 hit points.

A monster's hit points are presented both as a die expres&shy;sion and as an average number. For example, a monster with 2d8 hit points has 9 hit points on average (2 x 4½).

##### Hit Dice by Size
|&nbsp; Monster Size | Hit Dice | Average HP per Die |
|:-------------------|:---:|:---:|
|&nbsp; Tiny         |  d4 |  2½ |
|&nbsp; Small        |  d6 |  3½ |
|&nbsp; Medium       |  d8 |  4½ |
|&nbsp; Large        | d10 |  5½ |
|&nbsp; Huge         | d12 |  6½ |
|&nbsp; Gargantuan   | d20 | 10½ |

A monster's Constitution modifier also affects the number of hit points it has. Its Constitution modifier is multiplied by the number of Hit Dice it possesses, and the result is added to its hit points. For example, if a monster has a Constitution of 12 (+1 modifier) and 2d8 Hit Dice, it has 2d8 + 2 hit points (average 11).

<div class='footnote'>CHAPTER 2 | INTRODUCTION </div>


\pagebreakNum

### Speed
A monster's speed tells you how far it can move on its turn. For more information on speed, see the 5th edition *Player's Handbook*.

All creatures have a walking speed, simply called the monster's speed. Creatures that have no form of ground-based locomotion have a walking speed of 0 feet.

Some creatures have one or more of the following additional movement modes.
<div style='margin-top:-5px;'></div>

#### Burrow
A monster that has a burrowing speed can use that speed to move through sand, earth, mud, or ice. A monster can't burrow through solid rock unless it has a special trait that allows it to do so.
<div style='margin-top:-5px;'></div>

#### Climb
A monster that has a climbing speed can use all or part of its movement to move on vertical surfaces. The monster doesn't need to spend extra movement to climb.
<div style='margin-top:-5px;'></div>

#### Fly
A monster that has a flying speed can use all or part of its movement to fly. Some monsters have the ability to **hover**, which makes them hard to knock out of the air (as ex&shy;plained in the rules on flying in the 5th edition *Player's Handbook*). Such a monster stops hovering when it dies.
<div style='margin-top:-5px;'></div>

#### Swim
A monster that has a swimming speed doesn't need to spend extra movement to swim.

### Ability Scores
Every monster has six ability scores (Strength, Dexterity, Constitution, Intelligence, Wisdom, and Charisma) and corresponding modifiers. For more information on ability scores and how they're used in play, see the 5th edition *Player's Handbook*.

### Saving Throws
The Saving Throws entry is reserved for creatures that are adept at resisting certain kinds of effects. For example, a creature that isn't easily charmed or frightened might gain a bonus on its Wisdom saving throws. Most creatures don't have special saving throw bonuses, in which case this section is absent.

A saving throw bonus is the sum of a monster's relevant ability modifier and its proficiency bonus, which is deter&shy;mined by the monster's challenge rating (as shown in the Proficiency Bonus by Challenge Rating table).

> ##### Armor, Weapon, & Tool Proficiency
> Assume that a creature is proficient with its armor, weapons, and tools. If you swap them out, you decide whether the creature is proficient with its new equipment.
>
> For example, an ogre typically wears hide armor and wields a greatclub. You could equip an ogre with chain mail and a greataxe instead, and assume the ogre is proficient with both, one or the other, or neither.
>
> See the 5th edition *Player's Handbook* for rules on using armor or weapons without proficiency.

\columnbreak

##### Proficiency Bonus by Challenge Rating

<div style='column-count:2'>

| Challenge | Proficiency<br>Bonus |
|:--:|:--:|
|  0 | +2 |
| 1/8| +2 |
| 1/4| +2 |
| 1/2| +2 |
|  1 | +2 |
|  2 | +2 |
|  3 | +2 |
|  4 | +2 |
|  5 | +3 |
|  6 | +3 |
|  7 | +3 |
|  8 | +3 |
|  9 | +4 |
| 10 | +4 |
| 11 | +4 |
| 12 | +4 |
| 13 | +5 |

| Challenge | Proficiency<br>Bonus |
|:--:|:--:|
| 14 | +5 |
| 15 | +5 |
| 16 | +5 |
| 17 | +6 |
| 18 | +6 |
| 19 | +6 |
| 20 | +6 |
| 21 | +7 |
| 22 | +7 |
| 23 | +7 |
| 24 | +7 |
| 25 | +8 |
| 26 | +8 |
| 27 | +8 |
| 28 | +8 |
| 29 | +9 |
| 30 | +9 |
</div>

### Skills
The Skills entry is reserved for monsters that are proficient in one or more skills. For example, a monster that is very perceptive and stealthy might have bonuses to Wisdom (Perception) and Dexterity (Stealth) checks.

A skill bonus is the sum of a monster's relevant ability modifier and its proficiency bonus, which is determined by the monster's challenge rating (as shown in the Proficiency Bonus by Challenge Rating table). Other modifiers might apply. For instance, a monster might have a larger-than-expected bonus (usually double its proficiency bonus) to account for its heightened expertise.

### Vulnerabilities, Resistances, <br>and Immunities
Some creatures have vulnerability, resistance, or immunity to certain types of damage. Additionally, some creatures are immune to certain conditions. If a monster is immune to a game effect that isn't considered damage or a condition, it has a special trait.

<div class='footnote'>CHAPTER 2 | INTRODUCTION </div>
<img src='https://www.gmbinder.com/images/uZAKe3K.jpg' style='position:absolute; top:760px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:0px; right:0px; width:960px' />

\pagebreakNum

### Senses
The Senses entry notes a monster's passive Wisdom (Perception) score, as well as any special senses the monster might have. Special senses are described below.

#### Blindsight
A monster with blindsight can perceive its surroundings without relying on sight, within a specific radius.

Creatures without eyes, such as oozes, typically have this special sense, as do creatures with echolocation or height&shy;ened senses, such as bats and the dragonflights.

If a monster is naturally blind, it has a parenthetical note to this effect, indicating that the radius of its blindsight defines the maximum range of its perception.

#### Darkvision
A monster with darkvision can see in the dark within a specific radius. The monster can see in dim light within the radius as if it were bright light, and in darkness as if it were dim light. The monster can't discern color in darkness, only shades of gray. Many creatures that live underground have this special sense.

#### Tremorsense
A monster with tremorsense can detect and pinpoint the origin of vibrations within a specific radius, provided that the monster and the source of the vibrations are in contact with the same ground or substance. Tremorsense can't be used to detect flying or incorporeal creatures.

#### Truesight
A monster with truesight can, out to a specific range, see in normal and magical darkness, see invisible creatures and objects, automatically detect visual illusions and succeed on saving throws against them, and perceive the original form of a shapechanger or a creature that is transformed by magic. Furthermore, the monster can see into the Ethereal Plane within the same range.

### Languages
The languages that a monster can speak are listed in alphabetical order. Sometimes a monster can understand a language but can't speak it, and this is noted in its entry.

A "—" indicates that a creature neither speaks nor under&shy;stands any language.

#### Telepathy
Telepathy is a magical ability that allows a monster to communicate mentally with another creature within a specified range. The contacted creature doesn't need to share a language with the monster to communicate in this way with it, but it must be able to understand at least one language. A creature without telepathy can receive and respond to telepathic messages but can't initiate or terminate a telepathic conversation.

A telepathic monster doesn't need to see the creature and can end the telepathic contact at any time. The contact is broken as soon as the two creatures are no longer within range of each other or if the telepathic monster contacts a different creature within range. A telepathic monster can initiative or terminate a telepathic conversation without using an action, but while the monster is incapacitated, it can't initiate telepathic contact, and contact is terminated.

A creature within the area of an *antimagic field* or in any other location where magic doesn't function can't send or receive telepathic messages.

\columnbreak

### Challenge
A monster's **challenge rating** tells you how great a threat the monster is. An appropriately equipped and well-rested party of four adventurers should be able to defeat monsters that has a challenge rating equal to its level without suffering any deaths. For example, a party of four 3rd-level characters should find a monster with a challenge rating of 3 to be a worthy challenge, but not a deadly one.

Monsters that are significantly weaker than 1st-level characters have a challenge rating lower than 1. Monsters with a challenge rating of 0 are insignificant except in large numbers; those with no effective attacks are worth no experience points, while those that have attacks are worth 10 XP each.

Some monsters present a greater challenge than even a typical 20th-level party can handle. These monsters have a challenge rating of 21 or higher and are specifically designed to test player skill.

#### Experience Points
The number of experience points (XP) a monster is worth is based on its challenge rating. Typically, XP is awarded for defeating the monster although the DM may also award XP for neutralizing the threat posed by the monster in some other manner.

Unless something tells you otherwise, a monster summoned by a spell or other magical ability is worth the XP noted in its stat block.

The 5th edition *Dungeon Master's Guide* explains how to create encounters using XP budgets, as well as how to adjust an encounter's difficulty.

##### Experience Points by Challenge Rating

<div style='column-count:2'>

| Challenge | XP |
|:--:|:------:|
|  0 | 0 or 10|
| 1/8|     25 |
| 1/4|     50 |
| 1/2|    100 |
|  1 |    200 |
|  2 |    450 |
|  3 |    700 |
|  4 |  1,100 |
|  5 |  1,800 |
|  6 |  2,300 |
|  7 |  2,900 |
|  8 |  3,900 |
|  9 |  5,000 |
| 10 |  5,900 |
| 11 |  7,200 |
| 12 |  8,400 |
| 13 | 10,000 |

| Challenge | XP |
|:--:|:-------:|
| 14 |  11,500 |
| 15 |  13,000 |
| 16 |  15,000 |
| 17 |  18,000 |
| 18 |  20,000 |
| 19 |  22,000 |
| 20 |  25,000 |
| 21 |  33,000 |
| 22 |  41,000 |
| 23 |  50,000 |
| 24 |  62,000 |
| 25 |  75,000 |
| 26 |  90,000 |
| 27 | 105,000 |
| 28 | 120,000 |
| 29 | 135,000 |
| 30 | 155,000 |
</div>

<div class='footnote'>CHAPTER 2 | INTRODUCTION </div>


\pagebreakNum

### Special Traits
Special traits (which appear after a monster's challenge rating but before any actions or reactions) are character&shy;istics that are likely to be relevant in a combat encounter and that require some explanation.

#### Innate Spellcasting
A monster with this innate ability to cast spells has the Innate Spellcasting special trait. Unless noted otherwise, an innate spell of 1st level or higher is always cast as its lowest possible level and can't be cast at a higher level. If a monster has a cantrip where its level matters and no level is given, use the monster's challenge rating.

An innate spell can have special rules or restrictions. For example, a spell might have a "self only" restriction, which means that the spell affects only the caster.

A monster's innate spells can't be swapped out with other spells. If a monster's innate spells don't require attack rolls, no attack bonus is given for them.

#### Spellcasting
A monster with the Spellcasting class feature has a spellcaster level and spell slots, which it uses to cast its spells of 1st level and higher (as explained in the 5th edition *Player's Handbook*). The spellcaster level is also used for any cantrips included in the feature.

The monster has a list of spells known or prepared from a particular class. The list might also include spells from a feature in that class, such as the Divine Priesthood feature of the priest or the Druid Path feature of the druid.

A monster can cast spells from its list at a higher level if it has the spell slot to do so. For example, a creature with the 3rd-level *lightning bolt* spell can cast it as a higher level spell if such a spell slot is available.

You can change the spells that a monster knows or has prepared, replacing any spell on a monster's spell list with a different spell of the same level and from the same class list. If you do so, you might cause the monster to be a greater or lesser threat than suggested by its challenge rating.

#### Psionics
A monster that casts spells using only the power of its mind has the psionics tag added to its Spellcasting or Innate Spellcasting special trait. This tag carries no special rules of its own, but other parts of the game might refer to it. A monster that has this tag typically doesn't require any components to cast its spells.

### Actions
When a monster takes its action, it can choose from the options in the Action section of its stat block or use one of the actions available to all creatures, such as the Dash or Hide action, as described in the 5th edition *Player's Handbook*

#### Melee and Ranged Attacks
The most common action that a monster will take in combat are melee and ranged attacks. These can be spell attacks or weapon attacks, where the "weapon" might be a manufactured item or a natural weapon, such as a claw or tail spike. For more information on the different kinds of attacks, see the 5th edition *Player's Handbook*.

***Creature vs. Target.*** The target of a melee or ranged attack is either one creature or one target, the difference being that a "target" can be a creature or an object

<div class='footnote'>CHAPTER 2 | INTRODUCTION </div>
<img src='https://www.gmbinder.com/images/PjJ1cuU.jpg' style='position:absolute; top:0px; right:-70px; width:770px' />
<img src='https://www.gmbinder.com/images/VSTbbfG.png' style='position:absolute; top:0px; right:-50px; width:900px' />

\pagebreakNum

&nbsp;&nbsp;&nbsp; ***Hit.*** any damage dealt or other effects that occur as a result of an attack hitting a target are described after the *"Hit"* notation. You have the option of taking average damage or rolling the damage; for this reason, both the average damage and the die expression are presented.

***Miss.*** If an attack has an effect that occurs on a miss that information is presented after the *"Miss:"* notation.

#### Multiattack
A creature that can make multiple attacks on its turn has the Multiattack ability. A creature can't use Multiattack when making an opportunity attack, which must be a single melee attack.

#### Ammunition
A monster carries enough ammunition to make its ranged attacks. You can assume that a monster has 2d4 pieces of ammunition for a thrown weapon attack, and 2d10 pieces of ammunition for a projectile weapon such as a bow or crossbow.

### Reactions
If a monster can do something special with its reaction, that information is contained here. If a creature has no special reaction, this section is absent.

### Limited Usage
Some special abilities have restrictions on the number of times they can be used.

***X/Day.*** The notation "X/Day" means a special ability can be used X number of times and that a monster must finish a long rest to use it again.

***Recharge X—Y.*** The notation "Recharge X—Y" means a monster can use a special ability once and that the ability then has a random chance of recharging during each subsequent round of combat. At the start of each of the monster's turns, roll a d6. If the roll is one of the numbers in the recharge notation, the monster regains the use of the special ability. The ability also recharges when the monster finishes a short or long rest.

For example, "Recharge 5-6" means a monster can use the special ability once. Then, at the start of the monster's turn, it regains the use of that ability if it rolls a 5-6 on a d6.

***Recharge after a Short or Long Rest.*** This notation means that a monster can use a special ability once and then must finish a short or long rest to use it again.

> ##### Grapple Rules for Monsters
> Many monsters have special attacks that allow them to quickly grapple prey. When a monster hits with such an attack, it doesn't need to make an additional ability check to determine whether the grapple succeeds, unless said otherwise.
>
> A creature grappled by the monster can use its action to try and escape. To do so, it must succeed on a Strength (Athletics) or Dexterity (Acrobatics) check against the escape DC in the monster's stat block. If no escape DC is given, assume the DC is 10 + the monster's Strength (Athletics) modifier.

\columnbreak

### Equipment
A stat block rarely refers to equipment, other than armor or weapons used by a monster. A creature that customarily wears clothes, such as humanoid, is assumed to be dressed appropriately.

You can equip monsters with additional gear and trinkets however you like, using the equipment chapter of the 5th edition *Player's Handbook*, and our *Heroes Handbook* for inspiration, and you decide how much of a monster's equip&shy;ment is recoverable after the creature is slain and whether any of that equipment is still usable. A battered suit of armor made for a monster is rarely usable by someone else, for instance.

If a monster with spellcasting requires material components to cast its spells, assume that it has the material components it needs to cast the spells in its stat block.

## Legendary Creatures
A legendary creature can do things that ordinary creatures can't. Legendary creatures can take special actions outside their turns, and a few can exert power over their environ&shy;ment, causing extraordinary magical effects to occur in their vicinity.

### Legendary Actions
A legendary creature can take a certain number of special actions—called legendary actions—outside its turn. Only one legendary action option can be used at a time and only at the end of another creature's turn. A legendary creature regains spent legendary actions at the start of its turn. It isn't required to use its legendary actions, and it can't use legendary actions while incapacitated.

### A Legendary Creature's Lair
A legendary creature might have a section of describing its lair and the special effects it can create while there, either by act of will or simply by being present. Not all legendary creatures have lairs. This section only applies to legendary creatures that spend a great deal of time in their lairs and are most likely to be encountered there.

#### Lair Actions
If a legendary creature has lair actions, it can use them to harness the ambient magic in its lair. On initiative count 20 (losing all initiative ties), the creature can use one of its lair action options, or forgo using any of them that round.

#### Regional Effects
The mere presence of a legendary creature can have strange and wondrous effects on its environment, as noted in this section. Regional effects end abruptly or dissipate over time when the legendary creature dies.



<div class='footnote'>CHAPTER 2 | INTRODUCTION </div>

<img src='https://www.gmbinder.com/images/Z8yFnva.jpg' style='position:absolute; top:880px; right:-20px; width:400px;mix-blend-mode:multiply;transform:rotate(-6deg)' />

\pagebreakNum

<div style='margin-top:414px;'></div>

___
> ## Ancient Protector 
>*Huge plant, neutral good*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 105 (10d12 + 40)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|21 (+5)|8 (-1)|19 (+4)|12 (+1)|16 (+3)|12 (+1)|
>___
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** bludgeoning, piercing
> - **Senses** darkvision 120 ft., passive Perception 13
> - **Languages** Darnassian, Druidic
> - **Challenge** 6 (2,300 XP)
> ___
> ***False Appearance.*** While the ancient remains motion&shy;less, it is indistinguishable from a normal tree.
>
> ***Siege Monster.*** The ancient deals double damage to objects and structures.
>
> ### Actions
> ***Multiattack.*** The ancient makes two slam attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 15 (3d6 + 5) bludgeoning damage.
>
> ***Rock*** *Ranged Weapon Attack:* +8 to hit, range 60/180 ft., one target. *Hit:* 27 (5d8 + 5) bludgeoning damage.
>
> ***Take Root.*** The ancient buries its roots in the ground. While rooted, the ancient's speed becomes 0, it gains advantage on its attack rolls, and is immune to any effect that would force the ancient to move or be moved. The ancient can end this effect by repeating this action to uproot itself. <!-- https://wc5e-cr-calculator.frogvall.com/?1;15;105;8;16;30;0;30;0;30;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:185px;'></div>

## <span style="margin-left:76px"></span> Ancients

<span style="margin-left:76px"></span> The Ancients are massive, leaf-covered trees
<span style="margin-left:72px"></span> given life. With an unparalleled wisdom and
<span style="margin-left:64px"></span> insight into the world around them, they act as
<span style="margin-left:60px"></span> guardians of the forests where they dwell -- such
<span style="margin-left:60px"></span> as those of northern Kalimdor, where their
<span style="margin-left:46px"></span> shared bonds with the night elves have kept the
<span style="margin-left:32px"></span> two races in a long-lasting symbiosis.

***Staunch Defenders.*** An ancient is grown from an acorn, like so many other trees, though the acorn itself is far rarer and far more powerful. It takes years upon years for an ancient to grow to its full size, where it stays for thousands of years without feeling the wear of old age.

The ancients who have allied themselves with the honorable night elves stand guard of their cities, and of their border territories. They can burrow their rooted feet into the soil beneath, becoming indistinguishable from a normal tree if they stand perfectly still. This allows both for other creatures to take shelter between its leaves, such as a squirrel with its own acorns, and for the ancient to keep quiet watch over the wilds.

Due to their immense lifespan and often slow, lumbering presence, an ancient sees time differently from mortal races. Often times, years may become akin to hours, minutes, or even seconds.

***Plantlike Creatures.*** An ancient doesn't require food or sleep. Instead, it draws nourishment from the soil and can carry on for weeks without a fresh supply of water.

### Ancient Protector
Most often when the acorn of an ancient sprouts, it grows to become an ancient protector. These hulking trees make up most of the ancients, and are critical in safeguarding night elven civic areas and groves.

### Ancient of Lore
Some ancients grow to become enlightened beings of the forest, wise beyond belief and capable of establishing meaningful contact with the free-spirited dryads. These ancient have a close connection to night elven druids and priests, taking on a role as instructors in the ways of magic and the secrets of nature.

### Ancient of War
The toughest of ancients grow into ancients of war; mighty plants often found defending night elven settle&shy;ments or supporting Alliance forces in battle. Embodied in these ancient guardians are the spirits of courage and determination, which they wield to call upon the forest itself to rise in order to turn the tide of battle in favour of them and their allies.

<div class='letterheader'></div>
<div class="mmletter mml-a"></div>
<div class="pageLetter">A</div>
<div class='footnote'>ANCIENTS </div>


<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='top:-210px; left:-310px; width:900px;'>
<img src='https://www.gmbinder.com/images/TfR3uTq.png' style='position:absolute; top:0px; right:300px; width:550px;transform:scalex(-1)' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Ancient of Lore
>*Huge plant, neutral good*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 94 (9d12 + 36)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|8 (-1)|19 (+4)|14 (+2)|21 (+5)|12 (+1)|
>___
> - **Saving Throws** Wis +8
> - **Skills** History +5, Nature +8
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** bludgeoning, piercing
> - **Senses** darkvision 120 ft., passive Perception 15
> - **Languages** Darnassian, Druidic
> - **Challenge** 8 (3,900 XP)
> ___
> ***False Appearance.*** While the ancient remains motion&shy;less, it is indistinguishable from a normal tree.
>
> ***Siege Monster.*** The ancient deals double damage to objects and structures.
>
> ***Speak with Nature.*** The ancient can communicate with beasts and plants as if they shared a language.
>
> ***Spellcasting.*** The ancient is a 11th-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 16, +8 to hit with spell attacks). It requires no material components to cast its spells. The ancient has the following druid spells prepared:
>
> Cantrips (at will): *dancing lights, druidcraft, ✦ solar <br>&nbsp;&nbsp;&nbsp; wrath, thorn whip*
> <br> 1st level (4 slots): *detect magic, detect poison and <br>&nbsp;&nbsp;&nbsp; disease, faerie fire, ✦ starfire*
> <br> 2nd level (3 slots): *locate animals and plants, <br>&nbsp;&nbsp;&nbsp; moonbeam, skywrite*
> <br> 3rd level (3 slots): *dispel magic, plant growth, <br>&nbsp;&nbsp;&nbsp; protection from energy, ✦ starsurge*
> <br> 4th level (3 slots): *confusion, locate creature*
> <br> 5th level (2 slots): *dream, wrath of nature*
> <br> 6th level (1 slot): *✦ starfall, wall of thorns*
>
> ### Actions
> ***Multiattack.*** The ancient makes two slam attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 13 (3d6 + 3) bludgeoning damage.
>
> ***Rock*** *Ranged Weapon Attack:* +6 to hit, range 60/180 ft., one target. *Hit:* 25 (5d8 + 3) bludgeoning damage.
>
> ***Take Root.*** The ancient buries its roots in the ground. While rooted, the ancient's speed becomes 0, it gains advantage on its attack rolls, and is immune to any effect that would force the ancient to move or be moved. The ancient can end this effect by repeating this action to uproot itself.<!-- https://wc5e-cr-calculator.frogvall.com/?1;14;94;0;16;84;0;70;0;70;0;0;0;0;0;0;0;1;;;1;1;;;;;;;;;;1;;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">A</div>
<div class='footnote'>ANCIENTS </div>
<img src='https://www.gmbinder.com/images/W7JrNLv.jpg' style='position:absolute; top:0px; right:-170px; width:1300px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:90px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:64px;'>

> ##### Variant: Tree of Life
> A tree of life is a sapling born from the world tree Nordrassil, these ancients have suffered great losses in recent wars, and those who remain have returned to the forest to spread their seeds and replenish their numbers undisturbed.
>
> A tree of life has a challenge rating of 10 (5,900 XP). It has the same statistics as an ancient of lore, and gains the following additional traits:
> <div style='margin-top:0px;'></div>
>
> &nbsp;&nbsp;&nbsp; ***Nature's Blessing.*** The tree add its Wisdom <br>&nbsp;&nbsp;&nbsp; modifier to its Armor Class (AC 19).
> <div style='margin-top:0px;'></div>
>
> &nbsp;&nbsp;&nbsp; ***Rooted Tranquility.*** While the tree have taken root, <br>&nbsp;&nbsp;&nbsp; each plant of the tree's choice within 60 feet of it <br>&nbsp;&nbsp;&nbsp; regains 20 hit points at the start of its turn. If the <br>&nbsp;&nbsp;&nbsp; plant takes fire damage, this trait doesn't function <br>&nbsp;&nbsp;&nbsp; at the start of the plant's next turn. A plant dies if <br>&nbsp;&nbsp;&nbsp; it starts its turn with 0 hit points.
> <div style='margin-top:0px;'></div>
>
> &nbsp;&nbsp;&nbsp; ***Spellcasting.*** The tree has the following additional <br>&nbsp;&nbsp;&nbsp; spells prepared.
>
> <br>&nbsp;&nbsp;&nbsp; 4th level: *guardian of nature, grasping vine*
> <br>&nbsp;&nbsp;&nbsp; 5th level: *commune with nature*
> <br>&nbsp;&nbsp;&nbsp; 6th level: *druid grove, sunbeam*
> <div style='margin-top:0px;'></div>
>
> The tree has the following additional action option.
> <div style='margin-top:0px;'></div>
>
> &nbsp;&nbsp;&nbsp; ***Summon Wisps (1/Day).*** The tree calls forth ten <br>&nbsp;&nbsp;&nbsp; wisps that appear in empty spaces within 60 feet <br>&nbsp;&nbsp;&nbsp; of it. These wisps act as allies of the tree. The <br>&nbsp;&nbsp;&nbsp; wisps remains for 1 day or until they die.<!-- https://wc5e-cr-calculator.frogvall.com/?1;19;94;8;16;84;0;70;0;70;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

</div>

<div class='statblock-bottom-wide'>

___
___
> ## Ancient of War
>*Huge plant, neutral good*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 138 (12d12 + 60)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|23 (+6)|8 (-1)|21 (+5)|12 (+1)|16 (+3)|12 (+1)|
>___
> - **Skills** Athletics +10, Nature +7, Perception +7
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** bludgeoning, piercing
> - **Condition Immunities** charmed, frightened
> - **Senses** darkvision 120 ft., passive Perception 17
> - **Languages** Darnassian, Druidic
> - **Challenge** 9 (5,000 XP)
> ___
> ***False Appearance.*** While the ancient remains motion&shy;less, it is indistinguishable from a normal tree.
>
> ***Resilient Nature.*** Unless the ancient of war is incapa&shy;citated, it and plant creatures of its choice within 60 feet of it have advantage on saving throws against being charmed or frightened.
>
> ***Siege Monster.*** The ancient deals double damage to objects and structures.
>
> ### Actions
> ***Multiattack.*** The ancient makes two slam attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +10 to hit, reach 5 ft., one target. *Hit:* 23 (5d6 + 6) bludgeoning damage.
>
> ***Rock.*** *Ranged Weapon Attack:* +10 to hit, range 60/180 ft., one target. *Hit:* 42 (8d8 + 6) bludgeoning.
>
> ***Take Root.*** The ancient buries its roots in the ground. While rooted, the ancient's speed becomes 0, it gains advantage on its attack rolls, and is immune to any effect that would force the ancient to move or be moved. The ancient can end this effect by repeating this action to uproot itself.
>
> ***Animate Trees (1/Day).*** The ancient magically animates five or fewer trees that it can see within 60 feet of it. The trees have the statistics of a treant, except they have Intelligence and Charisma scores of 1 and they only have the Claw action. An animated tree acts as an ally of the ancient. The tree remains animated for 1 day, until it dies, or until the ancient takes a bonus action to turn it back into an inanimate tree. If the tree doesn't die and is made inanimate, it takes root again if it can.<!-- https://wc5e-cr-calculator.frogvall.com/?1;16;138;10;12;46;0;46;0;46;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">A</div>
<div class='footnote'>ANCIENTS </div>
<img src="https://www.gmbinder.com/images/m6qCwvJ.png" class="inkblot" style="top:-190px; right:-250px; width:800px; transform:rotate(14deg);">
<img src="https://www.gmbinder.com/images/8eBnSv5.png" style="position:absolute;top: -70px;right: -93px;width: 580px;transform: scalex(-1);">

\pagebreakNum

<div style='margin-top:370px;'></div>

___
> ## Basilisk
>*Medium monstrosity, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 52 (8d8 + 16)
> - **Speed** 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|8 (-1)|15 (+2)|2 (-4)|8 (-1)|7 (-2)|
>___
> - **Senses** Darkvision 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 3 (700 XP)
>___
>  **Petrifying Gaze.**  If a creature starts its turn within 30 feet of the basilisk and the two of them can see each other, the basilisk can force the creature to make a DC 12 Constitution saving throw if the basilisk isn't incapacitated. On a failed save, the creature magically begins to turn to stone and is restrained. It must repeat the saving throw at the end of its next turn. On a success, the effect ends. On a failure, the creature is petrified until freed by the greater restoration spell or other magic.
> <br>&nbsp;&nbsp;&nbsp; A creature that isn't surprised can avert its eyes to avoid the saving throw at the start of its turn. If it does so, it can't see the basilisk until the start of its next turn, when it can avert its eyes again.  If it looks at the basilisk in the meantime, it must immediately make the save.
> <br>&nbsp;&nbsp;&nbsp; If the basilisk sees its reflection within 30 feet of it in bright light, it mistakes itself for a rival and targets itself with its gaze.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit* 10 (2d6 +3) piercing damage plus 7 (2d6) poison damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;15;52;5;12;17;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:430px;'></div>

## Basilisk
Sometimes, travelers find carved
<br> stone statues of people or wildlife that
<br> look remarkably lifelike. Sometimes these statues are whole. Other times, the parts that are missing appear to have been bitten off. Seasoned explorers regard such relics as a warning, know&shy;ing that the basilisk responsible is likely to still be close by.

***Territorial Creatures.*** Although basilisks are powerful creatures, and fierce combatants, they rarely exhibit a deliberately cruel or violent intent. Basilisks live as solitary predators, sometimes in small colonies, and keep a watch&shy;ful eye on the borders of their territory. From their domain, they prefer to hunt those who choose to trespass, leaving behind petrified chunks of whatever remains.

***Gaze of Stone.*** As far as predators go, basilisks are often slow and ponderous creatures, as they rarely need to chase their prey. Meeting a basilisk's supernatural gaze can be enough to rapidly transform their prey into stone -- which the basilisk then breaks apart with its strong jaws, perfectly capable of tearing down the stone for nutrition.

***A Fondness for Crystals.*** Though many scholars have examined the basilisk's inherent attraction to crystals, there is no agreement as to why the lumbering beasts exhibit such fondness for them.

They exhibit great fondness for crystalline structures and are capable of sensing them from a great distance, which they will gladly traverse -- in groups or by their lonesome -- to retrieve their coveted prize. Basilisks have such an insatiable hunger for such crystals, it is not uncommon to find colonies that have begun to sprout crystal formations across their rocky hides, as a side-effect of their gluttonous diet.

In Stranglethorn Vale, especially, some colonies have taken to forming their nests from these same crystals, making for an attractive gamble for any adventurers daring enough to come face to face with the terrifying beasts.

<div class='letterheader'></div>
<div class="mmletter mml-b"></div>
<div class="pageLetter">B</div>
<div class='footnote'>BASILISK </div>

<img src="https://www.gmbinder.com/images/KcRAZwq.png" class="inkblot" style="top: -80px;right: 175px;width: 540px;transform: rotate(78deg);">
<img src='https://www.gmbinder.com/images/wqJdnmf.png' style='position:absolute; top:-70px; right:70px; width:700px' />

\pagebreakNum

## Bog Beasts
A bog beast is a massive, shambling monster made of plants, roots, and flesh. Inhabiting bogs and swamps, they hide away beneath the water surface, disguising them&shy;selves as thick, waterlogged lumps of vegetation. There they wait patiently for any unaware critters to venture too close -- or better yet, unaware adventurers.

***Creatures of Mystery.*** Bog beasts are frightful crea&shy;tures, and notoriously elusive. They are adept at avoiding the gaze of scholars attempting to study them; and for many who have tried, only moss-riddled remains have been found. Their aggressive, territorial nature makes them a considerable danger to any unfortunate enough to cross paths with them.

***Plants Anatomy.*** Thick roots stretch across the entirety of the bog beast's form, as if to conceal what hides under&shy;neath. It is speculated that they have no real need for sustenance apart from the waters they dwell in, and some have been observed spending months still in the murky depths -- only barely grasping the surface to draw breath.

***Naturally Powerful.*** Explorers who have encountered a bog beast and lived to tell the tale, describe them as immen&shy;sely powerful and resilient to harm. Their massive limbs can quickly overwhelm their enemies, crushing opponents with their fists or with whatever nearby objects they can throw.

### Timberling
A timberling is by many considered the child of bog beasts, very similar and yet considerably smaller at a height comparable to that of a dwarf. As far as bog beasts go, timberlings are fairly peaceful creatures that live in harmony with the land. However, any disruption to their habitat will quickly drive them into an unnatural frenzy.

### Thistleshrub
Thistleshrubs, unlike most bog beasts, do not dwell in swamps or marshes. Instead they prefer arid climates, and bear a resemblance to a large mass of withered vines cov&shy;ered in sharp briars. They are known to be very hostile, and will certainly attack anyone foolish enough to approach; sporadically lashing out with whip-like thorns at anything that comes near.

### Swampwalker
These hulking masses are rarely ever witnessed outside of dense swamps, and blend perfectly into their chosen habitat with their dark green and brown colors.

They are both the most territorial and the most cunning among bog beasts, and have been witnessed deliberately attempting to lure travellers farther into their lair in order to spring a trap. Their natural camouflage allows them to move through their territory entirely unseen, and have left adventurers wary even of rippling water and rustling leaves when venturing through swamps.

### Tar Creeper
Cherishing humid air and temperatures, the tar creeper is by far the most abnormal of all bog beasts for its viscous, tar-like appearance. Not to mention the most dangerous.

Though they might seem slow, these massive beasts can cut through tar like a fish through water; lunging forth to trap their prey and drag it back down below.

<div class="pageLetter">B</div>
<div class='footnote'>BOG BEASTS </div>
<img src='https://www.gmbinder.com/images/mwRXhNd.jpg' style='position:absolute; top:0px; right:-125px; width:700px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-15px; width:900px' />

\pagebreakNum

<div style='margin-top:408px;'></div>

___
> ## Timberling
>*Medium plant, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 26 (4d8 + 8)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|12 (+1)|14 (+2)|4 (-3)|10 (+0)|7 (-2)|
>___
> - **Skills** Perception +2, Stealth +3
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** lightning; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** -
> - **Challenge** 1 (200 XP)
> ___
>
> ***Hold Breath.*** The timberling can hold its breath for 30 minutes.
>
> ***Swamp Camouflage.*** The timberling has advantage on Dexterity (Stealth) checks made to hide in swampy terrain.
>
> ***Swamp Mobility.*** The timberling ignores difficult terrain created by swamps, and can see through nonmagical mists of swamplands.
>
> ### Actions
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 9 (2d6 + 2) slashing damage. If the target is Medium or smaller, it is either grappled (escape DC 12) or pushed up to 10 feet away. Until the grapple ends, the target is restrained.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;26;4;12;9;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:222px;'></div>

___
> ## Thistleshrub
>*Large plant, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 68 (8d10 + 24)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|12 (+1)|16 (+3)|4 (-3)|10 (+0)|7 (-2)|
>___
> - **Skills** Perception +3, Stealth +4
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** lightning; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 4 (1,100 XP)
> ___
>
> ***False Appearance.*** While the thistleshrub remains motionless, it is indistinguishable from a shrub covered in thorns.
>
> ***Water Awareness.*** The thistleshrub can sense the pre&shy;sence of water reservoirs up to 5 miles away, as well as water within a creature's body. It knows the general direction they're in but no their exact location.
>
> ### Actions
> ***Multiattack.*** The thistleshrub makes two claw attacks.
>
> ***Thorny Claw.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 12 (2d8 + 3) piercing damage. If the target is Large or smaller, it is either grappled (escape DC 14) or pushed up to 10 feet away. Until the grapple ends, the target is restrained, and the thistle&shy;shrub can only make one claw attack.
>
> ***Entangling Roots (Recharge 5-6).*** Grasping thorny roots and vines sprout in a 15-foot radius centered on the thistleshrub, withering away after 1 minute. For the duration, that area is difficult terrain for non-plant creatures. In addition, each creature of the thistleshrub's choice in that area when the plants appear must succeed on a DC 14 Strength saving throw or become restrained. While restrained in this way, the target takes 9 (2d8) piercing damage at the start of their turn. A creature can use its action to make a DC 14 Strength check, freeing itself or another entangled creature within reach on a success.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;68;6;12;24;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">B</div>
<div class='footnote'>BOG BEASTS </div>

<img src="https://www.gmbinder.com/images/OkSEy3f.png" class="inkblot" style="top: -170px;left: -85px;width: 700px;transform: rotate(248deg);">
<img src='https://www.gmbinder.com/images/JKyUFKT.png' style='position:absolute; top:10px; right:220px; width:700px' />

\pagebreakNum

___
> ## Swampwalker
>*Large plant, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 93 (11d10 + 33)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|14 (+2)|16 (+3)|4 (-3)|10 (+0)|7 (-2)|
>___
> - **Skills** Perception +3, Stealth +5
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** lightning; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 5 (1,800 XP)
> ___
> ***Hold Breath.*** The swampwalker can hold its breath for 30 minutes.
>
> ***Regeneration.*** The swampwalker regains 5 hit points at the start of its turn. If the swampwalker takes acid or fire damage, this trait doesn't function at the start of the swampwalker's next turn. The swampwalker dies if it starts its turn with 0 hit points.
>
> ***Swamp Camouflage.*** The swampwalker has advantage on Dexterity (Stealth) checks made to hide in swampy terrain.
>
> ***Swamp Mobility.*** The swampwalker ignores difficult terrain created by swamps, and can see through nonmagical mists of swamplands.
>
> ### Actions
> ***Multiattack.*** The swampwalker makes two claw attacks.
>
> ***Claw.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., <br>one target. *Hit:* 13 (2d8 + 4) slashing damage. If the target is Large or smaller, it is either grappled (escape DC 13) or pushed up to 10 feet away. Until the grapple ends, the target is restrained, and the swamp&shy;walker can only make one claw attack.<!-- https://wc5e-cr-calculator.frogvall.com/?1;15;93;7;12;26;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;1;5;;;;;; -->

\columnbreak

___
> ## Tar Creeper
>*Large elemental, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 123 (13d10 + 52)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|20 (+5)|15 (+2)|18 (+4)|4 (-3)|10 (+0)|7 (-2)|
>___
> - **Skills** Perception +3, Stealth +5
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** lightning; bludgeoning, piercing and slashing from nonmagical attacks
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 8 (3,900 XP)
> ___
> ***Hold Breath.*** The tar creeper can hold its breath for 30 minutes.
>
> ***Tar Stench.*** Any creature other than a tar creeper that starts its turn within 5 feet of the tar creeper must succeed on a DC 14 Constitution saving throw or be poisoned until the start of the creature's next turn. On a successful saving throw, the creature is immune to the stench of all tar creepers for 1 hour.
>
> ***Swamp Camouflage.*** The tar creeper has advantage on Dexterity (Stealth) checks made to hide in swampy terrain.
>
> ***Swamp Mobility.*** The tar creeper ignores difficult terrain created by swamps, and can see through nonmagical mists of swamplands.
>
> ***Charge.*** If the tar creeper moves at least 10 feet straight toward a target and then hits it with a claw attack on the same turn, the target takes an additional 14 (3d8) bludgeoning damage. If the target is a creature, it must succeed on a DC 16 Strength saving throw or be pushed up to 10 feet away and knocked prone.
>
> ### Actions
> ***Multiattack.*** The tar creeper makes two attacks with its poison claws.
>
> ***Poison Claw.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 14 (2d8 + 5) slashing damage plus 7 (2d6) poison damage.
>
> ***Tar Spray (1/Day).*** The tar creeper sprays sticky tar in a 15-foot cone. Each creature in that area must make a DC 14 Dexterity saving throw. On a failed saving throw a creature's speed is halved, it takes a -2 penalty to AC and Dexterity saving throws, and it can't use reactions.
> <br>&nbsp;&nbsp;&nbsp; A creature can remove the tar on itself during a short or long rest by bathing in water, alcohol, or vinegar.<!-- https://wc5e-cr-calculator.frogvall.com/?1;15;123;7;12;42;14;42;0;42;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;1;;;;;5;;;;;; -->

<div class="pageLetter">B</div>
<div class='footnote'>BOG BEASTS </div>
<img src='https://www.gmbinder.com/images/cjYRUeP.jpg' style='position:absolute; top:500px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/hIpYyKx.png' style='position:absolute; top:-50px; right:0px; width:900px' />

\pagebreakNum

---

\columnbreak

<div style='margin-top:140px;'></div>

## Centaurs
Abundant across the plains of central and southern Kalimdor, the centaur are a race of half-horse humanoids, appearing as a human's torso, arms, and head extending from the neck of an equine body. Full-grown centaurs stand over seven feet tall, hooves to head, and weigh over a ton.

***Nomadic Culture.*** They keep in small nomadic tribes, roaming the broad regions they consider their territory, with regular spots by which they settle their tents to hunt and forage. Each tribe is lorded by its khan, who'll more often than not keep open conflict with both neighboring tribes and races alike.

While on their warpath, travelling from place to place, centaurs often claim prisoners during their raids. Usually, these prisoners are tortured, driven to exhaustion, and eventually eaten.

***Cycle of Conflict.*** Though many attempts have been made, either between tribes or at the behest of tauren settlements in a tribe's warpath, the centaur have never been ones for diplomacy.

Both the Horde and the Alliance have done their part to feed this inter-tribal conflict, seeing it as a necessary act to keep scattered clans, especially in regions such as the Barrens or Desolace, from banding together and becoming a more dangerous foe.

### Centaur Earthcaller
Though centaurs follow a shamanistic faith, their rites and rituals are unique; given their heritage as children of the elemental princess Theradras. Earth Callers are commonly female centaurs, acting as shamans of their tribes as they wield the power to rain elemental earth upon their foes.

### Centaur Khan
At the heart of each centaur tribe is the khan, who acts as a leader both for their great intelligence and their unmatched ferocity. Rage and savagery are key to the centaur khans, allowing them to lead their tribe into battle as a fearless commander without equal.

### Centaur Names and Languages
The centaur speak Low Common, and often learn phrases from the languages of their enemies; including Common, Orcish, Goblin, and Taur-ahe. A few centaurs  even go as far as to learn the entirety of these languages, with fewer still adopting this second language as their primary language.

Their names are short and sharp, while tribes draw their name from the first khan to lead them -- such as khan Gelk of the Gelkis. The ending of a tribe's name sits at the whim of its first khan, it is speculated that they draw these from other languages spoken by the tribe's founding members.

<div style='margin-top:-5px;'></div>

**Centaur Names:** Ablik, Arug, Blizh, Drothar, Feth,
<br />&nbsp;&nbsp;&nbsp; Jamrek, Kerrak, Kromzar, Magra, Sherik, Shodo, Warug
<br />**Tribe Names:** Galak, Jhenek, Kolkar, Krenek, Okrim,
<br />&nbsp;&nbsp;&nbsp; Wethek, Worrak

<div class='letterheader'></div>
<div class="mmletter mml-c"></div>
<div class="pageLetter">C</div>
<div class='footnote'>CENTAURS </div>
<img src='https://www.gmbinder.com/images/bGAMsIn.jpg' style='position:absolute; top:0px; right:250px; width:820px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-80px; width:900px; transform:scalex(-1)' />

\pagebreakNum

<div style='margin-top:48px;'></div>

> ##### The Children of Zaetar
> The centaur are the progeny of Zaetar, a Keeper of the Grove and son of Cenarius; Lord of the forest and Demigod of the Groves. Though Zaetar was no lesser than his brother, Remulos, he often felt himself living in the shadow of his brother's presence and accomplishments.
>
> When Cenarius sent his son Zaetar out to investigate the re-emergence of the elemental princess Theradras, daughter of Therazane the Stonemother, Zaetar saw himself enchanted by Theradras' beauty.
>
> The two became mates, in secrecy, and out of their forbidden union the centaur were born. Zaetar realized his deed upon seeing the centaurs, who in turn saw the disgust in their father's eyes and brutally murdered him. Therazane chastised them for the deed, for which the centaurs promised to honor Zaetar's memory to please their beloved mother.
>
> Theradras entombed her lover's spirit within her own lair, which the centaur gave the name Maraudon and grew to be regarded as a sacred place.

___
> ## Centaur
>*Large humanoid (centaur), chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 45 (6d10 + 12)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|14 (+2)|14 (+2)|9 (-1)|13 (+1)|11 (+0)|
>___
> - **Skills** Athletics +6, Perception +3, Survival +3
> - **Senses** passive Perception 13
> - **Languages** Common
> - **Challenge** 2 (450 XP)
> ___
> ***Charge.*** If the centaur moves at least 30 feet straight toward a target and then hits it with a pike attack on the same turn, the target takes an extra 10 (3d6) piercing damage.
>
> ### Actions
> ***Multiattack.*** The centaur makes two attacks: one with its hooves and one with another melee weapon, or two with its longbow.
>
> ***Greataxe.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 10 (1d12 + 4) slashing damage.
>
> ***Pike.*** *Melee Weapon Attack:* +6 to hit, reach 10 ft., one target. *Hit:* 9 (1d10 + 4) piercing damage.
>
> ***Hooves.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 11 (2d6 + 4) bludgeoning damage.
>
> ***Longbow.*** *Ranged Weapon Attack:* +4 to hit, range 150/600 ft., one target. *Hit:* 6 (1d8 + 2) piercing.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;45;6;12;20;10;21;0;21;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:259px;'></div>

___
> ## Centaur Earthcaller
>*Large humanoid (centaur), chaotic evil*
> ___
> - **Armor Class** 13 (leather)
> - **Hit Points** 52 (7d10 + 14)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|14 (+2)|14 (+2)|11 (+0)|17 (+3)|11 (+0)|
>___
> - **Skills** Athletics +5, Perception +6, Survival +6
> - **Senses** passive Perception 16
> - **Languages** Common
> - **Challenge** 4 (1,100 XP)
> ___
> ***Charge.*** If the centaur moves at least 30 feet straight toward a target and then hits it with a pike attack on the same turn, the target takes an extra 10 (3d6) piercing damage.
>
> ***Spellcasting.*** The centaur is a 5th-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 13, +5 to hit with spell attacks). It has the following shaman spells prepared:
>
> Cantrips (at will): *✦ lightning blast, mending, mold earth*
> <br> 1st level (4 slots): *detect magic, earth tremor, fog <br>&nbsp;&nbsp;&nbsp; cloud, thunderwave*
> <br> 2nd level (3 slots): *✦ lava burst, maximilian's <br>&nbsp;&nbsp;&nbsp; earthen grasp*
> <br> 3rd level (2 slots): *call lightning, ✦ chain heal, ✦ earthen spike*
>
> ### Actions
> ***Multiattack.*** The centaur makes two attacks: one with its hooves and one with another melee weapon.
>
> ***Pike.*** *Melee Weapon Attack:* +5 to hit, reach 10 ft., one target. *Hit:* 8 (1d10 + 3) piercing damage.
>
> ***Hooves.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) bludgeoning damage.
>
> ### Reactions
> ***Earthen Shield (3/Day).*** When a creature makes an attack against another creature within 15 feet of the centaur, the centaur can give all attacks against that creature disadvantage until the start of its next turn.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;52;5;13;54;0;54;0;26;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">C</div>
<div class='footnote'>CENTAURS </div>

<img src="https://www.gmbinder.com/images/64Wsryy.png" class="inkblot" style=" top:0px; right:-130px; width:640px; transform:rotate(-47deg);">
<img src='https://www.gmbinder.com/images/3myZ2DH.png' style='position:absolute; top:-20px; right:-70px; width:500px;' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Centaur Khan
>*Large humanoid (centaur), chaotic evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 105 (11d10 + 44)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|20 (+5)|14 (+2)|18 (+4)|11 (+0)|14 (+2)|11 (+0)|
>___
> - **Skills** Athletics +8, Perception +5, Survival +5
> - **Senses** passive Perception 15
> - **Languages** Common
> - **Challenge** 6 (2,300 XP)
> ___
> ***Brave.*** The centaur has advantage on saving throws against being frightened.
>
> ***Brute.*** A melee weapon deals one extra damage die when the centaur hits with it (included in the attack).
>
> ***Charge.*** If the centaur moves at least 30 feet straight toward a target and then hits it with a greataxe attack on the same turn, the target takes an extra 10 (3d6) piercing damage.
>
> ***Relentless (Recharges after a Short or Long Rest).*** If the centaur takes 25 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ### Actions
> ***Multiattack.*** The centaur makes three attacks: two with its greataxe and one with its hooves.
>
> ***Greataxe.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 18 (2d12 + 5) slashing damage.
>
> ***Hooves.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 15 (3d6 + 5) bludgeoning damage.
>
> ***War Cry (1/Day).*** Each creature of the centaurs choice within 30 feet of it that can hear it gains advantage on attack rolls until the start of the centaurs next turn. The centaur then makes a melee weapon attack as a bonus action.<!-- https://wc5e-cr-calculator.frogvall.com/?1;15;105;8;12;51;10;51;0;51;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;1;;;;;-->

</div>

<div class="pageLetter">C</div>
<div class='footnote'>CENTAURS </div>
<img src='https://www.gmbinder.com/images/jPRzhev.jpg' style='position:absolute; top:0px; right:-180px; width:1500px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/pZatMx5.png' style='position:absolute; top:350px; right:0px; width:900px;' />

\pagebreakNum

<div style='margin-top:480px;'></div>

___
> ## Dark Iron Hound
>*Medium elemental, neutral evil*
> ___
> - **Armor Class** 14
> - **Hit Points** 30 (4d8 + 12)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|10 (+0)|17 (+3)|6 (-2)|11 (+0)|5 (-3)|
>___
> - **Damage Immunities** fire
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** understands Kalimag, and Dwarven but can't speak
> - **Challenge** 2 (450 XP)
> ___
> ***Charge.*** If the hound moves at least 20 feet straight toward a target and then hits it with a bite attack on the same turn, the target takes an extra 7 (2d6) piercing damage. If the target is a creature, it must succeed on a Dc 13 Strength saving throw or be knocked prone.
>
> ***Illumination.*** The hound sheds bright light in a 10-foot radius and dim light in an additional 10 feet.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:*  7 (1d8 + 3) piercing damage plus 7 (2d6) fire damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;30;5;12;14;7;14;0;14;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:355px;'></div>

## Core Hounds
Most who venture to Blackrock Mountain would rather face a squad of orcs than confront a single core hound. These hulking bulldogs drip of magma as they trail, guard&shy;ing the molten core of the black mountain -- as well as the scorched earth of the lands around.

A core hound's body is covered in thick, sweltering metal plates, with streaks of fire running the length of its back. Its mouth is filled with rows of sharp teeth, said to be hotter than white-hot steel.

***Faithful Servants.*** Core hounds are the faithful servants of the Firelord and his minions, and in many ways do act like loyal dogs in that regard, following the will of their fiery master as best they can.

***Endless Growth.*** If allowed, a core hound can grow for an eternity, ultimately becoming hulking titans of gargan&shy;tuan size -- like their progenitor, Magmadar. Few core hounds ever manage to reach such a size, as often their aggressive nature becomes their downfall.

The dark iron hounds, considered misshapen by true core hounds, cease to grow once they reach maturity.

### Core Hound
The core hound is a monstrous, vicious, two-headed bulldog with a faithful bond to the Firelord Ragnaros and his minions. Waves of scorching heat emanate from the core hound's body, and those who engage it with head-on quickly find their weapons rendered useless as each slash and stab melts it all away.

They are are ferocious, unforgivable beings. Hostility toward intruders is always a given, as they are impossible to reason with. They take orders solely from the Firelord's rank and file, or from the Firelord himself.

### Dark Iron Hound
A dark iron hounds is smaller, one headed, core hound. They are often seen accompanying the dark iron dwarves who dwell within Blackrock Mountain.

These hounds are often used as mounts by the dark iron dwarves that keep them, though they do not take well to others.

<div class="pageLetter">C</div>
<div class='footnote'>CORE HOUNDS </div>
<img src='https://www.gmbinder.com/images/bST4TE9.jpg' style='position:absolute; top:-20px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:-30px; right:0px; width:900px;transform:scaley(-1)' />
<img src="https://www.gmbinder.com/images/6jRvJuJ.png" style="position:absolute;top: 139px;right: 320px;width: 500px;transform: rotate(-6deg);z-index: 100;">

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Core Hound
>*Large elemental, chaotic evil*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 126 (12d10 + 60)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|21 (+5)|9 (-1)|20 (+5)|8 (-1)|10 (+0)|6 (-2)|
>___
> - **Skills** Athletics +8
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** fire
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** understands Kalimag but can't speak
> - **Challenge** 7 (2,900 XP)
> ___
> ***Illumination.*** The core hound sheds bright light in a 15-foot radius and dim light in an additional 15 feet.
>
> ***Molten Core.*** A creature that touches the core hound or hits it with a melee attack while within 5 feet of it takes 4 (1d8) fire damage. In addition, any non&shy;magical weapon that hits the core hound melts. After dealing damage, the weapon takes a permanent and cumulative -1 penalty to damage rolls. If its penalty drops to -5, the weapon is destroyed. Nonmagical ammunition that hits the core hound is destroyed after dealing damage.
>
> ***Two Heads.*** The core hound has advantage on Wisdom (Perception) checks and on saving throws against being blinded, charmed, deafened, frightened, stunned, and knocked unconscious.
>
> ***Wakeful.*** When one of the core hounds heads is asleep, its other head is awake.
>
> ### Actions
> ***Multiattack.*** The core hound makes two bite attacks.
>
> ***Bite.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 10 (1d10 + 5) piercing damage plus 18 (4d8) fire damage.
>
> ***Molten Breath (Recharge 4-6).*** The core hound exhales searing flames in a 15-foot cone. Each creature in that area must make a DC 16 Dexterity saving throw, taking 11 (2d10) fire damage on a failed save, or half as much damage on a successful one. A creature failing the save who wears nonmagical armor or a shield take a permanent and cumulative -1 penalty to the AC it offers. Armor reduced to an AC of 10 or a shield that drops to a +0 bonus is destroyed.<!-- https://wc5e-cr-calculator.frogvall.com/?1;16;126;8;16;56;4;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">C</div>
<div class='footnote'>CORE HOUNDS </div>
<img src='https://www.gmbinder.com/images/KbFQk4a.png' style='position:absolute; top:-100px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/TYBvp5o.png' style='position:absolute; top:150px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:130px;'></div>

# Dinosaurs
Dinosaurs are among the oldest reptiles in the world, ancient in every sense of the word. Their presence can inspire both awe and dread into any adventurer fortunate -- or unfortunate -- enough to cross their path. They roam far and wide across Azeroth; all the way from remote mountain valleys, to humid jungles, and to rugged barren plains. 

***Feared and Revered.*** Some of Azeroth's denizens, trolls in particular, revere dinosaurs. Several of the primal Loa take the appearance of a dinosaur, such as the devilsaur Loa Rezan and the direhorn Loa Torcali. 

For the Zandalar tribe, it is a rite of passage to venture away from home, into the wilds, in order to steal or subdue a beast. Any beast would do for such trials, but a wild dinosaur is a prized claim.

***Giants Among Beasts.*** Dinosaurs come in many sizes and shapes, some absolutely tremendous, featuring a wide variety of markings and colorations. They primarily split into two groups: savage, territorial predators, and docile yet still undeniably dangerous herbivores.

### Ankylodon
The ankylodon is a broad, low-slung dinosaur, native to Zandalar. It is kept up by its powerful limbs, and almost every part of its body, save for the belly, is decked with hardened plates. Long spikes protrude from these plates; <br>a characteristic appearance that has flocks of ankylodons sometimes referred to as "thornhides". It is a herbivore, preferring to graze on ferns and low shrubs, shearing them off with its beak-like upper jaw.

### Brutosaur
Brutosaurs are enormous, even among dinosaurs. They have small heads and incredibly long necks, relative to the rest of their body, and move along at a lumbering pace with their pillar-like legs. Despite their imposing stature, bruto&shy;saurs are known to be very docile unless threatened. They are omnivores, yet most appear to have an exclusively herb&shy;ivorous diet, rarely ever hunting meat of their own volition.

### Devilsaur
This giant lizard stands tall on its two powerful hind legs, with two stunted forelimbs stretched out before it. The devilsaur takes its name from its utterly savage attacks, as it tackles its prey down with immense force before tearing it limb from limb. Despite its ferocity, the devilsaur's massive size has many hunters seeking the beast out for its hide, which is both supple and extraordinarily tough. Devilsaurs may grow well above thirty feet, weighing in at almost sixteen tons. 

Female devilsaurs tend to be smaller and lighter, though they are even more aggressive than their male counterpart. During mating seasons, once the nest has been made and her eggs have been laid, she will leave it to the male who fathered the clutch to protect them until they hatch.

<div class='letterheader'></div>
<div class="mmletter mml-d"></div>
<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src='https://www.gmbinder.com/images/din7hXr.jpg' style='position:absolute; top:0px; right:-750px; width:2020px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-15px; width:900px' />

\pagebreakNum

### Diemetradon
The diemetradon—one of the strongest predators in the Un'Goro Crater—is recognized for the two enormous, jag&shy;ged crests protruding from its back. Its legs are squat and strong, for which it is far from the fastest dinosaur, though its body is decked in plate-like scales able to withstand tremendous force. When a diemetradon fights or hunts, it is known to simply lumber dead ahead against its target; rushing in to pin them down against a tree or in a swamp.

It is said that the diemetradon's howl is deafening, like a thundering boom capable of drowning out most other sounds around it.

### Direhorn
Direhorns are three-horned saurian titans known to popu&shy;late many islands throughout the South Seas. They are especially prominent on Zandalar, the Isle of Giants and the Isle of Thunder. They may seem like gentle giants at first, though they are among the toughest and strongest animals to walk on Azeroth. Even juvenile direhorns have been known to wreak utter havoc on unsuspecting victims. 

### Pterrordax
Tall as a horse and weighing up to 1,500 pounds, the pterrordax's keen senses guides it along as it soars through the air in search for fresh meat. Its claw-tipped wings are utterly tremendous, and its beak-like snout is lined with razor-sharp teeth. The pterrordax prefers to hunt alone, swooping down on unsuspecting prey from above to batter it to death with its wings before proceeding to tear flesh from bone. It is a solitary hunter, and adventurers' accounts of multiple have mainly been during mating season: a two-week period during early spring-time.

If their breeding grounds are threatened, otherwise lone pterrordax are quick to band together in large flights to fend off attackers. Afterwards, they disband just as quickly.

A pterrordax's pigmentation ranges from bright mossy greens to deep emerald hues, with brightly shining eyes. Closely related to the pterrordax is the even more terrifying pterrorwing—also known as Skyscreamer. It is massive in comparison, and stands out for the large sail on its snout.

### Raptor
The raptor is a large, aggressive dinosaur, known far and wide for its strength and immense speed. Out in the open, it is near impossible to outrun its leaping stride, and once it has caught up to its prey it pounces; driving its hooked talons in deep.

Even among dinosaurs, raptors are exceptionally intelli&shy;gent. Their packs act closer to colonies, with established hierarchies and and breeding grounds that could be mis&shy;taken for settlements when viewed from afar. They are very visually striking creatures, decked in scales and feathers ranging from bright blue and white, to striking red and orange, to deep black, purple, and green. 

### Sabertusk
Little is known about the enigmatic sabertusk, other than its nativity to Zandalar and occasional sightings on other, smaller islands nearby.  Though unwary adventurers have occasionally mistaken it for other land-dwelling reptiles, the sabertusk is visibly striking for the long and heavy tusks protruding from its maw. Its legs are long and its tail is narrow, with tall and coarse spikes running the length of its spine; all the way up to a prominent horn on its snout. 

\columnbreak

### Saurid
Saurid are small bipedal dinosaurs native to Zandalar, known for their nimble grace and venomous bite. The Zandalari trolls consider the saurid to be vermin, no better than rats, as they frequently steal food, poison waters, and prey on children and on the wounded.

However, when Zandalar renewed their alliance with the mogu at the Isle of Thunder, they brought the saurid with them to train. There, the tiny critters proved an immensely valuable weapon in the trolls' arsenal, let out loose in the wilds to hunt in the night.

### Stegodon
Stegodons are large herbivorous dinosaurs, whose massive bodies are heaved along on legs the size of tree trunks. They are notorious for their short temper and alarmingly aggressive turns, often attacking trespassers on sight as they patrol their territories. An enormous horn extends from the stegodon's snout, and spike-like plates run like a jagged fin across the length of its spine, over a back decked in hardened scales. Most stegodons have skin in dark shades of green, though some grow paler and grittier hues.

### Threshadon
The threshadon is a marine dinosaur, whose compact body is driven by a set of powerful flippers. Much like a bruto&shy;saur, its neck accounts for a third of its total length, and is able to flex and twist in whichever direction it needs to dig around muddy lake-beds and pull branches from riversides.

Though they are herbivores first and foremost, grazing threshadon herds are notorious for how fast they tear through and and all plant life within reach—before migrat&shy;ing on to new grounds. When a herd has found a grazing spot, the threshadons defend it aggressively. Any other creatures they encounter are attacked on sight. When it fights, the threshadon uses its long neck to lunge at its target, dealing devastating blows with rows of long, jagged teeth. Its jaws are strong enough to crush armor and snap bones, and it is not unusual for it to consume it kills whole.

___
> ## Ankylodon
> *Large beast, unaligned*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 52 (7d10 + 14)
> - **Speed** 30 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 19 (+4)|11 (+0)|15 (+2)|2 (-4)|12 (+1)|5 (-3)|
> ___
> - **Damage Resistances** poison; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Senses** passive Perception 11
> - **Languages** —
> - **Challenge** 4 (1,100 XP)
> ___
>
> ### Actions
> ***Claws.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 22 (4d8+4) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;16;52;6;12;22;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

\pagebreakNum

<div style='margin-top:530px;'></div>

___
> ## Brutosaur
> *Gargantuan beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 162 (12d20 + 36)
> - **Speed** 30 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 21 (+5)|9 (-1)|17 (+3)|2 (-4)|10 (+0)|7 (-2)|
> ___
> - **Saving Throws** Con +6
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 6 (2,300 XP)
> ___
>
> ### Actions
> ***Stomp.*** *Melee Weapon Attack:* +8 to hit, reach 20 ft., one target. *Hit:* 36 (7d8 + 5) bludgeoning damage, and the target must succeed on a DC 16 Strength saving throw or be knocked prone.
>
> ***Tail.*** *Melee Weapon Attack:* +8 to hit, reach 20 ft., one target. *Hit:* 32 (6d8 + 5) bludgeoning damage. If the target is a creature, it must succeed on a DC 15 Strength saving throw or be pushed up to 30 feet away from the brutosaur and knocked prone.<!-- https://wc5e-cr-calculator.frogvall.com/?1;12;162;8;12;36;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:249px;'></div>

___
> ## Devilsaur
> *Huge beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 136 (13d12 + 52)
> - **Speed** 50 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 25 (+7)|10 (+0)|19 (+4)|2 (-4)|12 (+1)|9 (-1)|
> ___
> - **Skills** Perception +4
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 8 (3,900 XP)
> ___
>
> ### Actions
> ***Multiattack.*** The devilsaur makes two attacks: one with its bite and one with its tail. It can't make both attacks against the same target.
>
> ***Bite.*** *Melee Weapon Attack:* +10 to hit, reach 10ft., one target. *Hit:* 39 (5d12 + 7) piercing damage. If the target is a Medium or smaller creature, it is grappled (escape DC 17) . Until this grapple ends, the target is restrained, and the devilsaur can't bite another target.
>
> ***Tail.*** *Melee Weapon Attack:* +10 to hit, reach 10ft., one target. *Hit:* 25 (4d8 + 7) bludgeoning damage. If the target is a creature, it must succeed on a DC 17 Strength saving throw or be pushed up to 10 feet away from the devilsaur and knocked prone.
>
> ***Maim.*** One creature grappled by the devilsaur's bite takes 59 (8d12 + 7) piercing damage. If this reduces the creature to 0 hp, the devilsaur swallows it and the grapple ends. While swallowed, the creature is blinded and restrained, it has total cover against attacks and other effects outside the devilsaur, and it takes 10 (3d6) acid damage at the start of each of the devilsaur's turns.
> If the Devilsaur takes 20 damage or more on a single turn from creatures inside it, it must succeed on a DC 15 Constitution saving throw at the end of that turn or regurgitate all swallowed creatures, which fall prone in a space within 10 feet of it. If the devilsaur dies, a swallowed creature is no longer restrained by him and can escape from the corpse using 15 feet of movement, exiting prone. 
>
><!-- https://wc5e-cr-calculator.frogvall.com/?1;13;136;10;12;39;25;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;;-->

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src="https://www.gmbinder.com/images/tiU4RnD.png" class="inkblot" style="top:-100px; right:0px; width:800px; transform:rotate(90deg)">
<img src='https://www.gmbinder.com/images/DOHKZPb.png' style='position:absolute; top:0px; right:0px; width:1200px' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Devilsaur King
> *Huge beast, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 187 (15d12 + 90)
> - **Speed** 50 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 29 (+9)|12 (+1)|22 (+6)|2 (-4)|12 (+1)|15 (+2)|
> ___
> - **Skills** Intimidation +6, Perception +6, Stealth +6
> - **Senses** passive Perception 16
> - **Languages** —
> - **Challenge** 14 (11,500 XP)
> ___
>
> ***Legendary Resistance (1/Day).*** If the devilsaur king fails a saving throw, it can choose to succeed instead.
>
> ***Trample.*** Whenever the devilsaur moves into an area occupied by a Medium or smaller creature, the creature must succeed on a DC 19 Strength saving throw or be knocked prone, taking 11 (2d10) bludgeoning damage.
>
> ### Actions
> ***Multiattack.*** The devilsaur king makes two attacks: one with its bite and one with its tail. It can't make both attacks against the same target.
>
> ***Bite.*** *Melee Weapon Attack:* +14 to hit, reach 10ft., one target. *Hit:* 39 (5d12 + 7) piercing damage. If the target is a Medium or smaller creature, it is grappled (escape DC 19) . Until this grapple ends, the target is restrained, and the devilsaur king can't bite another target.
>
> ***Tail.*** *Melee Weapon Attack:* +14 to hit, reach 10ft., one target. *Hit:* 25 (4d8 + 7) bludgeoning damage. If the target is a creature, it must succeed on a DC 19 Strength saving throw or be pushed up to 10 feet away from the devilsaur king and knocked prone.
>
> ***Maim.*** One grappled creature takes 59 (8d12 + 7) piercing damage. If this reduces the creature to 0 hp, the devilsaur swallows it and the grapple ends. While swallowed, the creature is blinded and restrained, it has total cover against attacks and other effects outside the devilsaur king, and it takes 21 (6d6) acid damage at the start of each of the devilsaur king's turns.
If the devil&shy;saur king takes 45 damage or more on a single turn from creatures inside it, it must succeed on a DC 15 Constitution saving throw at the end of that turn or regurgitate all swallowed creatures, which fall prone in a space within 10 feet of it. If the devilsaur king dies, a swallowed creature is no longer restrained by it and can escape from the corpse using 15 feet of movement, exiting prone.
>
> ***Terrifying Roar.***  Each creature within 60 feet of the devilsaur king that can hear him must succeed on a DC 17 Wisdom saving throw or be frightened for 1 minute. A frightened target can repeat the saving throw at the end of each of its turns, ending the frightened condition on itself on a success.
>
> ### Legendary Actions
> The devilsaur king can take 3 legendary actions, choosing from the options below. Only one legendary action option can be used at a time and only at the end of another creature's turn. The devilsaur king regains spent legendary actions at the start of his turn.
>
>**Move.** The devilsaur king moves half his speed.
> <br> **Terrifying Roar** The devilsaur king uses Terrifying Roar.
> <br> **Swallow (Costs 2 Actions).** The devilsaur king swallows <br>&nbsp;&nbsp;&nbsp; a creature it is grappling and the grapple ends. <!--https://wc5e-cr-calculator.frogvall.com/?2;15;187;14;12;75;11;75;32;75;53;0;0;0;0;0;0;;;;;3;;;;;;;;;1;1;;;;;;;;10;;;;;;-->

</div>

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src="https://www.gmbinder.com/images/ZpfPXvK.jpg" style="position:absolute; top:-49px; right:-456px; width:1380px; transform:scalex(1);">
<img src='https://www.gmbinder.com/images/M4hsHsw.png' style='position:absolute; top:60px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:480px;'></div>

___
> ## Diemetradon
> *Large beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 90 (12d10 + 24)
> - **Speed** 25 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 14 (+2)|10 (+0)|14 (+2)|2 (-4)|12 (+1)|4 (-3)|
> ___
> - **Skills** Stealth +2
> - **Senses** passive Perception 11
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
>
> ***Hold Breath.*** The diemetradon can hold its breath for 15 minutes.
>
> ### Actions
> ***Multiattack.*** The diemetradon makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 12 (3d6+2) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 11 (2d8+2) slashing damage.
>
> ***Silencing Howl (1/day).*** The diemetradon casts *silence*, centered on itself.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;90;4;12;23;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:220px;'></div>

___
> ## Direhorn
> *Huge beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 95 (10d12 + 30)
> - **Speed** 50 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 22 (+6)|9 (-1)|17 (+3)|2 (-4)|11 (+0)|5 (-3)|
> ___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 5 (1,800 XP)
> ___
>
> ***Reflective Armor Plating.*** The direhorn has advantage on saving throws against spells and other magical effects.
>
> ***Trampling Charge.*** If the direhorn moves at least 20 feet straight toward a creature and then hits it with a gore attack on the same turn, that target must succeed on a DC 14 Strength saving throw or be knocked prone. If the target is prone, the direhorn can make one stomp attack against it as a bonus action.
>
> ### Actions
> ***Gore.*** *Melee Weapon Attack:* +9 to hit, reach 5 ft., one target. *Hit:* 24 (4d8 + 6) piercing damage.
>
> ***Stomp.*** *Melee Weapon Attack:* +9 to hit, reach 5 ft., one prone creature. *Hit:* 22 (3d10 + 6) bludgeoning damage.<!-- https://wc5e-cr-calculator.frogvall.com/?1;13;95;9;12;24;22;24;0;24;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;1;;;;;;;10;;;;;; -->

> ##### Variant: Incendosaur
> Found in regions of searing flames and flowing lava, an incendosaur is a distent relative to the diemetra&shy;don. An incendorsaur has the same statistics as a diemetradon, except it is immune to fire damage and replaces the diemetradon's silencing howl with the following action.
>
> ***Fire Breath (Recharge 5-6).***  The incendosaur exhales fire in a 15-foot cone. Each creature in that area must make a DC 12 Dexterity saving throw, taking 17 (5d6) fire damage on a failed save, or half as much damage on a successful one.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;90;4;12;34;0;23;0;23;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src="https://www.gmbinder.com/images/tiU4RnD.png" class="inkblot" style="top:0px; right:-150px; width:800px">
<img src="https://www.gmbinder.com/images/C2WIUg2.png" style="position:absolute; top:0px; right:0px; width:800px;">

\pagebreakNum

<div style='margin-top:390px;'></div>

___
> ## Pterrordax
> *Large beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 44 (8d10)
> - **Speed** 10 ft., fly 60 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 10 (+0)|16 (+3)|10 (+0)|2 (-4)|13 (+1)|5 (-3)|
> ___
> - **Skills** Perception +5
> - **Senses** passive Perception 15
> - **Languages** —
> - **Challenge** 2 (450 XP)
> ___
>
> ***Flyby.*** The pterrordax doesn’t provoke an opportunity attack when it flies out of an enemy’s reach.
>
> ### Actions
> ***Multiattack.*** The pterrordax can use its Terrifying Screech. It then makes two claw attacks.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) slashing damage.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 12 (2d8 + 3) piercing damage.
>
> ***Terrifying Screech.*** Each creature within 60 feet of the pterrordax that can hear it must succeed on a DC 11 Wisdom saving throw or be frightened for 1 minute. A frightened target can repeat the saving throw at the end of each of its turns, ending the frightened condition on itself on a success. If a target's saving throw is successful or the effect ends for it, the target is immune to this pterrordax's Frightful Screech for the next 24 hours.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;44;5;12;14;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;1;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:271px;'></div>

___
> ## Pterrorwing
> *Huge beast, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 85 (10d12+20)
> - **Speed** 10 ft., fly 60 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 13 (+1)|17 (+3)|14 (+2)|2 (-4)|14 (+2)|5 (-3)|
> ___
> - **Skills** Perception +8
> - **Senses** passive Perception 18
> - **Languages** —
> - **Challenge** 5 (1800 XP)
> ___
>
> ***Flyby.*** The pterrorwing doesn’t provoke an opportunity attack when it flies out of an enemy’s reach.
>
> ### Actions
> ***Multiattack.*** The pterrorwing can use its Terrifying Screech. It then makes three attacks: one with its bite and two with its claws.
>
> ***Claw.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) slashing damage.
>
> ***Bite.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 12 (2d8 + 3) piercing damage.
>
> ***Terrifying Screech.*** Each creature within 60 feet of the pterrorwing that can hear it must succeed on a DC 15 Wisdom saving throw or be frightened for 1 minute. A frightened target can repeat the saving throw at the end of each of its turns, ending the frightened condition on itself on a success. If a target's saving throw is successful or the effect ends for it, the target is immune to this pterrorwing's Frightful Screech for the next 24 hours.
>
> ***Skycall (Recharge 5-6).*** The pterrorwing screams and a thunderous force sweeps out from it in a 15 foot cone. Each creature in that area must make a DC 15 Constitution saving throw, taking 33 (6d10) thunder damage on a failed save and is pushed 15 feet away from it. On a successful save, the creature takes half as much damage and isn't pushed.<!-- https://wc5e-cr-calculator.frogvall.com/?1;15;85;6;12;66;0;26;0;26;0;0;0;0;0;0;0;;;;;3;;;;;;;1;;;1;;;;;;;;10;;;;;; -->

<img src="https://www.gmbinder.com/images/0hVRLNf.png" class="inkblot" style="top:-100px; right:80px; width:800px; transform:rotate(120deg)">
<img src='https://www.gmbinder.com/images/LHF6snZ.png' style='position:absolute; top:27px; right:50px; width:720px' />

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

\pagebreakNum

<div style='margin-top:84px;'></div>

> ##### Variant: Ravagers and Falcosaurs
> Some raptors are referred to as ravagers. A **raptor ravager** has the statistics of a raptor, a challenge rating of 2 (450 XP) and the following traits:
>
> <br>&nbsp;&nbsp;&nbsp; **Rampage.** When the raptor reduces a creature to <br>&nbsp;&nbsp;&nbsp; 0 hit points with a melee attack on its turn, the <br>&nbsp;&nbsp;&nbsp; raptor can take a bonus action to move up to half <br>&nbsp;&nbsp;&nbsp; its speed and make a bite attack.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;27;5;12;14;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;1;;10;;;;;; -->
>
> <br> Falcosaurs are invasive predatory dinosaurs found on the coastlines of the Broken Isles, that resemble fea&shy;thered raptors with huge beaks for maws. A **falcosaur raptor** uses the statistics of a raptor and a raptor matriarch, and has the following trait:
>
> <br>&nbsp;&nbsp;&nbsp; ***Natural Camouflage.*** The falcosaur has advantage <br>&nbsp;&nbsp;&nbsp; on Dexterity (Stealth) checks made to hide.

___
> ## Raptor
>*Medium beast, unaligned*
> ___
> - **Armor Class** 13 (Natural Armor)
> - **Hit Points** 27 (5d8 + 5)
> - **Speed** 50 ft
> ___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|16 (+3)|12 (+1)|3 (-4)|14 (+2)|6 (-2)|
> ___
> - **Skills** Perception +4, Stealth +4
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Keen Hearing and Smell.*** The raptor has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Pack Tactics.*** The raptor has advantage on attack rolls against a creature if at least one of the raptor's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Pounce***. If the raptor moves at least 20 ft. straight toward a creature and then hits it with a claw or bite attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ### Actions
> ***Multiattack.*** The raptor makes two attacks: one with its bite and one with its claws.
>
> ***Bite***. Melee Weapon Attack: +5 to hit, reach 5 ft., one creature. Hit: 6 (1d6+3) piercing damage.
>
> ***Claws***. Melee Weapon Attack: +5 to hit, reach 5 ft., one creature. Hit: 8 (1d8+3) slashing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;27;5;12;14;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:314px;'></div>

___
> ## Raptor Matriarch
>*Medium beast, unaligned*
> ___
> - **Armor Class** 13 (Natural Armor)
> - **Hit Points** 65 (10d8 + 20)
> - **Speed** 50 ft
> ___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|17 (+3)|14 (+2)|8 (-1)|14 (+2)|12 (+1)|
> ___
> - **Skills** Perception +4, Stealth +5, Intimidation +3
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
> ***Keen Hearing and Smell.*** The raptor has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Pack Tactics.*** The raptor has advantage on attack rolls against a creature if at least one of the raptor's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Pounce***. If the raptor moves at least 20 ft. straight toward a creature and then hits it with a claw or bite attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ### Actions
> ***Multiattack.*** The raptor makes two attacks: one with its bite and one with its claws.
>
> ***Bite***. Melee Weapon Attack: +5 to hit, reach 5 ft., one creature. Hit: 10 (2d6+3) piercing damage.
>
> ***Claws***. Melee Weapon Attack: +5 to hit, reach 5 ft., one creature. Hit: 12 (2d8+3) slashing damage.
>
> ***Matron's Call (1/Day).*** The raptor utters a series of guttural noises and cries. Other raptors within 30 ft. who hear the call, can use their reaction to make an opportunity attack against a creature within 5 ft. of them.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;65;5;12;22;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src="https://www.gmbinder.com/images/KcRAZwq.png" class="inkblot" style="top:-300px; right:0px; width:800px; transform:rotate(40deg)">
<img src='https://www.gmbinder.com/images/ZlkfRr5.png' style='position:absolute; top:-40px; right:-230px; width:900px; transform:scalex(-1)' />

\pagebreakNum

<div style='margin-top:380px;'></div>

___
> ## Sabertusk
> *Large beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 65 (10d10 + 10)
> - **Speed** 40 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 11 (+0)|18 (+4)|12 (+1)|2 (-4)|15 (+2)|9 (-1)|
> ___
> - **Skills** Perception +6, Stealth +6, Survival +4
> - **Senses** passive Perception 16
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
>
> ***Keen Smell.*** The sabertusk has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pounce.*** If the sabertusk moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 14 Strength saving throw or be knocked prone. If the target is prone, the sabertusk can make one bite attack against it as a bonus action.
>
> ***Tendon Rip.*** If the sabertusk hits the same creature with two claw attacks in the same turn, the creature takes another 7 (2d6) slashing damage and its speed is halved until the end of its next turn.
>
> ### Actions
> ***Multiattack.*** The sabertusk makes two claw attacks.
>
> ***Bite.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 13 (2d8+4) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 7 (1d6+4) slashing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;65;6;12;14;20;14;7;14;7;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:481px;'></div>

___
> ## Saurid
> *Tiny beast, unaligned*
> ___
> - **Armor Class** 11 (natural armor)
> - **Hit Points** 12 (5d4)
> - **Speed** 25 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 7 (-2)|13 (+1)|11 (+0)|2 (-4)|10 (+0)|4 (-3)|
> ___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Keen Smell.*** The saurid has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pack Tactics.*** The saurid has advantage on an attack roll against a creature if at least one of the saurid's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ### Actions
> ***Attack.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4+1) piercing damage, and the target must succeed on a DC 11 Constitution saving throw or take 7 (3d4) poison damage and be poisoned for 1 minute. The target can repeat the saving throw at the end of each of its turns, ending the poison on itself on a success.<!-- https://wc5e-cr-calculator.frogvall.com/?0;11;12;3;12;10;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src="https://www.gmbinder.com/images/0hVRLNf.png" class="inkblot" style="top:-100px; right:110px; width:730px; transform:rotate(479deg);">
<img src="https://www.gmbinder.com/images/x2uBrWh.png" style="position:absolute; top:50px; right:150px; width:600px;">

\pagebreakNum

___
> ## Threshadon
>*Huge beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 60 (7d10 + 22)
> - **Speed** 20 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|15 (+2)|14 (+2)|2 (-4)|12 (+1)|5 (-3)|
>___
> - **Skills** Perception +3, Stealth +4
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
> ***Hold breath.*** The threshadon can hold its breath for 30 minutes.
>
> ***Keen Hearing.*** The threshadon has advantage on Wisdom (Perception) checks that rely on hearing.
>
> ***Relentless (Recharges after a Short or Long Rest).*** <br> If the threshadon takes 12 points of damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ### Actions
> ***Multiattack.*** The threshadon makes two bite attacks. 
>
> ***Bite.*** *Melee Weapon Attack*: +6 to hit, reach 10 ft., one target. Hit: 14 (3d6 + 4) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;60;6;12;28;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;1;;;;; -->

\columnbreak

___
> ## Stegodon
>*Huge beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 95 (10d12 + 30)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|21 (+5)|9 (-1)|17 (+3)|4 (-3)|11 (+0)|6 (-2)|
>___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 4 (1,100 XP)
> ___
> ***Trampling Charge.*** If the stegodon moves at least 20 feet straight towards a creature and then hits it with a gore attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone. If the target is prone, the stegadon can make one stomp attack against it as a bonus action.
>
> ### Actions
> ***Gore.*** *Melee Attack Weapon:* +7 to hit, reach 5 ft., one target. *Hit:* 18 (3d8 + 5) piercing damage.
>
> ***Stomp.*** *Melee Attack Weapon:* +7 to hit, reach 5 ft., one target. *Hit:* 21 (3d10 + 5) bludgeoning damage.
>
> ***Impale***. *Melee Weapon Attack:* +7 to hit, reach 10 ft., one creature. *Hit:* 23 (4d8 + 5) piercing damage. If the target is a Medium or smaller creature, it is grappled (escape DC 13). Until this grapple ends, the target is restrained, and the stegadon can't use its impale on another target.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;95;7;12;18;21;23;0;21;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DINOSAURS </div>

<img src='https://www.gmbinder.com/images/qJf7wgU.jpg' style='position:absolute; top:450px; right:-300px; width:1200px' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:-200px; right:0px; width:800px; transform:scalex(-1)' />


\pagebreakNum

<div style='margin-top:106px;'></div>

## Dragonhawks
Travelers entering the enchanted forests of Quel'Thalas might catch a glimpse of the mystical dragonhawk gliding above the trees. An unusual warmth hangs in the air, as the majestic beast vanishes out of sight.

***Bred for War.*** The elves of Quel'Thalas have a long standing tradition domesticating dragonhawks. They are vicious flying predators, swift and deft, able to crack bones and pierce hides with their long talons, and the elves have long mastered training them for use as aerial mounts. Majestic and magnificent creatures, dragonhawks and their elven riders make for an impressive sight.

***Wild Legends.*** Few wild dragonhawks still exist. Most of the beasts found in Quel'Thalas, if not all, are kept by the elves. Wild ones are near-mythical beings that few ever witness, as they stay clear of their tamed kin and have become masters of avoiding detection. These dragonhawks are formidable hunters and among the deadliest predators found on the Eastern Kingdoms.

___
> ## Young Dragonhawk
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 33 (6d8 + 6)
> - **Speed** 10 ft., fly 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|15 (+2)|13 (+1)|7 (-2)|12 (+1)|8 (-1)|
>___
> - **Skills** Perception +3
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** understands Thalassian but can't speak
> - **Challenge** 1 (200 XP)
> ___
>
> ***Keen Sight.*** The dragonhawk has advantage on Wisdom (Perception) checks that rely on sight.
>
> ***Avoidance.*** If the dragonhawk is subjected to an effect that allows it to make a saving throw to take only half damage, it instead takes no damage if it succeeds on the saving throw, and only half damage if it fails.
> ### Actions
> ***Multiattack.*** The dragonhawk makes two attacks with its talons.
>
> ***Talons.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) slashing damage.
>
> ***Fire Breath (Recharges after a Short or Long Rest).*** The dragonhawk exhales fire  in a 15-foot cone. Each creature in that area must make a DC 11 Dexterity saving throw, taking 10 (3d6) fire damage on a failed save, or half as much damage on a successful one.
<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;33;4;11;20;0;8;0;8;0;0;0;0;0;0;0;;;;;3;;;1;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:395px;'></div>

___
> ## Dragonhawk
>*Large beast, unaligned*
> ___
> - **Armor Class** 14
> - **Hit Points** 105 (14d10 + 28)
> - **Speed** 10 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|18 (+4)|15 (+2)|7 (-2)|14 (+2)|8 (-1)|
>___
> - **Saving Throws** Dex +5, Con +4
> - **Skills** Perception +4
> - **Damage Resistances** fire
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** understands Thalassian but can't speak
> - **Challenge** 4 (1,100 XP)
> ___
>
> ***Keen Sight.*** The dragonhawk has advantage on Wisdom (Perception) checks that rely on sight.
>
> ***Avoidance.*** If the dragonhawk is subjected to an effect that allows it to make a saving throw to take only half damage, it instead takes no damage if it succeeds on the saving throw, and only half damage if it fails.
>
> ### Actions
> ***Multiattack.*** The dragonhawk makes two attacks with its talons.
>
> ***Talons.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 4) slashing damage.
>
> ***Fire Breath (Recharge 5-6).*** The dragonhawk exhales fire  in a 15-foot cone. Each creature in that area must make a DC 12 Dexterity saving throw, taking 24 (7d6) fire damage on a failed save, or half as much damage on a successful one.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;105;6;12;48;0;14;0;14;0;0;0;0;0;0;0;;;;;3;;;1;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DRAGONHAWKS </div>
<img src="https://www.gmbinder.com/images/kg2n3mX.jpg" style="position:absolute; top:0px; right:-95px; width:530px;">
<img src="https://www.gmbinder.com/images/qKrtKxo.png" style="position:absolute; top:0px; right:-50px; width:950px;">
<img src="https://www.gmbinder.com/images/TYBvp5o.png" style="position:absolute; top:0px; right:-100px; width:900px;">
<img src="https://www.gmbinder.com/images/wHoaPUq.png" style="position:absolute; top:-90px; right:472px; width:290px; transform:rotate(20deg);">

\pagebreakNum

## Dust Devil
A dust devil is an elemental of air and earth. Roaring out across the land, these violent vortexes can spell a real problem for any  nearby settlements, as their chaotic nature makes them prone to cause great upheaval.

***Eternal Nuisance.*** Dust devils find an unusual enjoy&shy;ment in their uncanny roaming, destroying whatever they come across in their path by sending forth incredible gusts of wind or by tearing it asunder with their hands.

***Conjured by Magic.*** Certain spells and magic items can conjure forth elementals from the Elemental Plane to the Material Plane. Elementals, and dust devils in particular, resent this treatment and the shackles of servitude that comes with it. A creature that summons an elemental must assert the force of will to control it.

***Elemental Nature.*** A dust devil doesn't require air, food, drink, or sleep.

<div style='margin-top:-10px;'></div>

___
> ## Dust Devil
>*Medium elemental, chaotic neutral*
> ___
> - **Armor Class** 14
> - **Hit Points** 44 (8d8 + 8)
> - **Speed** 0 ft., fly 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|16 (+3)|13 (+1)|6 (-2)|10 (+0)|6 (-2)|
>___
> - **Damage Resistances** thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Auran
> - **Challenge** 2 (450 XP)
> ___
> ***Air Form.*** The elemental can enter a hostile creature's space and stop there. It can move through a space as narrow as 1 inch wide without squeezing.
>
> ### Actions
> ***Multiattack.*** The elemental makes two attacks: one with its slam and one with its gust.
>
> ***Slam.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) bludgeoning damage.
>
> ***Gust.*** One target must make a DC 11 Strength saving throw. On a failure, the target takes 7 (2d6) bludgeo&shy;ning damage and is flung up to 20 feet directly away from the elemental and knocked prone. If the saving throw is successful, the target only takes half damage and isn't flung away or knocked prone.
>
> ***Upheaval (Recharge 4-6).*** The elemental pushes dust upwards at a point it can see within 15 feet of it. Each creature other than the elemental within 5 feet of the upheaval must succeed on a DC 13 Dexterity saving throw or be blinded until the end of the elemental's next turn. The elemental needs loose earth, rock, or something similar to use upheaval.

<div class="pageLetter">D</div>
<div class='footnote'>DUST DEVIL </div>
<img src='https://www.gmbinder.com/images/H7oC3xR.png' style='position:absolute; top:0px; right:-350px; width:920px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

## Dwarves: Dark Iron
Known for their fiery tempers and fierce determination, the Dark Iron clan of dwarves has a history of strife with the other dwarven clans, as well as within their own ranks. Twisted by the influence of Ragnaros the Firelord, they are a greedy, cruel, and despotic kind.

Most dark iron dwarves have hair as red as fire or black as coal, trickling with ember flakes, and skin the color of ash. Though their clothes are drab and dark, their ornate style and lavish jewelry is a prominent display of status.

***Legacy of Thaurissan.*** In ages past, the Dark Iron clan cut out their own from the Bronzebeard clan of Ironforge and the Wildhammer clan of Grim Batol. Sworn to revenge on his dwarven king, the Sorcerer-Thane Thaurissan and his wife Modgud led their clansfolk to the southern borders of Khaz Modan, into the far-reaching stretches of the Redridge Mountains.

There, founding the city of Thaurissan, the clan let their hatred seethe and and their forces swell, before they ultimately led a two-pronged assault on both Ironforge and Grim Batol. Thaurissan himself was routed by the Bronzebeards at Ironforge and his wife saw her end to the Wildhammers at Grim Batol. The Dark Iron clan fled back to their home in the Redridge Mountains, where they were ultimately cornered by their dwarven kin -- intent to wipe Thaurissan's legacy from the continent.

***Rise of the Firelord.*** To avoid a seemingly inevitable defeat, Thaurissan attempted to summon forth and ancient power that had been left sleeping beneath the earth. What he brought forth was the Firelord, Ragnaros, once locked away by the Titans when the world was still young.

The towering elemental Lord rose forth, unleashed from his prison, in an apocalyptic rebirth that shattered the Redridge Mountains. At the center of the devastation, a volcano rose forth to spew ash and molten rock across the land. This volcano became known as Blackrock Mountain. The smoldering crater of destruction to its north became known as the Searing Gorge, while the lifeless reaches to its south became the Burning Steppes.

Though Sorcerer-Thane Thaurissan himself was killed in the eruption, both the legacy of his name and the legacy of his surviving clansfolk have lived on. Enslaved by the Ragnaros the Firelord and his elemental hordes.

***Shadowforge City.*** For decades after, the Dark Iron clan lived in servitude to their elemental master. Not as thralls in chains, but as devoted warriors under the Firelord's scalding banner. Following in the footsteps the Sorcerer-Thane's legacy was the son of him and his wife Modgud; Dagran Thaurissan, crowned emperor of the Dark Iron clan and their new home beneath Blackrock Mountain: Shadowforge City.

<div class="pageLetter">D</div>
<div class='footnote'>DWARVES: DARK IRON </div>
<img src='https://www.gmbinder.com/images/UUqvr23.jpg' style='position:absolute; top:0px; right:-250px; width:900px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-20px; width:900px' />
<img src='https://www.gmbinder.com/images/MYPQgR3.png' style='position:absolute; top:830px; right:435px; width:300px' />

\pagebreakNum

&nbsp;&nbsp;&nbsp; ***Born in Flames.*** Like other dwarves, dark iron dwarves have a strong constitution. Adding to their formidable stamina is an incredible affinity to fire -- a gift granted to them by their long servitude to Ragnaros the Firelord.

Though fire can still harm them, the soot-stained skin of a dark iron dwarf shields them well from the smoldering fires at the heart of Blackrock Mountain.

***Conflicted Kin.*** The dark iron dwarves have long nurtured conflict with the other dwarven clans. A failed coup in Ironforge ignited the War of the Three Hammers, which in turn became the catalyst that ultimately brought forth Ragnaros. Worse still, the dwarves remain as split within their own ranks as they are with the other clans.

Open conflicts between independent groups and splintered factions is a common occurrence within the blackened halls beneath the mountain.

### Dark Iron Sorcerer
For those among the dark iron dwarves who lack the strength to train as warriors, a few hold the privilege to instead pursue the study of magic. Sorcerers within the Dark Iron clan have unlocked the power to harness their inner fire, and even yield some control of the mountain's elemental forces from their master. This power seats them at the heart of clan.

### Dark Iron Overseer
The Dark Iron Overseers keep the daily operations of the clan's numerous prospects -- both within Blackrock Mountain and out across the surrounding landscape. The Searing Gorge, in particular, has proven beyond valuable for its mithril and truesilver.

As the tireless work of the dark iron work drudges on, the overseers stand with hateful smiles on their faces, cracking the whips that drive their labouring thralls forward.

### Dark Iron Herald
Heralds stand at the pinnacle of dark iron society. They are the voice of their kin, the mouth through which the Firelord
enacts his will upon the dwarves. Their presence brings
<br> <span style="margin-left:10px"></span> forth the fiery temper that has become the clan's legacy;
<br> <span style="margin-left:20px"></span> driving dwarves around them to fanatical extremes.

<span style="margin-left:50px"></span> To this end, they have been bestowed with the
<br> <span style="margin-left:80px"></span> power to weave devastating spells and
<br> <span style="margin-left:95px"></span> conjure forth the Firelord's minions to
<br> <span style="margin-left:110px"></span> their own aid.

\columnbreak

<div style='margin-top:420px;'></div>

___
> ## Dark Iron Dwarf
>*Medium humanoid (dwarf), lawful evil*
> ___
> - **Armor Class** 16 (breastplate, shield)
> - **Hit Points** 26 (4d8 + 8)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|11 (+0)|14 (+2)|12 (+1)|10 (+0)|9 (-1)|
>___
> - **Damage Resistances** fire
> - **Senses** darkvision 120 ft., passive Perception 10
> - **Languages** Common, Dwarven
> - **Challenge** 1 (200 XP)
> ___
> ***Innate Spellcasting.*** The dwarf's spellcasting ability is Intelligence (spell save DC 11, +3 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *produce flame*
> <br> 1/day each: *lesser restoration, searing smite*
>
> ***Sunlight Sensitivity.*** While in sunlight, the dwarf has disadvantage on attack rolls, as well as on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Battleaxe.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) slashing damage, or 7 (1d10 + 2) slashing damage if used with two hands to make a melee attack.
>
> ***Blunderbuss.*** *Ranged Weapon Attack:* +2 to hit, range 15/60 ft., one target. *Hit:* 9 (2d8) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;16;26;3;11;7;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DWARVES: DARK IRON </div>
<img src='https://www.gmbinder.com/images/bST4TE9.jpg' style='position:absolute; top:530px; right:330px; width:1050px' />
<img src='https://www.gmbinder.com/images/luZTiQ3.png' style='position:absolute; top:0px; right:-180px; width:1000px' />
<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot' style='top:-100px; right:-100px; width:600px'>
<img src='https://www.gmbinder.com/images/NxtWzOA.png' style='position:absolute; top:0px; right:0px; width:400px' />


\pagebreakNum

___
> ## Dark Iron Sorcerer
>*Medium humanoid (dwarf), lawful evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 52 (8d8 + 16)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|14 (+2)|14 (+2)|17 (+3)|10 (+0)|10 (+0)|
>___
> - **Saving Throws** Int +5
> - **Damage Resistances** fire
> - **Senses** darkvision 120 ft., passive Perception 10
> - **Languages** Common, Dwarven
> - **Challenge** 5 (1,800 XP)
> ___
> ***Forged in Flames.*** Any melee weapon the dwarf wields deals an extra 3 (1d6) fire damage on a hit (included in the attack).
>
> ***Innate Spellcasting.*** The dwarf's spellcasting ability is Intelligence (spell save DC 13, +5 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *produce flame*
> <br> 1/day each: *lesser restoration, searing smite*
>
> ***Spellcasting.*** The dwarf is an 8th-level spellcaster. Its spellcasting ability is Intelligence (save DC 13, +5 to hit with spell attacks). The dwarf has the following mage spells prepared:
>
> Cantrips (at will): *control flames, fire bolt, mage hand*
> <br> 1st level (4 slots): *burning hands, hellish rebuke, <br>&nbsp;&nbsp;&nbsp; sudden awakening*
> <br> 2nd level (3 slots): *aganazzar's scorcher, continual <br>&nbsp;&nbsp;&nbsp; flame, flaming sphere, hold person, ✦ living bomb*
> <br> 3rd level (3 slots): *counterspell, slow*
> <br> 4th level (2 slots): *fire shield, wall of fire*
>
> ***Sunlight Sensitivity.*** While in sunlight, the dwarf has disadvantage on attack rolls, as well as on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Warhammer.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) bludgeoning damage, or 7 (1d10 + 2) bludgeoning damage if used with two hands to make a melee attack, plus 3 (1d6) fire damage.
>
> ***Summon Darkhound (1/Day).*** The dwarf magically summons a pair of darkhounds. The darkhounds appears in unoccupied spaces within 60 feet of the summoner, and acts as an ally of its summoner. They remain for 10 minutes, until they die, or until the summoner dismisses them as an action.<!-- https://wc5e-cr-calculator.frogvall.com/?1;12;52;0;13;44;22;44;44;36;38;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

___
> ## Dark Iron Overseer
>*Medium humanoid (dwarf), lawful evil*
> ___
> - **Armor Class** 17 (half plate, shield)
> - **Hit Points** 153 (18d8 + 72)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|11 (+0)|18 (+4)|14 (+2)|10 (+0)|12 (+1)|
>___
> - **Skills** Investigation +5, Insight +3, Intimidation +4
> - **Damage Resistances** fire
> - **Senses** darkvision 120 ft., passive Perception 10
> - **Languages** Common, Dwarven
> - **Challenge** 7 (2,900 XP)
> ___
> ***Forged in Flames.*** Any melee weapon the dwarf wields deals an extra 7 (2d6) fire damage on a hit (included in the attack).
>
> ***Innate Spellcasting.*** The dwarf's spellcasting ability is Intelligence (spell save DC 13, +5 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *produce flame*
> <br> 1/day each: *lesser restoration, searing smite*
>
> ***Sunlight Sensitivity.*** While in sunlight, the dwarf has disadvantage on attack rolls, as well as on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Multiattack.*** The dwarf makes three battleaxe attacks, or two blunderbuss attacks and uses Call to Attack.
>
> ***Battleaxe.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) slashing damage, or 8 (1d10 + 3) slashing damage if used with two hands to make a melee attack, plus 7 (2d6) fire damage.
>
> ***Blunderbuss.*** *Ranged Weapon Attack:* +2 to hit, range 15/60 ft., one target. *Hit:* 9 (2d8) piercing damage.
>
> ***Call to Attack.*** Up to three allied dark iron dwarves within 120 feet of this dwarf that can hear it can each use their reaction to make one weapon attack.
>
> ### Reactions
> ***Hateful Command.*** When an ally that the dwarf can see makes a d20 roll, the dwarf can roll a d6 and the ally can add the number rolled to the d20 roll by taking 3 (1d6) psychic damage. A creature immune to psychic damage can't be affected by Hateful Command.<!-- https://wc5e-cr-calculator.frogvall.com/?1;17;153;6;12;45;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">D</div>
<div class='footnote'>DWARVES: DARK IRON </div>
<img src='https://www.gmbinder.com/images/bST4TE9.jpg' style='position:absolute; top:530px; right:-490px; width:1050px' />
<img src='https://www.gmbinder.com/images/8x5CGKk.png' style='position:absolute; top:0px; right:0px; width:900px;transform:scaley(-1)' />
<img src='https://www.gmbinder.com/images/0AudugF.png' style='position:absolute; top:800px; right:420px; width:520px;transform:rotate(60deg)' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Dark Iron Herald
>*Medium humanoid (dwarf), lawful evil*
> ___
> - **Armor Class** 18 (plate)
> - **Hit Points** 110 (13d8 + 52)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|14 (+2)|18 (+4)|19 (+4)|13 (+1)|12 (+1)|
>___
> - **Saving Throws** Str +6, Con +8, Int +8
> - **Skills** History +8, Insight +5, Intimidation +5
> - **Damage Resistances** fire
> - **Senses** darkvision 120 ft., passive Perception 11
> - **Languages** Common, Dwarven
> - **Challenge** 10 (5,900 XP)
> ___
> ***Forged in Flames.*** Any melee weapon the dwarf wields deals an extra 10 (3d6) fire damage on a hit (included in the attack).
>
> ***Innate Spellcasting.*** The dwarf's spellcasting ability is Intelligence (spell save DC 15, +7 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *produce flame*
> <br> 1/day each: *lesser restoration, searing smite*
>
> ***Spellcasting.*** The dwarf is a 14th-level spellcaster. Its spellcasting ability is Intelligence (save DC 15, +7 to hit with spell attacks). The dwarf has the following mage spells prepared:
>
> Cantrips (at will): *control flames, fire bolt, mage hand, <br>&nbsp;&nbsp;&nbsp; minor illusion, prestidigitation*
>
> 1st level (4 slots): *burning hands, hellish rebuke, <br>&nbsp;&nbsp;&nbsp; sudden awakening*
> <br> 2nd level (3 slots): *aganazzar's scorcher, continual <br>&nbsp;&nbsp;&nbsp; flame, flaming sphere, hold person, ✦ living bomb*
> <br> 3rd level (3 slots): *counterspell, fireball, slow*
> <br> 4th level (3 slots): *confusion, fire shield, wall of fire*
> <br> 5th level (2 slots): *dominate person, immolation*
> <br> 6th level (1 slot): *investiture of flame*
>
> **The dwarf casts fire shield on itself before combat.*
>
> ***Sunlight Sensitivity.*** While in sunlight, the dwarf has disadvantage on attack rolls, as well as on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Multiattack.*** The dwarf makes two warhammer attacks.
>
> ***Warhammer.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) bludgeoning damage, or 7 (1d10 + 2) bludgeoning damage if used with two hands to make a melee attack, plus 10 (3d6) fire damage.
>
> ***Conjure Fire Elemental (1/Day).*** The dwarf magically conjures a fire elemental. The fire elemental appears in an unoccupied space within 60 feet of its conjurer, and acts as an ally of its conjurer. It remains for 10 minutes, or until it dies.<!-- https://wc5e-cr-calculator.frogvall.com/?2;18;110;0;15;62;36;54;36;54;36;0;0;0;0;0;0;;;;1;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">D</div>
<div class='footnote'>DWARVES: DARK IRON </div>
<img src='https://www.gmbinder.com/images/iBiU601.jpg' style='position:absolute; top:0px; right:-50px; width:850px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:-20px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:140px;'></div>

## Elementals
Elementals are as ageless as they are unchanging; volatile beings of raw elemental power, manifested in physical form. Since the early days of creation, as life hurdled through the cosmos and manifested itself upon countless worlds, the most common primordial form of life has been the elementals -- who now populate nearly every world spanning across the great dark beyond, nourishing themselves off of the energies within.

***Bound to the Elemental Plane.*** On Azeroth, as the titanic Keepers saw to the ordering of the world, they found the elementals wreaking havoc under the corrupting influence of the Old Gods. As a safeguard, to protect their intended new denizens of the planet from such a destructive force, the Keepers constructed the Elemental Plane as a prison in which the elementals could be locked away, free to roam at their own behest. In their absence, the Keepers could tend to their task at hand; settling the natural order of Azeroth.

The Elemental Plane is divided into four interlinked regions, each existing within its own pocket dimension as a representation of its associated element: The Abyssal Maw, domain of water; Deepholm, domain of earth; the Firelands, domain of fire; and Skywall, domain of air.

***An Eternity of Conflict.*** Though the domains within the Elemental Plane are intended to be sealed off, none of them accessible from the others, the elementals have never ceased their endless strife with one another. By what means they can, whether by breaching the walls of their domain to invade another or by taking their conflict to the physical plane with the help of mortal hands, the elementals are quick to clash as they meet -- sometimes waging battles of titanic proportions.

***The Ordering of Elements.*** Though elementals are chaotic and violent by nature, some more so than others, they themselves follow a strict ordering of power within their elemental domain.

Above all other sits the Elemental Lords; beings of untamed power, whose sum can be considered even larger than most else existing within their realm. They hold power over their domain within the Elemental Plane, subjugating lesser elementals to carry out their bidding. It is said that if magic drawing power from the Elemental Plane is cast in the presence of the Elemental Lord governing that particular elemental domain, it may well fall to said Lord to take control of the spell at their own whim.

Carrying out the bidding of the Elemental Lords are their lieutenants. While nowhere near as powerful as their respective Lord, it is not uncommon for an elemental lieutenant to wield both great power and agency in carrying out their master's bidding.

***Elemental Nature.*** An elemental doesn't require air, food, drink, or sleep.

\columnbreak

<div style='margin-top:140px;'></div>

### Air Elemental
Taking form as a swirling storm, or a billowing cloud given faint humanoid shape, an air elemental holds command of wind and weather. Fast and silent, it strikes out by enveloping its foes in a blinding whirlwind to seize the upper hand.
<div style='margin-top:-5px;'></div>

### Arcane Elemental
Appearing in areas suffused with arcane energy, these ele&shy;mentals manifest from its energy and are often found in the service of mages, feeding of the fluctuation of magic from their spells.
<div style='margin-top:-5px;'></div>

### Earth Elemental
Near indistinguishable from rocks if standing still, an earth elemental is as hardy and steadfast as the element it embodies. It burrows through the ground with utmost ease, and faces its opponents head-on if engaged.
<div style='margin-top:-5px;'></div>

### Fire Elemental
A fire elemental manifests as a smoldering pillar of unwavering destruction. While susceptible to water, it is a cunning presence that will often attempt to overwhelm and outright engulf those who try to stand in its way.
<div style='margin-top:-5px;'></div>

### Ice Elemental
Manifest from frozen water, ice elementals share domain and allegiance with other water elementals. It moves unhindered through the icy reaches in which it dwells, and is very quick to enrage at the sight of fire wielded in its vicinity.
<div style='margin-top:-5px;'></div>

### Water Elemental
A favoured companion among mages, human mages in particular, a water elemental is near impossible to discern while underwater. If able, it often attempts to deal with threats by luring them along into the water -- dragging them from there into the murky depths.

> ##### Variant: Elemental Revenant
> An elemental revenant is a furious elemental being that has manifested itself with a crude suit of armor for protection.
>
>A revenant has the same statistics as its elemental counterpart, except for an Armor Class of 17 (half plate, shield). It loses any ability to move through and stop in the space of other creatures, as well as any ability to move through spaces smaller than 2 feet, its slam or touch action is replaced with the following option, using the same attack modifier and damage type as the original action.
>
> ***Maul.*** *Melee Weapon Attack:* +8 to hit, reach 10 ft., one target. *Hit:* 16 (2d12 + 5) damage of the elemental's type.

<div class='letterheader'></div>
<div class="mmletter mml-e"></div>
<div class="pageLetter">E</div>
<div class='footnote'>ELEMENTALS </div>


\pagebreakNum

<div style='margin-top:313px;'></div>

___
> ## Air Elemental
>*Large elemental, neutral*
> ___
> - **Armor Class** 15
> - **Hit Points** 90 (12d10 + 24)
> - **Speed** 0 ft., fly 90 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|20 (+5)|14 (+2)|6 (-2)|10 (+0)|6 (-2)|
>___
> - **Damage Resistances** lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Auran
> - **Challenge** 5 (1,800 XP)
> ___
>
> ***Air Form.*** The elemental can enter a hostile creature's space and stop there. It can move through a space as narrow as 1 inch wide without squeezing.
>
> ### Actions
> ***Multiattack.*** The elemental makes two slam attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 14 (2d8 + 5) bludgeoning damage.
>
> ***Whirlwind (Recharge 4-6).*** Each creature in the elemental's space must make a DC 13 Strength saving throw. On a failure, a target takes 15 (3d8 + 2) bludgeoning damage and is flung up to 20 feet away from the elemental in a random direction and knocked prone. If a thrown target strikes an object, such as a wall or floor, the target takes 3 (1d6) blud&shy;geoning damage for every 10 feet it was thrown. If the target is thrown at another creature, that creature must succeed on a DC 13 Dexterity saving throw or take the same damage and be knocked prone.
> <br>&nbsp;&nbsp;&nbsp; If the save is successful, the target takes half the damage and isn't flung away or knocked prone.

\columnbreak

<div style='margin-top:278px;'></div>

___
> ## Arcane Elemental
> *Large elemental, neutral*
> ___
> - **Armor Class** 14
> - **Hit Points** 76 (9d10 + 27)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|18 (+4)|16 (+3)|7 (-2)|10 (+0)|6 (-2)|
>___
> - **Damage Resistances** acid; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** force, poison
> - **Condition Immunities** exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 5 (1,800 XP)
> ___
> ***Arcane Form.*** The elemental can enter a hostile creature's space and stop there. It can move through a space as narrow as 1 inch wide without squeezing. When the elemental enters the area of an *antimagic field* spell for the first time on a turn or starts its turn there, it must succeed on a Constitution saving throw against the spell save DC of its spellcaster, or be stunned until the start of its next turn.
>
> ***Illumination.*** The elemental sheds bright light in a <br> 15-foot radius and dim light in an additional 15 feet.
>
> ### Actions
> ***Multiattack.*** The elemental makes two touch attacks.
>
> ***Touch.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) force damage. If the target is a creature, it must succeed on a DC 14 Strength saving throw or be knocked prone.
>
> ***Arcane Blast (Recharge 5-6).*** The elemental erupts arcane energy at a point it can see within 60 feet of it. Each creature within 10 feet of that point must make a DC 14 Dexterity saving throw, taking 10 (4d4) force damage on a failed save, or half as much damage on a successful one.

<div class="pageLetter">E</div>
<div class='footnote'>ELEMENTALS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='position:absolute; top:-300px; right:-100px; width:900px; transform:rotate(60deg)' />
<img src='https://www.gmbinder.com/images/9oFdFdN.jpg' style='position:absolute; top:40px; right:400px; width:400px;mix-blend-mode:darken' />
<img src='https://www.gmbinder.com/images/119Iqk8.png' style='position:absolute; top:0px; right:0px; width:400px' />

\pagebreakNum

<div style='margin-top:428px;'></div>

___
> ## Earth Elemental
>*Large elemental, neutral*
> ___
> - **Armor Class** 17 (natural armor)
> - **Hit Points** 126 (12d10 + 60)
> - **Speed** 30 ft., burrow 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|20 (+5)|8 (-1)|20 (+5)|5 (-3)|10 (+0)|5 (-3)|
>___
> - **Damage Vulnerabilities** thunder
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, paralyzed, petrified, poisoned, unconscious
> - **Senses** darkvision 60 ft., tremorsense 60 ft., <br> passive Perception 10
> - **Languages** Terran
> - **Challenge** 5 (1,800 XP)
> ___
> ***Earth Glide.*** The elemental can burrow through nonmagical unworked earth and stone. While doing so, the elemental doesn't disturb the material it moves through.
>
> ***Siege Monster.*** The elemental deals double damage to objects and structures.
>
> ### Actions
> ***Multiattack.*** The elemental makes two slam attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 14 (2d8 + 5) bludgeoning damage.

\columnbreak

<div style='margin-top:280px;'></div>

___
> ## Fire Elemental
>*Large elemental, neutral*
> ___
> - **Armor Class** 13
> - **Hit Points** 102 (12d10 + 36)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|17 (+3)|16 (+3)|6 (-2)|10 (+0)|7 (-2)|
>___
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** fire, poison
> - **Condition Immunities** exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Ignan
> - **Challenge** 5 (1,800 XP)
> ___
> ***Fire Form.*** The elemental can move through a space as narrow as 1 inch wide without squeezing. A creature that touches the elemental or hits it with a melee attack while within 5 feet of it takes 5 (1d10) fire damage. In addition, the elemental can enter a hostile creature's space and stop there. The first time it enters a creature's space on a turn, that creature takes 5 (1d10) fire damage and catches fire; until someone takes an action to douse the fire, the creature takes 5 (1d10) fire damage at the start of each of its turns.
>
> ***Illumination.*** The elemental sheds bright light in a <br>30-foot radius and dim light in an additional 30 feet.
>
> ***Water Susceptibility.*** For every 5 feet the elemental moves in water, or for every gallon of water splashed on it, it takes 1 cold damage.
>
> ### Actions
> ***Multiattack.*** The elemental makes two touch attacks
>
> ***Touch.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) fire damage. If the target is a creature or a flammable object, it ignites. Until a creature takes an action to douse the fire, the target takes 5 (1d10) fire damage at the start of its turn.

<div class="pageLetter">E</div>
<div class='footnote'>ELEMENTALS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='position:absolute; top:-100px; right:50px; width:800px; transform:rotate(110deg)' />
<img src='https://www.gmbinder.com/images/6aDvUEv.png' style='position:absolute; top:160px; right:370px; width:450px' />
<img src='https://www.gmbinder.com/images/cNtNh1F.jpg' style='position:absolute; top:-10px; right:10px; width:400px;mix-blend-mode:darken' />

\pagebreakNum

<div style='margin-top:310px;'></div>

___
> ## Ice Elemental
>*Large elemental, neutral*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 95 (10d10 + 40)
> - **Speed** 40 ft., burrow 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|14 (+2)|18 (+4)|5 (-3)|10 (+0)|8 (-1)|
>___
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** cold, poison
> - **Condition Immunities** exhaustion, paralyzed, petrified, poisoned, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Aquan
> - **Challenge** 5 (1,800 XP)
> ___
> ***Frost Form.*** The elemental can burrow through nonmagical unworked ice and snow. While doing so, the elemental doesn't disturb the material it moves through. A creature that touches the elemental or hits it with a melee attack while within 5 feet of it takes 5 (1d10) cold damage. Additionally, the elemental freezes non-creature liquids within a 10-foot radius of it. A creature caught in the liquid when the elemental freezes it is grappled (escape DC 14).
>
> ***Ice Walk.*** The elemental can move across and climb icy surfaces without needing to make an ability check. Additionally, difficult terrain composed of ice or snow doesn't cost extra movement.
>
> ### Actions
> ***Multiattack.*** The elemental makes two attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) bludgeoning damage.
>
> ***Icicle.*** *Ranged Weapon Attack:* +7 to hit, range 30/60 ft., one target. *Hit:* 11 (2d12) piercing damage.

\columnbreak

<div style='margin-top:240px;'></div>

___
> ## Water Elemental
>*Large elemental, neutral*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 114 (12d10 + 48)
> - **Speed** 30 ft., swim 90 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|14 (+2)|18 (+4)|5 (-3)|10 (+0)|8 (-1)|
>___
> - **Damage Resistances** acid; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Aquan
> - **Challenge** 5 (1,800 XP)
> ___
> ***Water Form.*** The elemental can enter a hostile creature's space and stop there. It can move through a space as narrow as 1 inch wide without squeezing.
>
> ***Freeze.*** If the elemental takes cold damage, it partially freezes; its speed is reduced by 20 feet until the end of its next turn.
>
> ### Actions
> ***Multiattack.*** The elemental makes two slam attacks.
>
> ***Slam.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) bludgeoning damage.
>
> ***Whelm (Recharge 4-6).*** Each creature in the elemen&shy;tal's space must make a DC 15 Strength saving throw. On a failure, a target takes 13 (2d8 + 4) bludgeoning damage. If it is Large or smaller, it is also grappled (escape DC 14). Until this grapple ends, the target is restrained and unable to breathe unless it can breathe water. If the saving throw is successful, the target is pushed out of the elemental's space.
> <br>&nbsp;&nbsp;&nbsp; The elemental can grapple one Large creature or up to two Medium or smaller creatures at one time. At the start of each of the elemental's turns, each target grappled by it takes 13 (2d8 + 4) bludgeoning damage. A creature within 5 feet of the elemental can pull a creature or object out of it by taking an action to make a DC 14 Strength and succeeding.

<div class="pageLetter">E</div>
<div class='footnote'>ELEMENTALS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='position:absolute; top:-150px; right:300px; width:700px' />
<img src='https://www.gmbinder.com/images/7urPPrg.png' style='position:absolute; top:0px; right:380px; width:400px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/FTRgu1c.jpg' style='position:absolute; top:-50px; right:20px; width:400px; transform:scalex(-1); mix-blend-mode:darken' />

\pagebreakNum

<div style='margin-top:140px;'></div>

## Faceless Ones
The faceless ones are a monstrous kin, brought forth from the organic matter that seeped away from the Old Gods in primordial times, before the Titans brought about the ordering of Azeroth. Cunning and intelligent, they serve their eldritch masters with fanatical devotion. Tales of their unspeakable deeds paint them as unstoppable juggernauts.

***Spawn of the Old Gods.*** The faceless ones are the creation of the Old Gods, in the most literal sense of the word. They are shaped from the Old Gods' own flesh and blood; trickled from their eternal prisons through the core of the planet, like bile through the gutters.

Some of these aberrations are unique, while others are so uniform as to be virtually identical. They are all loyal to the gods that spawned them forth, unwavering in their devotion to the will of their creators.

***Unexpected Allies.*** These eldritch horrors are powerful, but not innumerable. What they lack in either is quickly recouped by corrupting other beings that happen in their path. Even a faceless one on its own is almost guaranteed to never truly be alone.

The faceless ones keep a few valuable allies, such as the Naga, while simultaneously seeding hatred and distrust even among the most loyal of factions.

***Corrupting Presence.*** Faceless ones carry the stain of the Old Gods with the, wherever they go, and their presence alone can change things for the worse. Life is tainted in their wake, slowly twisted around as friends become foes and alliances dissolve into bitter hatred.

Whether by instilling paranoia or asserting dominance directly, the faceless ones will always seek to divide and conquer.

***Return of the Black Empire.*** The Old Gods once ruled over Azeroth, in a time long before mortal races saw the light of day. Locked away by the Titans, they have long ever since to return to power -- an end to which their faceless servants are the means by which they act.

Long have they sown the seeds of corruption, turning the denizens of the world against one another, so that they can break free and seize control once more.

### Zoatroid
Many would see the small, squid-like zoatroid as utterly inconsequential. Nowhere near as dangerous as the towering n'raqi. Fools are those who underestimate them, as these merciless critters hunt to gain complete of their victims -- which they do by latching onto the face of a suitable target in order to bore into its mind.

Zoatroids have found a second home among the Naga, saiding their serpentine allies by infiltrating and corrupting their enemies. Some zoatroids are only able to seize control of a creature's body, while others are able to claim both body and mind as their own.

<div class='letterheader'></div>
<div class="mmletter mml-f"></div>
<div class="pageLetter">F</div>
<div class='footnote'>FACELESS ONES </div>
<img src='https://www.gmbinder.com/images/FyPqjM3.png' style='position:absolute; top:0px; right:-310px; width:850px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-15px; width:900px' />

\pagebreakNum

<div style='margin-top:32px;'></div>

> ##### Variant: Royal Zoatroid
> A royal zoatroid has a challenge rating of 6 (2,300 XP). It has the same statistics as a zoatroid except that it adds its Wisdom modifier to its Armor Class (AC 17) and gains the following additional trait:
>
> <br>&nbsp;&nbsp; ***Magic Resistance.*** The zoatroid has advantage on
<br>&nbsp;&nbsp; saves against spells and other magical effects.
>
> <br>The royal zoatroid has the following action option in place of the zoatroid's Enslave:
>
> <br>&nbsp;&nbsp; ***Dominate (Recharge 6).*** One humanoid grappled
<br>&nbsp;&nbsp; by the zoatroid must succeed on a DC 13 Wisdom
<br>&nbsp;&nbsp; saving throw or be dominated by the zoatroid: the
<br>&nbsp;&nbsp; dominated target goes on the zoatroids initiative,
<br>&nbsp;&nbsp; it controls the target using its action. The *Domi-*
<br>&nbsp;&nbsp; *nate* deprives the target of its vision but not its
<br>&nbsp;&nbsp; awareness. The royal zoatroid can be targeted by
<br>&nbsp;&nbsp; attacks, spells, and other effects but any attack roll
<br>&nbsp;&nbsp; that misses the zoatroid automatically hits its
<br>&nbsp;&nbsp; dominated target.
> <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The domination lasts until the target drops to 0
<br>&nbsp;&nbsp; hit points, the zoatroid ends it as a bonus action,
<br>&nbsp;&nbsp; or a creature uses their action to attempt a
<br>&nbsp;&nbsp; grapple check contested by the zoatroid.<!-- https://wc5e-cr-calculator.frogvall.com/?1;17;63;5;12;20;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;1;;;;1;1;;;;;;;10;;;;;; -->

<div class='statblock-bottom-wide'>

___
___
> ## Zoatroid
>*Small aberration, neutral evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 63 (14d6 + 14)
> - **Speed** 5 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|14 (+2)|13 (+1)|8 (-1)|14 (+2)|4 (-3)|
>___
> - **Saving Throws** Dex +4, Wis +4
> - **Skills** Athletics +8, Perception +4
> - **Condition Immunities** charmed
> - **Senses** darkvision 30 ft., passive Perception 14
> - **Languages** understands Nazja but can't speak, telepathy 60 ft.
> - **Challenge** 4 (1,100 XP)
> ___
> ***Hold Breath.*** While out of water, the zoatroid can hold its breath for 1 hour.
>
> ***Water Breathing.*** The zoatroid can breathe only underwater.
>
> ### Actions
> ***Tentacles.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) bludgeoning damage, plus 13 (3d8) psychic damage. If the target is a crea&shy;ture, it is grappled (escape DC 16). Until the grapple ends, the zoatroid shares space with it, the target is blinded, and the zoatroid can't use its tentacles on another target without ending the grapple.
>
> ***Enslave (Recharge 6).*** One humanoid grappled by the zoatroid must succeed on a DC 13 Wisdom saving throw or be enslaved by the zoatroid; the enslaved target goes on the zoatroids initiative, it controls the target's body using its actions, but it doesn't gain access to the target's knowledge, class features, or proficiencies. The enslave deprives the target of its vision but not its awareness. The zoatroid can be targeted by attacks, spells, and other effects, but any attack roll that misses it automatically hits its enslaved target.
> <br>&nbsp;&nbsp;&nbsp; The enslavement lasts until the target drops to 0 hit points, the zoatroid ends it as a bonus action, or a creature uses their action to attempt a grapple check contested by the zoatroid.
>
> ***Fogged Mind (Recharges after a Short or Long Rest).*** Each non-aberration creature within 10 feet of the zoatroid must succeed on a DC 12 Wisdom saving throw or be blinded for 1 minute. A blinded target can repeat the saving throw at the end of each of its turns.
>
> ### Reactions
> ***Reactive Shield.*** The zoatroid forces an attack roll that would hit it to instead hit its enslaved target. To do so, the zoatroid must be able to see the attacker.
> <br><div style='margin-top:130px;'></div><!-- https://wc5e-cr-calculator.frogvall.com/?0;15;63;5;12;20;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;1;;;10;;;;;; -->

</div>

<div class="pageLetter">F</div>
<div class='footnote'>FACELESS ONES </div>

<img src='https://www.gmbinder.com/images/P8KAHYS.jpg' style='position:absolute; top:0px; right:-15px; width:500px;mix-blend-mode:darken' />

\pagebreakNum

<div style='margin-top:110px;'></div>

___
> ## Fleshbeast
>*Small aberration, neutral evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 36 (8d6 + 8)
> - **Speed** 20 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|9 (-1)|14 (+2)|13 (+1)|4 (-3)|12 (+1)|2 (-4)|
>___
> - **Damage Resistances** poison
> - **Condition Immunities** blinded, poisoned
> - **Senses** blindsight 60 ft. (blind beyond this radius), passive Perception 11
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
> ***Damage Transfer.*** While attached to a creature, the fleshbeast takes only half the damage dealt to it (rounded down), and that creature takes the other half.
>
> ### Actions
> ***Multiattack.*** The fleshbeast makes two attacks: one with its tentacle and one with its bite. If attached it makes two bite attacks against the creature it is attached to instead.
>
> ***Tentacle.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 9 (2d6+2) bludgeoning damage, and if the target is Small or larger, the fleshbeast attaches to it, moving into its space which is shared with the target. The fleshbeast's movement speed becomes 0 and it gains advantage on bite attacks against the target. In addition, at the start of each of the target's turns, the target takes 7 (2d6) acid damage and if the target moves the fleshbeast moves with it. The fleshbeast can detach itself as a bonus action, in which case it regains its movement speed and needs to spend that movement speed to move out of the target's space. A creature, including the target, can take its action to detach the fleshbeast by succeeding on a DC 14 Strength check.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 7 (2d4 + 2) piercing damage. If the target is a creature, it must succeed on a DC 12 Constitu&shy;tion saving throw against disease or become poisoned until the disease is cured. Every 24 hours that elapse, the target must repeat the saving throw, reducing its hit point maximum by 3 (1d6) on a failure. The disease is cured on a success. The target dies if the disease reduces its hit point maximum to 0. This reduction to the target's hit point maximum lasts until the disease is cured. A swarm of insect's crawl out of a creature 1d4 rounds after it died if it was diseased upon its death.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;36;4;12;16;7;14;7;14;7;0;0;0;0;0;0;;;;;3;;;;;;1;;;;1;;;1;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:650px;'></div>

## Fleshbeast
Though the exact origin of these monstrous aberrations is unknown, the theories are many. Some even go so far as to claim them a product of the Twisting Nether itself, pulled from there onto other worlds.

***Nightmare Made Flesh.*** Slavering, hungering monstro&shy;sities, the best way to describe the terrifying fleshbeasts are plainly as creatures of nightmare. Their presence has been witnessed both on Azeroth and beyond, as they appear to tail along on magical experiments that try to exploit the powers of the Twisting Nether, using them as rifts through which they can travel between worlds.

***Parasitic Brood.*** Fleshbeasts are decidedly mindless, acting entirely on instinct. They hunt by flocking together in large swarms, overpowering their prey and consuming it, sometimes while it is still alive. Even after the fleshbeast has had its fill, most of the victim will still be left behind intact -- a perfect nesting ground for their wormlike spawn, who will later devour the remains as they hatch.

Other predators attempting to scavenge remains left behind by a fleshbeast will most likely be infected as well, and later devoured by the hatchlings.

<div class="pageLetter">F</div>
<div class='footnote'>Fleshbeast </div>
<img src='https://www.gmbinder.com/images/fUjDAtF.jpg' style='position:absolute; top:-10px; right:0px; width:990px' />
<img src='https://www.gmbinder.com/images/pZatMx5.png' style='position:absolute; top:0px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/cfCly0q.png' style='position:absolute; top:200px; right:-165px; width:700px; z-index:100' />

\pagebreakNum

<div style='margin-top:250px;'></div>

## Furbolg
Furbolgs are large, kind-hearted creatures. Resembling humanoid bears, they form tribal settlements in caves, forest thickets, and other defensible locations. Though they have care little for conflict, they appear particularly susceptible to corruption.

***Peaceful Nature.*** Furbolgs are a peaceful race, wishing to live for themselves with as little outside interference as they can. They keep a close tie to nature and worship the ancient bear twins; Ursoc and Ursol.

Their tribes can grow exceptionally large, though they are masters at staying secluded from the world around. A furbolg tribe is its family, and tension within is rare. Most tribes are led by its wisest, oldest shaman.

***Corrupted Kin.*** Perhaps leading to their secluded nature, furbolgs have been shown to be easily manipulated by outside forces. As the lands around have blighted, tribes have been transformed into vicious, hateful packs.

Many such tribes lost their ways to the Burning Legion's invading forces, as well as to the corrupting influence of the Old Gods.  Turned away from their kin and onto a bloody path of war.

### Furbolg Names and Languages
Furbolgs have their own language, Furbolg, whose sayings are usually intended literally. A few also speak Darnassian or Common. Their names are comprised of short utterings, each of which has meaning in their own tongue.

<div style='margin-top:-5px;'></div>

**Furbolg Names:** Ak, Adak, Dal, Grazle, Krolg, Oota, Rann
<br /> **Tribe Names:** Barkskin, Blackwood, Deadwood, Frostpaw
<br />&nbsp;&nbsp;&nbsp; Gnarlpine, Redfang, Timbermaw, Thistlefur

> ##### Variant: Furbolg Shaman
> Some furbolgs devote themselves to becoming a shaman for their tribe. A furbolg shaman has a challenge rating of 3 (700 XP) and gains the Spellcasting trait.
>
> ***Spellcasting.*** The furbolg is a 3rd-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). It has the following shaman spells
>
> <br> Cantrips (at will): *gust, produce flame*
> <br> 1st level (4 slots): *chromatic orb, cure wounds, fog <br>&nbsp;&nbsp;&nbsp; cloud, thunderwave*
> <br> 2nd level (2 slots): *heat metal, lesser restoration*<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;90;5;12;9;0;12;9;12;16;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:370px;'></div>

___
> ## Furbolg
>*Medium humanoid (furbolg), neutral*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 90 (12d8 + 36)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|12 (+1)|16 (+3)|10 (+0)|15 (+2)|7 (-2)|
>___
> - **Skills** Nature +2, Perception +4, Survival +4
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** Druidic, Furbolg
> - **Challenge** 2 (450 XP)
> ___
>
> ***Innate Spellcasting.*** The furbolg's spellcasting ability is Wisdom (spell save DC 12). The furbolg can innately cast the following spells, requiring no material components.
>
> At will: *dancing lights, druidcraft*
> <br> 1/day each: *enhance ability, entangle*
>
> **Wounded Fury.** While it has 10 hit points or fewer, the furbolg has advantage on attack rolls. In addition, it deals an extra 7 (2d6) damage to any target it hits with a melee attack.
>
> ### Actions
> ***Multiattack.*** The furbolg makes two claw attacks, or one with its claws and one with its quarterstaff.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 5 (1d4 + 3) slashing damage
>
> ***Quarterstaff.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) bludgeoning damage, or 7 (1d8 + 3) bludgeoning damage if used with two hands to make a melee attack.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;90;5;12;12;0;12;0;12;7;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">F</div>
<div class='footnote'>FURBOLG </div>
<img src='https://www.gmbinder.com/images/RK0T5LI.jpg' style='position:absolute; top:0px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/hIpYyKx.png' style='position:absolute; top:-170px; right:0px; width:1000px; transform:rotate(180deg)' />
<img src="https://www.gmbinder.com/images/Dn83KUf.png " style="position:absolute;top: 0px;right: -52px;width: 480px;">

\pagebreakNum

<div style='margin-top:140px;'></div>

## Ghosts
While most mortal souls eventually find their way to the Shadowlands, not all who have died manage to find rest. Some are unwillingly bound to roam the trackless wastes that exist between the Shadowlands and the physical world, appearing in the latter as ghostly apparitions as they search for release from their endless suffering.

***Existing Between Worlds.*** There are many reasons for why a soul would remain. Curses and deliberate magical entrapment are both common, though the most prevalent are souls unwilling to abandon the physical realm -- also known as the Material Plane -- for the realm of spirits. A person whose life ended abruptly at the hands of someone else is very likely to return as a malevolent spectre, seeking to exact revenge upon those who did them wrong.

Conversely, other spirits may be unwilling to find rest out of fear for what lies beyond, or for a feeling that their life never really reached its full potential.

***Bitter Resentment.*** It is not uncommon for ghosts, especially those forced to dwell in this state for too long, to grow resentful of the living. Unable to accept their own death, and envious of those still living, they grow to foster a seething hatred for warmth, hope, and joy. The presence of such may even drive them into a murderous frenzy.

***The Shadowlands.*** Shaped before mortal life even walked the universe, the Shadowlands is a realm of existence spanning all known worlds, including Azeroth. Those who have seen it describe it as a nightmarish world of decay; a labyrinth of intertwined spiritual planes all teeming with the souls of the dead.

Many believe this to be the final destination for all mortal souls. The realm into which they are drawn in death, destined to remain forever after. Others choose to hope for their final rest to be brighter -- more pleasant than an eternity languishing such cold and bleak confines.

Within the Shadowlands, time does not pass as it would elsewhere. Sometimes, years outside of the Shadowlands may only seem like days within. Sometimes, a year passed by within this bleak domain takes little more than a minute, or perhaps an hour, in the physical realm. While it is often next to impossible to see what lies ahead inside the Shadowlands, it is possible for those within to hear whispered fragments of what is happening outside.

It is said that Icecrown, the frozen peak of Northrend and citadel of the Scourge, exists as an anchoring bridge between the Shadowlands and the physical world.

Some of the most prominent beings dwelling in the Shadowlands are regarded as patrons of death among various races; such as Bwonsamdi, the troll Loa of death.

Also prominent are the Spirit Healers; ascendant Val'kyr who, following the banishment of Helya and the sealing of the Halls of Valor, disappeared into the Shadowlands -- hidden away there, even from the corrupting influence of the Lich King.

\columnbreak

<div style='margin-top:520px;'></div>

> ##### The Spirit Healers
>
> The first of the Val'kyr was the titanic Watcher Helya, bound by the Keeper Odyn to an eternal servitude as the bringer of souls to his gilded Halls of Valor: the golden realm for all slain spirits of Odyn's followers. Her servitude was not willing, but a punishment, and one for which she had let her hatred for Odyn simmer for millennia.
>
> When the Keeper Loken came with a promise of a way out, and subsequently broke her chains, she called upon her powers to bend the arcane energies of Azeroth into an impregnable seal around Odyn's halls, its inhabitants sealed within.
>
> Free from her servitude, Helya forged the mist-shrouded realm of Helheim as a new home for herself and her Val'kyr, though not all chose to follow her on this path. Instead, some chose to break bonds and disappear into the Shadowlands.
>
> There, just as they once guided fallen vrykul to the Halls of Valor, these Val'kyr have dubbed themselves *Spirit Healers*. From their refuge in the Shadowlands, they have kept an eye on those who enter the dark beyond, and have on occasion granted passage back for those they've found worthy.
>
> ***Encountering a Spirit Healer.*** If your adventurers have met an untimely demise and their quest rem&shy;ains unsolved, seeking out a Spirit Healer within the Shadowlands could be an option for them. The Spirit Healer may judge, or other&shy;wise be convinced, that it is not yet their time and return them to the realm of the living.

<div class='letterheader'></div>
<div class="mmletter mml-g"></div>
<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>
<img src='https://www.gmbinder.com/images/fA29o73.jpg' style='position:absolute; top:0px; right:-440px; width:1290px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-25px; width:900px' />

\pagebreakNum

### Apparition
An apparition is a spectral impression whose presence in the Material Plane has been caught in flux with the latent energies from a nearby ley line or other font of magical power. As a result, apparitions wield the power to weave their anguish and their resentment into powerful, often harrowing spells.

### Banshee
A banshee is the tormented remnant of an elven woman, whose death came to pass in the most gruesome manner -- with the fall of the Highborne, the first coming of the Bur&shy;ning Legion, and the fall of Quel'Thalas all noteworthy events from which banshees have been formed.

Robbed of their elven gift of immortality, the banshees were left to wander the world in tormented silence until they were discovered by Ner'zhul, the first Lich King. In return for a promise of servitude to the Scourge, Ner'zhul gifted the banshees their terrible, blood-curdling voice, which they in turn have used to enact their revenge.

Though some banshees still roam free in their own lamentation, most remain beholden to their bond with the Scourge. Some banshees, particularly those formed after the fall of Quel'Thalas, have since found new purpose among the Forsaken.

### Shade
Shades are much alike other ghosts, appearing as disembodied spirits left to wander the reaches between the physical realm and the darkness beyond. This, however, is as far as the similarities go.

While other ghostly beings are the remnants of those unwilling or unable to accept death, shades are formed through willing sacrifice: necromancers offering up their acolytes to better serve the undead Scourge.

Empowered by the Lich King, shades can remain unseen if they will it, detectable only by powerful magic. This allows them to act as the eyes and ears of their undead masters.

### Spectre
Much like the banshee, a spectre is the tormented remnant of an elven man, slain by monstrous foes and robbed of their immortality. Though spectres do not possess the anguished screams for which banshees are known and feared, they still remain a considerable danger to those who encounter them.

Driven both by a bitter resentment for the living and by their hubris in death, a spectre may attempt to lure unwary travelers into dangerous traps, waiting for an opportune moment to overpower them and seep away their life force.

### Wisp
Wisps are the disembodied spirits of deceased night elves, made one with the forest in their passing. Unlike other ghosts who wander the world in anguish, wisps use their spiritual being to bridge a connection ever closer to the forests where they delve.

Though silent for all but a soft, quiet humming, wisps are able to communicate with the living. Acting together in unison with the tree-like ancients, they act as guardians and caretakers -- often flourishing around druidic groves.

\columnbreak

### Wraith
Though they are beholden to their masters -- whether they necromantic cults or the undead Scourge -- wraiths are notorious for how they retain most of their intelligence and in&shy;dividuality, even in death. Self-motivated and exception&shy;ally cunning, it is not uncommon for a wraith to act by its own accord, in defiance of its master's plan.

Some wraiths may be found holding to the same sense of honour and law as they did in life, and may even be willing to negotiate with the living if prompted. Other wraiths, meanwhile, offer little more than a jealous rage for those who approach them. Spurred by a resentment for their undead state, these wraiths readily yearn for a chance to visit their anguish upon any unfortunate enough to cross their path.

### Ghost Template
Ghosts are the spectral remnants of intelligent beings who, for one reason or another, cannot rest easily in their graves. A ghost greatly resembles its corporeal form in life, but in some cases the spiritual form can be altered.

When a creature becomes a ghost, it retains its statistics unless otherwise is stated below. The ghost loses any trait that assumes a living physiology.

***Type.*** The ghost's type is undead, and it loses any other tags. It no longer requires air, food, drink or sleep.

***Speed.*** The ghost loses its original movement speed and gains fly 40 ft. (hover).

***Senses.*** The ghost has darkvision with a radius of 60 ft.

***Damage Resistances.*** The ghost gains resistance to acid, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks

***Damage Immunities.*** The ghost gains immunity to cold, necrotic and poison damage.

***Condition Immunities.*** The ghost can't be charmed, exhaustion, frightened, grappled, paralyzed, petrified, poisoned, prone, restrained

***Ethereal Sight.*** The ghost can see 60 ft. into the Spirit World when it is on the Material Plane, and vice versa.

***Incorporeal Movement.*** The ghost can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.

***New Action: Etherealness.*** The ghost enters the Spirit World from the Material Plane, or vice versa. It is visible on the Material Plane while it is in the Border Spirit World, and vice versa, yet it can't affect or be affected by anything on the other plane.

***Hit Points.*** If the creature already has three or more damage resistances or immunities, its hit points remain unchanged. Otherwise, the creature's hit points are reduced by a multiplier based on its challenge rating.

Using the Hit Points Based on Challenge Rating table, apply the appropriate multiplier to the creature's hit points to determine ghost's hit point.

#####  Hit Points Based on Challenge Rating
| Creature <br> Challenge Rating  | HP Multiplier |
|:-----------:|:------:|
|  1-10       | x 0.5  |
|  11-16      | x 0.65 |
|  17 or more | x 0.8  |

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>


\pagebreakNum

<div style='margin-top:103px;'></div>

___
> ## Ghost Knight
>*Medium undead (any race), any alignment*
> ___
> - **Armor Class** 18 (plate)
> - **Hit Points** 26 (4d8 + 8)
> - **Speed** 0 ft., fly 40 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|11 (+0)|14 (+2)|11 (+0)|11 (+0)|15 (+2)|
>___
> - **Saving Throws** Con +4, Wis +2
> - **Damage Resistances** acid, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** cold, necrotic, poison
> - **Condition Immunities** charmed, exhaustion, frightened grappled, paralyzed, petrified, poisoned, prone, restrained
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** any two languages
> - **Challenge** 3 (700 XP)
> ___
> ***Ethereal Sight.*** The ghost can see 60 ft. into the Spirit World when it is on the Material Plane, and vice versa.
>
> ***Incorporeal Movement.*** The ghost can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.
>
> ### Actions
> ***Multiattack.*** The ghost makes two melee attacks.
>
> ***Greatsword.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.
>
> ***Heavy Crossbow.*** *Ranged Weapon Attack:* +2 to hit, range 100/400 ft., one target. *Hit:* 5 (1d10) piercing damage.
>
> ***Leadership (Recharges after a Short or Long Rest).*** For 1 minute, the ghost can utter a special command or warning whenever a non-hostile creature that it can see within 30 feet of it makes an attack roll or a saving throw. The creature can add a d4 to its roll provided it can hear and understand the ghost. A creature can benefit from only one Leadership die at a time. This effect ends if the knight is incapacitated.
>
> ***Etherealness.*** The ghost enters the Spirit World from the Material Plane, or vice versa. It is visible on the Material Plane while it is in the Border Spirit World, and vice versa, yet it can't affect or be affected by anything on the other plane.
>
> ### Reactions
> ***Parry.*** The ghost adds 2 to its AC against one melee attack that would hit it. To do so, the knight must see the attacker and be wielding a melee weapon.

\columnbreak

<div style='margin-top:136px;'></div>

___
> ## Ghost Spy
>*Medium undead (any race), any alignment*
> ___
> - **Armor Class** 12
> - **Hit Points** 13 (3d8)
> - **Speed** 0 ft., fly 40 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|15 (+2)|10 (+0)|12 (+1)|14 (+2)|16 (+3)|
>___
> - **Skills** Deception +5, Insight +4, Perception +6, <br>Persuasion +5, Stealth +4
> - **Damage Resistances** acid, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** cold, necrotic, poison
> - **Condition Immunities** charmed, exhaustion, frightened grappled, paralyzed, petrified, poisoned, prone, restrained
> - **Senses** darkvision 60 ft., passive Perception 16
> - **Languages** any two languages
> - **Challenge** 1 (200 XP)
> ___
> ***Cunning Action.*** On each of its turns, the spy can use a bonus action to take the Dash, Disengage, or Hide action.
>
> ***Ethereal Sight.*** The ghost can see 60 ft. into the Spirit World when it is on the Material Plane, and vice versa.
>
> ***Incorporeal Movement.*** The ghost can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.
>
> ***Sneak Attack (1/Turn).*** The ghost deals an extra 7 (2d6) damage when it hits a target with a weapon attack and has advantage on the attack roll, or when the target is within 5 feet of an ally of the ghost that isn't incapacitated and the ghost doesn't have disadvantage on the attack roll.
>
> ### Actions
> ***Multiattack.*** The ghost makes two melee attacks.
>
> ***Shortsword.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) slashing damage.
>
> ***Hand Crossbow.*** *Ranged Weapon Attack:* +5 to hit, range 30/120 ft., one target. *Hit:* 5 (ld6 +3) piercing damage.
>
> ***Etherealness.*** The ghost enters the Spirit World from the Material Plane, or vice versa. It is visible on the Material Plane while it is in the Border Spirit World, and vice versa, yet it can't affect or be affected by anything on the other plane.

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>
<img src='https://www.gmbinder.com/images/LQhllM1.jpg' style='position:absolute; top:-300px; right:0px; width:1100px' />
<img src='https://www.gmbinder.com/images/TYBvp5o.png' style='position:absolute; top:-300px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:160px;'></div>

___
> ## Ghost Witch Doctor
>*Medium undead (any troll), chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 32 (5d8 + 10)
> - **Speed** 0 ft., fly 40 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|15 (+2)|14 (+2)|13 (+1)|17 (+3)|12 (+1)|
>___
> - **Saving Throws** Con +4, Wis +5
> - **Skills** Arcana +3, Insight +6, Medicine +6, Nature +6
> - **Damage Resistances** acid, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks.
> - **Damage Immunities** cold, necrotic, poison
> - **Condition Immunities** charmed, exhaustion, frightened grappled, paralyzed, petrified, poisoned, prone, restrained
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** Common, Zandali
> - **Challenge** 5 (1,800 XP)
> ___
> ***Ethereal Sight.*** The ghost can see 60 ft. into the Spirit World when it is on the Material Plane, and vice versa.
>
> ***Incorporeal Movement.*** The ghost can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.
>
> ***Loa's Blessing.*** The ghost has advantage on saving throws against being charmed.
>
> ***Spellcasting.*** The ghost is an 8th-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 14, +6 to hit with spell attacks). The troll has the following priest and shaman spells prepared:
>
> Cantrips (at will): *light, shocking grasp, spare the <br>&nbsp;&nbsp;&nbsp; dying, toll the dead*
> <br> 1st level (4 slots): *absorb elements, inflict wounds, <br>&nbsp;&nbsp;&nbsp; thunderwave*
> <br> 2nd level (3 slots): *gentle repose, lesser restoration*
> <br> 3rd level (3 slots): *bestow curse, lightning bolt, <br>&nbsp;&nbsp;&nbsp; revivify, speak with dead*
> <br> 4th level (2 slots): *banishment, death ward*
>
> ### Actions
> ***Multiattack.*** The ghost makes two quarterstaff attacks.
>
> ***Quarterstaff.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft, one target. *Hit:* 3 (1d6) bludgeoning damage, or 4 (1d8) bludgeoning damage if used with two hands to make a melee attack.

\columnbreak

<div style='margin-top:283px;'></div>

___
> ## Apparition
>*Medium undead, chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 22 (5d8)
> - **Speed** 0 ft., fly 40 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|1 (-5)|14 (+2)|11 (+0)|14 (+2)|10 (+0)|12 (+1)|
>___
> - **Damage Resistances** acid, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** cold, necrotic, poison
> - **Condition Immunities** charmed, exhaustion, frightened grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** understands any language it knew in life, but can't speak
> - **Challenge** 2 (450 XP)
> ___
> ***Incorporeal Movement.*** The apparition can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.
>
> ***Spellcasting.*** The apparition is a 4th-level spellcaster. Its spellcasting ability is Intelligence (spell save DC 12, +4 to hit with spell attacks). The apparition has the following mage spells prepared:
>
> Cantrips (at will): *✦ flurry, frostbite, ray of frost*
> <br> 1st level (4 slots): *armor of Agathys, ✦ frostfire bolt, <br>&nbsp;&nbsp;&nbsp; ice knife*
> <br> 2nd level (3 slots): *detect thoughts, hold person, <br>&nbsp;&nbsp;&nbsp; misty step*
>
> ***Sunlight Sensitivity.***  While in sunlight, the apparition has disadvantage on attack rolls, as well as on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Withering Touch.*** *Melee Weapon Attack:* Melee Weapon Attack: +3 to hit, reach 5 ft., one target. Hit: 15 (4d6 + 1) necrotic damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;22;4;12;21;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>
<img src='https://www.gmbinder.com/images/LQhllM1.jpg' style='position:absolute; top:-200px; right:0px; width:1100px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/TYBvp5o.png' style='position:absolute; top:-200px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Banshee
>*Medium undead, chaotic evil*
> ___
> - **Armor Class** 13
> - **Hit Points** 91 (14d8 + 28)
> - **Speed** 0 ft., fly 40 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|1 (-5)|16 (+3)|14 (+2)|11 (+0)|13 (+1)|19 (+4)|
>___
> - **Saving Throws** Wis +4, Cha +7
> - **Damage Resistances** acid, fire, lightning, <br/>thunder; bludgeoning, piercing, and slashing from nonmagical attacks.
> - **Damage Immunities** cold, necrotic, poison
> - **Condition Immunities** charmed, exhaustion, grappled, frightened,  paralyzed, petrified, poisoned, prone, restrained
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** Common, Darnassian or Thalassian
> - **Challenge** 7 (2,900 XP)
> ___
> ***Detect Life.*** The banshee can magically sense the presence of living creatures up to 5 miles away. She knows the general direction they're in but not their exact locations.
>
> ***Incorporeal Movement.*** The banshee can move through other creatures and objects as if they were difficult terrain. She takes 5 (1d10) force damage if she ends her turn inside an object.
>
>
> ### Actions
> ***Multiattack.*** The banshee can use its Banshee's Curse. It then makes two attacks with its withering touch.
>
> ***Withering Touch.*** *Melee or Ranged Weapon Attack:* +6 to hit, reach 5 ft. or range 30/60 ft., one target. *Hit:* 12 (2d8 + 3) necrotic damage.
>
> ***Banshee's Curse.*** One creature of the banshee's choice within 60 feet of it must make a DC 13 Constitution saving throw or have disadvantage on all ability checks, saving throws, and attack rolls until the end of the banshee's next turn.
>
> ***Wail (Recharge 4-6).*** The banshee releases a mournful wail. This wail has no effect on constructs and undead. All other creatures within 30 feet of her that can hear her must make a DC 13 Constitution saving throw, taking 22 (4d12) necrotic damage on a failed save, or half as much damage on a successful one.
>
> ***Possession (1/Day).*** One humanoid that the banshee can see within 5 feet of it must succeed on a DC 15 Charisma saving throw or be possessed by the banshee; the banshee then disappears, and the target is incapacitated and loses control of its body. The banshee now controls the body but doesn't deprive the target of awareness. The banshee can't be targeted by any attack, spell, or other effect except ones that turn undead, and it retains its alignment, Intelligence, Wisdom, Charisma, and immunity to being charmed and frightened. It otherwise uses the possessed target's statistics, but doesn't gain access to the target's knowledge, class features, or proficiencies.
> <br/>&nbsp;&nbsp;&nbsp; The possession lasts until the body drops to 0 hit points, the banshee ends it as a bonus action, or the banshee is turned or forced out by an effect like the *dispel evil and good* spell. When the possession ends, the banshee reappears in an unoccupied space within 5 feet of the body.
>
> ### Reactions
> ***Anti-magic Shell.*** The banshee adds 3 to its AC against one spell attack that would hit it. To do so, the banshee must see the attacker.
>
> <br/> <br/><!-- https://wc5e-cr-calculator.frogvall.com/?1;13;91;6;13;44;0;24;0;24;0;0;0;0;0;0;0;1;;;1;2;;;;;;;;;;1;;;;1;1;;;10;;;;;; -->

</div>

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>
<img src='https://www.gmbinder.com/images/umjLUNC.jpg' style='position:absolute; top:0px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:-40px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:310px;'></div>

___
> ## Shade
>*Medium undead, lawful evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 11 (2d8 + 2)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|6 (-2)|14 (+2)|13 (+1)|6 (-2)|10 (+0)|8 (-1)|
>___
> - **Skills** Stealth +4 (+6 in dim light or darkness)
> - **Damage Vulnerabilities** radiant
> - **Damage Resistances** acid, cold, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** necrotic, poison
> - **Condition Immunities** exhaustion, frightened, grappled paralyzed, petrified, poisoned, prone, restrained
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Telepathy 60 ft.
> - **Challenge** 1/2 (100 XP)
> ___
> ***Amorphous.*** The shade can move through a spade as narrow as 1 inch wide without squeezing.
>
> ***Shadow Stealth.*** While in dim light or darkness, the shade can take the Hide action as a bonus action.
>
> ***Sunlight Weakness.*** While in sunlight, the shade has disadvantage on attack rolls, ability checks, and saving throws.
>
> ### Actions
> ***Wisdom Drain.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 7 (2d4 + 2) necrotic damage, and the target's Wisdom score is reduced by 1d4. If the target's Wisdom score is reduced to 0, it is para&shy;lyzed until it regains at least one point of Wisdom.
>
> ***Invisibility (Recharges after a Short or Long Rest).*** The shade magically turns invisible until it attacks, or until its concentration is broken, up to 1 hour (as if con&shy;centrating on a spell)<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;11;4;12;7;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;1;;;; -->

\columnbreak

<div style='margin-top:240px;'></div>

___
> ## Spectre
>*Medium undead, chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 72 (16d8)
> - **Speed** 0 ft., fly 50 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|1 (-5)|14 (+2)|11 (+0)|10 (+0)|11 (+0)|15 (+2)|
>___
> - **Saving Throws** Wis +2, Cha +4
> - **Damage Resistances** acid, cold, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** necrotic, poison
> - **Condition Immunities** charmed, exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Common, Darnassian or Thalassian
> - **Challenge** 3 (700 XP)
> ___
> ***Incorporeal Movement.*** The spectre can move through other creatures and objects as if they were difficult terrain. He takes 5 (1d10) force damage if he ends his turn inside an object.
>
> ### Actions
> ***Siphon Life.*** *Melee Spell Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 18 (4d8) necrotic damage. The target must succeed on a DC 12 Constitution saving throw or its hit point maximum is reduced by an amount equal to the damage taken. This reduction lasts until the creature finishes a long rest. The target dies if this effect reduces its hit point maximum to 0. The spectre regains hit points by an amount equal to half the necrotic damage dealt.
>
> ***Horrifying Wail.*** Each non-undead creature within 60 feet of the spectre that can hear it must succeed on a DC 12 Wisdom saving throw or be frightened for 1 minute. A frightened creature can repeat the saving throw at the end of each of its turns, ending the frightened condition on itself on a success.
<br> &nbsp;&nbsp;&nbsp; If a target's saving throw is successful or the effect ends for it, the target is immune to this spectre's Horrifying Wail for the next 24 hours.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;72;4;12;18;0;0;0;0;0;0;0;0;0;0;0;1;;;1;2;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>

<img src='https://www.gmbinder.com/images/wJZvXi2.png' class='inkblot inkblot-green' style='position:absolute; top:-100px; right:50px; width:700px;transform:rotate(50deg)' />
<img src='https://www.gmbinder.com/images/m5HeoK6.png' style='position:absolute; top:-76px; right:325px; width:500px; z-index:100' />
<img src='https://www.gmbinder.com/images/Yvnlco0.png' style='position:absolute; top:-50px; right:20px; width:400px' />

\pagebreakNum

<div style='margin-top:115px;'></div>

___
> ## Wisp
>*Small fey, neutral good*
> ___
> - **Armor Class** 18
> - **Hit Points** 14 (4d6)
> - **Speed** 0 ft., fly 40 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|1 (-5)|26 (+8)|10 (+0)|13 (+1)|14 (+2)|11 (+0)|
>___
> - **Damage Resistances** acid, cold, fire, lightning, thunder; bludgeoning, piercing, and slashing from nonmagical attacks.
> - **Damage Immunities** poison, radiant
> - **Condition Immunities** exhaustion, grappled, paralyzed, poisoned, prone, restrained, unconscious
> - **Senses** darkvision 120 ft., passive Perception 12
> - **Languages** the languages it knew in life
> - **Challenge** 1/2 (100 XP)
> ___
> ***Ephemeral.*** The wisp can't wear or carry anything.
>
> ***Incorporeal Movement.*** The wisp can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.
>
> ***Variable Illumination.*** The wisp sheds bright light in a 5- to 20-foot radius and dim light for an additional number of feet equal to the chosen radius. The wisp can alter the radius as a bonus action.
>
> ### Actions
> ***Intertwine.*** The wisp enters the space of another creature and attempts entwine it in place. The target must pass a DC 12 Wisdom saving throw or be paralyzed for 1 minute. At the end of the target's turns, it can make another save, ending the paralysis on a successful one. While the wisp has a creature intertwined, attack rolls against it has disadvantage. If a target's saving throw is successful or the effect ends for it, the target is immune to this wisp's intertwine for the next 24 hours.
>
> ***Renew (Recharge 5-6).*** One plant that the wisp can see within 5 feet of it is renewed by the wisp; the wisp disappears. The wisp can't be targeted by any attack, spell, or other effect while renewing a plant. The renewed plant regains 10 hit points at the start of its turn. If the plant takes fire damage, the renew doesn't function at the start of its next turn. The plant dies if it starts its turn with 0 hit points.
> <br>&nbsp;&nbsp;&nbsp; The renew lasts until the renewed plant drops to 0 hit points, the wisp ends it as a bonus action. When the plant takes damage, the wisp must pass a Concen&shy;tration saving throw (as if concentrating on a spell) or be pushed out of the plant.<!-- https://wc5e-cr-calculator.frogvall.com/?0;18;14;4;12;0;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:700px;'></div>

> ##### Will of the Forest
> Five wisps within 30 feet of each other are able to cast powerful spells. Each of the five must use its action and movement on three consecutive turns to call upon the powers of Elune and must maintain concentration while doing so (as if concentrating on a spell). When all five have finished their third turn of the ritual, the wisps gain the Spellcasting trait and can cast one spell in total at a target or point within 120 feet, no matter the spells normal range.
>
> ***Innate Spellcasting.*** The wisps spellcasting ability is Wisdom (spell save DC 12). They can innately cast one of the following spells as a 4th-level spell, requiring no material components. If a spell requires concentration, all five wisps concentration must be broken to remove the spell:
> <div style='margin-top:0px;'></div>
>
> 1/ritual: *banishment, charm monster, confusion, <br>&nbsp;&nbsp;&nbsp; dispel magic, spike growth, wind wall*

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>
<img src='https://www.gmbinder.com/images/kaSbStn.jpg' style='position:absolute; top:0px; right:0px; width:1000px' />
<img src='https://www.gmbinder.com/images/TYBvp5o.png' style='position:absolute; top:300px; right:-200px; width:900px;transform:rotate(20deg)' />
<img src='https://www.gmbinder.com/images/LvWTTOl.png' style='position:absolute; top:0px; right:120px; width:900px;transform:scalex(-1)' />

\pagebreakNum

<br>

\columnbreak

<div style='margin-top:100px;'></div>

___
> ## Wraith
>*Medium undead, lawful evil*
> ___
> - **Armor Class** 14
> - **Hit Points** 90 (12d8 + 36)
> - **Speed** 0 ft., fly 60 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|6 (-2)|16 (+3)|16 (+3)|12 (+1)|14 (+2)|15 (+2)|
>___
> - **Damage Resistances** acid, cold, fire, lightning, thunder; bludgeoning, piercing, and slashing from non&shy;magical attacks and weapons that aren't silvered
> - **Damage Immunities** necrotic, poison
> - **Condition Immunities** charmed, exhaustion, grappled, paralyzed, petrified, poisoned, prone, restrained
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** the languages it knew in life
> - **Challenge** 5 (1,800 XP)
> ___
> ***Incorporeal Movement.*** The wraith can move through other creatures and objects as if they were difficult terrain. It takes 5 (1d10) force damage if it ends its turn inside an object.
>
> ***Sunlight Sensitivity.*** While in sunlight, the wraith has disadvantage on attack rolls, as well as on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Life Drain.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one creature. *Hit:* 21 (4d8 + 3) necrotic damage. The target must succeed on a DC 14 Constitution saving throw or its hit point maximum is reduced by an amount equal to the damage taken. This reduction lasts until the target finishes a long rest. The target dies if this effect reduces its hit point maximum to 0.
>
> ***Create Spawn.*** The wraith targets a humanoid within 10 feet of it that died a violent death and has been dead for no longer than 1 minute. The target's spirit rises as a wraith spawn in an unoccupied space by the corpse, under the wraith's control. The wraith spawn has the same statistics as the wraith, except that it has an Intelligence and Charisma score of 1, it cannot speak or use Create Spawn, and its Life Drain does not reduce a target creature's hit point maximum. The wraith can have no more than two wraith spawns active under its control at one time.<!-- https://wc5e-cr-calculator.frogvall.com/?1;14;90;6;12;21;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">G</div>
<div class='footnote'>GHOSTS </div>
<img src='https://www.gmbinder.com/images/zm4b43n.jpg' style='position:absolute; top:0px; right:150px; width:810px' />
<img src='https://www.gmbinder.com/images/Tg5WzQk.png' style='position:absolute; top:0px; right:-150px; width:900px' />

\pagebreakNum

## Gnolls
Gnolls are feral humanoids, resembling bipedal hyenas. They are known to attack frontier settlements and unsuspect&shy;ing hamlets without warning, rushing their way through to grab whatever they can escape with.

***Rampant Scavengers.*** Gnolls are notorious for how they hunt. Even those fortunate enough to spot a pack settling their camp might only have hours at best to prepare, before the gnolls come charging in to plunder.

In their wake, they leave little more than razed buildings, burnt crops, and gnawed remains. The easier their target, the better. If they perceive no threat to the pack after the raid has been done, they might stick around in one location for longer. If they fear retaliation from armed guards, like a nearby garrison, the pack will abandon what they must in order to move on as soon as they can.

***Hungering Nomads.*** Gnolls are not known for leaving anything lasting. Their weapons and armour are all scavenged from their victims, alongside trophies sewn into their patchwork clothing -- ears, teeth, scalps, and more.

To a gnoll, meat is meat. Once they've gone for the kill, they will gnaw the bones to the marrow. Though they are intelligent beasts, they won't go shy of cannibalizing rival packs and outcasts if they are hungry enough. Even if one of their own die in a fight, they'll try to drag the corpse away in order to eat it later.

### Gnoll Brute
Gnolls are known for their immense strength, though some of them show it better than the rest. A gnoll brute is hardly intelligent, but it is guaranteed to be ferocious without equal.

### Gnoll Mystic
Some gnolls are sensitive to the elemental forces coursing through the world. Though the powers they wield would be considered novice for true mages, these gnolls are both feared and respected by their pack; elevated to the title of mystics and regarded as wise beyond compare.

### Gnoll Pack Lord
The alpha of a gnoll pack is its pack lord. Keeping a steel-jawed hold on any gnoll following it, the pack lord claims first pick from the pack's raids, and many have been witnessed wearing ornate decor in the form of piercing and grotesque trophies.

### Gnoll Names and Languages
Gnolls speak Low Common and Gnoll; presumably a guttural offshoot of the former. Their names are often just descriptions, aiming to intimidate. A pack lord chooses the name for its pack in a similar fashion.

<div style='margin-top:-5px;'></div>

**Gnoll Names:** Dirtpaw, Cackler, Blackfang, White-Eye
<br />&nbsp;&nbsp;&nbsp; Snarlface, Loose-Tooth, Yowler
<br />**Pack Names:** Riverpaw, Mudtail, Ashfang, Bloodeyes,
<br />&nbsp;&nbsp;&nbsp; Road-Robbers, Rotclaws, Grimepack

\columnbreak

___
> ## Gnoll
> *Medium humanoid (gnoll), chaotic evil*   
> ___  
> - **Armor Class** 14 (hide armor)  
> - **Hit Points** 22 (4d8 + 4)
> - **Speed** 30 ft.  
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 11 (+0)|13 (+1)|12 (+1)|6 (-2)|10 (+0)|7 (-2)|
> ___  
> - **Senses** darkvision 60 ft., passive Perception 10  
> - **Languages** Low Common, Gnoll  
> - **Challenge** 1/2 (100 XP)  
> ___
>
> ***Last Stand.*** When the gnoll is reduced to 0 hit points, it can use its reaction to make a bite attack before falling unconscious.    
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one creature. *Hit:* 2 (1d4) piercing damage.   
>
> ***Scimitar.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) slashing damage.   
>
> ***Light Crossbow.*** *Ranged Weapon Attack:* +3 to hit, range 80/320 ft., one target. *Hit:* 5 (1d8 + 1) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;22;3;12;5;0;5;0;5;2;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;;  -->

___
> ## Gnoll Brute
> *Medium humanoid (gnoll), chaotic evil*   
> ___  
> - **Armor Class** 14 (hide armor)  
> - **Hit Points** 32 (5d8 + 10)  
> - **Speed** 30 ft.  
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 15 (+2)|13 (+1)|14 (+2)|6 (-2)|10 (+0)|7 (-2)|
> ___  
> - **Skills** Perception +2
> - **Senses** darkvision 60 ft., passive Perception 12  
> - **Languages** Low Common, Gnoll  
> - **Challenge** 1 (200 XP)
> ___
>
> ***Brute.*** A melee weapon deals one extra die when the gnoll hits with it (included in the attack).
>
> ***Last Stand.*** When the gnoll is reduced to 0 hit points, it can use its reaction to make a bite attack before falling unconscious.       
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one creature. *Hit:* 7 (2d4 + 2) piercing damage.   
>
> ***Greatclub.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 11 (2d8 + 2) bludgeoning damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;32;4;12;11;0;11;0;11;7;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">G</div>
<div class='footnote'>GNOLLS </div>

<img src='https://www.gmbinder.com/images/Z8yFnva.jpg' style='position:absolute; top:950px; right:325px; width:450px;mix-blend-mode:darken' />

\pagebreakNum

<div style='margin-top:472px;'></div>

___
> ## Gnoll Mystic
> *Medium humanoid (gnoll), chaotic evil*   
> ___  
> - **Armor Class** 12 (leather armor)  
> - **Hit Points** 22 (4d8 + 4)  
> - **Speed** 30 ft.  
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 10 (+0)|13 (+1)|12 (+1)|6 (-2)|14 (+2)|9 (-1)|
> ___  
> - **Skills** Insight +2, Perception +4, Deception +4
> - **Senses** darkvision 60 ft., passive Perception 14  
> - **Languages** Low Common, Gnoll  
> - **Challenge** 1 (200 XP)
> ___
>
> ***Last Stand.*** When the gnoll is reduced to 0 hit points, it can use its reaction to make a bite attack before falling unconscious.    
>
> ***Spellcasting.*** The gnoll is a 3rd-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). It has the following shaman spells prepared:     
>
> Cantrips (at will): *✦ lightning blast, gust*
> <br> 1st level (4 slots): *absorb elements, cure wounds, <br>&nbsp;&nbsp;&nbsp; detect magic, fog cloud*
> <br> 2nd level (2 slots): *dust devil, heat metal, ✦ lava burst*
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one creature. *Hit:* 2 (1d4) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;22;4;12;21;0;21;0;6;2;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:300px;'></div>

___
> ## Gnoll Pack Lord
> *Medium humanoid (gnoll), chaotic evil*   
> ___  
> - **Armor Class** 17 (chain shirt, shield)  
> - **Hit Points** 52   (8d8 + 16)
> - **Speed** 30 ft.  
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 17 (+3)|14 (+2)|15 (+2)|9 (-1)|12 (+1)|13 (+1)|
> ___  
> - **Skills** Athletics +5, Survival +3, Intimidation +3
> - **Senses** darkvision 60 ft., passive Perception 11  
> - **Languages** Low Common, Gnoll  
> - **Challenge** 3 (700 XP)
> ___
>
> ***Last Stand.*** When the gnoll is reduced to 0 hit points, it can use its reaction to make a bite attack before falling unconscious.    
>
> ***Rampage.*** When the gnoll reduces a creature to 0 hit points with a melee attack on its turn, the gnoll can take a bonus action to move up to half its speed and make a bite attack.   
>
> ### Actions
> ***Multiattack.*** The gnoll uses its Kill Command, if it can. It then makes two melee weapon attacks or one heavy crossbow attack.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 5 (1d4 + 3) piercing damage.   
>
> ***Battleaxe.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) slashing damage or 8 (1d10 + 3) slashing damage if used with two hands to make a melee attack.   
>
> ***Heavy Crossbow.*** *Ranged Weapon Attack:* +4 to hit, range 100/400 ft., one target. *Hit:* 7 (1d10 + 2) piercing damage.
>
> ***Kill Command (Recharge 5-6).*** The gnoll targets one ally it can see within 30 feet of it. If the target can see and hear it, the target can make one weapon attack as a reaction.<!-- https://wc5e-cr-calculator.frogvall.com/?0;17;52;5;12;14;0;14;0;14;5;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;1;;10;;;;;; -->

<div class="pageLetter">G</div>
<div class='footnote'>GNOLLS </div>
<img src='https://www.gmbinder.com/images/ZIjk1ea.jpg' style='position:absolute; top:-70px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/pZatMx5.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:480px;'></div>

### Gnoll King Hogger
Ask any person in Elwynn forest, from the simplest farmer to a soldier of the king's guard, and they can tell you stories of the Gnoll King and his horrific riverpaws. This notorious gnoll is unlike any other. As the leader of the Riverpaw clan he has transformed the ragtag gnolls into an organized clan wreaking havoc through the forests of Elwynn.

**The Gnoll King.** Hogger has crowned himself the *king* of gnolls, a title well deserved for the beast. He is a formidable foe on his own, and any adventurer seeking to take him down is advised to be well prepared. It is solely for his prowess in controlling other gnolls, making them work in unison, that he enjoys his status.

**Cheap Tactics**. The mad gnoll will stop at nothing to achieve his goals, and is not beneath utilizing dirty tricks to gain an advantage in doing so. Hogger is not a creature of honor and won't let notions of a fair fight get in his way. After all, there are no real laws of engagement for a gnoll; all that matters is that his quarry dies in the end.

***Unknown Alliances.*** Although many of their supplies are considered plundered goods, the Riverpaw clan have access to high quality steel tools, arms, and armor. All of it suggests that the gnolls -- or Hogger himself -- have an understanding with some unknown ally, one capable of escorting such tools to them in the dead of night. It is unknown, however, who such allies would even be.

**Public Enemy No. 1.** Through Elwynn forest and other nearby regions, the Riverpaw clan have gained a notorious reputation. With their supply of quality weaponry they are able to strike at small-and-large settlements alike.

Ever since the gnoll king took charge, the Riverpaws have become a thorn in the side of the Kingdom of Storm&shy;wind. Far and wide trough Stormwind's settlements, posters can be found offering rewards for their heads.

\columnbreak

<div style='margin-top:297px;'></div>

### Hogger's Lair
Hogger is a notorious villain. Even when he is captured and put under lock-and-key, the gnoll king is still capable of rallying the creatures around him. Hogger's lair reeks of death, as the carcasses of previous meals are scattered across the floor and decorated on spikes. 

Through his life, Hogger has had two different lairs, both of which are described in further detail below:

***Hogger Hill.*** In the southwestern thickets of Elwynn forest, unlucky travelers may stumble upon Hogger Hill.

A hill of insignificant proportions, it has become home to the Riverpaws; a clan of gnolls ruled with an iron fist and grim temper by Hogger himself. Adventures are unlikely to ever find Hogger alone, as his clan is never far away and willing to rush to his aid in the event that a fight breaks out.

***Stockades.*** Rumors claim that hogger was once caught by Alliance troops and locked away in Stormwind's stock&shy;ades. His loyal Riverpaw's would use the cover of night to sneak into Stormwind, tearing apart the guards keeping watch over the prison. From the depths of the stockades, he would turn the other prisoners to his side, claiming its torch-lit tunnels as his domain.

#### Lair Actions
On initiative count 20 (losing initiative ties), Hogger takes a lair action to cause one of the following effects:

 - Hogger screams for aid. 1d4 **gnolls** within 300 feet of Hogger that can hear him rush to his side, appearing in a space within 60 feet of him. This lair action has no effect if there are no gnolls within 300 feet of Hogger.
 - Each gnoll that Hogger can see can use its reaction to move up to its speed without provoking attacks of opportunity.
 - Until the next initiative count 20, all gnolls within the lair are enraged, causing them to have advantage on melee weapon attack rolls and causing attack rolls to have advantage against them.

#### Lair Traits
Hogger's lair might have any or all of the following effects in place:

 - The lair is considered difficult terrain for any non-gnoll creature that moves across it.
 - Any gnoll within the lair has advantage on saving throws against being charmed or frightened.

<div class="pageLetter">G</div>
<div class='footnote'>GNOLLS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot inkblot-green' style='top:-150px; right:0px; width:500px; transform:rotate(30deg)'>
<img src="https://www.gmbinder.com/images/B2sq3QS.png" style="position:absolute;top:0px;right: 350px;width:400px;transform:rotate(5deg);z-index: 200;filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">
<img src="https://www.gmbinder.com/images/qTyTr67.png" style="position:absolute;top: 52px;right: 95px;transform: rotate(-3deg);z-index: 100;filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Gnoll King Hogger
> *Medium humanoid (gnoll), chaotic evil*
> ___
> - **Armor Class** 15 (chain shirt)
> - **Hit Points** 82  (11d8 + 33)
> - **Speed** 30 ft.
> ___
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 18 (+4)|14 (+2)|16 (+3)|9 (-1)|14 (+2)|13 (+1)|
> ___
> - **Skills** Athletics +7, Intimidation +7, Survival +5
> - **Senses** darkvision 60 ft. passive Perception 12
> - **Languages** Low Common, Gnoll
> - **Challenge** 5 (1800 XP)
> ___
>
> ***Charge.*** If Hogger moves at least 15 feet straight toward a target and then hits it with a battleaxe attack on the same turn, the target takes an extra 7 (2d6) slashing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ***Last Stand.*** When Hogger is reduced to 0 hit points, he can use his reaction to make a bite attack before falling unconscious.
>
> ***Rampage.*** When Hogger reduces a creature to 0 hit points with a melee attack on its turn, he can take a bonus action to move up to half his speed and make a bite attack.
>
> ### Actions
> ***Multiattack.*** Hogger uses his Kill Command, if he can. He then makes two melee weapon attacks.
>
> ***Bite.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one creature. *Hit:* 6 (1d4 + 4) piercing damage.
>
> ***Battleaxe.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 9 (1d10 + 4) slashing damage.
>
> ***Kill Command.*** Hogger targets one ally he can see within 30 feet of him. If the target can see and hear him, the target can make one weapon attack as a reaction.
>
> ### Reactions
>
> ***Headbutt.*** Hogger headbutts a creature within 5 feet that missed him with an attack. The creature must succeed on a DC 13 Constitution saving throw or be stunned until the end of Hogger's next turn. To do so, Hogger must see the attacker.
>
> ### Legendary Actions
> Hogger can take 3 legendary actions, choosing from the options below. Only one legendary action option can be used at a time and only at the end of another creature's turn. Hogger regains spent legendary actions at the start of his turn.
>
> **Attack.** Hogger makes one melee weapon attack.
> <br> **Move.** Hogger move up to half his speed.
> <br> **Kill Command (Costs 2 Actions).** Hogger uses Kill <br>&nbsp;&nbsp;&nbsp; Command.<!-- https://wc5e-cr-calculator.frogvall.com/?1;15;82;7;12;45;7;45;0;45;6;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;1;;10;;;;;; -->

</div>

<div class="pageLetter">G</div>
<div class='footnote'>GNOLLS </div>
<img src='https://www.gmbinder.com/images/sJ82mfc.jpg' style='position:absolute; top:-100px; right:0px; width:800px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/pZatMx5.png' style='position:absolute; top:430px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:295px;'></div>

___
> ## Harvest Golem
>*Large construct, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 66 (7d10 + 30)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|9 (-1)|18 (+4)|3 (-4)|8 (-1)|1 (-5)|
>___
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison, psychic
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** understands the languages of its creator but can't speak
> - **Challenge** 4 (1,100 XP)
> ___
> ***Charge.*** If the golem moves at least 15 feet straight toward a target and then hits it with a claw attack on the same turn, the target takes an extra 7 (2d6) slashing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ***False Appearance.*** While the harvest golem remains motionless, it is indistinguishable from an ordinary scarecrow.
>
> ***Immutable Form.*** The golem is immune to any spell or effect that would alter its form.
>
> ### Actions
> ***Multiattack.*** The golem makes two claw attacks.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) slashing damage.
>
> ***Razer Claws (Recharge 5-6).*** The golem upper body spins in a circle, slashing it claws at creatures within 5 feet of it. Each creature must make a DC 13 Dexterity saving throw, taking 18 (4d8) slashing damage on a failed save, or half as much damage on a success.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;66;4;12;26;7;36;0;26;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:300px;'></div>

## Golems
Though a golem is made from humble materials — flesh and bones, metal and stone — its creation is a complex process, wrought with magic. At the hands of a skilled creator, their power, durability, and potential is nothing short of astonishing.

These constructs hold no ambition, need no sustenance, feel no pain, and know no remorse. Most golems are made with a singular purpose in mind; usually as a guardian for a person or a place, or as a construct of war.

***Blind Obedience.*** A golem is created to perform its given task, without fault. If a golem is left without any new instructions, it will continue to follow its current orders to the best of its abilities. If it is unable to do so, it will either remain idle until new orders are given or break down into a violent rampage. It cannot think or act for itself. Though it understands its commands perfectly, it has no real grasp of language and cannot be tricked or reasoned with.

***Constructed Nature.*** A golem doesn't require air, food, drink, or sleep.

### Arcane Golem
Arcane golems are hulking constructs, powered by their crystallized arcane core, that are commonly employed as peacekeepers and defenders. Deep grooves are often carved into their outer shell, allowing the energies from their crystal to surge over them in colorful patterns.

They are highly favoured among blood elves, both for their sturdy build and for their magical resilience. In Quel'thalas, they vigilantly patrol the streets within the city and beyond.

### Harvest Golem
A lumbering figure skulking across the fields, with razor-sharp claws and blazing, orange eyes: that is the visage of the Harvest Golem. These large, terrifying 'scarecrows' sow terror and wreak havoc across the fallow fields of Westfall. Where they came from or who made them still remains a mystery, but it is clear as day that they have been programmed with a single goal in mind — driving the farmers from the land, killing them if necessary.

Anyone looking to cross Westfall would be wise to stay alert, look out for any odd figures in the distance, and keep clear of the fields after nightfall.

<div class="pageLetter">G</div>
<div class='footnote'>GOLEMS </div>

<img src='https://www.gmbinder.com/images/tiU4RnD.png' class='inkblot' style='top:-100px; right:150px; width:600px; transform:rotate(80deg)' />
<img src='https://www.gmbinder.com/images/auDVjw8.png' style='position:absolute; top:-45px; right:170px; width:700px; transform:scalex(-1)' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Arcane Golem
>*Large construct, unaligned*
> ___
> - **Armor Class** 12 (17 with *shield*)
> - **Hit Points** 95 (10d10 + 40)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|19 (+4)|9 (-1)|18 (+4)|20 (+5)|11 (+0)|1 (-5)|
>___
> - **Damage Immunities** poison, psychic; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 120 ft., passive Perception 10
> - **Languages** understands the languages of its creator but can't speak
> - **Challenge** 8 (3,900 XP)
> ___
> ***Immutable Form.*** The golem is immune to any spell or effect that would alter its form.
>
> ***Innate Spellcasting.*** The golem's innate spellcasting ability is Intelligence (spell save DC 16). The golem can innately cast the following spells, requiring no material components.
>
> At will: *detect magic, magic missile, shield*
> <br> 3/day each: *counterspell, dispel magic*
> <br> 1/day each: *✦ arcane explosion, wall of force*
>
> ***Magic Resistance.*** The golem has advantage on saving throws against spells and other magical effects.
>
> ***Magic Weapon.*** The golem's weapon attacks are magical.
>
> ### Actions
> ***Multiattack.*** The golem makes two slam attacks.
>
> ***Arcane Slam.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) bludgeoning damage plus 4 (1d8) force damage.
>
> ***Slow (Recharge 5-6).*** The golem targets one or more creatures it can see within 10 feet of it. Each target must make a DC 16 Wisdom saving throw against this magic. On a failed save, a target can't use reactions, its speed is halved, and it can't make more than one attack on its turn. In addition, the target can take either an action or a bonus action on its turn, not both. These effects last for 1 minute. A target can repeat the saving throw at the end of each of its turns, ending the effect on itself on a success.<!-- https://wc5e-cr-calculator.frogvall.com/?1;17;95;0;16;54;0;34;0;34;0;0;0;0;0;0;0;;1;;;3;;;;;;;;;;1;1;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">G</div>
<div class='footnote'>GOLEMS </div>
<img src='https://www.gmbinder.com/images/2OoW8Ni.jpg' style='position:absolute; top:-125px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:100px; right:0px; width:900px' />

\pagebreakNum

## Grell
A grell is a small, long-armed forest spirit with pointed ears and an accentuated brow. Though they are uncannily similar to imps, a grell is very large by comparison and lack any other features typical for a demon.

Among explorers, researchers, and naturalists, it is speculated that the similarities between grells and imps are not coincidental, and that the first imps were in fact grells fallen to corruption during the first invasion of the Burning Legion. Such theories are widespread, but have never been confirmed nor denied.

***Wild Presence.*** Most grells have skin in shades of green, orange, or brown, mimicking the wilderness where they dwell. Their arms and legs are covered in dense fur, and their hands and feet are all fitted with sharp claws. It is common for grells to fashion themselves simple clothes, as well as other adornments -- such as ear and nose-rings.

Some have speculated as to whether these adornments serve a purpose, such as magical foci for casting spells, or if they are just for decoration.

***Fiendish Personality.*** It is said that the grell exist as an embodiment of the wild, uncanny side of nature, and their personality shows this notion all too well. A grell on its own poses no particular danger, but a gang of grells working together can be a real threat to settlements and communities in their vicinity.

Grells who commit to keeping in a pack like this have been witnessed actively searching for travellers to ambush, overwhelm, and steal from. Though their diet mainly consists of moss, tubers, and mushrooms, it is not unheard of for a grell pack to hunt wild game.

<div style="margin-top:44px;"></div>

___
> ## Grell
>*Small fey, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 7 (2d6)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|13 (+1)|11 (+0)|8 (-1)|10 (+0)|12 (+1)|
>___
> - **Skills** Stealth +3
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Low Common
> - **Challenge** 1/8 (25 XP)
> ___
> ***Innate Spellcasting.*** The grell's innate spellcasting ability is Charisma (spell save DC 11, +3 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *✦ solar wrath*, *minor illusion*
> <br> 1/day each:  *blur*, *misty step*
>
> ### Actions
> ***Claw.***  *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) slashing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;11;7;3;1;4;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style="margin-top:467px;"></div>

___
> ## Vile Grell
>*Small fey, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 18 (4d6 + 4)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|14 (+2)|12 (+1)|8 (-1)|10 (+0)|13 (+1)|
>___
> - **Skills** Stealth +4
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Low Common
> - **Challenge** 1/2 (100 XP)
> ___
> ***Nimble Escape.*** The grell can take the Disengage or Hide action as a bonus action on each of its turns.
>
> ***Innate Spellcasting.*** The grell's innate spellcasting ability is Charisma (spell save DC 11, +3 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *✦ solar wrath*, *minor illusion*
> <br> 2/day each:  *blur*, *misty step*
>
> ### Actions
> ***Claw.***  *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) slashing damage.
>
> ***Scimitar.***  *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) slashing damage.<!--https://wc5e-cr-calculator.frogvall.com/?0;12;18;4;1;5;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;1;;;;;;10;;;;;; -->

<div class="pageLetter">G</div>
<div class='footnote'>GRELL </div>
<img src='https://www.gmbinder.com/images/wJZvXi2.png' class='inkblot' style='top:-100px; right:-120px; width:600px'>
<img src='https://www.gmbinder.com/images/4xBV4kG.png' style='position:absolute; top:45px; right:-80px; width:500px;transform:scalex(-1); z-index:100' />

\pagebreakNum

<div style='margin-top:140px;'></div>

## Harpies
Taking glee in suffering and death, the sadistic harpy is always on the hunt for prey. They are vicious predators, well-known for luring adventures back to their craggy lairs and a certain death.

A harpy combines the body, arms, and head of a night elf with the legs and wings of a hunting bird. Its wicked talons can rip flesh from bone, and its graceful wings lets it soar silently through the air as it hunts for its next kill. It is said that in the eyes of every harpy shines the evil dwelling in their heart.

***Noxious Nests.*** Harpies nest in high-perched, hard-to-reach places, from which they can terrorize their surroundings. A flock of harpies left unchecked may leave destruction in their wake; killing anything they encounter, leaving only their noxious odor in their wake. This stench, a mixture of rotting flesh and mottled feathers, makes it easy to discern the whereabouts of an active nest.

***Precious Collectors.*** These winged humanoids place great value in shiny baubles, ornate trinkets, rare gems, and ores, using them to adorn themselves and their nests. They may be willing to barter and negotiate with travellers and settlements, if there is a chance for them to claim a pretty prize from the ordeal. Whatever calm such trade may instill is never more than a temporary measure, before the harpies take wing to pillage once again.

***Beguiling Creatures.*** Harpies resembles malformed night elves, decked in feathers and given wings. Though they are a repulsive presence, they could be considered quite beautiful from afar -- and only become more beautiful as they grow older, with a strikingly vibrant plumage.

They are incapable of producing male children, as their eggs always hatch females. To this end, their survival relies on their ability to beguile and entrap males from other races, keeping them around until the end of their mating season before killing them off for food.

### Harpy Witch
Some harpies are capable of wielding the forces of nature at their will. These harpy witches are powerful individuals within their nest, with the most powerful exploiting their powers to rise to a near regal status. Keeping any semblance of control in a nest of harpies is a formidable task, driving those who try to extreme measures.

> ##### Variant: Beguiling Harpy
> Some harpies can have a special ability that allows them to charm humanoids.
>
> ***Innate Spellcasting (2/day).*** The harpy's can innately cast *charm person*, requiring no material or somatic components. Its spellcasting modifier is Wisdom.

<div class='letterheader'></div>
<div class="mmletter mml-h"></div>
<div class="pageLetter">H</div>
<div class='footnote'>HARPIES </div>
<img src='https://www.gmbinder.com/images/wJyeYKG.jpg' style='position:absolute; top:0px; right:-300px; width:900px' />
<img src='https://www.gmbinder.com/images/Tg5WzQk.png' style='position:absolute; top:0px; right:-80px; width:900px; transform:scalex(-1)' />

\pagebreakNum

<div style='margin-top:370px;'></div>

___
> ## Harpy
>*Medium humanoid (harpy), chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 36 (8d8)
> - **Speed** 20 ft., fly 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|14 (+2)|10 (+0)|11 (+0)|12 (+1)|8 (-1)|
>___
> - **Skills** Perception +5
> - **Senses** darkvision 60 ft., passive Perception 15
> - **Languages** Darnassian, Low Common
> - **Challenge** 1 (200 XP)
> ___
> ***Dive Attack.*** If the harpy is flying and dives at least 30 feet straight toward a target and then hits it with a melee weapon attack, the attack deals an extra 3 (1d6) damage to the target.
>
> ***Poisonous Kiss.*** If the harpy kisses a humanoid on the lips, the target must succeed on a DC 11 Constitution saving throw or be poisoned for 1d4 hours. While poisoned in this way, the target also has disadvantage on Wisdom saving throws.
>
> ### Actions
> ***Multiattack.*** The harpy can use its Incapacitating Screech if available. It then makes one attack with its talons.
>
> ***Talons.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 9 (2d6 + 2) slashing damage plus 2 (1d4) poison damage.
>
> ***Incapacitating Screech (Recharge 6).*** The harpy emits a horrific screech. Each creature within 15 feet of it that can hear it and that isn't a harpy must succeed on a DC 11 Constitution saving throw or be incapaci&shy;tated until the end of the harpy's next turn.

\columnbreak

<div style='margin-top:216px;'></div>

___
> ## Harpy Witch
>*Medium humanoid (harpy), chaotic evil*
> ___
> - **Armor Class** 13
> - **Hit Points** 50 (9d8 + 10)
> - **Speed** 20 ft., fly 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|16 (+3)|13 (+1)|12 (+1)|16 (+3)|9 (-1)|
>___
> - **Skills** Perception +5
> - **Senses** darkvision 60 ft., passive Perception 15
> - **Languages** Darnassian, Low Common
> - **Challenge** 3 (700 XP)
> ___
> ***Dive Attack.*** If the harpy is flying and dives at least 30 feet straight toward a target and then hits it with a melee weapon attack, the attack deals an extra 3 (1d6) damage to the target.
>
> ***Poisonous Kiss.*** If the harpy kisses a humanoid on the lips, the target must succeed on a DC 11 Constitution saving throw or be poisoned for 1d4 hours. While poisoned in this way, the target also has disadvantage on Wisdom saving throws.
>
> ***Spellcasting.*** The harpy is a 5th-level spellcaster. Its spellcasting ability is Wisdom (Spell save DC 13, +5 to hit with spell attacks). The harpy has the following shaman spells prepared:
>
> Cantrips (at will): *gust, ✦ lightning blast, thunderclap*
> <br> 1st level (4 slots): *absorb elements, earth tremor, <br>&nbsp;&nbsp;&nbsp; fog cloud, thunderwave*
> <br> 2nd level (3 slots): *dust devil, gust of wind*
> <br> 3rd level (2 slots): *lightning bolt, wind wall*
>
> ### Actions
> ***Multiattack.*** The harpy can use its Incapacitating Screech. It then makes two attacks: one with its talons and one with a prepared cantrip.
>
> ***Talons.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage plus 2 (1d4) poison damage.
>
> ***Incapacitating Screech (Recharge 6).*** The harpy emits a horrific screech. Each creature within 15 feet of it that can hear it and that isn't a harpy must succeed on a DC 11 Constitution saving throw or be incapaci&shy;tated until the end of the harpy's next turn.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;50;4;12;26;3;56;0;56;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">H</div>
<div class='footnote'>HARPIES </div>

<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot inkblot-green' style='top:0px; right:50px; width:700px'>
<img src='https://www.gmbinder.com/images/8xkJDn5.png' style='position:absolute; top:-50px; right:400px; width:400px; transform:scalex(-1)' />
<img src="https://www.gmbinder.com/images/mqqDcER.png" style="position:absolute;top: 75px;right: 100px;transform: rotate(-2deg);z-index:100;filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">

\pagebreakNum

<div style='margin-top:140px;'></div>

## Kobolds

Diminutive, rat-like, and subterranean, kobolds can be found dwelling in sprawling caverns and abandoned mines across Kalimdor and the Eastern Kingdoms alike. Even throughout Northrend one can find their aptly named cousins; the snobolds. As far back as the first human settlements in the Eastern Kingdoms, kobolds have been a persistent, and annoying, presence.

Kobolds average at four feet tall, with coarse skin, sharp claws, a pronounced snout, and a spindly tail. Educated guesses have pinned them as a distant offshoot from the troggs, though this has never been proven.

***Skittish Creatures.*** Adventurers who have seen a kobold, especially a kobold away from its pack and lair, can testify for their cowardice. Kobolds are not particularly intelligent, and many consider them more of a nuisance than real danger -- at least in smaller numbers.

***Massive Flocks.*** Kobolds are not only known to bear a resemblance to vermin; they breed like vermin as well. Wherever one kobold can be found, hundreds more are likely not too far behind. While kobolds are rarely threatening in smaller numbers, a pack numbering in dozens, even hundreds, can pose a threat even to seasoned adventurers if one were to try and evict them.

They have no concept of marriage. Rather, they form a loose structure of packs and clans based on their lineages, with young individuals opting to migrate between nests and warrens in search of mates outside of their own family.

Famously, a kobold can become very protective of its keepsakes, and they prefer to keep a distance from other races in order to keep themselves safe.

***Candle-Hoarders.*** Despite living deep underground, populating self-made caverns and abandoned mines -- sometimes even chasing miners away if the pack is large enough -- kobolds do not see well in the dark. They rely on candles to traverse whichever caverns they call home.

These candles are usually made by the kobolds them&shy;selves, twining wicks from their hairs and pulling wax from their ears, though in desperation a kobold may contemplate stealing candles from other nearby settlements. Once a candle has been acquired, it is placed atop the kobold's head and left to burn there.

***Legends of the Darkness.*** Kobold legends speak of a dark, devouring presence dwelling in the deep places of the world, giving reason to the creatures' candle obsession.

To the same end, some kobold packs have been seen keeping rats as pets, as the critters do not fear the dark&shy;ness themselves. A well-trained rat can keep the kobold company and help out with digging, while a not so well-trained rat can make for a good dinner.

\columnbreak

<div style='margin-top:545px;'></div>

___
> ## Kobold
> *Small humanoid (kobold), chaotic neutral*   
> ___  
> - **Armor Class** 12
> - **Hit Points** 5 (2d6 - 2)
> - **Speed** 30 ft.
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 12 (+1)|14 (+2)|8 (-1)|7 (-2)|7 (-2)|8 (-1)|
> ___  
> - **Skills** Perception +0
> - **Senses** passive Perception 10
> - **Languages** Low Common, Common  
> - **Challenge** 1/8 (25 XP)  
> ___
> ***Pack Tactics.*** The kobold has advantage on an attack roll against a creature if at least one of the kobold’s allies is within 5 ft. of the creature and the ally isn’t incapacitated.
>
> ### Actions
> ***Pickaxe.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one creature. *Hit:* 4 (1d6+1) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;10;5;3;12;4;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class='letterheader'></div>
<div class="mmletter mml-k"></div>
<div class="pageLetter">K</div>
<div class='footnote'>KOBOLDS </div>

<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot inkblot-green' style='top:50px; right:-80px; width:600px; transform:rotate(50deg)'>
<img src='https://www.gmbinder.com/images/F1ZgnDD.png' style='position:absolute; top:132px; right:-25px; width:510px; mix-blend-mode:darken' />
<img src='https://www.gmbinder.com/images/qLJ3Z1l.jpg' style='position:absolute; top:950px; right:390px; width:350px; mix-blend-mode:darken' />

\pagebreakNum

### Kobold Names and Languages
Kobolds typically speak Low Common, and often adopt other wide-spoken languages in the regions they dwell. The latter is especially prevalent across the Eastern Kingdoms, where most kobold packs and clans have learned Common over their long history of interacting with humans.

Kobold names and clan names are a descriptive amal&shy;gamation of everyday words. Kobold name usually has two parts; a short, easily vocalized first name, and a descriptive surname. Kobold surnames are personal and not inherited, but rather like a title that sums up their character, appear&shy;ance, or a well-known possession of theirs.

Their clan names often refer to common traits passed down through that clan's lineage, or to quirks unique to their society, though they can be hard to distinguish from the names the kobolds give themselves.

<div style='margin-top:-5px;'></div>

**Kobold Names:** Bukk, Feb, Feez, Gik, Kubb, Mlepp,
<br />&nbsp;&nbsp;&nbsp; Naal, Slag, Znaz, Zniv
<br /> **Kobold Surnames:** Fatcandle, Flintdagger, Goldtooth,
<br />&nbsp;&nbsp;&nbsp; Halfcandle, Luckybristles, Onetooth, Skullhat
<br /> **Clan Names:** Bluewax, Boulderslide, Gravelsnout,
<br />&nbsp;&nbsp;&nbsp;Mudwhisker, Skywhisker, Windshear

___
> ## Kobold Geomancer
> *Small humanoid (kobold), chaotic neutral*   
> ___  
> - **Armor Class** 12
> - **Hit Points** 17 (5d6)
> - **Speed** 30 ft.
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 10 (+0)|14 (+2)|10 (+0)|7 (-2)|14 (+2)|8 (-1)|
> ___  
> - **Skills** Perception +4
> - **Senses** passive Perception 14
> - **Languages** Low Common, Common  
> - **Challenge** 1/2 (100 XP)  
> ___
> ***Pack Tactics.*** The kobold has advantage on an attack roll against a creature if at least one of the kobold’s allies is within 5 ft. of the creature and the ally isn’t incapacitated.
>
> ***Spellcasting.*** The kobold is a 1st-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). It has the following shaman spells prepared:
>
> Cantrips (at will): *Produce Flame, Mold Earth*
> <br/> 1st level (2 slots): *Absorb Elements, Cure Wounds, Earth Tremor, Searing Smite, Thunderwave*
>
> ### Actions
> ***Club.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one creature. *Hit:* 2 (1d4) bludgeoning damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;10;17;0;12;18;0;18;0;4;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

\columnbreak

> ##### Variant: Candles in the Dark
> Kobold legends speak of a devouring presence, hiding in the darkness, giving to them their over&shy;whelming fear of the dark.
>
> A kobold without a lit candle, who is standing in dim light or darkness, must succeed on a DC 12 Wisdom saving throw or be frightened for 1 minute. The kobold can repeat the saving throw at the end of each its turns, also ending the effect if it manages to light a candle again.
>
> On a successful save, if another creature was responsible for the loss of candlelight, the kobold deals an extra 4 (1d6) damage when it hits that creature with a melee attack.

___
> ## Kobold Taskmaster
> *Small humanoid (kobold), chaotic neutral*   
> ___  
> - **Armor Class** 13 (leather armor)
> - **Hit Points** 22 (5d6 + 5)
> - **Speed** 30 ft.
> ___  
> STR | DEX | CON | INT | WIS | CHA
>|:---:|:---:|:---:|:---:|:---:|:---:|
> 14 (+2)|14 (+2)|12 (+1)|12 (+1)|9 (-1)|11 (+0)|
> ___  
> - **Skills** Perception +1
> - **Senses** passive Perception 11
> - **Languages** Low Common, Common  
> - **Challenge** 1 (200 XP)  
> ___
>
> ***Pack Tactics.*** The kobold has advantage on an attack roll against a creature if at least one of the kobold’s allies is within 5 ft. of the creature and the ally isn’t incapacitated.
>
> ### Actions
> ***Multiattack.*** The kobold makes two melee attacks.
>
> ***Shovel.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 6 (1d8 + 2) piercing damage.
>
> ***Leadership (Recharges after a Short or Long Rest).*** For 1 minute, the kobold can utter a special command or warning whenever a nonhostile creature that it can see within 30 ft. of it makes an attack roll or a saving throw. The creature can add a d4 to its roll provided it can hear and understand the kobold. A creature can benefit from only one Leadership die at a time. This effect ends if the kobold is incapacitated.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;22;4;12;12;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class="pageLetter">K</div>
<div class='footnote'>KOBOLDS </div>
<img src='https://www.gmbinder.com/images/QKD9YhA.jpg' style='position:absolute; top:500px; right:-450px; width:1300px' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:20px;'></div>

## Kodos
A kodo is a giant reptile, known for its thick hide <br/> and characteristics horns. Large and lumbering, <br/> these grazing beasts roam together in herds, <br/> their steps like rolling thunder across the plains <br/> of Kalimdor. Though their strength is immense, <br/> they are peaceful creatures whose horns serve <br> more to defend than to fight.

***Herd Animals.*** Kodos are pack animals, and <br/> show a clear line of authority in their herds. The <br/> head of the pack leads the way, while the rest keep <br/> close guard of the weak and young as to not leave <br> anyone behind. Most kodo herds number in a dozen at <br> the most, though some have been sighted in groups as large as fifty beasts. It is rare for a kodo to wander <br> alone, though some elderly beasts have been seen taking <br> to a life of solitude.

***Tauren Culture.*** Among the tauren, the kodos have a strong cultural presence as a symbol of vigor and power. Long have they hunted and tamed these imposing beasts, revering these acts important rites of passage for young tauren warriors. And for the size and brawn of the tauren themselves, few beasts can carry them as well as a kodo.

***Pack Beasts.*** Kodos are formidable pack beasts, long elevated as such by the tauren and since ingrained in the Horde as a whole. They can carry even immense loads for long periods of time without any trouble.

___
> ## Kodo
>*Large beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 45 (6d10 + 12)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|21 (+5)|9 (-1)|15 (+2)|3 (-4)|10 (+0)|6 (-2)|
>___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 2 (450 XP)
> ___
> ***Beast of Burden.*** The kodo is considered to be a Huge animal for the purpose of determining its carrying capacity.
> 
> ***Trampling Charge.*** If the kodo moves at least 20 feet straight towards a Large or smaller creature and then hits it with a gore attack on the same turn, that target must succeed on a DC 15 Strength saving throw or be knocked prone. If the target is prone, the kodo can make one stomp attack against it as a bonus action.
>
> ### Actions
> ***Gore.*** *Melee Attack Weapon:* +7 to hit, reach 5 ft., one target. *Hit:* 14 (2d8 + 5) piercing damage.
>
> ***Stomp.*** *Melee Attack Weapon:* +7 to hit, reach 5 ft., one prone target. *Hit:* 16 (2d10 + 5) bludgeoning damage. <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;45;7;15;30;0;14;0;14;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;30;;;;;; -->

\columnbreak

<div style='margin-top:185px;'></div>

___
> ## Ancient Kodo
>*Huge beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 114 (12d12 + 36)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|23 (+6)|9 (-1)|17 (+3)|4 (-3)|11 (+0)|6 (-2)|
>___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 4 (1,100 XP)
> ___
> ***Beast of Burden.*** The kodo is considered to be a Gargantuan animal for the purpose of determining its carrying capacity.
> 
> ***Trampling Charge.*** If the kodo moves at least 20 feet straight towards a creature and then hits it with a gore attack on the same turn, that target must succeed on a DC 16 Strength saving throw or be knocked prone. If the target is prone, the kodo can make one stomp attack against it as a bonus action.
>
> ### Actions
> ***Gore.*** *Melee Attack Weapon:* +8 to hit, reach 5 ft., one target. *Hit:* 19 (3d8 + 6) piercing damage.
>
> ***Stomp.*** *Melee Attack Weapon:* +8 to hit, reach 5 ft., one prone target. *Hit:* 22 (3d10 + 6) bludgeoning damage.
>
> ***Devour.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 17 (2d10 + 6) piercing damage. A Medium or smaller target must succeed on a DC 13 Dexterity saving throw or swallowed by the kodo. The kodo can only have one target swallowed at a time. If a target fails the saving throw while the kodo has a creature swallowed, it is grappled instead.
> <br>&nbsp;&nbsp;&nbsp; A swallowed target is blinded and restrained, it has total cover against attacks and other effects outside the kodo, and it takes 10 (3d6) acid damage at the start of each of the kodo's turns.
> <br>&nbsp;&nbsp;&nbsp; If the kodo takes 15 damage or more on a single turn from the swallowed creature, the kodo must succeed on a DC 16 Constitution saving throw at the end of that turn or regurgitate the creature, which falls prone in a space within 10 feet of the kodo. If the kodo dies, a swallowed creature is no longer restrained by it and can escape from the corpse using 10 feet of movement, exiting prone. <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;114;8;16;17;0;41;10;19;10;0;0;0;0;0;0;;;;;3;;;;;1;;;;;1;;;;;;;;30;;;;;; -->

<div class="pageLetter">K</div>
<div class='footnote'>KODOS </div>

<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot' style='top:0px; right:0px; width:500px'>
<img src='https://www.gmbinder.com/images/FgqGNWT.png' style='position:absolute; top:-190px; right:-240px; width:710px' />

\pagebreakNum

<div style='margin-top:110px;'></div>

## Lashers
Lashers are a family of large, slithering flora, known for their long, appendage-like tendrils and found across most of Azeroth. Though most lashers are not predatory, they will defend themselves if threatened.

***Sentient Plants.*** Their existence is the result of nature magic, seeped down into the ground and left to spread. There, it has given the plants enough will to uproot themselves and roam around. For some lashers, this awakening has been deliberate and fairly harmless. For others, it has transformed the plants into vile monstrosities.

***Widely Adapted.*** With their presence found far and wide, most lashers have found ways to adapt to their surroundings -- be it lush jungles, arid hills, or even barren tundras. They plant their seeds wherever there's magic to sustain them, quickly sprouting into a myriad of tiny creatures before slowly maturing.

***Fast Learners.*** Though they appear driven by little more than instinct, fully mature lashers have shown themselves to be remarkably intelligent. Even capable of laying traps, forming decorations, and conveying messages with simple gestures.

### Lasher Spitter
A lasher spitter is a large, carnivorous plant. It produces a strong acid within its stalk, which it then spits out with impressive accuracy through the large maw situated between its petals. The acid is strong enough to dissolve flesh, for easier consumption.

### Barbed Orchid
A barbed orchid stands out from other lashers for its large, vibrant flower-head, centre of which some describe as resembling an owlbeast's beak. Their long tendrils are covered with barbs, which they strike out at prey and intruders alike.

### Bloodpetal Flayer
At a glance, most would take the bloodpetal flayer for little more than a very colorful lasher. Looks are sure to betray, however; as these lashers are unmatched for their ferocity, and for the potency of the vile toxin kept in their sharp thorns.

> ##### Variant: Mature Lasher
> When lashers reach maturity, some learn to channel the powers of the moon in their favor.
>
> A mature lashers has the same statistics as a lasher spitter, except that it has a Wisdom score of 12, and replaces the spitter's action options with the following action options
>
> ***Dream Lash.*** *Ranged Spell Attack:* +3 to hit, range 15/30 ft., one target. *Hit:* 5 (1d10) radiant damage.

\columnbreak

<div style='margin-top:580px;'></div>

___
> ## Lasher
>*Medium plant, unaligned*
> ___
> - **Armor Class** 11 (natural armor)
> - **Hit Points** 5 (1d8 + 1)
> - **Speed** 30 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|13 (+1)|12 (+1)|4 (-3)|8 (-1)|3 (-4)|
>___
> - **Skills** Stealth +3
> - **Damage Vulnerabilities** fire
> - **Condition Immunities** blinded, deafened
> - **Senses** blindsight 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
> ***False Appearance.*** While the lasher remains motion&shy;less, it is indistinguishable from an ordinary plant.
>
> ### Actions
> ***Thorny Slash.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;11;5;3;12;4;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class='letterheader'></div>
<div class="mmletter mml-l"></div>
<div class="pageLetter">L</div>
<div class='footnote'>LASHERS </div>
<img src='https://www.gmbinder.com/images/l3b8R8Q.png' style='position:absolute; top:0px; right:-200px; width:700px' />
<img src='https://www.gmbinder.com/images/TYBvp5o.png' style='position:absolute; top:200px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-15px; width:900px' />

\pagebreakNum

___
> ## Lasher Spitter
>*Medium plant, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 13 (2d8 + 4)
> - **Speed** 30 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|14 (+2)|14 (+2)|4 (-3)|8 (-1)|3 (-4)|
>___
> - **Skills** Stealth +4
> - **Damage Vulnerabilities** fire
> - **Condition Immunities** blinded, deafened
> - **Senses** blindsight 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
> ***False Appearance.*** While the lasher remains motion&shy;less, it is indistinguishable from an ordinary plant.
>
> ### Actions
> ***Thorn Slash.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Acid Spit.*** *Ranged Weapon Attack:* +4 to hit, range 15/30 ft., one creature. *Hit:* 6 (1d8 + 2) acid damage. At the end of each of its turns, the creature must make a DC 10 Constitution saving throw, taking 2 (1d4) acid damage on a failure or ending the recurring acid damage on a success.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;13;4;12;6;2;6;4;6;4;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div style='margin-top:100px;'></div>

___
> ## Barbed Orchid
>*Medium plant, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 26 (4d8 + 8)
> - **Speed** 30 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|15 (+2)|14 (+2)|4 (-3)|8 (-1)|3 (-4)|
>___
> - **Skills** Stealth +5
> - **Damage Vulnerabilities** fire
> - **Condition Immunities** blinded, deafened
> - **Senses** blindsight 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***False Appearance.*** While the lasher remains motion&shy;less, it is indistinguishable from an ordinary orchid.
>
> ### Actions
> ***Multiattack.*** The lasher makes two thorn slash attacks.
>
> ***Thorn Slash.***  *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Thorn Volley.*** *Ranged Weapon Attack:* +4 to hit, range 15/30 ft., one creature. *Hit:* 6 (1d8 + 2) poison damage.
>
> ### Reactions
> ***Thorn Shield.*** When a creature within 5 feet of the lasher hits it with a melee attack, the creature takes 5 (2d4) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;26;4;12;10;5;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

___
___
> ## Bloodpetal Flayer
>*Medium plant, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 39 (6d8 + 12)
> - **Speed** 30 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|16 (+3)|14 (+2)|4 (-3)|8 (-1)|3 (-4)|
>___
> - **Skills** Stealth +5
> - **Damage Vulnerabilities** fire
> - **Condition Immunities** blinded, deafened
> - **Senses** blindsight 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 2 (450 XP)
>___
> ***False Appearance.*** While the lasher remains motion&shy;less, it is indistinguishable from an ordinary flower.
>
> ### Actions
> ***Multiattack.*** The lasher makes two thorn slash attacks.
>
> ***Thorn Slash.***  *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) piercing damage, and the target must succeed on a DC 13 Constitution saving throw or take 2 (1d4) poison damage.
>
> ***Whirlwind Strike (Recharge 5-6).*** The lasher lashes out in all directions with thorny vines, tearing any opponent within range. Each creature in a 10-foot radius centered on the lasher must make a DC 13 Dexterity saving throw. On a failed save, a creature takes 9 (2d8) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;15;39;5;12;18;0;12;4;12;4;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->
> <div style='margin-top:25px;'></div>

<div class="pageLetter">L</div>
<div class='footnote'>LASHERS </div>

<img src='https://www.gmbinder.com/images/a81VyUK.png' class='inkblot inkblot-green' style='top:200px; right:100px; width:700px'>

\pagebreakNum

<div style='margin-top:380px;'></div>

___
> ## Leper Gnome
>*Small humanoid (gnome), chaotic evil*
> ___
> - **Armor Class** 11
> - **Hit Points** 9 (2d6 + 2)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|13 (+1)|12 (+1)|13 (+1)|10 (+0)|9 (-1)|
>___
> - **Damage Resistances** poison
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Common, Gnomish
> - **Challenge** 1/4 (50 XP)
> ___
>
> ***Escape Artist.*** The gnome can move through the space of any Medium or larger creature.
>
> ***Gnome Cunning.*** The gnome has advantage on Intelligence, Wisdom, and Charisma saving throws against magic.
>
> ***Miasma.*** When the gnome dies, toxic fumes spread in a 10-foot radius out from it. The fumes spread around corners and its area is lightly obscured. It lasts for 1 minute or until a strong wind disperses it. Creatures that start their turn in that area must succeed on a DC 11 Constitution saving throw or gain the radiation sickness. Read the Radiation Sickness sidebar for more information.
>
> ### Actions
> ***Shortsword.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) piercing damage.
>
> ***Pistol (Recharge 5-6).*** *Ranged Weapon Attack:* +3 to hit, range 60/240 ft., one target. *Hit:* 6 (1d10 + 1) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;11;9;3;12;6;0;4;0;4;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;1;;;;;;;10;;;;;; -->

\columnbreak

## Leper Gnome
Beneath the snow capped mountains of Dun Morogh lay the halls of Gnomeregan. Once the gnomish capitol, the city's irradiated halls now only swarm with troggs and crazed, addled gnomes. These gnomes, permeating with radiation, have become known as leper gnomes. Their skin has turned a sickly green, dotted with abscesses that burst at the smallest stress or strain.

***A Necessary Sacrifice.*** When the gnomish capitol of Gnomeregan was invaded by troggs, a desperate decision was made when the High Tinker ordered all radioactive waste from the city's numerous machines unleashed.

Vented through the city in a noxious green gas, and flooded through the pipes in rivers of green goop, the attempt to cull their invaders ultimately killed off more gnomes than troggs -- and left the city a radioactive wasteland, riddled with danger.

Worse yet, as the city's ruins were later explored, it became clear how many had survived the ordeal; all of them mutated and driven mad by the city's green haze.

***Hostile Insanity.*** Fractious at best, the leper gnomes have continued their life in Gnomeregan as though all is as it once was. Their minds warped by toxic fumes, most leper gnomes do not seem to grasp the reality of their situation. Most dangerous are the few that do.

Still sharing the city with their trogg invaders, leper gnomes are known to be extremely paranoid and prone to immediate hostility toward any who would come looking for them. After all, anyone they don't know could suddenly turn out to be in tow with the troggs.

***Mutated Creatures.*** Once the radiation takes hold in a creature, as witnessed with the leper gnomes, it slowly warps into something else; gradually tearing it apart until little more is left than a mindless puddle of toxic sludge. With the time the leper gnomes have spent below the earth, in Gnomeregan, some unfortunate few have already twisted and devolved into monstrous aberrations.

<div style='margin-top:27px;'></div>

> ##### Radiation Disease
> When an uninfected creature comes into contact with a source of radiation — such as contaminated water, being bitten by an infected creature, or for every hour spent in a high-radiation area — the creature must succeed on a DC 11 a Constitution saving throw or contract the radiation disease.
>
> It takes 1d4 days for the disease to manifest. As it does, the creature's skin takes on a sickly green tint and abscesses start to spread across its surface. At the end of that period, the creature gains advantage on saving throws against poison and resistance against poison damage. However, the creature also has disadvantage on all Strength and Dexterity ability checks, as well as weapon attack rolls.
>
> Once a creature has carried the radiation disease for more than two weeks, its skin turns completely green. It no longer suffers from disadvantage on ability checks or weapon attacks, but it gains an indefinite madness as described in the *Dungeon Master's Guide* (p. 260).
>
> The radiation symptoms can be cured by a spell, such as *lesser restoration*. Once the disease has manifested, a more potent spell such as *greater restoration* or *heal* is required.

<div class="pageLetter">L</div>
<div class='footnote'>LEPER GNOME </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot inkblot-green' style='top:0px; right:327px; width:500px'>
<img src='https://www.gmbinder.com/images/l0q9dDf.jpg' style='position:absolute; top:15px; right:370px; width:480px;mix-blend-mode:darken;transform:scalex(-1)' />

\pagebreakNum

<div style='margin-top:147px;'></div>

## Makrura
A makrura is a large aquatic creature found living in small colonies along Azeroth's numerous coastlines and deep oceans. They resemble enormous crayfish, some near six feet tall, to which some call them *lobster men*.

***Aggressive and Hostile.*** Makruras within the confines of their colony are immediately hostile toward intruders, and will attack anyone who dare approach. With their massive claws, they pinch and pin their target down, before subsequently tearing it into tiny pieces.

***Wrecked Colonies.*** With their homes often situated in turbulent waters or along contested shorelines, it is not uncommon for a colony to seek seclusion by taking shelter inside wrecked ships or underwater caverns.

***Savory Prey.*** Makrura meat is a delicacy, tried and tested, for many races both above and beneath the ocean. Some towns and villages may try to turn a nearby colony into a hunting opportunity, though the most prominent enemy of the makrura are murlocs and naga.

### Makrura Tidecaller
Some Makrura have an innate affinity for water magic, able to summon its powers at will. These notorious mystics are known as tidecallers; often wise sages in their colonies, they bring forth the tides both to heal and to harm.

___
> ## Makrura
>*Medium monstrosity, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 32 (5d8 + 10)
> - **Speed** 30 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|15 (+2)|14 (+2)|7 (-2)|10 (+0)|6 (-2)|
>___
> - **Skills** Stealth +4
> - **Senses** blindsight 30 ft., passive Perception 10
> - **Languages** Nerglish
> - **Challenge** 1 (200 XP)
> ___
> ***Amphibious.*** The makrura can breathe air and water.
>
> ### Actions
> ***Multiattack.*** The makrura attacks twice with its claws.
>
> ***Claw.***  *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 5 (1d8 + 1) bludgeoning damage. The target is grappled (escape DC 11) The makrura has two claws, each of which can grapple only one target.<!-- https://wc5e-cr-calculator.frogvall.com/?0;15;32;3;12;10;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:450px;'></div>

___
> ## Makrura Tidecaller
>*Medium monstrosity, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 97 (15d8 + 30)
> - **Speed** 30 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|15 (+2)|14 (+2)|10 (+0)|14 (+2)|6 (-2)|
>___
> - **Skills** Perception +4, Stealth +4
> - **Senses** blindsight 30 ft., passive Perception 14
> - **Languages** Nerglish
> - **Challenge** 3 (700 XP)
> ___
> ***Amphibious.*** The makrura can breathe air and water.
>
> ***Innate Spellcasting.*** The makrura's innate spellcasting ability is Wisdom (spell save DC 12). It can innately cast the
following spells, requiring no material components:
>
> At will: *frostbite*, *mending*, *shape water*
> <br> 3/day each: *armor of agathys, entangle, healing word*
> <br> 1/day each: *fog cloud, mass healing word, tidal wave*
>
> ### Actions
> ***Multiattack.*** The makrura attacks twice with its claws.
>
> ***Claw.***  *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 8 (2d6 + 1) bludgeoning damage. The target is grappled (escape DC 11) The makrura has two claws, each of which can grapple only one target.<!-- https://wc5e-cr-calculator.frogvall.com/?0;15;97;3;12;36;0;16;0;16;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class='letterheader'></div>
<div class="mmletter mml-m"></div>
<div class="pageLetter">M</div>
<div class='footnote'>MAKRURA </div>
<img src='https://www.gmbinder.com/images/Q9DEb99.jpg' style='position:absolute; top:-40px; right:0px; width:800px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/OfQ7zSw.png' style='position:absolute; top:-600px; right:0px; width:900px;transform:rotate(90deg)' />
<img src='https://www.gmbinder.com/images/C2bOp8u.png' style='position:absolute; top:100px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/KcRAZwq.png' class='inkblot inkblot-blue' style='top:-50px; right:-200px; width:500px; transform:rotate(50deg)'>
<img src='https://www.gmbinder.com/images/SaNsWJP.png' style='position:absolute; top:100px; right:-30px; width:450px' />

\pagebreakNum

<div style='margin-top:270px;'></div>

___
> ## Arcane Wyrm
>*Large elemental, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 29 (4d10 + 8)
> - **Speed** 0 ft., fly 50 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|17 (+3)|14 (+2)|12 (+1)|11 (+0)|8 (-1)|
>___
> - **Damage Immunities** force
> - **Condition Immunities** prone
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 2 (450 XP)
> ___
> ***Death Burst.*** When the wyrm dies, it explodes in a burst of arcane. Each creature within 15 feet of it must make a DC 13 Dexterity saving throw, taking 10 (3d6) force damage on a failed save, or half as much damage on a successful one.
>
> ***Magic Sense.*** The wyrm can sense magic users within 30 feet of it, and focus its attacks on those creatures.
>
> ***Mana Burn.*** Whenever the wyrm hits a target with its bite, the target must succeed on a DC 13 Intelligence saving throw or have their lowest available spell slot expended. The target regains any spell slots lost in this way when they finish a short rest.
>
> ### Actions
> ***Multiattack.*** The wyrm makes two attacks: one with its bite and one to constrict.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) force damage.
>
> ***Constrict.*** *Melee Weapon Attack:* +5 to hit, reach <br> 5 ft., one Medium or smaller creature. *Hit:* 2 (1d4) bludgeoning damage plus 7 (2d4 +3) force damage. The target is grappled (escape DC 13) if the wyrm isn't already constricting a creature, and the target is restrained until this grapple ends.
>
> ***Faerie Fire (1/day).*** The wyrm manifests the effects of a *faerie fire* spell within 60 feet of it (spell save DC 12).

\columnbreak

## Mana Wyrms
Manifesting near pockets of arcane energy, mana wyrms are, as the name implies, serpent-like creatures that shimmer with arcane energy.

Their bodies are translucent, hovering above the ground as though they are swimming through the air. More a nuisance than a threat, they rarely pose much concern for seasoned adventurers who happen by them.

***Unstable Temperament.*** The temperament of a mana wyrm hangs solely on how long it’s been since it last fed. Though they are considered fairly harmless, an agitated wyrm can very quickly turn aggressive. If threatened, they are known to explode in a flash of arcane energy.

***Arcane Sense.*** A mana wyrms can sense the presence of arcane energy around it, and will gravitate toward its source. If the source is a creature and the wyrm is hungry, it may attempt to attack the creature accordingly.

### Arcane Wyrm
An arcane wyrm is in many ways similar to a mana wyrm, though it is much, much larger, slowly snaking their way through the air near arcane fonts.

Some have attributed their existence to them simply being left to feed on too much energy, though their temperament is still calm and even so long as they are not directly threatened.

<div style='margin-top:17px;'></div>

___
> ## Mana Wyrm
>*Small elemental, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 4 (1d6 + 1)
> - **Speed** 0 ft., fly 30 ft. (hover)
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|7 (-2)|14 (+2)|12 (+1)|10 (+0)|11 (+0)|8 (-1)|
>___
> - **Damage Immunities** force
> - **Condition Immunities** prone
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
> ***Death Burst.*** When the wyrm dies, it explodes in a burst of arcane. Each creature within 10 feet of it must make a DC 11 Dexterity saving throw, taking 5 (2d4) force damage on a failed save, or half as much damage on a successful one.
>
> ***Magic Sense.*** The wyrm can sense magic users within 30 feet of it, and focus its attacks on those creatures.
>
> ***Mana Burn.*** Whenever the wyrm hits a target with its bite, the target must succeed on a DC 11 Intelligence saving throw or have their lowest available spell slot expended. The target regains any spell slots lost in this way when they finish a short rest.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) force damage.

<div class="pageLetter">M</div>
<div class='footnote'>MANA WYRMS </div>
<img src='https://www.gmbinder.com/images/0EF18Nx.png' style='position:absolute; top:0px; right:400px; width:450px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-80px; width:900px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/pZatMx5.png' style='position:absolute; top:80px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:530px;'></div>

___
> ## Mechanostrider
>*Medium construct, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 9 (2d8)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|13 (+1)|10 (+0)|3 (-4)|11 (+0)|1 (-5)|
>___
> - **Skills** Athletics +3
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** understands gnomish but can't speak
> - **Challenge** 1/8 (25 XP)
> ___
> ***Immutable Form.*** The mechanostrider is immune to any spell or effect that would alter its form.
>
> ### Actions
> ***Beak.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) slashing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;11;9;3;12;4;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

## Mechanicals
Mechanical constructs distinguish themselves from organic creatures mainly for their lack of blood, internal organs, and natural instincts. Instead, gears whirr and circuits spark inside these mobile machinations.

Some act only at the behest of whoever holds the remote, while others automatically carry out their given set of pre-configured instructions. Some mechanicals distinguish themselves even further, possessing instructions so meticulously crafted as to resemble genuine intelligence.

As they are wholly driven by the logic of their instructions, mechanical constructs do not possess the ability to give any emotional response: they cannot be charmed, and they certainly cannot be frightened.

***Titanic Legacy.*** The origin of Azeroth's great mechanical achievements can be traced back to the titanic Watchers and the ordering of Azeroth. There, the titanic Keeper Mimiron oversaw the creation of a race of diminutive clockwork humanoids -- mechagnomes, forerunners of the gnomes -- as well as a number of other mechanical creations that have since stood the test of time.

***Gnomish and Goblin Ingenuity.*** Alongside the legacy of the gnomes, instinctively carrying on the work of their titanic creator, another point of technological innova&shy;tion across Azeroth has been the artifically enhanced ingenuity of the goblins. Unlike the gnomes, however, goblin creations have a tendency to be remarkably destructive.

The two races lead a contested field of engineering, and have overseen countless mechanical wonders and mishaps across the years -- including cities, transportation systems, explosive automatons, and giant death rays.

***Constructed Nature.*** A mechanical creature doesn't require air, food, drink, or sleep.

### Mechanical Animal Template
A mechanical animal is any Huge or smaller construct created by a skilled engineer to mimic a beast of the same size. The following characteristics change or are added to a creature when a mechanical version is created.

***Retained Characteristics.*** The mechanical animal retains its Armor Class, hit points, Hit Dice, Speed, Strength, Dexterity, Constitution, vulnerabilities, resis&shy;tances, immunities, and special traits.

***Lost Characteristics.*** The mechanical animal loses its original saving throw and skill bonuses, and special sense. It loses any action that isn't Multiattack or a melee weapon attack that deals bludgeoning, piercing, or slashing damage. If it has an action or a melee weapon attack that deals some other type of damage, it loses the ability to deal damage of that type, unless the damage comes from a piece of equipment, such as a magic item.

***Type.*** The mechanical animal's type is construct, and it loses any tags it might have had.

***Alignment.*** The mechanical animal is unaligned.

***Ability Scores.*** The mechanical animal's ability scores change as follows: Int 3 (-4), Wis 11 (+0), Cha 1 (-5).

***Senses.*** The mechanical animal has 60 feet darkvision.

***Condition Immunities.*** The mechanical animal can't be charmed, frightened, paralyzed, petrified, poisoned, or gain exhaustion levels.

***Languages.*** The mechanical animal loses all languages it might've known, and understand the languages of its creator, but can't speak.

***Immutable Form.*** The mechanical animal is immune to any spell or effect that would alter its form.

#### Sample Mechanical Animal
As an example, the Mechanostrider shown here uses the base statistics of a tallstrider.

<div class="pageLetter">M</div>
<div class='footnote'>MECHANICALS </div>
<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot inkblot-blue' style='top:0px; right:335px; width:600px; transform:rotate(40deg);'>
<img src='https://www.gmbinder.com/images/42DIvZN.png' style='position:absolute; top:0px; right:350px; width:400px' />

\pagebreakNum

### Alarm-o-Bot
These constructs are, as the name suggests, walking alarms. Envisioned by gnomes as a safeguard against threats hiding in the dark, rugged terrain of their homeland, the alarm-o-bot keeps a constant watch for sights, sounds, and more with its numerous sensors. If there's a presence it cannot confirm to be friendly, it blares out a high-pitched warning that danger is afoot.

### Bombling
An old goblin classic, the bombling -- or bomb bot -- is a small set of legs and a pair of eyes designed to carry an explosive charge on its back. It can be primed both to a specific target and to a general swathe of targets, which it will then try to chase down. Once it gets close enough, it detonates.


<div style='margin-top:230px;'></div>

___
> ## Alarm-o-bot
>*Small construct, unaligned*
> ___
> - **Armor Class** 10
> - **Hit Points** 7 (2d6)
> - **Speed** 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|10 (+0)|10 (+0)|3 (-4)|11 (+0)|1 (-5)|
>___
> - **Skills** Perception +4
> - **Damage Resistances** poison
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., blindsight 60 ft., passive Perception 14
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> ***DANGER!*** When the alarm-o-bot notices a creature that isn't a construct or gnome it sends out a warning that can be heard within 240 feet of it.
>
> ***Immutable Form.*** The alarm-o-bot is immune to any spell or effect that would alter its form.
>
> ### Actions
> ***Fist.*** *Melee Weapon Attack:* +1 to hit, reach 5 ft., one target. *Hit:* 0 (1d4 - 1) bludgeoning damage.

\columnbreak

### Crowd Pummeler
A mechanical design adopted by both goblins and gnomes, crowd pummelers take the form of a tall, bipedal construct loaded with weapons. Its name is not coincidental, as it is often used as a cheap throw-away sentry; programmable with a set of laws and regulations, alongside a chief directive to pummel any perpetrators.

### Mechano-Tank
The Mechano-tank, or spider tank, is a gnomish construct best known for its armoured chassis and spider-like design. Built for close quarters, the tanks are reinforced to withstand the elements and fined-tuned for maximum destruction. Their legs are able to contract and release, allowing the tank to launch forward into combat.<!-- https://wc5e-cr-calculator.frogvall.com/?0;10;7;1;1;1;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div style='margin-top:245px;'></div>

___
> ## Bombling
>*Small construct, unaligned*
> ___
> - **Armor Class** 10
> - **Hit Points** 7 (2d6)
> - **Speed** 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|6 (-2)|10 (+0)|10 (+0)|3 (-4)|11 (+0)|1 (-5)|
>___
> - **Damage Resistances** poison
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
> ***Detonate.*** When the bombling dies, it detonates in a 10-foot radius explosion. Any creature within range must make a DC 10 Dexterity saving throw, taking 9 (2d8) fire damage on a failed save, or half as much damage on a successful one.
>
> ***Immutable Form.*** The bombling is immune to any spell or effect that would alter its form.
>
> ### Actions
> ***Self-destruct.*** The bombling immediately detonates, killing itself in the process.<!-- https://wc5e-cr-calculator.frogvall.com/?0;10;7;0;10;6;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">M</div>
<div class='footnote'>MECHANICALS </div>

<img src='https://www.gmbinder.com/images/YpvK7Ef.png' class='inkblot inkblot-blue' style='top:110px; right:150px; width:500px; transform:rotate(248deg)' />
<img src='https://www.gmbinder.com/images/9nXCFwU.png' style='position:absolute; top:325px; right:100px; width:200px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/ggaGnjz.png' style='position:absolute; top:280px; right:360px; width:400px;transform:scalex(-1)' />

\pagebreakNum

<div style='margin-top:-15px;'></div>

___
> ## Crowd Pummeler
>*Medium construct, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 32 (5d6 + 15)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|9 (-1)|16 (+3)|3 (-4)|11 (+0)|1 (-5)|
>___
> - **Damage Resistances** poison, psychic; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** understands gnomish but can't speak
> - **Challenge** 3 (700 XP)
> ___
>
> ***Immutable Form.*** The pummeler is immune to any spell or effect that would alter its form.
>
> ### Actions
> ***Multiattack.*** The pummeler makes two claw attacks.
>
> ***Claw.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) slashing damage.
>
> ***Crowd Pummel (Recharge 6).*** The pummeler slams its claws into the ground. Each creature within 5 feet of it must make a DC 12 Dexterity saving throw, taking 11 (2d10) bludgeoning damage on a failed save, or half as much damage on a successful one. On a failed saving throw, the target is knocked prone.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;32;6;12;26;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div style='margin-top:20px;'></div>

> ##### Variant: Arcane Nullifier
> An arcane nullifier has a challenge rating of 4 (1,100 XP). It has the same statistics as a crowd pummeler except that it replaces the pummeler's action options with the following action options.
> <div style='margin-top:5px;'></div>
>
> &nbsp;&nbsp;&nbsp; ***Multiattack.*** The nullifier makes two claw attacks.
>
> ***Claw.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) slashing damage.
>
> ***Slow (Recharge 5-6).*** The nullifier targets one creature it can see within 10 feet of it. The creature must make a DC 13 Wisdom saving throw against this magic. On a failed save, the creature can't use reactions, its speed is halved, and it can't make more than one attack on its turn. In addition, the creature can take either an action or a bonus action on its turn, not both. The effect lasts for 1 minute. The creature can repeat the saving throw at the end of each of its turns.
>
> ***Nullify (Recharge after a Long Rest).*** The nullifier attempts to dispel all magical effects within 30 feet of it, as if it had cast the *dispel magic* as a 3rd-level spell on everything within range.
> <div style='margin-top:5px;'></div>
>
> The nullifier also gains the following reaction.
> <div style='margin-top:5px;'></div>
>
> &nbsp;&nbsp;&nbsp; ***Reflection Field.*** When a creature hits the nullifier with a ranged spell attack, the nullifier can reflect the spell onto a target within 15 feet of it.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;32;6;12;26;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;1;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:459px;'></div>

> ##### Crewing a Mechano-tank
> Most mechano-tanks are manual machines that require a pilot to operate, and even autopiloted tanks can be overwritten to work manually for a time.
>
> A creature can use its action to attempt to climb a **piloted** mechano-tank by succeeding on a DC 14 Strength (Athletics) check. On a failed save, the creature expends half its movement and is unable to climb the mechano-tank.
>
> The controls of the mechano-tank is sealed tight behind a hatch. The hatch can be opened with a successful DC 20 Strength check, or broken if dealt 20 bludgeoning, piercing, or slashing damage, it has an Armor Class (AC 15).
>
> A Small or smaller creature can expend 5 feet of movement to enter an unoccupied mechano-tank. A creature unfamiliar with the controls of tank must succeed on a DC 15 Intelligence check to under&shy;stand the controls of the machine before it is able to pilot it and control its actions and movement.
>
> While piloted, the mechano-tank's Intelligence, Wisdom, and Charisma scores are exchanged with those of the pilot. A piloted tank uses the initiative of its pilot. The pilot must use its action, reaction, and movement to use the machines action options or force it to move to a new location. While a crea&shy;ture is crewing the mechano-tank, it is considered to have full cover against any attack made against it from the ground.
>
> Taking control of an **autopiloted** tank requires a successful DC 17 Tinker's Tool Intelligence check. On a successful save, the creature takes control of the tank until the end of the creature's next turn. At which point the tank's failsafe mechanisms return, requiring a new save to temporarily take control of it.

<div class="pageLetter">M</div>
<div class='footnote'>MECHANICALS </div>
<img src='https://www.gmbinder.com/images/64Wsryy.png' class='inkblot inkblot-blue' style='top:00px; right:0px; width:400px; transform:rotate(90deg)' />
<img src='https://www.gmbinder.com/images/FwruUvJ.png' style='position:absolute; top:-80px; right:0px; width:450px' />

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Mechano-tank
>*Large construct, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 95 (10d10 + 30)
> - **Speed** 40 ft., climb 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|14 (+2)|16 (+3)|13 (+1)|10 (+0)|9 (-1)|
>___
> - **Damage Resistances** poison; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., blindsight 60 ft., passive Perception 10
> - **Languages** Common, Gnomish
> - **Challenge** 6 (2,300 XP)
> ___
> ***Immutable Form.*** The tank is immune to any spell or effect that would alter its form.
>
> ***Magic Resistance.*** The tank has advantage on saving throws against spells and other magical effects.
>
> ***Mechano Resistance.*** The tank is resistance to the damage type of its thrower weapon, as described in the Mechano-tank Type table below.
>
> ### <br><br> Actions
> ***Multiattack.*** The tank can use its Charged Leap. It then makes two machine gun attacks.
>
> ***Machine Gun.*** *Ranged Weapon Attack:* +5 to hit, range 120/380 ft., one target. *Hit:* 11 (2d8 + 2) piercing damage.
>
> ***Thrower Weapon (Recharge 5-6).*** The tank uses its thrower to spew out a blast of destructive energy. The mechano-tank type determines the size, shape, and damage type of the thrower's attack. Each creature in the area of the thrower must make a DC 14 saving throw, the type of which is determined by the tank's thrower type. A creature takes 18 (4d8) damage on a failed save, or half as much damage on a success.
>
> ***Charged Leap (Recharge 6).*** The tank leaps high into the air, landing in a space no more than 60 feet from where it started. Each creature in the tank's space when it lands must make a DC 15 Dexterity saving throw, taking 10 (3d6) damage of the tank's thrower type on a failed save, or half as much damage on a successful one. On a failed saving throw, a target is knocked prone.
>
> ##### Mechano-tank Type
> |&nbsp; Type        | Damage |&nbsp;| Thrower Weapon         |
> |:------------------|:--------------:|-|:----------------------------|
> |&nbsp; Firewalker  | Fire           || 15 ft. cone (Dex. save)      |
> |&nbsp; Frostwalker | Cold           || 15 ft. cone (Con. save)      |
> |&nbsp; Shockwalker | Lightning      || 5 by 30 ft. line (Dex. save) |<!-- https://wc5e-cr-calculator.frogvall.com/?1;15;95;5;14;22;20;36;0;22;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;1;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">M</div>
<div class='footnote'>MECHANICALS </div>
<img src='https://www.gmbinder.com/images/64Wsryy.png' class='inkblot inkblot-blue' style='top:-300px; right:0px; width:700px; transform:rotate(90deg)' />
<img src='https://www.gmbinder.com/images/DsvKvCU.png' style='position:absolute; top:-100px; right:-190px; width:1200px' />

\pagebreakNum

## Murloc
From a distance, the degenerate and fishlike murlocs might not seem like much of a threat, but the small creatures are rarely cornered alone. They rarely venture far from their waters, and never too far from their tribe. Though they might seem humorous for their ways, behind their blank expressions hides a murderous mind.

***Strange Territories.*** Murlocs populate coastlines, lake&shy;shores and swamps, and prefer to keep within their territory. A murloc tribe on the move is often one looking for a new place to settle -- and settled they certainly have, in nearly every corner of Azeroth.

They build their chaotic villages out of mud-and-twig huts, resembling structures more suited for life underwater than life along the shore. There's no orderly pattern to where a murloc would build its home, though the tribe's oracle and strongest fighters tend to claim the best spots.

***Questionable Intelligence.*** Most would argue that murlocs are not very intelligent, considering their simple lives and near-indecipherable language.

Still, they are ferocious hunters and zealous in their faith. There does not appear to be any singular belief to which the murlocs keep. Instead, they follow the whim of what signs they read from the elements, and occasionally the will of other aquatic entities -- including naga.

***Pack Hunters.*** Though murlocs are not particularly brave, they will attempt to hunt foes that they can outnumber. In doing so, they lead just a few murlocs ahead to trick their quarry into giving chase, often into murky waters if they can. There, the brunt of the tribe's hunters lay in wait, leaping into the fray like a swarm of hungry fish.

### Murloc Tidehunter
While most murlocs know to wield a blade or a spear, some select few have harnessed an aptitude for bringing finer tools to the hunt. The tidehunters weave and keep their own nets, sharing techniques for heavy weights and barbed hooks within their hunting parties. A group of tidehunters on the prowl can be a serious threat to anyone foolish enough to pass through their territory.

### Murloc Oracle
A few select murlocs are elevated above the rest of their tribe, born to a strong will and a natural affinity for magic. These murlocs, known as oracles, are adept spellcasters. They are masters of the elements and can use them to control the environment around their enemies.

### Murloc Names and Languages
The murlocs' native tongue is Nerglish; a strange, aquatic language in similar lieu to Low Common, which they share with a handful of other creatures.

Their names, just like their language, are wet and soft-sounding. They don't keep individual surnames, but rather take to their name of their tribe -- which in turn recalls the tribe's deeds, appearance, history, or tradition.
<div style='margin-top:10px;'></div>

**Male Names:** Ashmol, Loshof, Molgoo, Shlesh
<br>
**Female Names:** Malash, Orgloom, Seeshen, Shyresh
<br>
**Tribe Names:** Blindlight, Bluegill, Greymist, Slatspittle

\columnbreak

<div style='margin-top:450px;'></div>

___
> ## Murloc
>*Small humanoid (murloc), neutral evil*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 4 (1d6 + 1)
> - **Speed** 25 ft., swim 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|13 (+1)|12 (+1)|9 (-1)|12 (+1)|7 (-2)|
>___
> - **Skills** Survival +3
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** Nerglish
> - **Challenge** 1/8 (25 XP)
> ___
> ***Amphibious.*** The murloc can breathe air and water.
>
> ***Pack Tactics.*** The murloc has advantage on an attack roll against a creature if at least one of the murloc's allies is within 5 feet of that creature and the ally isn't incapacitated.
>
> ***Slippery.*** The murloc has advantage on ability checks and saving throws made to escape grapple.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) piercing damage.
>
> ***Spear.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft. or range 20/60 ft., one target. *Hit:* 4 (1d6 + 1) piercing damage, or 5 (1d8 + 1) piercing damage if used with two hands to make a melee attack.<!-- https://wc5e-cr-calculator.frogvall.com/?0;12;4;3;12;5;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class="pageLetter">M</div>
<div class='footnote'>MURLOCS </div>
<img src='https://www.gmbinder.com/images/84P8ntb.png' style='position:absolute; top:0px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/QZfSRiM.pngg' class='inkblot inkblot-blue' style='top:30px; right:-150px; width:600px;'>
<img src='https://www.gmbinder.com/images/nBf8yxY.png' style='position:absolute; top:0px; right:-20px; width:450px' />

\pagebreakNum

<div style='margin-top:350px;'></div>

___
> ## Murloc Tidehunter
>*Medium humanoid (murloc), neutral evil*
> ___
> - **Armor Class** 14 (natural armor, shield)
> - **Hit Points** 11 (2d8 + 2)
> - **Speed** 30 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|13 (+1)|12 (+1)|9 (-1)|12 (+1)|7 (-2)|
>___
> - **Skills** Athletics +3, Survival +3
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** Nerglish
> - **Challenge** 1/4 (50 XP)
> ___
> ***Amphibious.*** The murloc can breathe air and water.
>
> ***Pack Tactics.*** The murloc has advantage on an attack roll against a creature if at least one of the murloc's allies is within 5 feet of that creature and the ally isn't incapacitated.
>
> ***Slippery.*** The murloc has advantage on ability checks and saving throws made to escape grapple.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) piercing damage.
>
> ***Spear.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft. or range 20/60 ft., one target. *Hit:* 4 (1d6 + 1) piercing damage, or 5 (1d8 + 1) piercing damage if used with two hands to make a melee attack.
>
> ***Net.*** *Ranged Weapon Attack.* +3 to hit, range 5/15 ft., one Large or smaller creature. *Hit:* The target is restrained. A creature can use its action to make a DC 10 Strength check to free itself or another creature in a net, ending the effect on a success. Dealing 5 slashing damage to the net (AC 10) frees the target without harming it and destroys the net.<!-- https://wc5e-cr-calculator.frogvall.com/?0;14;11;3;12;5;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:350px;'></div>

___
> ## Murloc Oracle
>*Medium humanoid (murloc), neutral evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 22 (4d8 + 4)
> - **Speed** 30 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|14 (+2)|12 (+1)|10 (+0)|14 (+2)|7 (-2)|
>___
> - **Skills** Perception +4 Survival +3
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** Nerglish
> - **Challenge** 1 (200 XP)
> ___
> ***Amphibious.*** The murloc can breathe air and water.
>
> ***Pack Tactics.*** The murloc has advantage on an attack roll against a creature if at least one of the murloc's allies is within 5 feet of that creature and the ally isn't incapacitated.
>
> ***Slippery.*** The murloc has advantage on ability checks and saving throws made to escape grapple.
>
> ***Innate Spellcasting.*** The murloc's innate spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). It can innately cast the following spells, requiring no material components:
>
> At will: *mending, shape water, toll the dead*
> <br> 3/day each: *fog cloud, sleep, thunderwave*
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.
>
> ***Spear.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft. or range 20/60 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage, or 6 (1d8 + 2) piercing damage if used with two hands to make a melee attack.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;22;3;12;18;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class="pageLetter">M</div>
<div class='footnote'>MURLOCS </div>
<img src='https://www.gmbinder.com/images/ijqWnhI.jpg' style='position:absolute; top:-30px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:-200px; right:0px; width:1000px' />
<img src="https://www.gmbinder.com/images/OyT2YY6.png" style="position:absolute;top: 295px;left: -6px; transform: rotate(3deg);z-index:100;filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">

\pagebreakNum

<div style='margin-top:120px;'></div>

## Naga
The naga are former Highborne night elves, transformed into a race of horrifying sea serpents.

During the Great Sundering, when the Kaldorei city of Zin-Azshari was destroyed, the Kaldorei Queen Azshara and many of her Highborne followers fell into the depths of the Great Sea. Unwilling to face death, Azshara forged a pact with an Old God, N'Zoth, which saw her and her followers twisted into serpentine aberrations.

Most naga who remain belong to either of two groups: those who followed the betrayer, Illidan Stormrage, to find a new home on the shattered world of Outland; and those still loyal to Queen Azshara and her plan to reclaim the surface of Azeroth.

***Mystical Culture.*** Naga culture is a complex, multi&shy;faceted affair. The distinction between male and female naga saturates everything from their appearance to their perceived place in society.

Male naga are large and muscular creatures, some of them growing to be veritable behemoths with the strength to tear down walls with their bare hands. Most serve as soldiers and guardians, while some hold power as cruel taskmasters or as warlords on the battlefield.

Female naga are more delicate, though ruthlessly cunning and intellectually superior. They are natural spellcasters, and hone their skills to perfection in order to sunder their foes. Naga society is inherently matriarchal, favouring female leaders in zealous homage to their Highborne queen.

***Azshara's Followers.*** The naga revere their Queen, the mighty Azshara. To them, she is a living demigod in both power and stature, and all they do is by her design.

Factions of naga work tirelessly in their bid for power, seeking the Queen's blessing. To this end, there are few limits to how far they will go to earn her favour -- even at the cost of their own lives.

### Naga Myrmidon
The myrmidons, with their navy blue skin and fearsome tridents, are among the strongest among naga warriors. They are feared by all who dwell near the sea; though most prominently by the makrura.

They are often the most fanatical in their loyalty to the Queen. So much so that some would never take to their orders with anything other than utmost obedience.

### Naga Siren
Naga sirens are female naga who possess potent arcane spellcasting, capable of incapacitating their foes. While not as physical strong as their myrmidon, they are just as fearsome. 

Many gather to sing and practice their arcane arts at the Shrines of Azshara, perfecting and improving their insidious craft. 
<div class='letterheader'></div>
<div class="mmletter mml-n"></div>
<div class="pageLetter">N</div>
<div class='footnote'>NAGA </div>
<img src='https://www.gmbinder.com/images/4C0c6NF.jpg' style='position:absolute; top:100px; right:-250px; width:800px' />
<img src='https://www.gmbinder.com/images/l4AHa3B.png' style='position:absolute; top:-200px; right:-130px; width:1100px' />

\pagebreakNum

### Naga War Lord
Naga war lords are male naga warriors with shells and stone-like carapace fused to their skin, entirely covering their head and most of their upper body.

Their right arm has taken on the appearance of a large hermit crab, though it is unknown whether this is an inherent mutation or a deliberate choice.

### Naga Brute
Naga brutes are massive, lumbering beasts, strong enough to stand as siege weapons for the naga army. Some carry rank and title, while others act like little more than beasts.

Whichever is the case for a particular brute, they are not avoid of intelligence. They follow given orders to the best of their abilities, and know well enough to strategize their way around an obvious trap when they see one.

### Naga Names and Languages

In addition to speaking Common, the Naga have derived their own language from their Kaldorei roots -- Nazja.

Since the time of the Great Sundering, the language has grown to a distinctly sharp, wheezing character; well-suited for keeping conversation under the sea.

___
> ## Naga
>*Medium humanoid (naga), neutral evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 26 (4d8 + 8)
> - **Speed** 20 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|13 (+1)|14 (+2)|9 (-1)|12 (+1)|10 (+0)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** Common, Nazja
> - **Challenge** 1/2 (100 XP)
> ___
> ***Amphibious.*** The naga can breathe air and water.
>
> ***Slippery.*** The naga has advantage on ability checks and saving throws made to escape a grapple.
>
> ### Actions
> ***Scimitar.*** *Melee Weapon Attack:* +4 to hit, reach 5ft, one creature. *Hit:* 5 (1d6 + 2)
>
> ***Trident.*** *Melee or Ranged Weapon Attack:* +4 to hit, reach 10 ft. or range 20/60 ft., one creature. *Hit:* 5 (1d6 + 2) piercing damage, or 6 (1d8 + 2) piercing damage if used with two hands to make a melee attack.
>
> ***Constrict.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one Medium or smaller creature. *Hit:* 6 (1d8 + 2) bludgeoning damage, and target is grappled (escape DC 12). Until the grapple ends, the creature is restrained, and the naga cannot constrict another target.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;26;4;12;6;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;1;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

**Male names:** Atoph, Drazj, Heth'jatar, Kriellith, Nazjak,
<br />&nbsp;&nbsp;&nbsp; Naz'jaran, Skesessh, Zan'zarak
<br />**Female names:** Athiasa, Asrasi, Chazjia, Fyashi, Kazsi,
<br />&nbsp;&nbsp;&nbsp; Scyalla, Najesha, Zhiasi
<br />**Surnames:** Bloodstrike, Darksquall, Murkwail, Stormbow,
<br />&nbsp;&nbsp;&nbsp; Slitherfin, Stormscale, Wrathtail

<div style='margin-top:20px;'></div>

> ##### Variant: Naga Sorceress 
> Female naga are primarily spellcasters, and consider&shy;ably powerful ones at that for how they wield the turbulent powers of the sea. Naga sorceresses are novice spellcasters, as apprentices of a sea witches and sirens.
>
> A naga sorceress has the same statistics as a naga, save for Intelligence 14, Charisma 12, and the following additional trait:
>
> <br> ***Innate Spellcasting.*** The naga's innate spellcasting ability
is Intelligence (spell save DC 12). It can innately cast the
following spells, requiring no material components:
>
> <br> At will: *blade ward, ray of frost*
> <br> 1/day each:  *armor of agathys, ice knife*<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;26;4;12;19;0;6;0;6;0;0;0;0;0;0;0;;;;;3;;;;;1;;;;;1;;;;;;;;10;;;;;; -->

___
> ## Naga Myrmidon
>*Medium humanoid (naga), neutral evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 52 (7d8 + 21)
> - **Speed** 20 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|15 (+2)|16 (+3)|9 (-1)|12 (+1)|10 (+0)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** Common, Nazja
> - **Challenge** 3 (700 XP)
> ___
> ***Aggressive.*** As a bonus action, the naga can move up to its speed toward an enemy of its choice that it can see or hear. It must end this move closer to the enemy than it started.
>
> ***Amphibious.*** The naga can breathe air and water.
>
> ***Slippery.*** The naga has advantage on ability checks and saving throws made to escape a grapple.
>
> ### Actions
> ***Multiattack.*** The naga makes two halberd attacks, one of which can be replaced with its constrict attack.
>
> ***Halberd.*** *Melee Weapon Attack:* +5 to hit, reach 10 ft., one creature. *Hit:* 8 (1d10 + 3) slashing damage.
>
> ***Constrict.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one Medium or smaller creature. *Hit:* 7 (1d8 + 3) bludgeoning damage, and target is grappled (escape DC 13). Until the grapple ends, the creature is restrained, and the naga cannot constrict another target.<!-- https://wc5e-cr-calculator.frogvall.com/?0;15;52;5;12;16;0;0;0;0;0;0;0;0;0;0;0;;;;;3;1;;;;1;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">N</div>
<div class='footnote'>NAGA </div>
<img src='https://www.gmbinder.com/images/ePn0VkB.jpg' style='position:absolute; top:650px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

___
> ## Naga Siren
>*Medium humanoid (naga), neutral evil*
> ___
> - **Armor Class** 13 (16 with *mage armor*)
> - **Hit Points** 91 (14d8 + 28)
> - **Speed** 20 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|15 (+2)|14 (+2)|16 (+3)|12 (+1)|15 (+2)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** Common, Nazja
> - **Challenge** 4 (1,100 XP)
> ___
> ***Amphibious.*** The naga can breathe air and water.
>
> ***Slippery.*** The naga has advantage on ability checks and saving throws made to escape a grapple.
>
> ***Spellcasting.*** The naga is an 7th-level spellcaster. Its spellcasting ability is Intelligence (spell save DC 13, +5 to hit with spell attacks). The naga has the following mage and shaman spells prepared:
>
> Cantrips (at will):  *shape water, ✦ flurry, <br>&nbsp;&nbsp;&nbsp;✦ lightning blast*
> <br> 1st level (4 slots): *cure wounds, ice knife, <br>&nbsp;&nbsp;&nbsp; mage armor, thunderwave*
> <br> 2nd level (3 slots): *darkness, hold person, <br>&nbsp;&nbsp;&nbsp; warding wind*
> <br> 3rd level (3 slots): *✦ blizzard, tidal wave*
> <br> 4th level (1 slot):  *✦ amplify or dampen magic, <br>&nbsp;&nbsp;&nbsp; control water*
>
> ### Actions
> ***Multiattack.*** The naga makes two scimitar attacks, one of which can be replaced with its constrict attack.
>
> ***Scimitar.*** *Melee Weapon Attack:* +4 to hit, reach 5ft, one creature. *Hit:* 11 (2d8 + 2)
>
> ***Constrict.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one Medium or smaller creature. *Hit:* 6 (1d8 + 2) bludgeoning damage, and target is grappled (escape DC 12). Until the grapple ends, the creature is restrained, and the naga cannot constrict another target.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;91;5;13;44;0;36;0;36;0;0;0;0;0;0;0;;;;;3;;;;;1;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

___
> ## Naga War Lord
>*Large humanoid (naga), neutral evil*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 170 (20d10 + 60)
> - **Speed** 25 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|15 (+2)|16 (+3)|9 (-1)|12 (+1)|15 (+2)|
>___
> - **Skills** Perception +4
> - **Senses** passive Perception 14
> - **Languages** Common, Nazja
> - **Challenge** 7 (2,900 XP)
> ___
> ***Amphibious.*** The naga can breathe air and water.
>
> ***Slippery.*** The naga has advantage on ability checks and saving throws made to escape a grapple.
>
> ### Actions
> ***Multiattack.*** The naga makes two halberd attacks, one of which can be replaced with its constrict attack.
>
> ***Halberd.*** *Melee Weapon Attack:* +7 to hit, reach 10 ft., one creature. *Hit:* 20 (3d10 + 4) slashing damage.
>
> ***Constrict.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one Large or smaller creature. *Hit:* 13 (2d8 + 4) bludgeoning damage, and target is grappled (escape DC 15). Until the grapple ends, the creature is restrained, and the naga cannot constrict another target.
>
> ***Crashing Wave (Recharges 5-6).*** The naga charges forward creating a wave of water that crashes anyone on its path. The naga moves 20 feet forward in a straight line producing a wave 20 feet long, 10 feet tall and 10 feet wide . Each creature in that area must make a Dexterity saving throw. On a failed save, a creature takes 22 (5d8) bludgeoning damage and is knocked prone. On a successful save, a creature takes half as much damage and isn't knocked prone.
>
> ***Leadership (Recharges after a Short or Long Rest).*** For 1 minute, the naga can utter a special command or warning whenever a non-hostile creature that it can see within 30 feet of it makes an attack roll or a saving throw. The creature can add a d4 to its roll provided it can hear and understand the naga. A creature can benefit from only one Leadership die at a time. This effect ends if the naga is incapacitated.
>
> ### Reactions
> ***Parry.*** The naga adds 3 to its AC against one melee attack that would hit it. To do so, the naga must see the attacker and be wielding a melee weapon.<!-- https://wc5e-cr-calculator.frogvall.com/?1;16;170;7;13;44;0;40;0;40;0;0;0;0;0;0;0;;;;;3;;;;;1;;;;;1;;;;1;;;;10;;;;;; -->

<div class="pageLetter">N</div>
<div class='footnote'>NAGA </div>
<img src='https://www.gmbinder.com/images/QOgKqCD.jpg' style='position:absolute; top:700px; right:0px; width:800px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/epoShfv.png' style='position:absolute; top:-390px; right:-50px; width:1000px;transform:rotate(5deg)' />

\pagebreakNum

<div style='margin-top:1000px;'></div>

___
___
> ## Naga Brute
>*Huge monstrosity, neutral evil*
> ___
> - **Armor Class** 17 (natural armor)
> - **Hit Points** 178 (17d12 + 68)
> - **Speed** 30 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|21 (+5)|15 (+2)|18 (+4)|8 (-1)|12 (+1)|7 (-2)|
>___
> - **Skills** Perception +5
> - **Senses** passive Perception 15
> - **Languages** understands Nazja but doesn't speak
> - **Challenge** 9 (5,000 XP)
> ___
> ***Amphibious.*** The naga can breathe air and water.
>
> ***Relentless (Recharges after a Short or Long Rest).*** if the naga takes 20 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ***Slippery.*** The naga has advantage on ability checks and saving throws made to escape a grapple.
>
> ### Actions
> ***Multiattack.*** The naga makes one bite attack and one slam attack.
>
> ***Bite.*** *Melee Weapon Attack:* +9 to hit, reach 5 ft., one target. *Hit:* 18 (3d8 + 5) piercing damage.
>
> ***Slam.*** *Melee Weapon Attack:* +9 to hit, reach 5 ft., one target. *Hit:* 27 (4d10 + 5) bludgeoning damage.
>
> ***Massive Crash (Recharges 4-6).*** The naga slams the ground creating an earth tremor around it. Each creature other than the naga in a 10-foot radius centered on the naga must make a Dexterity saving throw. On a failed save, a creature takes 31 (7d8) bludgeoning damage and is knocked prone. On a successful save, a creature takes half as much damage and isn't knocked prone.<!-- https://wc5e-cr-calculator.frogvall.com/?1;17;178;9;13;62;0;45;0;45;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;1;;;;; -->

<div class="pageLetter">N</div>
<div class='footnote'>NAGA </div>
<img src='https://www.gmbinder.com/images/hvUUxG8.jpg' style='position:absolute; top:570px; right:-180px; width:1000px' />
<img src='https://www.gmbinder.com/images/hIpYyKx.png' style='position:absolute; top:-70px; right:0px; width:950px' />
<img src='https://www.gmbinder.com/images/QZfSRiM.png' class='inkblot' style='top:-100px; right:-50px; width:900px'>
<img src='https://www.gmbinder.com/images/ZYrQqIH.jpg' style='position:absolute; top:0px; right:20px; width:700px;mix-blend-mode:darken' />

\pagebreakNum

<div style='margin-top:140px;'></div>

## Ogres
Ogres are large, brutish humanoids of immense strength. Though native to the crumbling world of Draenor, many ogres have since settled as independent clans on Azeroth. The average adult ogre stands between 9 and 10 feet tall, weighing in at almost a thousand pounds.

As far as the ogre is concerned, size is paramount. They eschew any attempt to cover themselves up, keeping their clothing simple, while brandishing fearsome warpaints.

***Distant Settlements.*** Following the Horde's second failure to invade Azeroth, the ogre clans that had come with them from Draenor quickly dispersed.

Each clean headed in their own direction. Some sought to return back home, while most were content to stake a claim in this new world. Since then, ogres have settled across the world; from the hills of Arathi and the Cape of Stranglethorn, to the lush reaches of Feralas.

***Clan Culture.*** Within ogre clans, it is the strongest that stand in highest regard. An immense show of force is the fastest way to rise, though also the fastest way to fall <br/> at the hands of any enemies made along the way.

Still, for as highly as the ogres regard their <br/> strength, the powerful and keen-minded ogre <br/> magi are often the real presence of power <br/> within their clan. Whether acting as the right <br/> hand of an ogre lord, or as the clan leader <br/> directly, they are the ones pulling the strings.

***Brutish Combatants.*** For an ogre, the best <br/> solution is often the simplest one. When engaged <br/> in a fight, it is not uncommon for the ogre to risk <br/> even deadly harm if thinks it can push through and <br/> come out on top by sheer virtue of strength.

They are vicious opponents, strong enough to rend limb from limb with their bare hands, and crush skulls with their spiked clubs and stone-hewn mauls.

### Ogre Magi
The ogre magi, with its two heads, holds an intelligence far exceeding the rest of its kin. Borne of the same magic that they wield, it was not uncommon for the Horde -- in its second invasion of Azeroth -- to force this transformation in order to bolster its rank of spellcasters.

Although the two heads are not always in agreement, they are paramount to the ogre's magical aptitude. A living proof that having two heads can be better than having one.

### Ogre Lord
Ogre lords are massive, hulking figures, towering above their clan in both size and status. While they have no aptitude for magic and little thought for intricate plans, their imposing presence precedes them well enough to keep the rest of their clan in check.

Many might try to challenge an ogre lord's power over the course of its heavy-handed rule, though for most of them this confrontation doesn't end well.

\columnbreak

<div style='margin-top:600px;'></div>

___
> ## Ogre
>*Large giant, chaotic evil*
> ___
> - **Armor Class** 11 (hide armor)
> - **Hit Points**  93 (11d10 + 33)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|19 (+4)|    8 (-1)|    16 (+3)|    8 (-1)|    7 (-2)|    7 (-2)|
>___
> - **Senses** darkvision 60 ft., passive Perception 8
> - **Languages** Low Common
> - **Challenge** 2 (450 XP)
> ___
>
> ### Actions
>
> ***Greatclub.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) bludgeoning damage.
>
> ***Rock.*** *Ranged Weapon Attack:* +6 to hit, range 60/180 ft., one target. Hit: 15 (2d10 + 4) bludgeoning damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;11;93;6;12;15;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class='letterheader'></div>
<div class="mmletter mml-o"></div>
<div class="pageLetter">O</div>
<div class='footnote'>OGRES </div>

<img src='https://www.gmbinder.com/images/64Wsryy.png' class='inkblot' style='top:0px; right:-100px; width:600px'>
<img src='https://www.gmbinder.com/images/cvz0pMW.png' style='position:absolute; top:20px; right:-60px; width:550px;transform:scalex(-1)' />

\pagebreakNum

> ##### Variant: Ogre Priest
> A few ogre magi supplement their dark powers with healing spells to aid their allies. They are regarded as spiritual leaders and record-keepers for their tribe. An ogre priest has Intelligence 11 and Wisdom 14, as well as the following trait:
> <br>    ***Spellcasting.*** The ogre is a 9th-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 14, +6 to hit with spell attacks). The ogre has the following priest spells prepared:
> <div style='margin-top:-15px;'></div>
>
> <br> Cantrips (at will): *✦ mind blast, resistance,<br>&nbsp;&nbsp;&nbsp; ✦ shadow bolt, virtue*
> <br> 1st level (4 slots): *cause fear, ✦ dark void,<br>&nbsp;&nbsp;&nbsp; healing word, shield of faith*
> <br> 2nd level (3 slots): *lesser restoration, ✦ mind flay, <br>&nbsp;&nbsp;&nbsp; silence*
> <br> 3rd level (3 slots): *dispel magic, hunger of hadar,<br>&nbsp;&nbsp;&nbsp; speak with dead*
> <br> 4th level (3 slots): *death ward, ✦ void shift*
> <br> 5th level (1 slot): *✦ shadow crash*
> <div style='margin-top:-30px;'></div>
>
> <br><br> *The ogre casts shield of faith on itself before combat*<!-- https://wc5e-cr-calculator.frogvall.com/?1;11;90;0;14;0;28;72;28;14;28;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div style='margin-top:-20px;'></div>

___
> ## Ogre Magi
>*Large giant, chaotic evil*
> ___
> - **Armor Class** 9 (12 with *mage armor*)
> - **Hit Points**  90 (12d10 + 24)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|19 (+4)| 9 (-1)| 14 (+2)| 14 (+2)|  11 (+0)|    7 (-2)|
>___
> - **Skills** Arcana +5, History +5
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Common, Ogre, Low Common
> - **Challenge** 5 (1800 XP)
> ___
> ***Spellcasting.*** The ogre is a 7th-level spellcaster. Its spellcasting ability is Intelligence (spell save DC 14, +6 to hit with spell attacks). The ogre has the following mage spells prepared:
>
> Cantrips (at will): *✦ arcane blast, blade ward,<br>&nbsp;&nbsp;&nbsp; create bonfire, fire bolt*
> <br> 1st level (4 slots): *armor of agathys, mage armor, <br>&nbsp;&nbsp;&nbsp; magic missile*
> <br> 2nd level (3 slots): *enlarge/reduce, scorching ray, <br>&nbsp;&nbsp;&nbsp; see invisibility*
> <br> 3rd level (3 slots): *✦ arcane explosion, glyph of <br>&nbsp;&nbsp;&nbsp; warding, haste, slow*
> <br> 4th level (1 slot): *✦ arcane barrage*
>
> *The ogre casts mage armor on itself before combat.*
>
>***Two Heads.*** The ogre has advantage on Wisdom (Perception) checks and on saving throws against being blinded, charmed, deafened, frightened, stunned, and knocked unconscious.
>
> ### Actions
> ***Maul:*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 11 (2d6 + 4) bludgeoning damage.<!-- https://wc5e-cr-calculator.frogvall.com/?1;12;90;0;14;62;0;54;0;54;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:17px;'></div>

### Ogre Names and Languages
Historically, ogres have long held their own tongue, though their dispersion across Azeroth have turned many clans to broken forms of Common -- and sometimes Orcish.

Ogre is a very coarse language, largely consisting of short, throaty sounds. Its written form has long been kept solely to the upper echelons of ogre society.

For many ogres, the closest remnant of their language is in their names. Some ogres carry simple, descriptive titles for names, though many still use names with clear meaning in their own tongue.

Most prominent are the names of the **ogre magi**. Their two heads have each a mind of their own, and with it their own name. The full name of the magi is a combination of the two: the smartest head first and the other thereafter.

<div style='margin-top:-5px;'></div>

**Male names:** Chokk, Drak, Garg, Hok'kran, Krol, Mug
<br />**Female names:** Agra, Baki, Brakka, Nakki, Mruka, Ugra'ka
<br />**Tribe names:** Bloodcrush, Boulderfist, Dustgorge,
<br />    Splinterstone, Stonemaul, Warmaul

___
> ## Ogre Lord
>*Huge giant, chaotic evil*
> ___
> - **Armor Class** 17 (natural armor, metal plates)
> - **Hit Points**  147 (14d12+56)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|21 (+5)| 9 (-1)| 18 (+4)| 10 (+0)| 9 (-1)| 7 (-2)|
>___
> - **Skills** Perception +2
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** Low Common, Ogre
> - **Challenge** 7 (2900 XP)
> ___
> ***Aggressive.*** As a bonus action, the ogre can move up to its speed toward an enemy of its choice that it can see or hear. It must end this move closer to the enemy than it started.
>
> ***Mighty Presence.*** While it is conscious, the ogre and any friendly creature within 10 feet of it has advantage on saving throws against being frightened.
>
> ### Actions
>
> ***Multiattack.*** The ogre makes two greatclub attacks, one of which can be replaced with its shockwave.
>
> ***Greatclub.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one target. *Hit:* 18 (3d8 + 5) bludgeoning damage.
>
> ***Rock.*** *Ranged Weapon Attack:* +8 to hit, range 60/180 ft., one target. Hit: 27 (4d10 + 5) bludgeoning damage.
>
> ***Shockwave (Recharge 5-6).***  The ogre hits the ground with its greatclub causing a burst of concussive force. Each creature in a 15-foot cone  originating from the ogre must make a Dexterity saving throw. On a failed save, a creature takes 14 (4d6) bludgeoning damage and is knocked prone. If the ground in that area is loose earth or stone, it becomes difficult terrain.<!-- https://wc5e-cr-calculator.frogvall.com/?1;17;147;8;12;18;28;36;0;36;0;0;0;0;0;0;0;;;;;3;1;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">O</div>
<div class='footnote'>OGRES </div>


\pagebreakNum

<div style='margin-top:410px;'></div>

___
> ## Owlbeast
>*Large monstrosity, neutral good*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 90 (12d10 + 24)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|12 (+1)|15 (+2)|6 (-2)|12 (+1)|8 (-1)|
>___
> - **Skills** Perception +3
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** understands Darnassian but can't speak
> - **Challenge** 3 (700 XP)
> ___
> ***Keen Sight and Smell.*** The owlbeast has advantage on Wisdom (Perception) checks it makes that rely on sight or smell.
>
> ### Actions
> ***Multiattack.*** The owlbeast makes two attacks: one with its beak and one with its claws.
>
> ***Beak.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 7 (1d8 + 3) piercing damage, or 10 (1d8 + 6) piercing damage while enraged.
>
> ***Claws.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 10 (2d6 + 3) slashing damage, or 13 (2d6 + 6) slashing damage while enraged.
>
> ***Wild Rage (Recharges after a Short or Long Rest).*** <br>For 1 minute the owlbeast enters a rage. While enraged, the owlbeast's attacks deal an additional 3 damage (included in the attacks), and makes Strength checks and Strength saving throws with advantage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;90;5;12;17;0;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:460px;'></div>

## Owlbeasts
The owlbeasts are serene and powerful creatures, <br/> inhabiting many forested regions across Azeroth. <br>They resemble a cross between a bear and an owl, <br>suited with the antlers of a great stag and the massive, <br/>hooked beak of a bird of prey.

With their lumbering build and remarkably strong claws, they might seem like fearsome predators. However, their looks betray them for the gentle creatures they really are -- at least when they are left well alone.

***Forest Settlements.*** Owlbeasts keep to dense forests, finding shelter to build nests between rocks and inside caves. They are social creatures at heart, living harmoni&shy;ously with their fellows in small colonies, not keeping to any apparent structure of leadership.

From time to time, their choice of settlement may bring them into close contact with another race. For the most part, this is not a problem, as the creatures have been seen thriving in the company of night elves and tauren.

Other times, it may force them to fight for their claim or move on to somewhere else. Once first provoked, they are quick to enrage -- at which point all hope for reason may well be lost.

***Peaceful Creatures.*** Travellers with the care to show respect are seldom hard-pressed to find aid from these gentle giants; whether they're seeking help, or a safe passage out of the woods. Still, if one does opt to disregard the owlbeasts or meet them with hostile intent, they are rarely ever shy to respond in kind.

***Children of Elune.*** The goddess Elune first created the Owlbeasts in ages past, joining the strength of the bear with the wisdom of the owl, to serve as guardians for the demigod Cenarius. Though blessed by the moon, some have fallen stray from their path, lost and confused without the guidance of their goddess.

<div class="pageLetter">O</div>
<div class='footnote'>OWLBEASTS</div>
<img src='https://www.gmbinder.com/images/CmjXePR.jpg' style='position:absolute; top:-20px; right:-20px; width:640px' />
<img src='https://www.gmbinder.com/images/z86Lpca.png' style='position:absolute; top:-150px; right:0px; width:1000px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/lKUDalm.png' style='position:absolute; top:-100px; right:340px; width:600px' />

\pagebreakNum

&nbsp;&nbsp;&nbsp; ***Corruptible Minds.*** Owlbeasts are, as with most wild beings on Azeroth, susceptible to corruption. Whether by fel energies or nightmarish whispers, it only takes so much to tip the scales and turn these docile beings into ferocious monsters. Such flocks are eventually sought out by druids seeking to intervene, though there is no telling what chaos they might have wrought in the meantime.

### Moonkin
Though all owlbeasts are children of Elune, few keep their blessing closer to heart than the graceful moonkin. The two may seem near indistinguishable at first, but the moonkin's heightened mind leaves it more than capable of coherent dialogue and rational thought.

Bound to their groves and keeping in druidic circles, to whom they act as guardians, they boast a formidable breadth of magical power.

___
> ## Moonkin
>*Large monstrosity, chaotic good*
> ___
> - **Armor Class** 13 (16 with *barkskin*)
> - **Hit Points** 85 (10d10 + 30)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|12 (+1)|16 (+3)|10 (+0)|16 (+3)|8 (-1)|
>___
> - **Skills** Perception +6
> - **Senses** darkvision 60 ft., passive Perception 16
> - **Languages** Darnassian
> - **Challenge** 5 (1,800 XP)
> ___
>
> ***Keen Sight and Smell.*** The moonkin has advantage on Wisdom (Perception) checks it makes that rely on sight or smell.
>
> ***Spellcasting.*** The moonkin is a 9th-level spellcaster. Its spell casting ability is Wisdom (spell save DC 14, +6 to hit with spell attacks). The moonkin has the following druid spells prepared:
>
> Cantrips (at will) :  *druidcraft, resistance, ✦ solar wrath*
> <br> 1st level (4 slots): *healing word, entangle, faerie fire, <br>&nbsp;&nbsp;&nbsp; ✦ starfire*
> <br> 2nd level (3 slots): *barkskin, ✦ cyclone, moonbeam*
> <br> 3rd level (3 slots): *mass healing word, plant growth, <br>&nbsp;&nbsp;&nbsp; ✦ starsurge*
> <br> 4th level (3 slots): *grasping vine, guardian of nature*,
> <br> 5th level (1 slot):  *wrath of nature*
>
> ### Actions
> ***Multiattack.*** The moonkin makes two attacks: one with its beak and one with its claws.
>
> ***Beak.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 10 (2d6 + 3) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 12 (2d8 + 3) slashing damage<!-- https://wc5e-cr-calculator.frogvall.com/?1;13;85;0;14;70;0;62;0;62;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">O</div>
<div class='footnote'>OWLBEASTS</div>
<img src='https://www.gmbinder.com/images/mxHF0lq.jpg' style='position:absolute; top:0px; right:-350px; width:850px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/VSTbbfG.png' style='position:absolute; top:0px; right:-30px; width:900px' />

\pagebreakNum

<div style='margin-top:440px;'></div>

___
> ## Quilboar
>*Medium humanoid (quilboar), neutral evil*
> ___
> - **Armor Class** 10
> - **Hit Points** 7 (1d8 + 2)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|11 (+0)|14 (+2)|8 (-1)|10 (+0)|9 (-1)|
>___
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Common, Quilboar
> - **Challenge** 1/4 (50 XP)
> ___
> ***Keen Smell.*** The quilboar has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Vengeance.*** The quilboar can make an opportunity attack with disadvantage against a target within range when another quilboar that it can see or hear dies.
>
> ### Actions
> ***Tusk.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) slashing damage.
>
> ***Mace.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) bludgeoning damage.
>
> ### Reactions
> ***Quills.*** In response to being hit by a melee attack, the quilboar can spew quills back at the attacker. *Melee Weapon Attack:* +4 to hit, range 10 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.
<!-- https://wc5e-cr-calculator.frogvall.com/?0;10;7;3;12;4;4;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:300px;'></div>

## <span style="margin-left:95px"></span> Quilboars
<span style="margin-left:110px"></span> A ferocious, suicidally brave race, quil-
<span style="margin-left:115px"></span> boars are renowned for their stubby,
<span style="margin-left:125px"></span> pig-like appearance. Rows of sharp
<span style="margin-left:130px"></span> spines run down their hunched
<span style="margin-left:125px"></span> backs, and stubby tusks protrude
<span style="margin-left:110px"></span> from their mouth.

<span style="margin-left:40px"></span> They adorn their skin with tribal markings and tattoos, and their devotion to their tribe may seem almost alien to most other races.

***Sacred Settlements.*** Quilboars live in the protective shade of enormous bramble roots, so large that they choke the land of all other life. These thorny landscapes, believed to have first grown from the blood of the ancient guardian Agamaggan, are considered sacred to the quilboars.

Should the land become too barren for even them, they are quick to tear down and move on. Once a tribe finds a new place to settle, its mighty thornweavers seed and grow forth new roots for them to live in.

***Hostile Colonies.*** Within their thorny settlements, a quilboar tribe can grow impressively large. Loyalty to the tribe is paramount for its survival, to which they train their young quickly to meet any outsiders with hostility.

***Ancient Powers.*** Quilboars practice a crude form of shamanism, with the blessing of Agamaggan. These shamans, known as thornweavers, are kept in high regard by their tribes as the voice of their ancient guardian.

They revere Agamaggan, the great boar, as their creator. By making offerings in his name, a tribe's fighters can summon forth terrifying strength as they descend upon their foes.

### Quilboar Packmaster
With their natural bond to the great boar, some quilboars have have made it their lives to raise and fight alongside such creatures. A packmaster rarely walks alone, always taking one or more boars in its company.

### Quilboar Thornweaver
The thornweavers are vital to a quilboar tribe's survival, as these wise shamans bring forth the thorny brambles in which the tribe makes its home. Even the tribe's chieftain knows well to respect the word of a thornweaver. By their bond, they are the voice of Agamaggan.

<div class='letterheader'></div>
<div class="mmletter mml-q"></div>
<div class="pageLetter">Q</div>
<div class='footnote'>QUILBOARS </div>

<img src='https://www.gmbinder.com/images/KcRAZwq.png' class='inkblot inkblot-green' style='top:-100px; right:300px; width:500px; transform:rotate(40deg)'>
<img src='https://www.gmbinder.com/images/ljH3Xaj.png' style='position:absolute; top:40px; right:250px; width:650px' />

\pagebreakNum

### Quilboar Chieftain
At the head of the quilboar tribe sits its chieftain. In most cases, the rise of a tribe's chieftain came at the demise of its last. They surround themselves with their thornweavers for guidance, and sometimes wield a host of battleguards at their side.

### Quilboar Names and Languages
The quilboar language is a rough, sharp-spoken tongue that relies on a mixture of guttural sounds and sharp squeals. There is little room for eloquence in their vocabulary, though it is by no means primitive.

Their names follow a mixture of native descriptions and short words, and their names lead descriptive, evocative titles -- for which rough translations in other languages often become the most widely known.

<div style='margin-top:-5px;'></div>

**Quilboar Names:** Aggem, Jargba, Gukk'rok, Hagg,
<br />&nbsp;&nbsp;&nbsp; Kuz, Mok, Nak, Roogug, Snokh, Trok
<br />**Clan Names:** Blacksnout, Briarback, Bristleback,
<br />&nbsp;&nbsp;&nbsp; Foultusk, Razorfen, Razormane

<div style='margin-top:-10px;'></div>

___
> ## Quilboar Packmaster
>*Medium humanoid (quilboar), neutral evil*
> ___
> - **Armor Class** 13 (leather)
> - **Hit Points** 13 (3d8)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|14 (+2)|10 (+0)|9 (-1)|12 (+1)|9 (-1)|
>___
> - **Skills** Animal Handling +3
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** Common, Quilboar
> - **Challenge** 1/2 (100 XP)
> ___
> ***Keen Smell.*** The quilboar has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Vengeance.*** The quilboar can make an opportunity attack with disadvantage against a target within range when an ally that it can see or hear dies.
>
> ### Actions
> ***Multiattack.*** The quilboar uses its Master's Command. It then makes one attack with its tusks or javelin.
>
> ***Tusk.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one target. *Hit:* 2 (1d4) slashing damage.
>
> ***Javelin.*** *Melee or Ranged Weapon Attack:* +4 to hit, reach 5 ft. or range 30/120 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Master's Command.*** The quilboar commands a tamed beast within 30 feet of it to attack a target, giving the beast advantage on the next attack it makes against it.
>
> ### Reactions
> ***Quills.*** In response to being hit by a melee attack, the quilboar can spew quills back at the attacker. *Melee Weapon Attack:* +4 to hit, range 10 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;13;13;4;12;5;4;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:330px;'></div>

___
> ## Quilboar Thornweaver
>*Medium humanoid (quilboar), neutral evil*
> ___
> - **Armor Class** 12 (16 with barkskin)
> - **Hit Points** 22 (4d8 + 4)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|14 (+2)|13 (+1)|9 (-1)|15 (+2)|9 (-1)|
>___
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** Common, Quilboar
> - **Challenge** 1 (200 XP)
> ___
> ***Keen Smell.*** The quilboar has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Vengeance.*** The quilboar can make an opportunity attack with disadvantage against a target within range when an ally that it can see or hear dies.
>
> ***Spellcasting.*** The quilboar is a 3rd-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). It has the following druid spells prepared:
>
> Cantrips (at will): *resistance, shillelagh, thorn whip*
> <br> 1st level (4 slots): *cure wounds, faerie fire, sleep*
> <br> 2nd level (2 slots): *barkskin, spike growth*
>
> **The quilboar casts barkskin on itself before combat.*
>
> ### Actions
> ***Tusk.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one target. *Hit:* 2 (1d4) slashing damage.
>
> ***Quarterstaff.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one target. *Hit:* 4 (1d8) bludgeoning damage.
>
> ### Reactions
> ***Quills.*** In response to being hit by a melee attack, the quilboar can spew quills back at the attacker. *Melee Weapon Attack:* +4 to hit, range 10 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;16;22;4;12;6;4;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">Q</div>
<div class='footnote'>QUILBOARS </div>

<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot inkblot-green' style='top:0px; right:0px; width:500px'>
<img src='https://www.gmbinder.com/images/Tmf8a9n.png' style='position:absolute; top:-20px; right:25px; width:390px' />

\pagebreakNum

<div style='margin-top:320px;'></div>

> ##### Variant: Quilboar Battleguard
> A quilboar battleguard has a challenge rating of 4 (1,100 XP). It has the same statistics as a quilboar chieftain, except it gains the following special abilities and loses the Leadership action.
>
> ***Charge.*** If the quilboar moves at least 20 feet straight toward a target and then hits it with a tusk attack on the same turn, the target takes an extra 5 (2d4) slashing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ***Relentless (Recharges after a Short or Long rest).*** If the quilboar takes 12 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.

<div class='statblock-bottom-wide'>

___
___
> ## Quilboar Chieftain
>*Medium humanoid (quilboar), neutral evil*
> ___
> - **Armor Class** 15 (breastplate)
> - **Hit Points** 52 (8d8 + 16)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|12 (+1)|15 (+2)|13 (+1)|12 (+1)|9 (-1)|
>___
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** Common, Quilboar
> - **Challenge** 3 (700 XP)
> ___
> ***Keen Smell.*** The quilboar has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Vengeance.*** The quilboar can make an opportunity attack with disadvantage against a target within range when an ally that it can see or hear dies.
>
> ***Brute.*** A melee weapon deals one extra die of its damage when the quilboar hits with it (included in the attack).
>
> ### Actions
> ***Multiattack.*** The quilboar makes two melee attacks: one with its tusk and one with its battleaxe.
>
> ***Tusk.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (2d4 + 3) slashing damage.
>
> ***Battleaxe.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 12 (2d8 + 3) slashing damage, or 14 (2d10 + 3) slashing damage if used with two hands to make a melee attack.
>
> ***Leadership (Recharges after a Short or Long Rest).*** For 1 minute, the quilboar can utter a special command or warning whenever a nonhostile creature that it can see within 30 feet of it makes an attack roll or a saving throw. The creature can add a d4 to its rolls provided it can hear and understand the quilboar. A creature can benefit from only one Leadership die at a time. This effect ends if the quilboar is incapacitated.
>
> ### Reactions
> ***Quills.*** In response to being hit by a melee attack, the quilboar can spew quills back at the attacker. *Melee Weapon Attack:* +4 to hit, range 10 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.<!-- https://wc5e-cr-calculator.frogvall.com/?0;15;52;5;12;22;4;0;0;0;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

</div>

<div class="pageLetter">Q</div>
<div class='footnote'>QUILBOARS </div>
<img src='https://www.gmbinder.com/images/wYkRYT1.jpg' style='position:absolute; top:0px; right:-150px; width:1000px' />
<img src='https://www.gmbinder.com/images/8x5CGKk.png' style='position:absolute; top:0px; right:0px; width:900px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/YpvK7Ef.png' class='inkblot inkblot-green' style='top:50px; right:-100px; width:600px'>
<img src='https://www.gmbinder.com/images/DY0bq9o.png' style='position:absolute; top:0px; right:-20px; width:600px' />

\pagebreakNum

<div style='margin-top:470px;'></div>

___
> ## Ravager <!-- https://wc5e-cr-calculator.frogvall.com/?0;14;44;5;12;9;0;9;0;9;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 44 (8d8 + 8)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|16 (+3)|13 (+1)|4 (-3)|9 (-1)|3 (-4)|
>___
> - **Skills** Stealth +5
> - **Damage Resistances** bludgeoning
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Keen Smell.*** The ravager has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Swarming.*** The ravager can move through a hostile creature's space even if the creature isn't two sizes larger or smaller than the ravager.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) piercing damage plus 3 (1d6) poison damage. If the target is wearing armor and the attack roll exceeds the target's AC by 5 or more, the target's armor takes a permanent and cumulative <br>-1 penalty to the AC it offers. Armor reduced to an AC of 10 is destroyed.

\columnbreak

<div style='margin-top:140px;'></div>

## Ravagers
Native to the world of Draenor, these quadrupedal beings roam across their surrounding land in search of food to fill their insatiable appetite, ready to hound down and tear apart any creature made of flesh.

Ravagers resemble giant insectiods, equipped with ragged teeth and a voracious lust for meat. Their bodies are covered in hard chitin, which combined with their impressive speed make them amicable fighters.

***Ferocious Carnivores.*** Being such fierce predators, ravagers hunt together in swarms. They hide behind rocks and within crevices, waiting for their quarry to come within reach. Then, as soon as the moment comes, lunge out from hiding and rush into the fray with overwhelming force.

***Swarm Mentality.*** Perhaps not too surprising, given their insect-like appearance, are the ever-growing ravager colonies. Though their hive mind is not as intrinsically linked as some others, it still binds the colony together as a large, fiercely protective swarm.

***Migrated Creatures.*** Ravagers are native to the world of Draenor, with no true equal on Azeroth -- save for one small colony, locked away on the Exodar with the fleeing Draenei.

The ship's subsequent crash off the northern coast of Kalimdor saw this particular group of ravagers released into the wild. Most were stopped in their tracks, though some may yet have escaped to flee deeper into the thickets, or across the waters to the mainland.

### Ravager Brood Mother
At the heart of a ravager colony sits its queen; the brood mother. She grants the colony life, by laying the eggs that hatch into the ravager larva. For her vital part in keeping the colony alive, other ravagers in the colony will go to extreme lengths to ensure her safety.

### Ravager Wasp
Following the birth of a ravager larva, the creature quickly cocoons itself in order to grow further. From the cocoon, the ravager emerges as a slender wasp with a ferocious sting. The ravager wasp gorges itself on its prey, feeding until its wings can no longer support the weight of its body. Then, its wings are shed; as the wasp undergoes one final metamorphosis into a full-grown, four-legged ravager.

> ##### Ravagers on alternate Draenor
> The ravagers of alternate Draenor were never exposed to the powers of fel, their bodies were not malformed. These creatures have evolved into large monsters more resembling four-legged spiders, their wings have grown with them giving all ravagers a flying speed equal to their normal speed.

<div class='letterheader'></div>
<div class="mmletter mml-r"></div>
<div class="pageLetter">R</div>
<div class='footnote'>RAVAGERS </div>

<img src='https://www.gmbinder.com/images/OkSEy3f.png' class='inkblot inkblot-green' style='position:absolute; top:0px; right:380px; width:600px' />
<img src='https://www.gmbinder.com/images/zzz8zOr.png' style='position:absolute; top:60px; right:350px; width:450px' />

\pagebreakNum

___
> ## Ravager Brood Mother <!-- https://wc5e-cr-calculator.frogvall.com/?0;16;105;6;12;22;0;22;0;22;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large beast, unaligned*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 105 (14d10 + 28)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|13 (+1)|15 (+2)|4 (-3)|12 (+1)|3 (-4)|
>___
> - **Skills** Stealth +5
> - **Damage Resistances** bludgeoning
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** —
> - **Challenge** 4 (1,100 XP)
> ___
> ***Brood's Courage.*** The ravager and allied creatures within 30 feet that can see or hear the ravager has advantage on saving throws against being frightened.
>
> ***Keen Smell.*** The ravager has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Multiattack.*** The ravager makes two bite attacks.
>
> ***Bite.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 8 (1d8 + 4) piercing damage plus 3 (1d6) poison damage. If the target is wearing armor and the attack roll exceeds the target's AC by 5 or more, the target's armor takes a permanent and cumulative <br>-1 penalty to the AC it offers. Armor reduced to an AC of 10 is destroyed.
>
> ***Distress Call (Recharge 6).*** The ravager makes a deafening screech, each creature within 20 feet of it that can hear it and that isn't a ravager must succeed on a DC 12 Constitution saving throw or be deafened for 1 minute. The screech can be heard within 240 feet of the ravager, altering the brood of danger.
>
> ***Stunning Screech (1/day).*** The ravager emits a horrific screech. Each creature within 20 feet of it that can hear it and that isn't a ravager must succeed on a DC 14 Constitution saving throw or be stunned until the end of the ravager's next turn.
>
> ### Reactions
> ***Brood's Protection.*** When a creature the ravager can see targets it with an attack, the ravager can choose another ravager within 5 feet of it. The chosen ravager uses its reaction to protect the brood mother, becoming the new target of the attack.

\columnbreak

___
> ## Ravager Wasp <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;21;3;12;5;0;5;0;5;0;0;0;0;0;0;0;;;1;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Small beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 21 (6d6)
> - **Speed** 10 ft., fly 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|7 (-2)|13 (+1)|10 (+0)|2 (-4)|7 (-2)|3 (-4)|
>___
> - **Senses** darkvision 60 ft., passive Perception 8
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
> ***Flyby.*** The ravager doesn't provoke opportunity attacks when it flies out of an enemy's reach.
>
> ***Swarming.*** The ravager can move through a hostile creature's space even if the creature isn't two sizes larger or smaller than the ravager.
>
> ### Actions
> ***Sting.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 2 (1d4) piercing damage plus 3 (1d6) poison damage.

<div class="pageLetter">R</div>
<div class='footnote'>RAVAGERS </div>
<img src='https://www.gmbinder.com/images/DLVtbKb.jpg' style='position:absolute; top:350px; right:-500px; width:2000px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:-360px; right:0px; width:900px' />
<img src="https://www.gmbinder.com/images/y63HAI5.png" style="position:absolute; top:470px; right:-18px; width:px; transform:rotate(-3deg); filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">

\pagebreakNum

<div style='margin-top:110px;'></div>

## Sabercats
Sabercats are cunning felines, native to the northern <br/> reaches of Kalimdor. These magnificent beasts have <br/> been the companions of many adventurers -- and the demise of many more. They are intelligent creatures; <br/> very loyal when properly domesticated, while still <br/> remaining aggressive and territorial in the wilds.

***Stalkers of Azeroth.*** Favoured as they are among travellers, sabercats have come to live far and wide across Azeroth. Still, the majority of their kind keep to Kalimdor, where they populate dense forests and icy wastes alike. They are quick to adapt to their given habitat, sprouting pelts able to blend their surroundings.

Many species of sabercats exist, each one distinct and differing remarkably in how it would approach outsiders. The most common types of sabercats are the dreadsabers, the frostsabers, and the nightsabers.

***Supreme Predators.*** Sabercats are deadly predators, representing the pinnacle of a stalking hunter. They are able to prowl up on their prey with ease, averting the gaze of even the most perceptive and watchful.

They are also pack animals, rarely ever hunting alone. Even when one does spot a prowling sabercat, it is likely that another is about to pounce from behind.

***Fierce Companion.*** Whether raised from a cub or tamed in the wild, the beasts become loyal to a fault once properly bonded. Night elves have bred and trained sabercats for thousands of years, even utilizing them as mounts in their armies.

### Manasaber
Manasabers are a type of sabercat found residing within the borders of Suramar. The well of power, radiating from inside the city, has infused them with mana and trans&shy;formed them into magical beings.

Most manasabers are domesticated animals, having lived in such close proximity to the elves of Suramar -- who in turn take great care to train them well.

<div style='margin-top:35px;'></div>

> ##### Variant: Sabercat Armor
> An armored sabercat has an AC based on the type of barding worn (see the *Player's Handbook* for more information on barding). The sabercat's AC includes its Dexterity modifier, where applicable. Barding doesn't alter the sabercat's challenge rating.
>
> <div style='column-count:2'>
>
> |&nbsp;&nbsp;&nbsp;AC &nbsp;&nbsp;| Barding |
> |:--:|:--------|
> | 13 | Leather |
> | 14 | Studded leather |
> | 15 | Ring mail |
> | 16 | Scale mail |
>
> |&nbsp;&nbsp;&nbsp;AC &nbsp;&nbsp;| Barding |
> |:--:|:--------|
> | 17 | Chain mail |
> | 18 | Splint |
> | 19 | Plate |
> </div>

\columnbreak

<div style='margin-top:470px;'></div>

___
> ## Young Sabercat <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;22;4;12;12;0;7;0;7;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 22 (5d6 + 5)
> - **Speed** 30 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|14 (+2)|13 (+1)|3 (-4)|11 (+0)|9 (-1)|
>___
> - **Skills** Perception +2, Stealth +6
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** —
> - **Challenge** 1/2 (450 XP)
> ___
> ***Keen Smell.*** The sabercat has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pounce.*** If the tiger moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 12 Strength saving throw or be knocked prone. If the target is prone, the tiger can make one bite attack against it as a bonus action.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 7 (2d4 + 2) slashing damage.

<div class='letterheader'></div>
<div class="mmletter mml-s"></div>
<div class="pageLetter">S</div>
<div class='footnote'>SABERCAT </div>
<img src='https://www.gmbinder.com/images/TQz5CzC.jpg' style='position:absolute; top:0px; right:-450px; width:1800px' />
<img src='https://www.gmbinder.com/images/LvWTTOl.png' style='position:absolute; top:0px; right:0px; width:900px;transform:scalex(-1)' />


\pagebreakNum

<div style='margin-top:470px;'></div>

___
> ## Sabercat <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;37;5;12;18;0;10;0;10;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 37 (5d10 + 10)
> - **Speed** 40 ft., climb 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|14 (+2)|15 (+2)|3 (-4)|12 (+1)|8 (-1)|
>___
> - **Skills** Perception +3, Stealth +6
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Keen Smell.*** The sabercat has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pounce.*** If the sabercat moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone. If the target is prone, the sabercat can make one bite attack against it as a bonus action.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (1d10 + 3) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.

\columnbreak

<div style='margin-top:280px;'></div>

___
> ## Manasaber <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;90;5;11;26;0;18;0;18;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;1;;;;;;;10;;;;;; -->
>*Large beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 90 (12d10 + 24)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|17 (+3)|15 (+2)|4 (-3)|12 (+1)|10 (+0)|
>___
> - **Skills** Perception +3, Stealth +6
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
> ***Keen Smell.*** The sabercat has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Innate Spellcasting.*** The manasaber's spellcasting ability is Wisdom (spell save DC 11). The manasaber can innately cast the following spells, requiring no components:
>
> 2/day each: *invisibility, misty step*
>
> ***Magic Resistance.*** The manasaber has advantage on saving throws against spells and other magical effects
>
> ***Magic Weapons.*** The manasaber's weapon attacks are considered magical.
>
> ***Pounce.*** If the sabercat moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone. If the target is prone, the sabercat can make one bite attack against it as a bonus action.
>
> ### Actions
> ***Multiattack.*** The manasaber makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (1d10 + 3) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.

<div class="pageLetter">S</div>
<div class='footnote'>SABERCAT </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot inkblot-green' style='top:-100px; right:200px; width:700px'>
<img src='https://www.gmbinder.com/images/0bxYxgb.png' style='position:absolute; top:130px; right:370px; width:380px' />
<img src='https://www.gmbinder.com/images/3u2fjsX.png' style='position:absolute; top:-80px; right:-300px; width:1000px; mix-blend-mode:multiply' />

\pagebreakNum

## Satyrs
An ancient curse borne by a highborne sorcerer brought forth the first satyr -- and with it, others would soon follow. These demonic beings were once night elves of the Kaldorei Empire, but little of that heritage remains in their twisted forms. Now there is only anger and hatred.

***Cursed Affliction.*** During the War of the Ancients, the Highborne sorcerer Xavius was tasked with opening a portal that would connect Azeroth to the Twisting Nether. His failture to do so brought upon him the wrath of Sargeras, who tore him asunder and tortured his spirit.

As pain and anguish shattered Xavius' mind, the Lord of the Burning Legion still saw use in the sorcerer; and set to forge a new, demonic form for his servant.

In the form of a satyr, Xavius was sent back to Azeroth to spread his curse through the Kaldorei Empire. Like himself, all who he affected were turned to misshapen beasts, capable of pasing their curse onto others in turn. Scores of night elves, and some other races as well, fell to Xavius' dark influence.

***Created, Not Born.*** Although both male and female satyrs exist, they have never been able to reproduce. All satyrs in existence were formed from their affliction, some thousands of years old. Though the ages have made them rare, they still pose an imminent threat to any unfortunate enough to encounter them.

***Burning Hatred.*** Satyrs are creatures of malice; their veins run a smoldering red as the anguish visited on Xavius is bestowed upon them in turn. They find an indescribable glee in visiting their pain upon others, beast or humanoid -- though none as much as their old elven kin. 

Should a satyr cross paths with an outsider, it is not unlikely for it to try and manipulate them, even corrupt them if possible.

***Tainted Magic.*** Wherever the satyrs walk, their demonic presence slowly seeps magic from the land. Life withers away, as if touched by the fel itself, while the satyr drains its power for its own nefarous needs.

All the power they drain is stored in their hooves. A peprceptive traveller may be able to distinguish the weak from the strong among satyrs, solely by examining its step -- as if the ground has been scorched by brimstone.

***Frightful Fighters.*** Satyrs are not known for forming organized armies with strategies or plans. They live in small and remote sects, tending to their sinister schemes. 

When a sentry sounds the alarm, every satyr is quick to join into the fray without any care for their own life. They act like a true horde of demons; one with no commander, and no orders to follow.

### Satyr Trickster
Certain satyrs show a penchant for laying painful traps and ambushing their targets. These tricksters revere and mimic their Lord, Xavius, for his sinister deeds. When the call to battle sounds, they take the subtle approach -- by sneaking up on their enemies to pick off any target they can waylay.

### Satyr Hellcaller
Satyrs who revel in the arts of fel and shadow magic alike, are known as hellcallers. These warlocks are by far more imposing than the common satyr, as their thirst for magic has bolstered their form just as much as it has tempered their apetite for destruction.

\columnbreak

<div style='margin-top:450px;'></div>

___
> ## Satyr <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;27;4;11;9;0;9;0;9;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium fiend (demon), chaotic evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 27 (6d8)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|14 (+2)|11 (+0)|9 (-1)|12 (+1)|14 (+2)|
>___
> - **Skills** Deception +4, Nature +3, Perception +3, <br>Stealth +4, Survival +3
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** Common, Darnassian
> - **Challenge** 1/2 (100 XP)
> ___
> ***Shadowmeld.*** The satyr can attempt to hide even when it is only lightly obscured by foliage, heavy rain, falling snow, mist, or other natural phenomena.
>
> ### Actions
> ***Multiattack.*** The satyr makes two attacks: one with its claw and one with its scimitar.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) slashing damage.
>
> ***Scimitar.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) slashing damage.
>
> ***Shortbow.*** *Ranged Weapon Attack:* +4 to hit, range 80/320 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.

<div class="pageLetter">S</div>
<div class='footnote'>SATYRS </div>
<img src='https://www.gmbinder.com/images/84P8ntb.png' style='position:absolute; top:0px; right:0px; width:900px'>
<img src='https://www.gmbinder.com/images/OkSEy3f.png' class='inkblot' style='top:150px; right:-50px; width:500px'>
<img src='https://www.gmbinder.com/images/0O5RO1a.png' style='position:absolute; top:-40px; right:-10px; width:430px' />

\pagebreakNum

<div style='margin-top:230px;'></div>

___
> ## Satyr Trickster <!-- https://wc5e-cr-calculator.frogvall.com/?0;14;40;5;12;18;0;11;0;11;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium fiend (demon), chaotic evil*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 40 (9d8)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|16 (+3)|11 (+0)|10 (+0)|12 (+1)|15 (+2)|
>___
> - **Skills** Deception +4, Nature +3, Perception +3, <br>Stealth +5, Survival +3
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** Common, Darnassian
> - **Challenge** 1 (200 XP)
> ___
> ***Cunning Action.*** The satyr can use its bonus action to take the Dash, Disengage, or Hide action.
>
> ***Innate spellcasting.*** The satyr's innate spellcasting ability is Charisma (spell save DC 12). It can innately cast the following spells, requiring no material components.
>
> At will: *mage hand, minor illusion*
> <br> 1/day each: *fog cloud, invisibility*
>
> ***Shadowmeld.*** The satyr can attempt to hide even when it is only lightly obscured by foliage, heavy rain, falling snow, mist, or other natural phenomena.
>
> ***Sneak Attack (1/Turn).*** The satyr deals an extra 7 (2d6) damage when it hits a target with a weapon attack and has advantage on the attack roll, or when the target is within 5 feet of an ally of the satyr that isn't incapacitated and the satyr doesn't have disadvantage on the attack roll.
>
> ### Actions
> ***Multiattack.*** The satyr makes two attacks: one with its claw and one with its scimitar.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 5 (1d4 + 3) slashing damage.
>
> ***Scimitar.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) slashing damage.
>
> ***Shortbow.*** *Ranged Weapon Attack:* +5 to hit, range 80/320 ft., one target. *Hit:* 6 (1d6 + 3) piercing damage.

\columnbreak

<div style='margin-top:314px;'></div>

___
> ## Satyr Hellcaller <!-- https://wc5e-cr-calculator.frogvall.com/?0;16;93;5;13;21;0;21;0;21;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium fiend (demon), chaotic evil*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 93 (17d8 + 17)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|14 (+2)|12 (+1)|11 (+0)|14 (+2)|16 (+3)|
>___
> - **Skills** Deception +5, Nature +4, Perception +4, <br>Stealth +4, Survival +4
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** Common, Darnassian
> - **Challenge** 3 (700 XP)
> ___
> ***Fiendish Blessing.*** While the satyr is wearing no armor, its AC includes its Charisma modifier.
>
> ***Spellcasting.*** The satyr is a 5th-level spellcaster. Its spellcasting ability is Charisma (spell save DC 13, +5 to hit with spell attacks). It regains expended spell slots when it finishes a short or long rest. It knows the following warlock spells:
>
> Cantrips (at will): *fel flame** *, green-flame blade, mage <br>&nbsp;&nbsp;&nbsp; hand, shadow bolt*
> <br> 1st-5th level (2 3rd-level slots): *arms of hadar, <br>&nbsp;&nbsp;&nbsp; bestow curse, hypnotic pattern, scorching ray, <br>&nbsp;&nbsp;&nbsp; ray of enfeeblement*
>
> ***Shadowmeld.*** The satyr can attempt to hide even when it is only lightly obscured by foliage, heavy rain, falling snow, mist, or other natural phenomena.
>
> ### Actions
> ***Multiattack.*** The satyr makes two attacks: one with its claw and one with its scimitar.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) slashing damage.
>
> ***Scimitar.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) slashing damage.

<div class="pageLetter">S</div>
<div class='footnote'>SATYRS </div>
<img src='https://www.gmbinder.com/images/ODT1rsG.jpg' style='position:absolute; top:-60px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/TYBvp5o.png' style='position:absolute; top:-170px; right:0px; width:1000px' />
<img src='https://www.gmbinder.com/images/OkSEy3f.png' class='inkblot' style='top:500px; right:-50px; width:700px'>

\pagebreakNum

<div style='margin-top:760px;'></div>

## Scourge
The Undead Scourge saw its creation at the hands of the Nathrezim; the cunning, bat-like dreadlords of the Burning Legion. In a second bid to conquer Azeroth, they envisioned themselves a grand army of the dead. A perfect precursor for their own triumphant return.

With its foothold on the arctic continent Northrend, under the command of the Lich King, the ranks of the Scourge swell larger with every passing day -- housing hordes of terrifying, destructive monstrosities. Brought forth by devoted cults of necromancers, and by Val'kyr held to their master's will.

***The Lich King.*** At the head of the Undead Scourge stands the Lich King, whose dread presence drives the shambling hordes forward.

\columnbreak

<div style='margin-top:794px;'></div>

The first Lich King, and creator of the Scourge, was the orc shaman Ner'zhul. Though the old shaman had intended to lead his followers in search of other worlds to conquer, he found himself apprehended by by Kil'jaeden; demon lord of the Burning Legion.

The demon lord tore the orc's body apart, but kept his spirit intact. Ner'zhul was offered one last chance to serve; to be forever bound to the demon-forged Helm of Domination and encased within a throne of ice, seated atop the tallest peak amidst Azeroth's northern wastes.

Ultimately, the orc chose to accept the demon's bargain, bidding for the power it would bestow upon him. Thus, the Lich King was born.

<div class="pageLetter">S</div>
<div class='footnote'>SCOURGE </div>
<img src='https://www.gmbinder.com/images/rUSVZoq.jpg' style='position:absolute; top:-200px; right:0px; width:800px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/iqsWrVi.png' style='position:absolute; top:230px; right:0px; width:840px;' />

\pagebreakNum

&nbsp;&nbsp;&nbsp; ***The Plague of Undeath.*** In service to the Burning Legion, the Lich King Ner'zhul would become the lone, governing mind of an army of the damned.

His first claim was to the frozen reaches of Northrend, after a long and hard-won war against the nerubians and their underground kingdom of Azjol-Nerub. His second was in unleashing the gruesome Plague of Undeath upon the human kingdom of Lordaeron.

The ambitious plan laid forth by the demon lord Kil'jaeden, to see Azeroth heel, required a new foothold through which the Legion could enter. Just as it had been the last time, the writings of the Guardian Medivh, locked away in the city of Dalaran, would be the key.

The Lich King reached far and wide for those with an aptitude for necromancy. Chief among them stood the archmage Kel'Thuzad; around whom the Cult of the Damned formed. It was to be the piece with which the Lich King's undead plague would spread.

***Crown Prince Menethil.*** Although the Lich King and the Scourge had been given form to prelude the Burning Legion, Ner'zhul's true ambition was his own salvation: to break free from the shackles of his demonic masters.

To this end, the Lich King sought a champion to carry out his will. He had already envisioned the crown piece of Lordaeron, Arthas Menethil, supplanting him in his rule of the damned. The prince was a capable warrior; a paladin of the Silver Hand, seasoned from numerous skirmishes with errant orc clans across the human kingdoms.

This new undead threat, however, was not one Arthas could bring to an end. It drove the prince to desperation; to the purging of his own homeland; to a vengeful crusade across Northrend; and ultimately to his doom.

***The Runeblade.*** Buried away in a frozen vault, Arthas drew forth an ancient runeblade -- Frostmourne. He had been told the blade would be the means to his long-sought ends, and by its powers he carved his way through the undead hordes with a might which none around him had seen before.

However, the blade would ultimately cost the crown prince his soul. Through it, the Lich King exerted his will upon Arthas, binding him as a champion of the Scourge.

***The Fall of Lordaeron.*** Upon his return to Lordaeron, Arthas ultimately drove his kingdom to ruin. Thereafter, the kingdoms of Quel'thalas and Dalaran fell just the same. From their ashes, with the aid of Kel'thuzad -- reborn a Lich -- Arthas saw the Burning Legion summoned forth.

Though the invasion of the Legion was ultimately a failure, and the lands of Dalaran and Quel'thalas reclaimed, Lordaeron was  forever enveloped in undeath. The final piece of the Lich King's plan, with which the Scourge would truly take foot, was to bring Arthas to his side.

***The Frozen Throne.*** And so, leaving Lordaeron behind for what would later become the Forsaken, Arthas took heed of his master's request and set sail back to Northrend. There, atop the peak of its glacial wastes, the prince found the frozen tomb in which Ner'zhul's spirit had been bound.

With his runeblade held aloft, Arthas shattered the ice; freeing the Helm of Domination to which the old shaman had been bound. As he placed the helm on his head, their spirit fused together as one. Bound to their trackless kingdom of the damned.

***The Icecrown Citadel.*** Since then, through the tireless machinations of the Scourge, a massive citadel has been erected around the Icecrown glacier upon which the Frozen Throne resides.

<div class="pageLetter">S</div>
<div class='footnote'>SCOURGE </div>
<img src="https://www.gmbinder.com/images/HmKUFpS.png" style="position:absolute;top: -151px;right: -203px;width: 990px;transform: rotate(17deg);">
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; left:-80px; width:880px;' />

\pagebreakNum

Its spiked walls and towering spires can be seen from every far-reaching corner of Northrend, as a warning to any who would set foot on its shores.

At the peak of the tallest spire, the Lich King dwells on his throne, projecting his iron will across Azeroth.

### Abomination
Twisted, mutilated creatures comprised of flesh from a multitude of corpses, Abominations are not risen like most undead. Instead, they are created, loosely stitched together. These putrid constructs resemble enormous mounds of flesh, given limbs and a vague semblance of form.

They are fearless, and take joy in cleaving flesh from bone with rusted cleavers. As though their creators saw it only fit to arm the beasts with weapons as bizarre as their excess of arms.

### Gargoyle
Unlike most creatures of the Undead Scourge, Gargoyles are not undead. These strange, wiry flyers are known for their rough, crystalline hides keep them well protected.

Native to Northrend, gargoyles were brought to Lordaeron at Arthas' command as scouts in the army of the Scourge. Chaotic by nature, they have proven effective in their task and a frightful aerial combatant.

### Ghoul
Ravenous cannibals that leave only havoc and devoured corpses behind them. Ghouls are the lumbering remains of once innocent humans, transformed into hollow-eyes terrors with an insatiable hunger for flesh.

They are the Scourge's prime tool for spreading panic; a mindless vanguard to swarm through settlements, breaking chaos before the rest of the Scourge arrive. Feasting on the living and dead alike as they do.

> ##### Variant: Greater Abomination <!-- https://wc5e-cr-calculator.frogvall.com/?1;17;161;8;13;33;0;33;0;33;0;0;0;0;0;0;0;1;;;;4;;;;;;;;;;1;;;;;;;;10;;;1;;; -->
> A greater abomination has a challenge rating of 9 (5,000 XP). It has the statistics of an abomination except that it has 161 (17d10 + 68) hit points, Armor Class (AC 17), +8 to hit with its weapon attacks, and gains the following action options.
>
>***Engorge.*** The abomination makes one cleaver attack and places a grappled target in its ribcage. The target becomes restrained, and can use its action to break free by succeeding on a DC 17 Strength (Athletics) or Dexterity (Acrobatics) check. While restrained in this way, a creature takes 14 (4d6) bludgeoning damage at the start of each of the abominations turns. An abomination can have only one creature restrained within its ribcage.
>
> ***Cannibalize.*** The abomination cannibalize the corpse of creature that has been dead for less than 24 hours. Each creature of the abomination's choice that is within 120 feet and can see it must succeed on a DC 17 Wisdom saving throw or become frightened for 1 minute. A creature can repeat the saving throw at the end of each of its turns, ending the effect on itself on a success. If a creature's saving throw is successful or the effect ends for it, the creature is immune to the abomination's Cannibalize for the next 24 hours.

\columnbreak

### Scourge Risen Template
A creature risen by the scourge is any Huge or smaller creature brought back to life by vile necromantic energies. A creature that was never flesh and blood to begin with (such as a construct) can't be risen under the scourge's control. The following characteristics change or are added to a creature that becomes a scourge risen creature.

***Retained Characteristics.*** The risen retain its Armor Class, hit points, Hit Dice, Strength, Dexterity, Constitu&shy;tion, vulnerabilities, resistances, and immunities.

***Lost Characteristics.*** The risen loses its original saving throw and skill bonuses, special senses and special traits. It loses any action that isn't multiattack or a melee weapon that deals bludgeoning, piercing, or slashing damage. If it has an action or a melee weapon attack that deals some other type of damage, it loses the ability to deal damage of that type, unless the damage comes from a piece of equipment, such as a magic item.

***Type.*** The risen's type is undead, and it loses any tags.

***Alignment.*** The risen is neutral evil.

***Ability Scores.*** The risen's ability scores change as follows: Int 3 (-4), Wis 6 (-2), Cha 5 (-3).

***Senses.*** The risen has darkvision with a radius of 60 ft.

***Damage Immunities.*** The risen gains immunity to poison damage.

***Condition Immunities.*** poisoned.

***Languages.*** The risen understands all languages it knew in life, but cannot speak.

***Attacks.*** If the risen has no means of dealing damage, it can use its fists or limbs to make unarmed strikes. On a hit, an unarmed strike deals bludgeoning damage equal to 1d4 + the risen's Strength modifier, increasing by 1d4 for each size larger than Medium.

<div style='margin-top:-10px;'></div>

___
> ## Scourge Risen Knight
>*Medium undead, neutral evil*
> ___
> - **Armor Class** 18 (plate)
> - **Hit Points** 52 (8d8 + 16)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|11 (+0)|14 (+2)|3 (-4)|6 (-2)|5 (-3)|
>___
> - **Damage Immunities** poison
> - **Condition Immunities** poisoned
> - **Senses** darkvision 60 ft., passive Perception 8
> - **Languages** understands the languages it knew in life but can't speak
> - **Challenge** 3 (700 XP)
> ___
>
> ### Actions
> ***Multiattack.*** The knight makes two greatsword attacks.
>
> ***Greatsword.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.
>
> ### Reactions
> ***Parry.*** The knight adds 2 to its AC against one melee attack that would hit it. To do so, the knight must see the attacker and be wielding a melee weapon.

<div class="pageLetter">S</div>
<div class='footnote'>SCOURGE </div>


\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Abomination <!-- https://wc5e-cr-calculator.frogvall.com/?1;14;142;7;13;33;0;33;0;33;0;0;0;0;0;0;0;1;;;;4;;;;;;;;;;1;;;;;;;;10;;;1;;; -->
>*Large construct (undead), neutral evil*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 142 (15d10 + 60)
> - **Speed** 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|19 (+4)|9 (-1)|18 (+4)|3 (-4)|8 (-1)|4 (-3)|
>___
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, frightened, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** Common, Gutterspeak
> - **Challenge** 7 (2,900 XP)
> ___
> ***Immutable Form.*** The abomination is immune to any spell or effect that would alter its form.
>
> ***Stench.*** Any creature that starts its turn within 10 feet of the abomination must succeed on a DC 14 Con&shy;stitution saving throw or be poisoned until the start of the creature's next turn. On a successful saving throw, the creature is immune to the stench of all abominations for 1 minute.
>
> ### Actions
> ***Multiattack.*** The abomination makes two attacks: one with its cleaver and one with its horrific hook.
>
> ***Cleaver.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 15 (2d10 + 4) slashing damage plus 5 (1d10) poison damage, and the target must succeed on a DC 14 Constitution saving throw or be poisoned for 1 minute. It can repeat the saving throw at the end of each of its turns, ending the effect on a success.
>
> ***Horrific Hook.*** *Melee or Ranged Weapon Attack:* +7 to hit, reach 5 ft. or range 20/60 ft., one target. *Hit:* 13 (2d8 + 4) piercing damage, and if the target is a creature it must succeed on a DC 16 Strength saving throw or be grappled and pulled to an empty space next to the abomination.

</div>

<div class="pageLetter">S</div>
<div class='footnote'>SCOURGE </div>

<img src='https://www.gmbinder.com/images/tiU4RnD.png' class='inkblot' style='top:-100px; right:0px; width:900px; transform:rotate(40deg)' />
<img src='https://www.gmbinder.com/images/as7jPMa.png' style='position:absolute; top:-20px; right:-20px; width:900px' />

\pagebreakNum

<div style='margin-top:418px;'></div>

___
> ## Gargoyle <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;37;4;13;14;0;14;0;14;0;0;0;0;0;0;0;1;;1;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium monstrosity, chaotic evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 37 (5d8 + 15)
> - **Speed** 30 ft., fly 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|11 (+0)|16 (+3)|5 (-3)|11 (+0)|7 (-2)|
>___
> - **Damage Resistances** bludgeoning, piercing, and slash&shy;ing from nonmagical attacks that aren't adamantine
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** understands Common but can't speak
> - **Challenge** 2 (450 XP)
> ___
>
> ### Actions
> ***Multiattack.*** The gargoyle makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 9 (2d6 + 2) piercing damage.
>
> ***Stone Form.*** The gargoyle turns itself to stone making it indistinguishable from an inanimate statue. While it is turned this way, the gargoyle can't take any actions or move, and regains 5 hit points at the end of each of its turns. The gargoyle can turn itself into flesh using its bonus action.

\columnbreak

<div style='margin-top:390px;'></div>

___
> ## Ghoul <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;54;4;13;12;0;12;0;12;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium undead, chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 54 (12d8)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|15 (+2)|10 (+0)|7 (-2)|10 (+0)|6 (-2)|
>___
> - **Damage Immunities** poison
> - **Condition Immunities** charmed, exhaustion, poisoned
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
>
> ### Actions
> ***Multiattack.*** The ghoul makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 7 (2d4 + 2) slashing damage.
>
> ***Cannibalize (Recharge after a Short or Long Rest).*** The ghoul cannibalizes the corpse of a humanoid that has been dead for less than a day, regaining 10 hit points. Each creature of the ghoul's choice that is within 30 feet of the ghoul and can see it must succeed on a DC 12 Wisdom saving throw or become frightened for 1 minute. A creature can repeat the saving throw at the end of each of its turns, ending the effect on itself on a success. If a creature's save is successful or the effect ends for it, the creature is immune to any ghoul's cannibalize for the next 24 hours.

<div class="pageLetter">S</div>
<div class='footnote'>SCOURGE </div>
<img src='https://www.gmbinder.com/images/vALA45Q.png' style='position:absolute; top:0px; right:175px; width:800px' />
<img src='https://www.gmbinder.com/images/z86Lpca.png' style='position:absolute; top:-50px; right:-100px; width:940px' />
<img src='https://www.gmbinder.com/images/Sjc9IFl.png' class='inkblot' style='top:100px; right:-100px; width:500px; transform:rotate(40deg)' />
<img src='https://www.gmbinder.com/images/0xslXmq.png' style='position:absolute; top:40px; right:-20px; width:400px; z-index:100' />

\pagebreakNum

<div style='margin-top:525px;'></div>

___
> ## Zombie <!-- https://wc5e-cr-calculator.frogvall.com/?0;8;30;3;13;4;0;4;0;4;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;1; -->
>*Medium undead, neutral evil*
> ___
> - **Armor Class** 8
> - **Hit Points** 30 (4d8 + 12)
> - **Speed** 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|6 (-2)|16 (+3)|3 (-4)|6 (-2)|5 (-3)|
>___
> - **Saving Throws** Wis +0
> - **Damage Immunities** poison
> - **Condition Immunities** poisoned
> - **Senses** darkvision 60 ft., passive Perception 8
> - **Languages** understands the languages it knew in life  but can't speak
> - **Challenge** 1/4 (50 XP)
> ___
> ***Undead Fortitude.*** If damage reduces the zombie to 0 hit points, it must make a Constitution saving throw with a DC of 5 +the damage taken, unless the damage is radiant or from a critical hit. On a success, the zombie drops to 1 hit point instead.
>
> ### Actions
> ***Slam.*** *Melee Weapon Attack*: +3 to hit, reach 5 ft., one target. Hit: 4 (1d6 + 1) bludgeoning damage.

<div class="pageLetter">S</div>
<div class='footnote'>SCOURGE </div>
<img src='https://www.gmbinder.com/images/N8hYlAE.jpg' style='position:absolute; top:0px; right:-125px; width:650px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/zxp4HSp.png' class='inkblot' style='top:-50px; right:300px; width:600px' />
<img src='https://www.gmbinder.com/images/rUpA52w.png' style='position:absolute; top:5px; right:410px; width:320px; z-index:100' />

\pagebreakNum

<div style='margin-top:370px;'></div>

___
> ## Shale Spider
>*Large elemental, chaotic evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 42 (5d10 + 15)
> - **Speed** 30 ft., burrow 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|14 (+2)|16 (+3)|7 (-2)|10 (+0)|5 (-3)|
>___
> - **Damage Vulnerabilities** thunder
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, paralyzed, petrified, poisoned, unconscious
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
> ***Earth Glide.*** The spider can burrow through nonmagical unworked earth and stone. While doing so, it doesn't disturb the material it moves through.
>
> ***Spider Climb.*** The spider can climb difficult surfaces, including upside down on ceilings, without needing to make an ability check.
>
> ### Actions
> ***Multiattack.*** The spider makes two attacks: one with its bite and one slam.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. Hit: 7 (1d8 + 3) piercing damage plus 2 (1d4) acid damage.
>
> ***Slam.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. Hit: 12 (2d8 + 3) bludgeoning damage. <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;42;5;13;21;0;21;0;21;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:360px;'></div>

## Shale Spider
Shale spiders are durable diggers, native to the elemental plane of Deepholm. They possess a tenacity and ferocity not shown in many other elementals; as one will often fight until it is utterly and entirely torn asunder.

***Stone Nuisance.*** The spiders sometimes find their way out of Deepholm, emerging onto the surface. A newly emerged shale spider is fairly harmless, keeping reclusive while it tries to adapt to its new environment. Once it has, however, it sets out to hunt -- often with a voracious hunger.

***Swarmers.*** Above all, the shale spiders are notorious swarmers. They'll often work together to take down their prey. Sometimes, a single shale spider will pretend to be alone, while its kin lays in wait for an opportunity to strike.

***Elemental Nature.*** The shale spider doesn't require air, food, drink, or sleep.

> ##### Variant: Lava Spider
> A lava spider has adapted to burning climate around it, it drips molten magma as it skitters across the surface and illuminates its surroundings.
>
> A lava spider has immunity to fire damage, and gain the following additional trait:
>
> <br>&nbsp;&nbsp;&nbsp; ***Illumination.*** The spider sheds bright light in a 10-<br>&nbsp;&nbsp;&nbsp; foot radius and dim light for an additional 10 feet.
>
> <br> The lava spider replaces the shale's action options has the following action options:
>
> <br>&nbsp;&nbsp;&nbsp; ***Multiattack.*** The spider makes one bite attack and <br>&nbsp;&nbsp;&nbsp; uses its Spit Fire.
>
> <br>&nbsp;&nbsp;&nbsp; ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., <br>&nbsp;&nbsp;&nbsp; one target. *Hit:* 6 (1d8 + 2) piercing damage, plus <br>&nbsp;&nbsp;&nbsp; 4 (1d8) fire damage.
>
> <br>&nbsp;&nbsp;&nbsp; ***Spit Fire.*** *Ranged Weapon Attack:* +4 to hit, range <br>&nbsp;&nbsp;&nbsp; 15/30 ft., one target. *Hit:* 11 (2d8 + 2) fire <br>&nbsp;&nbsp;&nbsp; damage. <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;42;4;13;21;0;21;0;21;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">S</div>
<div class='footnote'>SHALE SPIDER </div>

<img src='https://www.gmbinder.com/images/I1Tt2hD.jpg' style='position:absolute; top:-30px; right:0px; width:800px' />
<img src='https://www.gmbinder.com/images/NO1EQoX.png' style='position:absolute; top:-130px; right:0px; width:1100px;transform:scalex(-1)' />

\pagebreakNum

## Shredder
Shredders are large mechanical constructs: a marvel of goblin ingenuity, created to truly maximize profits from mass deforestation. The sturdy machines are equipped with a clamping claw and a deadly sawblade, making them just as  efficient lumberjacks as effective combatants when outraged woodland denizens come for revenge.

Shredders are core to numerous goblin enterprises, across Azeroth. They are manual machines, requiring either an operator or an operator's instructions.

***Enemies of the Forest.*** The brutally efficient deforest&shy;ations conducted by shredders have garnered them a deep-seeded hatred among those who dwell in the wilds. Many of whom work tirelessly to push back and sabotage the constructs, if only to save their home.

***War Constructs.*** Shredders have on occasion become frontline fighters in times of war. If a goblin on its lonesome won't pose much of a threat, a ruthless goblin operating a spinning buzzer-blade certainly will.

___
> ## Shredder <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;52;5;13;20;0;20;0;20;0;0;0;0;0;0;0;1;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large construct, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 52 (7d10 + 14)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|9 (-1)|15 (+2)|3 (-4)|11 (+0)|1 (-5)|
>___
> - **Damage Resistances** poison; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Condition Immunities** charmed, exhaustion, frightened paralyzed, petrified, poisoned
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Common, Goblin
> - **Challenge** 3 (700 XP)
> ___
> ***Immutable Form.*** The shredder is immune to any spell or effect that would alter its form.
>
> ### Actions
> ***Multiattack.*** The shredder makes two attacks: one with its claw and one with its sawblade
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (2d4 + 3) bludgeoning damage. If the target is a Medium or smaller creature, the target is grappled (escape DC 13). Until this grapple ends, the target is restrained, and the shredder can't use its claw against another target.
>
> ***Sawblade.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft. or range 30/60 ft., one target. *Hit:* 12 (2d8 + 3) slashing damage.
>
> ### Reactions
> ***Halt!*** The shredder can make one claw or sawblade attack against a creature that's attempting to climb it, if hit by the sawblade, the creature must make a DC 13 Dexterity saving throw, or fall prone in an empty space next to the shredder.

\columnbreak

<div style='margin-top:530px;'></div>

> ##### Crewing a Shredder
> Most shredders are manual machines that require a pilot to operate, and even autopiloted shredders can be overwritten to work manually for a time.
>
> A creature can use its action to attempt to climb a **piloted** shredder by succeeding on a DC 13 Strength (Athletics) check. On a failed save, the creature expends half its movement and is unable to climb the shredder.
>
> A Medium or smaller creature can expend 5 feet of movement to enter an unoccupied shredder. A creature unfamiliar with the controls of shredders must succeed on a DC 12 Intelligence check to understand the controls of the machine before it is able to pilot it and control its actions and movement.
>
> While piloted, the shredder's Intelligence, Wisdom, and Charisma scores are exchanged with those of the pilot. A piloted shredder uses the initiative of its pilot. The pilot must use its action, reaction, and movement to use the machines action options or force it to move to a new location. While a creature is crewing the shredder, it is considered to have three-quarters cover against any attack made against it from the ground.
>
> Taking control of an **autopiloted** shredder requires a successful DC 14 Tinker's Tool Intelligence check. On a successful save, the creature takes control of the shredder until the end of the creature's next turn. At which point the shredder’s  failsafe mechanisms return, requiring a new save to temporarily take control of it.

<div class="pageLetter">S</div>
<div class='footnote'>SHREDDER </div>
<img src='https://www.gmbinder.com/images/dOk8Uqf.jpg' style='position:absolute; top:0px; right:-30px; width:450px' />
<img src='https://www.gmbinder.com/images/qKrtKxo.png' style='position:absolute; top:0px; right:-20px; width:900px' />

\pagebreakNum

<div style='margin-top:486px;'></div>

## Silithids
Silithids are frightful insectoids, living in large colonies excavated beneath scorching sands. Although their individual strength is questionable at best, a colony's collective hive-mind can send signals and pain surging through the hive to alert its members of intruders.

They range dramatically in size. Beginning their life as small insignificant larva, they grow into the swarms of monstrosities that make up their flock. Whatever their size may be, they all resemble massive insects -- if those insects were grotesquely mutated and thirsting for flesh.

***Spawns of Qiraji.*** As the kingdom of the aqir was left in ruins, those who remained split in two and ventured in opposite directions. One grouped traveled far south, where they found and ransacked a titan research station near Uldum. Turning the facility into a hive, they renamed themselves the qiraji -- and their new home, Ahn'Qiraj.

But their new hive held a dark secret: it was the prison of C'Thun, one of the Old Gods who had ruled primordial Azeroth. Just as the aqir before them had served him, the qiraji quickly bowed down to his will.

The facility was transformed from a prison into a seat of power, one from which the qiraji grew over milennia into an army; one capable of exacting the Old God's revenge. The key to Cthun's plan was the creation of the silithid: a race of insectoid creatures born from the qiraji, one with which Ahn'Qiraj would be poised to as a new empire.

***Bestial Drones.*** Unlike the qiraji, silithids aren't sentient beings. They are slavering beasts at most, linked together in a hive-mind that spans the entirety of southern Kalimdor.

 C'Thun created them to be mindless servants of the qiraji; minions that would be eternally loyal to their masters -- and in turn to C'Thun himself.

\columnbreak

<div style='margin-top:733px;'></div>

&nbsp;&nbsp;&nbsp; ***Collective Hive-Mind.*** Although silithids might seem to be acting on their own accord, their actions are all the exertion of their hive collective. This, however, does not make them any less dangerous.

A hive of silithids are controlled by one or more colossi, whose masive -- sometimes exposed -- brain keeps a tidy order of all other members of its hive, directing them.

The colossi in turn are controlled by the qiraji, whose dominance over the race is absolute. Hives typically possess a strange crystalline prism, hidden deep within its core, through which the qiraji communicate with them.

***Adaptable Hive.*** No other creature can adapt to changes in their environment as quickly as the silithid. 

Adventurers daring enough to delve into the heart of a silithid hive, hoping to kill its colossi and hamper the colony as a whole, will soon find it replaced. Before long, another colossi will have taken over before long; acting as a surrogate until a new one can rise from the hive's young.

<div class="pageLetter">S</div>
<div class='footnote'>SILITHIDS </div>
<img src='https://www.gmbinder.com/images/iYKnm2x.jpg' style='position:absolute; top:0px; right:-100px; width:1000px' />
<img src='https://www.gmbinder.com/images/pZatMx5.png' style='position:absolute; top:0px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/1dtuzPF.png' style='position:absolute; top:480px; right:-40px; width:px; transform:rotate(-5deg); filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42))' />

\pagebreakNum

<div style='margin-top:460px;'></div>

___
> ## Silithid Larva <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;2;2;13;1;0;1;0;1;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 2 (1d4)
> - **Speed** 20 ft., burrow 10 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|9 (-1)|8 (-1)|11 (+0)|1 (-5)|8 (-1)|4 (-3)|
>___
> - **Damage Resistances** poison
> - **Condition Immunities** blinded, poisoned
> - **Senses** tremorsense 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> ***Hive Mind.*** The silithid can transmit simple messages and emotions to any silithid within 240 feet of it that is part of the same hive.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one creature. *Hit:* 1 (1d4 - 1) piercing damage, and the larva attaches to the target. While attached, the larva doesn't attack. Instead, at the start of each of the larva's turns, the target loses 1 (1d4 - 1) hit points due to blood loss.
> <br>&nbsp;&nbsp;&nbsp; The larva can detach itself by spending 5 feet of movement. It does so after it drains 10 hit points of blood from the target or the target dies. A creature, including the target, can use its action to detach the larva.

\columnbreak

<div style='margin-top:372px;'></div>

___
> ## Silithid Worker <!-- https://wc5e-cr-calculator.frogvall.com/?0;14;65;4;13;12;0;12;0;12;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 65 (10d8 + 20)
> - **Speed** 30 ft., burrow 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|13 (+1)|15 (+2)|4 (-3)|12 (+1)|5 (-3)|
>___
> - **Damage Resistances** poison
> - **Condition Immunities** poisoned
> - **Skills** Perception +3
> - **Senses** darkvision 60 ft., tremorsense 60 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Hive Mind.*** The silithid can transmit simple messages and emotions to any silithid within 240 feet of it that is part of the same hive.
>
> ***Spider Climb.*** The silithid can climb difficult surfaces, including upside down on ceilings, without needing to make an ability check.
>
> ### Actions
> ***Multiattack.*** The silithid makes two bite attacks and uses its Adhesive Acid if it can.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Adhesive Acid (recharge 5-6).*** *Melee or Ranged Weapon Attack:* +4 to hit, reach 5 ft. or range 30/60 ft., one creature. *Hit:* 7 (2d6) acid damage, and the target must succeed on a DC 12 Strength saving throw or have its speed reduced to 0 until the end of the silithid's next turn.

<div class="pageLetter">S</div>
<div class='footnote'>SILITHIDS </div>

<img src='https://www.gmbinder.com/images/a81VyUK.png' class='inkblot inkblot-green' style='top:-300px; right:25px; width:800px' />
<img src='https://www.gmbinder.com/images/Bbtl4ll.png' style='position:absolute; top:350px; right:400px; width:400px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/N6dK0xs.png' style='position:absolute; top:170px; right:-75px; width:600px' />

\pagebreakNum

<div style='margin-top:247px;'></div>

___
> ## Silithid Wasp <!-- https://wc5e-cr-calculator.frogvall.com/?0;14;93;5;13;18;0;18;0;18;0;0;0;0;0;0;0;;;1;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 93 (17d8 + 17)
> - **Speed** 10 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|16 (+3)|12 (+1)|4 (-3)|15 (+2)|5 (-3)|
>___
> - **Damage Resistances** poison
> - **Condition Immunities** poisoned
> - **Skills** Perception +4
> - **Senses** darkvision 60 ft., tremorsense 60 ft., passive Perception 14
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
>
> ***Keen Hearing and Sight.*** The silithid has advantage on Wisdom (Perception) checks that rely on hearing or sight.
>
> ***Hive Mind.*** The silithid can transmit simple messages and emotions to any silithid within 240 feet of it that is part of the same hive.
>
> ***Flyby.*** The silithid doesn't provoke opportunity attacks when it flies out of an enemy's reach.
>
> ### Actions
> ***Multiattack.*** The silithid makes two sting attacks.
>
> ***Sting.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 6 (1d6 + 3) piercing damage plus 3 (1d6) poison damage.
>
> ***Noxious Spit.*** *Ranged Weapon Attack:* +5 to hit, range 30/60 ft., one creature. *Hit:* 10 (2d6 + 3) poison damage, and the target must make a DC 13 Constitution saving throw or be poisoned for 1 minute. The creature can repeat the saving throw at the end of each of its turns, ending the effect on a success.
> <br>&nbsp;&nbsp;&nbsp; While poisoned this way, any non-silithid creature that ends its turn within 5 feet of the target must succeed on a DC 12 Constitution saving throw. The creature takes 7 (2d6) poison damage on a failed save, or half as much on a successful one.

\columnbreak

<div style='margin-top:170px;'></div>

___
> ## Silithid Reaver <!-- https://wc5e-cr-calculator.frogvall.com/?1;16;142;6;13;68;0;20;0;20;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large beast, unaligned*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 142 (19d10 + 38)
> - **Speed** 40 ft., burrow 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|14 (+2)|15 (+2)|4 (-3)|13 (+1)|5 (-3)|
>___
> - **Damage Resistances** poison
> - **Condition Immunities** poisoned
> - **Skills** Perception +4
> - **Senses** darkvision 60 ft., tremorsense 60 ft., passive Perception 14
> - **Languages** —
> - **Challenge** 5 (1,800 XP)
> ___
> ***Keen Hearing and Sight.*** The silithid has advantage on Wisdom (Perception) checks that rely on hearing or sight.
>
> ***Hive Mind.*** The silithid can transmit simple messages and emotions to any silithid within 240 feet of it that is part of the same hive.
>
> ***Spider Climb.*** The silithid can climb difficult surfaces, including upside down on ceilings, without needing to make an ability check.
>
> ***Standing Leap.*** The silithid’s long jump is up to 30 ft. and its high jump is up to 15 ft., with or without a running start.
>
> ### Actions
> ***Multiattack.*** The silithid makes two bite attacks.
>
> ***Bite.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one creature. *Hit:* 10 (2d6 + 3) piercing damage.
>
> ***Deadly Leap.*** If the silithid jumps at least 15 ft. as part of its movement, it can then use this action to land on its feet in a space that contains one or more other creatures. Each of those creatures must succeed on a DC 14 Strength or Dexterity saving throw (target’s choice) or be knocked prone and take 17 (4d6 + 3) bludgeoning damage plus 17 (4d6 + 3) slashing damage.
> <br>&nbsp;&nbsp;&nbsp; On a successful save, the creature takes only half the damage, isn’t knocked prone, and is pushed 5 ft. out of the silithid's space into an unoccupied space of the creature’s choice. If no unoccupied space is within range, the creature instead falls prone in the silithid's space.

<div class="pageLetter">S</div>
<div class='footnote'>SILITHIDS </div>

<img src='https://www.gmbinder.com/images/R7wbd4k.png' class='inkblot inkblot-green' style='top:-300px; right:-50px; width:800px; transform:rotate(270deg)' />
<img src='https://www.gmbinder.com/images/HxIk06X.png' style='position:absolute; top:-100px; right:430px; width:450px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/zFgCBp8.png' style='position:absolute; top:-65px; right:25px; width:400px; z-index:100' />

\pagebreakNum

<div style='margin-top:200px;'></div>

> ##### Variant: Hive Controller
> The strongest of a hive's colossi exerts direct command over other silithids in the hive. Usually this is either the hive lord, closest of the queen's consorts, or the hive queen herself.
>
> The Hive Controller can be distinguished by its see-through cranium, leaving its brain visible. It has the following additional trait.
>
> <br>***Leadership (Recharges after a Short or Long Rest).*** For 1 minute, the silithid can send a telepathic command whenever a nonhostile creature that it can see within 60 feet of it makes an attack roll or a saving throw. The creature can add a d4 to its roll provided it can receive the command. A creature can benefit from only one Leadership die at a time. This effect ends if the silithid is incapacitated.

<div class='statblock-bottom-wide'>

___
___
> ## Silithid Colossus <!-- https://wc5e-cr-calculator.frogvall.com/?1;17;199;8;13;53;0;37;0;58;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;1;;;;; -->
>*Huge beast, unaligned*
> ___
> - **Armor Class** 17 (natural armor)
> - **Hit Points** 199 (19d12 + 76)
> - **Speed** 40 ft., burrow 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|20 (+5)|9 (-1)|18 (+4)|6 (-2)|14 (+2)|8 (-1)|
>___
> - **Saving Throws** Str +9, Con +8
> - **Skills** Perception +6
> - **Damage Resistances** poison; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Condition Immunities** poisoned
> - **Senses** darkvision 60 ft., tremorsense 120 ft., passive Perception 16
> - **Languages** —
> - **Challenge** 9 (5,000 XP)
> ___
> ***Hive Mind.*** The silithid can transmit simple messages and emotions to any silithid within 240 feet of it that is part of the same hive.
>
> ***Charge.*** If the silithid moves at least 15 feet straight toward a target and then hits it with its claws on the same turn, the target takes an extra 16 (3d10) slashing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ***Relentless (Recharges after a Short or Long Rest).*** If the silithid takes 14 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ### Actions
> ***Multiattack.*** The silithid makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +8 to hit, reach 5 ft., one creature. *Hit:* 16 (2d10 + 5) piercing damage. If the target is a creature, it is grappled (escape DC 17). Until this grapple ends, the target is restrained, and the silithid can't bite another target.
>
> ***Claw.*** Melee Weapon Attack: +8 to hit, reach 5 ft., one target. Hit: 21 (3d10 + 5) slashing damage.
>
> ***Swallow.*** The silithid makes one bite attack against a Medium or smaller creature it is grappling. If the attack hits, that creature takes the bite's damage and is swallowed, and the grapple ends. While swallowed, the creature is blinded and restrained, it has total cover against attacks and other effects outside the silithid, and it takes 21 (6d6) acid damage at the start of each of the silithid's turns.
> <br>&nbsp;&nbsp;&nbsp; If the silithid takes 30 damage or more on a single turn from a creature inside it, the silithid must succeed on a DC 15 Constitution saving throw at the end of that turn or regurgitate all swallowed creatures, which fall prone in a space within 10 feet of the silithid. If the silithid dies, a swallowed creature is no longer restrained by it and can escape from the corpse using 15 feet of movement, exiting prone.

</div>

<div class="pageLetter">S</div>
<div class='footnote'>SILITHIDS </div>

<img src='https://www.gmbinder.com/images/zxp4HSp.png' class='inkblot inkblot-green' style='top:-50px; right:-50px; width:900px;' />
<img src='https://www.gmbinder.com/images/nTVuEnM.png' style='position:absolute; top:-100px; right:-350px; width:1400px' />

\pagebreakNum

## Skeletons
Skeletons arise when animated by dark magic. Sometimes, they come at the behest of necromancers, who call them from their stony tombs and ancient battlegrounds.

Other times, they rise of their own accord -- drawn from their muddy graves in fields saturated with death.

***Animated Dead.*** Whatever sinister force awakened the skeleton, it infuses its bones with a dark vitality, adhering joint to joint and reassembling limbs. With its newfound energy, the skeleton is able to move and think in a fairly rudimentary fashion, like a foul imitation of what it once was like. Some forms of resurrection can restore a skeleton's body and soul, fully returning it to life.

While most animated remains are humanoid, skeletal undead can be made from the bones of other creatures. Sometimes even from a combination thereof; giving rise to a host of unique and terrifying forms.

***Obedient Servants.*** Skeletons who have been raised by a spell are bound to their creator. They follow their orders to the letter, regardless of the consequences, though often with very literal interpretation. For this, most skeletons adapt poorly to changing circumstances.

A skeleton can fight with weapons and wear armor, even load and fire catapults and trebuchets. Some are even raised with knowledge of their past life, making formidable warriors or mages able to perform complex incantations.

Most of them do lack the intelligence they possessed in life, though they are not entirely mindless. Rather than breaking its limbs trying to batter down a door, a skeleton has enough of a mind to open the door normally -- and even look for other ways through, should it be locked.

***Undead Nature.*** A skeleton doesn't require air, food, drink, or sleep.

<div style='margin-top:-1px;'></div>

___
> ## Giant Skeleton <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;75;6;14;17;0;17;0;17;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large undead, lawful evil*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 75 (10d10 + 20)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|11 (+0)|15 (+2)|6 (-2)|8 (-1)|5 (-3)|
>___
> - **Damage Vulnerabilities** bludgeoning
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, poison
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** understands all languages it knew in life but can't speak
> - **Challenge** 2 (450 XP)
> ___
>
> ***Brute.*** A melee weapon deals one extra damage die when the skeleton hits with it (included in the attack).
>
> ### Actions
> ***Greatclub.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 17 (3d8 + 4) bludgeoning damage. If the target is a creature, it must succeed on a DC 14 Strength saving throw or be knocked prone.

\columnbreak

<div style='margin-top:542px;'></div>

___
> ## Skeleton <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;19;4;13;5;0;5;0;5;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium undead, lawful evil*
> ___
> - **Armor Class** 13 (armor scraps)
> - **Hit Points** 19 (3d8 + 6)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|14 (+2)|15 (+2)|6 (-2)|8 (-1)|5 (-3)|
>___
> - **Damage Vulnerabilities** bludgeoning
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, poison
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** understands all languages it knew in life but can't speak
> - **Challenge** 1/4 (50 XP)
> ___
>
> ### Actions
> ***Shortsword.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Shortbow.*** *Ranged Weapon Attack:* +4 to hit, range 80/320 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.

<div class="pageLetter">S</div>
<div class='footnote'>SKELETONS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='top:-50px; right:-150px; width:600px'>
<img src='https://www.gmbinder.com/images/uabPXoK.png' style='position:absolute; top:0px; right:-50px; width:500px' />

\pagebreakNum

<div style='margin-top:470px;'></div>

___
> ## Skeleton Mage <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;91;4;12;12;0;12;0;12;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium undead, lawful evil*
> ___
> - **Armor Class** 12 (15 with *mage armor*)
> - **Hit Points** 91 (14d8 + 28)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|14 (+2)|15 (+2)|14 (+2)|8 (-1)|5 (-3)|
>___
> - **Damage Vulnerabilities** bludgeoning
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, poison
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** understands all languages it knew in life but can't speak
> - **Challenge** 2 (450 XP)
> ___
>
> ***Spellcasting.*** The skeleton is a 3rd-level spellcaster. Its spellcasting ability is Intelligence (spell save DC 12, +4 to hit with spell attacks). It requires no vocal component to cast its spells. The skeleton has the following mage spells prepared:
> <div style='margin-top:-12px;'></div>
>
> <br> Cantrips (at will): *blade ward, mage hand, ray of frost*
> <br> 1st level (4 slots): *ice knife, mage armor, silent image*
> <br> 2nd level (2 slots): *blindness/deafness, invisibility*
>
> ### Actions
> ***Shortsword.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.

****

\columnbreak

<div style='margin-top:120px;'></div>

___
> ## Skeleton Warrior <!-- https://wc5e-cr-calculator.frogvall.com/?0;17;19;3;12;13;0;13;0;13;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium undead, lawful evil*
> ___
> - **Armor Class** 17 (plate scraps, shield)
> - **Hit Points** 19 (3d8 + 6)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|12 (+1)|15 (+2)|7 (-2)|8 (-1)|5 (-3)|
>___
> - **Damage Vulnerabilities** bludgeoning
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, poison
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** understands all languages it knew in life but can't speak
> - **Challenge** 1 (200 XP)
> ___
>
> ***Martial Advantage.*** Once per turn, the skeleton can deal an extra 7 (2d6) damage to a creature it hits with a weapon attack if that creature is within 5 feet of an ally of the skeleton that isn't incapacitated.
>
> ### Actions
> ***Longsword.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 5 (1d8 + 1) slashing damage, or 6 (1d10 + 1) slashing damage if used with two hands.

___
> ## Warhorse Skeleton <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;22;6;12;7;0;7;0;7;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Large undead, lawful evil*
> ___
> - **Armor Class** 13 (barding scraps)
> - **Hit Points** 22 (3d10 + 6)
> - **Speed** 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|12 (+1)|15 (+2)|2 (-4)|8 (-1)|5 (-3)|
>___
> - **Damage Vulnerabilities** bludgeoning
> - **Damage Immunities** poison
> - **Condition Immunities** exhaustion, poison
> - **Senses** darkvision 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
>
> ### Actions
> ***Hooves.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 7 (1d6 + 4) bludgeoning damage

<div class="pageLetter">S</div>
<div class='footnote'>SKELETONS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='top:0px; right:200px; width:600px; transform:rotate(150deg)'>
<img src='https://www.gmbinder.com/images/O699N4q.png' style='position:absolute; top:-50px; right:163px; width:700px' />

\pagebreakNum

<div style='margin-top:440px;'></div>

## Treant 
Few would gaze upon the stout treants and assume them to be wise or strong, but these awakened trees have been imbued by the spirits of the forests in which they dwell. In times of peace, they act as keepers and tenders. In times of war, they rise to defend their groves with fervor.

***Saplings of Ancients.*** The treants begin their lives as sapling sprouds of the ancients, carrying many of the same qualities as the tree from which they came -- be it be it boldness, tenderness, or a great force of will. Like the forest around them, treants never cease to grow. Instead, they rise taller and taller, century by century passing by, until the time is right for one to rise into the annals as an ancient protector.

***Guardians of Nature.*** Like the ancients, treants live to serve the forces of nature. Should someone dare to bring harm to their domain, it is they who wander the woods in search the perpetrators. If confronted, the treants respond by slashing wildly with their barbed claws.

Their task of safe-guarding nature have granted them favor among druids and woodland creatures alike. It is rare to see a treant wandering alone, as they are often accompanied by sprouts and other critters.

***Corrupted and Unpredictable.*** During the Third War, as the Burning Legion once more invaded Azeroth, numerous forests were set ablaze -- most notably, the forests of Ashenvale and Quel'Thalas.

With the destruction of their groves, the treants who delved within were driven to the brink of insanity, their hollow shells quickly gripped by the Legion's influence.

Though the invasion was since quelled, many groves are still saturated with demonic corruption; the treants within ready to lash out at any who would dare appproach. Adventurers who have taken upon them to visit these ancient sites, have borne witness to withered shambles lurking between dead trees and fallen ruins.

\columnbreak

<div style='margin-top:230px;'></div>

___
> ## Treant <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;39;4;12;22;0;22;0;22;0;0;0;0;0;0;0;1;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
>*Medium plant, chaotic neutral*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 39 (6d8 + 12)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|9 (-1)|15 (+2)|11 (+0)|13 (+1)|6 (-2)|
>___
> - **Damage Vulnerabilities** fire
> - **Damage Resistances** bludgeoning, piercing
> - **Senses** passive Perception 11
> - **Languages** understands Darnassian but can't speak
> - **Challenge** 2 (450 XP)
> ___
>
> ***False Appearance.*** While the treant remains motionless, it is indistinguishable from a normal tree.
>
> ### Actions
> ***Multiattack.*** The treant makes two claw attacks.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 11 (2d8 + 2) slashing damage.
>
> ***Entangle (Recharges after a Short or Long Rest).*** <br> A creature within 60 feet must succeed on a DC 12 Strength saving throw or be restrained for 1 minute. The creature can use its action to make a DC 12 Strength check, freeing itself on a success.

<div style='margin-top:35px;'></div>

> ##### Variant: Treant Wildcaller <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;45;4;11;37;0;22;0;22;0;0;0;0;0;0;0;1;;;;4;;;;;;;;;;1;;;;;;;;10;;;;;; -->
> Although all treants can manipulate the forest to some degree, wildcallers can harness the full might of the wilderness. A treant wildcaller has a challenge rating of 3 (700 XP). It has 45 (7d8 + 14) hit points and the following trait.
>
> ***Spellcasting.*** The treant is a 4th-level spellcaster. its spellcasting ability is Wisdom (save DC 11, +3 to hit with spell attacks). The treant has the following druid spells prepared:
>
> <br> Cantrips (at will): *druidcraft, solar wrath, thorn whip*
> <br> 1st level (4 slots): *cure wounds, faerie fire, sleep*
> <br> 2nd level (3 slots): *barkskin, spike growth*

<div class='letterheader'></div>
<div class="mmletter mml-t"></div>
<div class="pageLetter">T</div>
<div class='footnote'>TREANT </div>
<img src='https://www.gmbinder.com/images/XudEmdt.jpg' style='position:absolute; top:0px; right:0px; width:800px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/NO1EQoX.png' style='position:absolute; top:0px; right:0px; width:900px; transform:scalex(-1)' />

\pagebreakNum

## Troggs
Troggs are savage creatures with long, muscular arms that look as though they were carved from stone. They grow thick, coarse beards in colors resembling granite and chalk, and it is not rare to see minerals growing on their bodies. Their slouched posture and burly proportions have many characterizing them as apelike troglodytes.

***Primitive and fierce.*** Troggs are best known for their stature, ferocity, and smell -- said to resemble a mixture of mold, mange, and sour monkey. Living together in tight-knit tribes and clans, their main driving force is an imposing psyche and impressive force of will, though they are not known to be intelligent beyond being sentient. Less so than even an ogre would be considered. They follow the leadership of whoever can prove themselves the biggest and strongest, with aspiring trogg chieftains often going to great lengths to prove their viciousness. Troggs are known to eat whatever they can get their hands on; including rocks, or even occasionally other troggs.

***Underground creatures.*** With most of their existence spent underground, troggs are not fond of sunlight. Wher&shy;ever troggs dwell, a deep network of intertwining tunnels is likely to be somewhere nearby. They do most of their digging by hand, using their jagged claws, and occasionally shape weapons and other tools out of the rocks they excavate. Like the troggs themselves, a trogg dwelling is ill-reputed for is repulsive smell.

***Titanic origins.*** After the titanic Keepers had ended their war with the Old Gods, their next goal was to shape a new generation of titan-forged creatures, using the Titan complex of Ulduar. Their initial designs, however, proved too complex; yielding a race of stone-skinned monsters.

Though the Keepers sought to rectify their mistakes, they did not want to destroy their defect creations -- who they chosen to call *troggs*. Rather, the titanic Keeper *Ironaya* constructed Uldaman; a Titan vault that would keep the troggs in stasis, with herself as its designated warden.

Over the years, a few small groups managed to break free from Uldaman. Some of these scattered themselves out across the surface of Azeroth, while others burrowed their way deeper down to dwell in the subterranean caverns of *Deepholm*. The rest stayed as they were, asleep beneath the earth, until a dwarven excavation managed to unearth the titanic vault. Once the seal of Uldaman was broken, the troggs awoke; quickly overpowering the dwarves as they swarmed to the surface.

There, the troggs burrowed their way through every peak and valley across Khaz Modan, including the subterranean gnomish city of Gnomeregan. To this day, trogg tribes can be found in every corner of the Khaz Modan -- with distant cousins scattered far and wide across Azeroth.

***Progenitor race.*** Though the troggs were considered a failed experiment by the titanic Keepers, who sought to flourish new life on Azeroth, their failure became the blueprint for future revised designs.

Ultimately, the Titans formed the *earthen*; a race of stone-carved beings formed to bring order the deep reaches of the world during the ordering of Azeroth.

Theories have also been floated, mainly by the prominent dwarven explorer Brann Bronzebeard, that the *kobolds* are themselves an evolved offshoot from an early group of troggs. Likely one that earlier broke free from the titanic vault of Uldaman, however, there has been no conclusive evidence of this, only theories based on their resemblance.

\columnbreak

<div style='margin-top:398px;'></div>

___
> ## Trogg <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;39;4;12;14;0;14;0;14;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;1;;;;;10;;;1;;; -->
>*Medium humanoid (trogg), chaotic evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 39 (6d8 + 12)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|12 (+1)|14 (+2)|6 (-2)|10 (+0)|6 (-2)|
>___
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Brute.*** A melee weapon deals one extra damage die when the trogg hits with it (included in the attack).
>
> ***Stench.*** Any creature other than a trogg that starts its turn within 5 feet of the trogg must succeed on a DC 12 Constitution saving throw or be poisoned until the start of the creature's next turn. On a successful saving throw, the creature is immune to the stench of all troggs for 1 hour.
>
> ***Pack Tactics.*** The trogg has advantage on attack rolls against a creature if at least one of the trogg's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ### Actions
> ***Multiattack.*** The trogg makes two melee attacks.
>
> ***Club.*** *Melee Weapon Attack*: +4 to hit, reach 5 ft., one target. Hit: 7 (2d4 + 2) bludgeoning damage.
>
> ***Sling.*** *Ranged Weapon Attack*: +3 to hit, reach 120 ft., one target. Hit: 3 (1d4 + 1) bludgeoning damage.

<div class="pageLetter">T</div>
<div class='footnote'>TROGGS </div>
<img src='https://www.gmbinder.com/images/gfW9xZA.png' style='position:absolute; top:-20px; right:30px; width:px; filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42)' />
<img src='https://www.gmbinder.com/images/qIrMiJF.png' style='position:absolute; top:70px; right:-150px; width:600px;transform:scalex(-1)' />

\pagebreakNum

### Trogg Names and Languages
Troggs do not possess any discernible language of their own, and tend to resort to violence rather than negotiation when faced with a threat. Still, those who do communicate do so in a mixture of grunts and what Common they know.

Their names draw from the same roots as the dwarven language, especially with its hard consonants and guttural sounds. Some troggs, usually tribe leaders, choose names in Common to best describe themselves. It is unclear whether these names are direct translations, or deliberate choices to intimidate other races.

Trogg tribes are usually in Common, and often draw from their way of being or directly from whichever place they claim as their home.

<div style='margin-top:-5px;'></div>

**Trogg Names:** Argh, Agrok, Bruggor, Gorgash, Grimlok,
<br />&nbsp;&nbsp;&nbsp; Morloch, Murdaloc, Raggosh, Revelosh
<br />**Clan Names:** Bonegnasher, Caverndeep, Gravelflint,
<br />&nbsp;&nbsp;&nbsp; Irondeep, Rockjaw, Scrapbone, Stonevault

<div style='margin-top:-15px;'></div>

___
> ## Trogg Ambusher <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;45;5;12;19;0;19;0;19;0;0;0;0;0;0;0;;;;;4;;1;;;;;;;;1;;;1;;;;;10;;;1;;; -->
>*Medium humanoid (trogg), chaotic evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 45 (7d8 + 14)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|12 (+1)|15 (+2)|6 (-2)|10 (+0)|6 (-2)|
>___
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 2 (450 XP)
> ___
> ***Ambusher.*** The trogg has advantage on attack rolls against any creature it has surprised.
>
> ***Brute.*** A melee weapon deals one extra damage die when the trogg hits with it (included in the attack).
>
> ***Pack Tactics.*** The trogg has advantage on attack rolls against a creature if at least one of the trogg's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Stench.*** Any creature other than a trogg that starts its turn within 5 feet of the trogg must succeed on a DC 12 Constitution saving throw or be poisoned until the start of the creature's next turn. On a successful saving throw, the creature is immune to the stench of all troggs for 1 hour.
>
> ### Actions
> ***Multiattack.*** The trogg makes two melee attacks: one with its axe and one with its claw.
>
> ***Axe.*** *Melee Weapon Attack*: +5 to hit, reach 5 ft., one target. Hit: 12 (2d8 + 3) slashing damage.
>
> ***Claw.*** *Melee Weapon Attack*: +5 to hit, reach 5 ft., one target. Hit: 7 (2d4 + 3) slashing damage.

<div class="pageLetter">T</div>
<div class='footnote'>TROGGS </div>
<img src='https://www.gmbinder.com/images/rRmnHpu.jpg' style='position:absolute; top:0px; right:-225px; width:880px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:250px; width:900px' />
<img src='https://www.gmbinder.com/images/eqKqmVA.png' style='position:absolute; top:0px; right:146px; width:900px;transform:scaley(-1)' />

\pagebreakNum

___
> ## Trogg Shaman <!-- https://wc5e-cr-calculator.frogvall.com/?0;13;78;4;12;54;0;54;0;21;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;1;;; -->
>*Medium humanoid (trogg), chaotic evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 78 (12d8 + 24)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|12 (+1)|14 (+2)|9 (-1)|14 (+2)|6 (-2)|
>___
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** Low Common
> - **Challenge** 3 (700 XP)
> ___
>
> ***Spellcasting.*** The trogg is a 5th level spellcaster. Its spellcasting ability is Wisdom (spell save DC 12, +4 to hit with spell attacks). The trogg has the following shaman spells prepared:
>
> Cantrips (at will): *mold earth, shocking grasp, <br>&nbsp;&nbsp;&nbsp;  produce flame*
> <br>1st level (4 slots): *earth tremor, elemental shock** *, <br>&nbsp;&nbsp;&nbsp; chromatic orb, absorb elements*
> <br>2nd level (3 slots): *lava burst** *, maximilian's <br>&nbsp;&nbsp;&nbsp; earthen grasp**
> <br>3rd level (2 slot): *earthen spike, stinking cloud*
>
> ***Stench.*** Any creature other than a trogg that starts its turn within 5 feet of the trogg must succeed on a DC 12 Constitution save or be poisoned until the start of the creature's next turn. On a successful saving throw, the creature is immune to the stench of all troggs for 1 hour.
>
> ### Actions
> ***Staff.*** *Melee Weapon Attack*: +4 to hit, reach 5 ft., one target. Hit: 5 (1d6 + 2) bludgeoning damage, or 7 (1d8 + 2) bludgeoning damage if used with two hands to make a melee attack.

\columnbreak

___
> ## Trogg Chieftain <!-- https://wc5e-cr-calculator.frogvall.com/?1;15;136;7;12;31;0;31;0;31;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;;10;;;1;;; -->
>*Large humanoid (trogg), chaotic evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 136 (16d8 + 64)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|10 (+0)|18 (+4)|8 (-1)|10 (+0)|12 (+1)|
>___
> - **Senses** darkvision 60 ft., passive Perception 10
> - **Languages** Low Common
> - **Challenge** 5 (1800 XP)
> ___
> ***Brute.*** A melee weapon deals one extra damage die when the trogg hits with it (included in the attack).
>
> ***Stench.*** Any creature other than a trogg that starts its turn within 5 feet of the trogg must succeed on a DC 12 Constitution saving throw or be poisoned until the start of the creature's next turn. On a successful saving throw, the creature is immune to the stench of all troggs for 1 hour.
>
> ### Actions
> ***Multiattack.*** The trogg makes two attacks: one with its club and one with its kick.
>
> ***Greatclub.*** *Melee Weapon Attack*: +7 to hit, reach 5 ft., one target. Hit: 22 (4d8 + 4) bludgeoning damage.
>
> ***Kick.*** *Melee Weapon Attack*: +7 to hit, reach 5 ft., one target. Hit: 9 (2d4 + 4) slashing damage.
>
> ***Leadership (Recharges after a Short or Long Rest).*** For 1 minute, the trogg can utter a special command or warning whenever a nonhostile creature that it can see within 30 ft. of it makes an attack roll or a saving throw. The creature can add a d4 to its roll provided it can hear and understand the trogg. A creature can benefit from only one Leadership die at a time. This effect ends if the trogg is incapacitated.

<div class="pageLetter">T</div>
<div class='footnote'>TROGGS </div>
<img src='https://www.gmbinder.com/images/2va1koF.jpg' style='position:absolute; top:470px; right:-10px; width:1300px' />
<img src='https://www.gmbinder.com/images/MVDaLa2.png' style='position:absolute; top:-200px; right:0px; width:900px' />

\pagebreakNum

## Trolls
Trolls have made their mark upon the world over milennia, as ancient divides among their kin have brought forth a wide foray of tribes. Today, trolls can be found far and wide across Azeroth, each tribe unuque in its own appearance, customs, and way of life.

***Rulers of the Ancient World.*** When the world was still one, before the Great Sundering, the troll race flourished under the rule of the powerful Zandalari empire; able to match even the mighty Mogu dynasti.

The Zandalari relied heavily on its intricate caste system, under which each troll had its given place in life. As time went on, many of these castes grew into a people of their own, parting from the Zandalari to cut their own path in life. From this, two other empires grew forth to rival the Zandalari -- the Amani and the Gurubashi.

Other, smaller tribes tried to escape conflict by settling farther away, though many were made to heel by the three empires. Although animosity between the three was great, Azeroth had a host of other threats that would often draw a common enemy between them.

***Progenitors of the Elves.*** Eventually, a colony of dark trolls split free from the Amani empire, ventured forth discover the heart of the continent -- and with it, the cosmic Well of Eternity. By the influence of the well, they were transformed into the Kaldorei, night elves. 

At the base of the well, they forged for themselves a new empire. One with which they systematically dismantled the trolls around them, leaving once great empires in ruin.

Ultimately, however, the elves' reckless use of magic lured the demonic Burning Legion to the world. With it, the War of the Ancients began, by the end of which the Well of Eternity imploded in a shockwave that shattered the land and split the continents as they have been ever since.

Great chunks of the remaining Amani and Gurubashi empires were lost, but plenty of land remained for the trolls to rebuild their  cities and reclaim their territories.

***Racial Differences.*** The troll race is considered one of the most numerous, yet thoroughly divided. As each tribe has split its own course and claimed its own land, a troll's appearance can alone tell who they are.

***Tribal Devotion.*** Trolls have always been a tribal race, isolating themselves and starting anew. A troll’s tribe is its family, and many will go to extreme lengths to protect it as such. They owe loyalty to no-one but their own.

***Outside Hostility.*** Trolls settle in remote and isolated areas, places where they can stake their claim and turn the land into their own. The ferocity with which they defend their borders is legendar,y to say the least, as they will retaliate swiftly and with force if threatened.

***Loa's Guidance.*** Loa is the name trolls have given their animalistic spirit gods. Countless Loa exist, many of them weak and shapeless beings that only trolls can sense, while others take the form of majestic animals. Most troll tribes and empires have their own Loas, manifested as though given shape by the trolls in their worship.

***Regeneration.*** Smashing a troll's bones and slashing through its rubbery hide will only serve to anger it, as a troll's wounds close at an extraordinary speed. Only through acid or fire can one arrest their regeneration.

The ability for trolls to regenerate themselves is nothing short of legendary. It can only restore so much, however; as once a troll heart pumps its last, there is no natural way for it to recover.

<div class="pageLetter">T</div>
<div class='footnote'>TROLLS </div>
<img src='https://www.gmbinder.com/images/OWWpOcC.jpg' style='position:absolute; top:0px; right:-250px; width:850px' />
<img src='https://www.gmbinder.com/images/7drSEMn.png' style='position:absolute; top:0px; right:-10px; width:900px' />

\pagebreakNum

<div style='margin-top:180px;'></div>

### Troll Berserker
To survive a tribe, one must be powerful. For a troll, being powerful means being stronger than one's enemy.

Berserkers are the embodiment of this; with their brutish strength, they hurl their weapons at their targets as they cry for blood. Fearless, they hurl themselves into the fray to attack with reckless abandon.

### Troll Headhunter
Headhunters are the trackers and hunters of a tribe, using a combination of spear and bolas to bring down their prey.

They make formidable fighters, keen to take trophies from their fallen opponent to display as adornments. These trophies are usually severed fingers or ears, as well as the odd trinket that their quarry might have worn.

### Troll Witch Doctor
A troll witch doctor holds status as a spiritual leader for its tribe, often acting as a close advisor to its chieftain. They are the eyes that see things which others cannot, and the ones who commune with the Loas on behalf of the tribe.

As cunning as they are intelligent, the wield great magical prowess in their practice of voodoo and alchemy. They know few limits for creating magical concoctions, both to cure ailments and to spur horrors.

### Dire Troll
These enormous trolls tower above the rest of their kin, as they wield their immense strength to hurl boulders and enemies alike through the air, as well as to pummel them into the ground with almost bestial ferocity.

There is no definitive way to say what stands behind a dire troll's immense stature. Some are elevated through magical or alchemical means, while others have simply evolved to stand larger than life. Whatever the case might be, they are revered as proud and honorable souls among the trolls.

> ##### Variant: Dire Troll Caster
> Some dire trolls possess innate magical powers in their blood. These trolls are known as *Warcasters*, or *Warmothers* if the troll in question is female. They have a Wisdom of 17 (+3), and gain the Innate Spellcasting trait as follows.
>
> ***Innate Spellcasting.*** The troll's spellcasting ability is Wisdom (spell save DC 15). The troll can innately cast the following spells, requiring no material components:
> <div style='margin-top:0px;'></div>
>
> 2/day each: *bestow curse, confusion, puppet, slow*
> <br> 1/day each: *stoneskin, synaptic static*

---

\columnbreak

<div style='margin-top:370px;'></div>

___
> ## Troll Berserker <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;90;5;12;20;0;20;0;20;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;1;5;;;;;; -->
>*Medium humanoid (any troll), chaotic evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 90 (12d8 + 36)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|15 (+2)|16 (+3)|11 (+0)|12 (+1)|9 (-1)|
>___
> - **Saving Throws** Str +5, Con +5
> - **Skills** Athletics +8, Survival +3
> - **Senses** darkvision 60 ft., passive Perception 11
> - **Languages** Zandali
> - **Challenge** 3 (700 XP)
> ___
> ***Brute.*** A melee weapon attack deals one extra die of its damage when the berserker hits a target with it (included in the attack).
>
> ***Reckless.*** At the start of its turn, the troll can gain advantage on all melee weapon attack rolls during that turn, but attack rolls against it have advantage until the start of its next turn.
>
> ***Regeneration.*** The troll regains 5 hit points at the start of its turn. If the troll takes acid or fire damage, this trait doesn't function at the start of the troll's next turn. The troll dies if it starts its turn with 0 hit points.
>
> ### Actions
> ***Multiattack.*** The troll makes two weapon attacks.
>
> ***Handaxe.*** *Melee or Ranged Weapon Attack:* +5 to hit, reach 5 ft., and range 20/60 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.
>
> ***Javelin.*** *Ranged Weapon Attack:* +5 to hit, reach 5 ft. and range 20/60 ft., one target. *Hit:* 10 (2d6 + 3) piercing damage.

<div class="pageLetter">T</div>
<div class='footnote'>TROLLS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='top:-100px; right:-110px; width:600px'>
<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='top:500px; right:-30px; width:700px; transform:rotate(40deg)'>
<img src="https://www.gmbinder.com/images/MaxlH3h.png" style="position:absolute; top:35px; right:400px; width:px; filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42)); transform:rotate(-2deg)">
<img src="https://www.gmbinder.com/images/h0bOYtd.png" style="position:absolute;top:-38px; right:-90px; width:530px; transform:rotate(-6deg);">

\pagebreakNum

<div style='margin-top:370px;'></div>

___
> ## Troll Headhunter <!-- https://wc5e-cr-calculator.frogvall.com/?0;14;52;4;12;18;0;12;0;12;0;0;0;0;0;0;0;;;;;4;;;;;;;;;;1;;;;;;;1;3;;;;;; -->
>*Medium humanoid (any troll), chaotic evil*
> ___
> - **Armor Class** 14 (leather armor)
> - **Hit Points** 52 (8d8 + 16)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|15 (+2)|14 (+2)|12 (+1)|15 (+2)|9 (-1)|
>___
> - **Skills** Stealth +5, Survival +4
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** Zandali
> - **Challenge** 1 (200 XP)
> ___
> ***Regeneration.*** The troll regains 3 hit points at the start of its turn. If the troll takes acid or fire damage, this trait doesn't function at the start of the troll's next turn. The troll dies if it starts its turn with 0 hit points.
>
> ***Swift Hunter.*** If the troll moves at least 20 feet straight towards a target whilst taking the Dash action, it can make one melee weapon attack against it.
>
> ### Actions
> ***Multiattack.*** The troll makes two attacks: two with its spear, or one with its spear and one with its bolas.
>
> ***Spear.*** *Melee or Ranged Weapon Attack:* +4 to hit, reach 5 ft. and  range 20/60 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage, or 6 (1d8 + 2) piercing damage if used with two hands to make a melee attack.
>
> ***Bolas.*** *Ranged Weapon Attack:* +4 to hit, range 20/60 ft., one target. *Hit:* 4 (1d4 + 2) bludgeoning damage. If the target is a Large or smaller creature with legs, it must succeed on a DC 13 Dexterity saving throw or be grappled and knocked prone. A target can use its action to remove the bolas, ending the grapple.

\columnbreak

<div style='margin-top:293px;'></div>

___
> ## Troll Witch Doctor <!-- https://wc5e-cr-calculator.frogvall.com/?1;12;91;6;14;56;0;56;0;56;0;0;0;0;0;0;0;;;;1;2;;;;;;;;;;1;;;;;;;1;5;;;;;; -->
>*Medium humanoid (any troll), chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 91 (14d8 + 28)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|15 (+2)|14 (+2)|13 (+1)|17 (+3)|12 (+1)|
>___
> - **Saving Throws** Con +4, Wis +5
> - **Skills** Arcana +3, Insight +6, Medicine +6, Nature +6
> - **Senses** darkvision 60 ft., passive Perception 13
> - **Languages** Zandali
> - **Challenge** 5 (1,800 XP)
> ___
> ***Loa's Blessing.*** The troll has advantage on saving throws against being charmed or frightened.
>
> ***Regeneration.*** The troll regains 5 hit points at the start of its turn. If the troll takes acid or fire damage, this trait doesn't function at the start of the troll's next turn. The troll dies if it starts its turn with 0 hit points.
>
> ***Spellcasting.*** The troll is an 8th-level spellcaster. Its spellcasting ability is Wisdom (spell save DC 14, +6 to hit with spell attacks). The troll has the following priest and shaman spells prepared:
>
> Cantrips (at will): *light, shocking grasp, spare the <br>&nbsp;&nbsp;&nbsp; dying, toll the dead*
> <br> 1st level (4 slots): *absorb elements, inflict wounds, <br>&nbsp;&nbsp;&nbsp; thunderwave*
> <br> 2nd level (3 slots): *gentle repose, lesser restoration*
> <br> 3rd level (3 slots): *bestow curse, lightning bolt, <br>&nbsp;&nbsp;&nbsp; revivify, speak with dead*
> <br> 4th level (2 slots): *banishment, death ward*
>
> ### Actions
> ***Multiattack.*** The troll makes two quarterstaff attacks.
>
> ***Quarterstaff.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft, one target. *Hit:* 3 (1d6) bludgeoning damage, or 4 (1d8) bludgeoning damage if used with two hands to make a melee attack.

<div class="pageLetter">T</div>
<div class='footnote'>TROLLS </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot' style='top:-100px; right:0px; width:700px; transform:rotate(40deg)'>
<img src='https://www.gmbinder.com/images/qE8yxm2.png' style='position:absolute; top:-18px; right:330px; width:500px; z-index:10; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/Hg6ngM7.png' style='position:absolute; top:-50px; right:-50px; width:500px'>

\pagebreakNum

<div class='statblock-bottom-wide'>

___
___
> ## Dire Troll <!-- https://wc5e-cr-calculator.frogvall.com/?1;12;157;9;16;51;0;61;0;51;0;0;0;0;0;0;0;;;;;2;;;;;;;;;;1;;;;;;;1;15;;;;;; -->
>*Huge humanoid (any troll), chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 157 (15d12 + 60)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|23 (+6)|14 (+2)|18 (+4)|9 (-1)|12 (+1)|7 (-2)|
>___
> - **Skills** Athletics +9, Perception +4
> - **Condition Immunities** Frightened, Stunned
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** Zandali
> - **Challenge** 8 (3,900 XP)
> ___
> ***Berserk.*** Whenever the troll starts its turn with 60 hit points or fewer, it must make a DC 11 Wisdom save. On a failed save, the troll goes berserk. On each of its turns while berserk, the troll attacks the nearest crea&shy;ture it can see. If no creature is near enough to move and attack, the troll attacks an object, with preference for an object smaller than itself. Once the troll goes berserk, it continues to dos so until its killed or regains all its hit points.
>
> ***Regeneration.*** The troll regains 15 hit points at the start of its turn. If the troll takes acid or fire damage, this trait doesn't function at the start of the troll's next turn. The troll dies only if it starts its turn with 0 hit points and doesn't regenerate.
>
> ### Actions
> ***Multiattack.*** The troll makes three fist attacks. It then uses its toss if able.
>
> ***Fist.*** *Melee Weapon Attack:* +9 to hit, reach 10 ft., one target. *Hit:* 17 (2d10 + 6) bludgeoning damage, and the target is grappled (escape DC 16). Until this grapple ends, the target is restrained.
>
> ***Toss.*** *Ranged Weapon Attack:* +9 to hit, range 60/120 ft., one target. *Hit:* 10 (1d8 + 6) bludgeoning damage. The troll can't use this attack if it doesn't have a target grappled. Both the target thrown and hit takes damage from the attack.
>
> ***Rock*** *Ranged Weapon Attack:* +9 to hit, range 50/100 ft., one target. *Hit:* 30 (7d6 + 6) bludgeoning damage.

</div>

<div class="pageLetter">T</div>
<div class='footnote'>TROLLS </div>

<img src='https://www.gmbinder.com/images/QZfSRiM.png' class='inkblot' style='top:-100px; right:-100px; width:900px'>
<img src='https://www.gmbinder.com/images/Ylc5uWv.png' style='position:absolute; top:20px; right:0px; width:800px' />

\pagebreakNum

<div style='margin-top:160px;'></div>

___
> ## Thunder Lizard
>*Huge monstrosity, chaotic neutral*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 138 (12d12 + 60)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|22 (+6)|9 (-1)|21 (+5)|7 (-2)|14 (+2)|6 (-2)|
>___
> - **Skills** Perception +6
> - **Damage Immunities** lightning
> - **Senses** darkvision 60 ft., passive Perception 16
> - **Languages** —
> - **Challenge** 7 (2,900 XP)
> ___
> ***Trampling Charge.*** If the lizard moves at least 20 feet straight towards a creature and then hits it with a gore attack on the same turn, that target must succeed on a DC 17 Strength saving throw or be knocked prone. If the target is prone, the lizard can make one devour attack against it as a bonus action.
>
> ### Actions
> ***Gore.*** *Melee Weapon Attack:* +9 to hit, reach 10 ft., one target. *Hit* 24 (4d8 + 6) piercing damage.
>
> ***Devour.*** *Melee Weapon Attack:* +9 to hit, reach 5 ft., one target. *Hit:* 17 (2d10 + 6) piercing damage. A Medium or smaller target must succeed on a DC 17 Dexterity saving throw or swallowed by the lizard. The lizard can only have one target swallowed at a time. If a target fails the saving throw while the lizard has a creature swallowed, it is grappled instead.
> <br>&nbsp;&nbsp;&nbsp; A swallowed target is blinded and restrained, it has total cover against attacks and other effects outside the lizard, and it takes 10 (3d6) acid damage at the start of each of the lizard's turns.
> <br>&nbsp;&nbsp;&nbsp; If the lizard takes 25 damage or more on a single turn from the swallowed creature, the lizard must succeed on a DC 15 Constitution saving throw at the end of that turn or regurgitate the creature, which falls prone in a space within 10 feet of the lizard. If the lizard dies, a swallowed creature is no longer restrained by it and can escape from the corpse using 10 feet of movement, exiting prone.
>
> ***Lightning Breath (Recharge 5-6).*** The lizard exhales a line of lightning that is 20 feet long and 5 feet wide. Each creature in that line must make a DC 16 Dexter&shy;ity saving throw, taking 39 (6d12) lightning damage on a failed save, or half as much damage on a success. <!-- https://wc5e-cr-calculator.frogvall.com/?1;16;138;9;17;41;0;78;10;24;10;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

<div style='margin-top:470px;'></div>

## Thunder Lizard
Few who scout a thunder lizard approaching dare engage the beast in an open skirmish. The thick-skinned beasts bears a striking resemblance to kodos and many have speculated that the two are related in one way or another.

But that is where the similarities between the creatures end; as the monstrous thunder lizard is easily aggravated, persistent in hunting down whoever would provoke it, and capable of exhaling a breath of lightning.

***Creature of Myth.*** Thunder lizards are considered mystical creatures and a rare sight by many. They are only made rarer by their aggressive nature, as failing to take necessary precautions before attempting to approach a thunder lizard may quickly spell doom.

Among the tauren, legends claim thunder lizards to be formed from ancient kodo spirits; bound to the sky and storm and brought back as thundering monsters.

***Grassland Scavengers.*** The lumbering creatures roam the vast plains of Kalimdor in search of prey. Thunder lizards are carnivorous, and will often eat their prey whole: dissolving both the creature and everything it carried in the process. Thankfully, magical items are usually left behind without being too much worse for wear.

Wary scouts who have witnessed the great thunder lizards and lived, often note that they leave ordinary kodos unharmed -- rather seeking food elsewhere.

***Lone Wanderers.*** Thunder lizards are rarely found in large numbers, preferring to either hunt alone or follow a pack of kodos as some form of guardian. 

They move vast distances in their tireless hunt, and tales have been told of thunder lizards even wandering their way through open settlements. They rarely cause any trouble, however, so long as they are not provoked.

<div class="pageLetter">T</div>
<div class='footnote'>THUNDER LIZARD </div>
<img src='https://www.gmbinder.com/images/YpvK7Ef.png' class='inkblot inkblot-green' style='top:-300px; right:0px; width:700px; transform:rotate(60deg)'>
<img src='https://www.gmbinder.com/images/wRMRQeP.png' style='position:absolute; top:-40px; right:-50px; width:1000px;transform:scalex(-1)' />

\pagebreakNum

<div style='margin-top:630px;'></div>

## Whale Shark
In the depths of the ocean, beneath the sun-bathed reaches of the Great Sea, swims the arbiter of the deep. Known to many simple as whale sharks, these legendary leviathans patrol the deepest oceans; devouring any inattentive or overzealous adventurer that would cross their path.

***Devourer of All*** These larger-than-life behemoths swim through the oceans of Azeroth in an eternal hunt for survival. With their massive, lumbering bodies, whale sharks rarely benefit from being aggressive enough to directly hunt down their meal. Instead, they eat what happens to be caught in front of their massive maw. 

So long as it can offer some form of sustenance, they care little for what -- or who -- else they might swallow.

***Guardians of the Deeps.*** Whale sharks are known for being fairly territorial. Their domains are large, and they patrol it in broad circles along its borders, swallowing down whatever they happen by along the way.

Some have been spotted roaming waters around ancient ruins, leading to speculations that they are safeguarding the remnants within. Few, however, have been daring enough to venture deep enough within their realm to prove whether these are true stories or flighty legends.

\columnbreak

<div style='margin-top:98px;'></div>

___
> ## Whale Shark
>*Gargantuan beast, unaligned*
> ___
> - **Armor Class** 18 (natural armor)
> - **Hit Points** 297 (18d20 + 108)
> - **Speed** 0 ft., swim 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|27 (+8)|11 (+0)|23 (+6)|7 (-2)|13 (+1)|11 (+0)|
>___
> - **Saving Throws** Dex +6, Con +12, Wis +7
> - **Damage Resistance** fire; bludgeoning, piercing, and slashing from nonmagical attacks
> - **Condition Immunities** frightened, paralyzed
> - **Skills** Perception +7
> - **Senses** blindsight 120 ft., passive Perception 17
> - **Languages** –
> - **Challenge** 19 (22,000 XP)
> ___
> ***Blood Frenzy.*** The whale shark has advantage on melee attack rolls against any creature that doesn't have all its hit points.
>
> ***Water Breathing.*** The whale shark can breathe only underwater.
>
> ### Actions
> ***Multiattack.*** The whale shark makes three bite attacks. It can make one tail attack in place of one bite attack.
>
> ***Bite.*** *Melee Weapon Attack:* +14 to hit, reach 5 ft., one target. *Hit:* 27 (3d12 + 8) piercing damage. If the target is a Large or smaller creature affected by the whale shark's Inhale, that creature is swallowed. While swallowed, the target is blinded and restrained, it has total cover against attacks and other effects outside the whale shark, and it takes 28 (8d6) acid damage at the start of each of the whale shark's turns.
> <br>&nbsp;&nbsp;&nbsp; If the whale shark takes 40 damage or more on a single turn from a creature inside it, the whale shark must succeed on a DC 25 Constitution saving throw at the end of that turn or regurgitate all swallowed creatures, which fall prone in a space within 10 feet of the whale shark. If the whale shark dies, a swallowed creature is no longer restrained by it and can escape from the corpse using 15 feet of movement, exiting prone.
>
> ***Tail.*** *Melee Weapon Attack:* +14 to hit, reach 15 ft., one target. *Hit:* 24 (3d10 + 8) bludgeoning damage. If the target is a creature, it must succeed on a DC 22 Strength saving throw or be pushed 10 feet away from the whale shark and knocked prone.
>
> ***Inhale.*** The whale shark inhales water in a 15-foot cube in front of it. Each creature in that cube that is Large or smaller must make a DC 20 Dexterity saving throw or have their movement speed reduced to 0 until the end of the whale shark's next turn. <!-- https://wc5e-cr-calculator.frogvall.com/?3;18;297;14;17;81;0;81;28;81;56;0;0;0;0;0;0;1;;;;3;;;;1;;;;;;1;;;;;;;;10;;;;;; -->

<div class='letterheader'></div>
<div class="mmletter mml-w"></div>
<div class="pageLetter">W</div>
<div class='footnote'>WHALE SHARK </div>
<img src='https://www.gmbinder.com/images/YpvK7Ef.png' class='inkblot inkblot-blue' style='top:-100px; right:0px; width:700px; transform:rotate(-60deg)'>
<img src='https://www.gmbinder.com/images/XARxGdz.png' style='position:absolute; top:150px; right:-200px; width:1000px' />

\pagebreakNum

<div style='margin-top:230px;'></div>

## Wind Serpents
Slithering across in the plains of Mulgore, flying through the frosty trees of Winterspring, or prowling beneath the burning sand of Tanaris. Wind serpents are adaptable beasts who can be found in all corners of Azeroth. The serpentine creatures rarely pay any attention to those who wander by, but once hungry -- or aggravated -- they quickly turn hostile; ready to strike with their venomous bite and innate power to spew elemental fury.

A wind serpent combines the bright-scaled body and head of a snake with the leathery wings of a drake, as well as the feathers of a brightly colored bird.

***Spiritual Creatures.*** Wind serpents are often seen by less intelligent creatures as spirits of the sky, and have long since been revered by tribal races like the quilboars.

They also carry a srong resemblance to Hakkar the Soulflayer, a prominent troll Loa, prompting those who worship him to keep and train the beasts in his reverence.

***Unseen Hunters.*** The serpentine beasts are formidable hunters; predators who utilize the environment to ambush their prey for a moment's advantage. Crawling among tree branches, stalk within fissures, or flying silently out from dark nooks towards their desired target.

They attack with lightning speed and swiftly retreat once the blow has been dealt, stalking for the next opportunity to strike. Perceptive adventurers might catch a glimpse of their colorful scales glinting, as a warning of their presence -- and potential quarry.

***Adapted Species.*** Wind serpents can be found in the far reaches of the world. They nest in hard-to-reach places where they may safely retire. The different subspecies of wind serpents have adapted and adjusted to the environ&shy;ment around them, changing elemental bond -- and color with it --  to better survive their harsh surroundings.

> ##### Variant: Adapted Wind Serpents
> Wind serpents are found throughout Azeroth and have adapted differently to their climate.
> <br>&nbsp;&nbsp;&nbsp; You can change a wind serpent's *lightning breath* and *shocking spit* attacks to deal cold or poison damage instead of lightning by making the following changes to the attacks:
>
> ***Breath Attack.*** The breath attack becomes a cone of a size equal to half the line's length, and requires a Constitution saving throw to resist.
>
> ***Spit.*** The spit attack requires a Constitution saving throw to resist.

\columnbreak

<div style='margin-top:390px;'></div>

___
> ## Wind Serpent
>*Medium beast, neutral*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 22 (5d8)
> - **Speed** 20 ft., fly 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|15 (+2)|11 (+0)|3 (-4)|14 (+2)|5 (-3)|
>___
> - **Skills** Perception +4, Stealth +4
> - **Damage Resistances** poison
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 1 (100 XP)
> ___
> ***Keen Smell.*** The serpent has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage plus 3 (1d6) poison damage.
>
> ***Constrict.*** *Melee Weapon Attack:* +4 to hit, reach 10 ft., one Medium or smaller creature. *Hit:* 9 (2d6 + 2) bludgeoning damage, and the target is grappled (escape DC 12). Until this grapple ends, the target is restrained, and the wind serpent can't constrict another target.
>
> ***Lightning Breath (Recharges after a Short or Long Rest).*** The serpent exhales lightning in a 20-foot line that is 5 feet wide. Each creature in that line must make a DC 12 Dexterity saving throw, taking 11 (2d10) lightning damage on a failed save, or half as much damage on a successful one. <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;22;4;12;22;0;9;0;9;0;0;0;0;0;0;0;;;;;3;;;;;1;;;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">W</div>
<div class='footnote'>WIND SERPENTS </div>
<img src='https://www.gmbinder.com/images/Vm7cCm7.jpg' style='position:absolute; top:0px; right:-200px; width:900px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/z86Lpca.png' style='position:absolute; top:0px; right:-40px; width:900px; transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot' style='top:-100px; right:500px; width:400px; transform:rotate(-40deg)'>
<img src="https://www.gmbinder.com/images/qoSXNIN.png" style="position:absolute;top: 65px;left: 50px;transform: rotate(1deg);z-index:100;filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">


\pagebreakNum

___
> ## Wind Serpent Stinglash
>*Medium beast, neutral*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 27 (5d8 + 5)
> - **Speed** 20 ft., fly 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|16 (+3)|12 (+1)|3 (-4)|14 (+2)|5 (-3)|
>___
> - **Skills** Perception +4, Stealth +5
> - **Damage Resistances** poison
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 2 (100 XP)
> ___
> ***Keen Smell.*** The serpent has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Venomous Bite.*** Once per turn, the serpent can deal an extra 3 (1d6) poison damage with its bite to a target that doesn't have all its hit points.
>
> ### Actions
> ***Multiattack.*** The serpent makes two attacks: one with its bite and one with its constrict.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) piercing damage plus 3 (1d6) poison damage.
>
> ***Constrict.*** *Melee Weapon Attack:* +5 to hit, reach 10 ft., one Medium or smaller creature. *Hit:* 10 (2d6 + 3) bludgeoning damage, and the target is grappled (escape DC 13). Until this grapple ends, the target is restrained, and the wind serpent can't constrict another target.
>
> ***Shocking Spit.*** *Ranged Weapon Attack:* +5 to hit, range 15/30 ft., one creature. *Hit:* The target must make a DC 13 Dexterity saving throw, taking 21 (6d6) lightning damage on a failed save, or half as much damage on a successful one. <!-- https://wc5e-cr-calculator.frogvall.com/?0;15;27;5;12;23;0;23;0;23;0;0;0;0;0;0;0;;;1;;3;;;;;1;;;;;1;;;;;;;;10;;;;;; -->

\columnbreak

___
> ## Wind Serpent Dreadfang
>*Large beast, neutral*
> ___
> - **Armor Class** 17 (natural armor)
> - **Hit Points** 65 (10d10 + 10)
> - **Speed** 30 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|9 (-1)|17 (+3)|13 (+1)|4 (-3)|15 (+2)|5 (-3)|
>___
> - **Skills** Perception +4, Stealth +5
> - **Damage Resistances** poison
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 4 (1,100 XP)
> ___
> ***Keen Smell.*** The serpent has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Multiattack.*** The serpent makes two attacks: one with its bite and one with its constrict.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 12 (2d8 + 3) piercing damage plus 7 (2d6) poison damage.
>
> ***Constrict.*** *Melee Weapon Attack:* +5 to hit, reach 10 ft., one Large or smaller creature. *Hit:* 13 (3d6 + 3) bludgeoning damage, and the target is grappled (escape DC 14). Until this grapple ends, the target is restrained, and the wind serpent can't constrict another target.
>
> ***Frightful Screech.*** Each creature within 60 feet of the serpent that can hear it must succeed on a DC 12 Wisdom saving throw or be frightened for 1 minute. A frightened target can repeat the saving throw at the end of each of its turns, ending the frightened condition on itself on a success. If a target's saving throw is successful or the effect ends for it, the target is immune to this serpent's Frightful Screech for the next 24 hours.
>
> ***Lightning Breath (Recharge 5-6).*** The serpent exhales lightning in a 40-foot line that is 5 feet wide. Each creature in that line must make a DC 14 Dexterity saving throw, taking 27 (5d10) lightning damage on a failed save, or half as much damage on a success. <!-- https://wc5e-cr-calculator.frogvall.com/?0;17;65;5;12;34;0;32;0;32;0;0;0;0;0;0;0;;;;;3;;;;;1;;1;;;1;;;;;;;;10;;;;;; -->

<div class="pageLetter">W</div>
<div class='footnote'>WIND SERPENTS </div>
<img src='https://www.gmbinder.com/images/QC98AHW.jpg' style='position:absolute; top:450px; right:0px; width:900px' />
<img src='https://www.gmbinder.com/images/hIpYyKx.png' style='position:absolute; top:0px; right:0px; width:900px' />

\pagebreakNum

<div style='margin-top:470px;'></div>

___
> ## Wretched
>*Medium humanoid (blood elf), chaotic neutral*
> ___
> - **Armor Class** 12
> - **Hit Points** 18 (4d8)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|14 (+2)|11 (+0)|12 (+1)|11 (+0)|10 (+0)|
>___
> - **Skills** Arcana +3, Perception +2
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** Thalassian
> - **Challenge** 1/4 (50 XP)
> ___
> ***Innate Spellcasting.*** The wretched's spellcasting ability is Intelligence (spell save DC 11). It can innately cast the following spells, requiring no material component
>
> At will: *blade ward, minor illusion*
> <br> 1/day each: *detect magic, magic missiles, shield*
>
> ***Magic Resistance.*** The wretched has advantage on saving throws against spells and other magical effects
>
> ### Actions
> ***Shortsword.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Longbow.*** *Ranged Weapon Attack:* +4 to hit, range 150/600 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage. <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;18;4;12;9;0;6;0;6;0;0;0;0;0;0;0;;;;;3;;;;;;;;;;1;1;;;;;;;10;;;;;; -->

\columnbreak

## Wretched
Poor souls who failed to control their addiction to magic, and thus gorged on arcane power to the point of deformity — that is the story of the wretched. 

These frail-bodied denizens of Quel'thalas are recogni&shy;sable for their gaunt, emaciated appearance, pale skin, and claw-like hands. Strange crystalling growths have spurred across their skin, giving them an eerie glow in darkness. They are a danger both to themselves and to others, with their violent and unpredictable nature. 

***Insane Elves.*** The wretched are obsessed with magic, willing to go to extreme lengths for any scrap of magic that they can drain; whether from enchanted items, arcane fonts, or even errant spellcasters. Their fixation goes to the brink of insanity, and often far beyond it.

Attempting to bargain with wretched for safe passage through their domain is rarely a peaceful affair, as their unpredictable nature makes them all too easy to anger.

***Pest of Quel'thalas.*** Being denizens of Quel'thalas themselves, the wretched elves rarely leave the confines of their magical kingdom. Instead, they have opted to scatter through the forest, taking up residence in ruins still left behind by the undead Scourge. There, they huddle together in small packs, letting their addiction take its toll.

For the most part, in the eyes of Silvermoon, the wretched are little more than a pest upon the land. Their violent nature have left few wretched able to gather a force large enough to spur any proper conflicts, though they would pose a true threat to their elven kin should such a leader arise.

### Wretched Names
Despite their addled presence and disownment by their kin, the wretches are still blood elves. As such, they still know to speak Thalassian. Few among them, however, seem to show any signs of remembering Common.

Their overindulgence have lead many wretched into insanity, with some forgetting their names entirely. Others simply choose to take one a new one, casting aside any remnants of their old identity.

The wretched use the same naming conventions as high and blood elves, but opt for descriptive and often profound titles in place of typical elven surnames — such as *the Reckless* or *the Hungerer*.

> ##### Variant: Magic Absorption
> Wretched have an insatiable craving for magic and will go to extreme lengths to obtain and consume it. Some wretched are able to devour the essence of a magic item and be empowered by it.
>
> A wretched devourer has a challenge rating of 1/2 (100 XP) and gains the following action option.
>
> ***Devour Magic (Recharge 6).*** The wretched chooses one creature within 60 feet of it, the target must succeed on a DC 11 Dexterity saving throw or have one of its magic items lose all magical properties until the start of the wretched's next turn. If the object is a charged item, it also loses 1d4 charges. Determine the affected item randomly, ignoring single-use items such as potions and scrolls.
>
> If the wretched successfully devours the magic of an item, it regains the use of one of its *once per day* innate spellcasting spells.

<div class="pageLetter">W</div>
<div class='footnote'>WRETCHED </div>
<img src='https://www.gmbinder.com/images/i7UrPYM.jpg' style='position:absolute; top:0px; right:350px; width:500px' />
<img src='https://www.gmbinder.com/images/61ldIkX.png' style='position:absolute; top:0px; right:-100px; width:900px; transform:scaley(-1)' />
<img src="https://www.gmbinder.com/images/m6qCwvJ.png" class="inkblot" style=" top:570px; right:600px; width:400px; transform:rotate(44deg);">

\pagebreakNum

## Worgen: Feral
The curse of the worgen can transform even the most civilized person into a ravenous, primal beast. Filled with rage, it gradually loses all vestiges of its former life, as it slowly turns into a mindless hunter. These feral beings bear a closer semblence to monstrous wolves than to intelligent humanoids. However, upon a closer inspection, their eyes betray the mind still trapped within.

***Ancient Curse.*** The worgen curse began with a sect of night elves, who tried to tame the powers of the ancient Godrinn. Instead, they were transformed into feral beasts, and subsequently locked away in the Emerald Dream. They were alter brought forth by the Archmage Arugal -- who himself sought a weapon against the Scourge.

Though the worgen were successful in keeping the damned at bay, they did not differ between the living and dead; leaving the curse to quickly seep through Gilneas.

***Pack Animals.*** Feral worgen have but a shred of humanity left, locked away in a beast that cannot be reasoned or communicated with. Like wolves, they keep to forested areas and gather  in large packs, headed by their strongest -- the alpha.

***Humanoid Cubs.*** Worgen do not give birth to lupine humanoids, but rather to a humanoid of their original race. Although the mother might care for its child, this is often not shared by the rest of its pack.

***Resistance to Undeath.*** The curse of the worgen draws its power from the Emerald Dream, and the light of the goddess Elune. For this, raising a worgen into undeath is by far more difficult than it is with most other humanoids.

***Feral Weaknesses.*** As vicious as they are, these feral beasts are hardly intimidated and rarely back down if the pack keeps together. They do, however, have a strong dislike for open fires, and avoid areas lit by open flames whenever possible -- so long as the hunger for flesh does not force them to push through.

They also appear to be very susceptible to the wolfsbane plant; a small, purple flower commonly found across the kingdom of Gilneas. If this seemingly harmless plant comes in contact with a worgen's wounds, it prevents the beast from recuperating.

> ##### Player Characters as Feral Worgen
> A humanoid bit by a worgen must succeed on a DC 12 Constitution saving throw or be cursed. The curse has no effect on undead beings, such as the forsaken. A character bit begins to show the effects of the curse after 1d4 days, at which point the character is transformed into a feral worgen. It gains a Strength of 15 if their score isn't already higher, and their alignment changes to Chaotic Evil.
>
> The cursed character also gains the following indefinite madness, *"I hunger for the taste of blood and will kill anyone to taste it once more."*
>
> The character remains a feral worgen until a *greater restoration* spell or more powerful magic rids the character of their indefinite madness, at which point alignment returns to what it was before being bit, and the character gains the *Two Forms* feature and the *Worgen Form Traits* of the Worgen race.

\columnbreak

<div style='margin-top:290px;'></div>

___
> ## Feral Worgen
>*Medium humanoid (worgen), chaotic evil*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 39 (6d8 + 12)
> - **Speed** 40 ft., climb 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|13 (+1)|14 (+2)|7 (-2)|11 (+0)|10 (+0)|
>___
> - **Skills** Perception +4, Survival +2, Stealth +3
> - **Damage Resistances** bludgeoning, piercing, and slashing from nonmagical attacks and weapons <br>that aren't silvered
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** Wolf
> - **Challenge** 2 (450 XP)
> ___
> ***Keen Hearing and Smell.*** The worgen has advantage on Wisdom (Perception) checks that rely on its hearing or smell.
>
> ***Pack Tactics.*** The worgen has advantage on an attack roll against a creature if at least one of the worgen's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Standing Leap.*** The worgen's long jump is up to 30 ft. and its high jump is up to 20 ft., with or without a running start.
>
> ### Actions
> ***Multiattack.*** The worgen makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage. If the target is a humanoid, it must succeed on a DC 12 Constitution saving throw or gain the worgen curse.
>
> ***Claws.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 7 (2d4 + 2) slashing damage. <!-- https://wc5e-cr-calculator.frogvall.com/?0;12;39;4;12;13;0;0;0;0;0;0;0;0;0;0;0;1;;;;3;;;;;;;;;;1;;;1;;;;;10;;;;;; -->

<div class="pageLetter">W</div>
<div class='footnote'>WORGEN: FERAL </div>
<img src='https://www.gmbinder.com/images/xLmKBtn.jpg' style='position:absolute; top:-100px; right:-65px; width:500px;transform:scalex(-1)' />
<img src='https://www.gmbinder.com/images/qKrtKxo.png' style='position:absolute; top:0px; right:-20px; width:900px' />

\pagebreakNum

<div style='margin-top:100px;'></div>

## Yeti
Yetis -- also known as Wendigos -- are hulking monstrosities that roam remote forests and snowy mountains. They exhibit a territorial ferocity rarely seen in other creatures, and make for terrifying and powerful foes. Especially with how they are willing to hunt any and all that would happen to wander too close to their den.

***Territorial Beings.*** The territorial nature of a yeti is common knowledge for any settlement near its hunting ground. When venturing outside, one must be sure to keep clear of any sign of the creature's trail; easily noticeable for the massive, clawed depressions and bloody carnage it leaves behind in the snow.

Yetis possess a desire for blood that cannot be <br/> quenched. They often continue to hunt even when they <br/> are not hungry, dragging any un-eaten scraps back to <br/> their lair as a snack for later. As such, a yeti found <br/> roaming is seldom one left without purpose: it is almost guaranteed to be out looking for easy prey.

***Horrific Dens.*** Yetis make their dens in caverns and under isolated overhangs, usually recognized by an entrance strewn across with bones and half-eaten corpses. The cold climate of their habitat keeps the smell at bay, though the sight is as unmistakable as it is terrifying.

This can, however, mean untold riches for strong-hearted adventurers. If anything manages to survive the yeti's frenzy, it is left strewn under the snow across its den -- like a treasure for any who would dare to collect it.

***Solitary Hunters.*** It is not a lack of intelligence, but an assertion of pride and dominance that drives the yeti to wander alone. If they first do decide to join together, whether to survive or simply for sport, they will first fight tooth and claw to establish a leader.

\columnbreak

<div class='statblock-bottom-wide'>

___
___
> ## Yeti
>*Large monstrosity, neutral evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 60 (7d10 + 18)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|11 (+0)|16 (+3)|9 (-1)|10 (+0)|7 (-2)|
>___
> - **Skills** Perception +2
> - **Damage Immunities** cold
> - **Senses** darkvision 60 ft., passive Perception 12
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
>
>***Keen Smell.*** The yeti has advantage on Wisdom (Perception) checks that rely on smell.
>
>***Snow Camouflage.*** The yeti has advantage on Dexterity (Stealth) checks made to hide in snowy terrain.
>
>***Charge.*** If the yeti moves at least 30 feet straight toward a target and then hits it with a horn attack on the same turn, the target takes an extra 12 (2d10) piercing damage.
>
> ### Actions
>***Multiattack.*** The yeti makes two claw attacks.
>
>***Claw.*** *Melee Weapon Attack*: +6 to hit, reach 5 ft., one target. Hit: 9 (1d8 + 4) slashing damage plus 2 (1d4) cold damage.
>
>***Horn.*** *Melee Weapon Attack*: +6 to hit, reach 5 ft., one target. Hit: 10 (1d10 + 4) piercing.
>
>***Roar.*** The yeti emits a roar. Each creature within 30 feet of the yeti and able to hear the roar must make a DC10 Wisdom saving throw, being Frightened for 1 minute on a fail. A Frightened creature can repeat the saving throw at the end of each of its turns, ending the effect on itself on a success. On a successful saving throw, the creature is immune to the roar of all yetis for 1 day.

</div>

<div class='letterheader'></div>
<div class="mmletter mml-y"></div>
<div class="pageLetter">Y</div>
<div class='footnote'>YETIS </div>
<img src='https://www.gmbinder.com/images/e5Dbuzd.png' class='inkblot' style='top:0px; right:-150px; width:700px'>
<img src='https://www.gmbinder.com/images/p2lxjIf.png' style='position:absolute; top:120px; right:-41px; width:500px' />

\pagebreakNum

<div style='margin-top:190px;'></div>

### Abominable Yeti
Abominable yetis are menacing creatures, towering above their kin with the posture of enormous apes. They make their dens high in the mountains, in places so remote that no one would dare to venture close. They care little for keeping a large perimeter and hunt only to survive. They are, however, far more aggressive in their hunt; willing to venture much farther from their den for food.

The greatest evidence of their existence are their primal roars; as loud as they are terrifying, echoing through the mountains. Little else is known of the abominable yeti, as few have encountered one and since lived to tell their tale.

<div class='statblock-bottom-wide'>

___
___
> ## Abominable Yeti
>*Huge monstrosity, neutral evil*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 171 (13d12 + 80)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|22 (+6)|16 (+3)|20 (+5)|6 (-2)|12 (+1)|9 (-1)|
>___
> - **Skills** Perception +5
> - **Damage Immunities** cold
> - **Senses** darkvision 60 ft., passive Perception 15
> - **Languages** —
> - **Challenge** 11 (7,200 XP)
> ___
>
>***Keen Smell.*** The yeti has advantage on Wisdom (Perception) checks that rely on smell.
>
>***Snow Camouflage.*** The yeti has advantage on Dexterity (Stealth) checks made to hide in snowy terrain.
>
>***Charge.*** If the yeti moves at least 30 feet straight toward a target and then hits it with a horn attack on the same turn, the target takes an extra 18 (3d10) piercing damage.
>
>***Standing Leap.*** The yeti's long jump is up to 40 ft. and its high jump is up to 20 ft., with or without a running start.
>
> ### Actions
>***Multiattack.*** The yeti makes two claw attacks.
>
>***Claw.*** *Melee Weapon Attack*: +10 to hit, reach 5 ft., one target. Hit:  12 (2d6 + 6) slashing damage plus 5 (1d8) cold damage.
>
>***Horn.*** *Melee Weapon Attack*: +10 to hit, reach 5 ft., one target. Hit: 24 (3d10 + 6) piercing damage.
>
>***Roar.*** The yeti emits a roar. Each creature within 30 feet of the yeti and able to hear the roar must make a DC15 Wisdom saving throw, being Frightened for 1 minute on a fail. A Frightened creature can repeat the saving throw at the end of each of its turns, ending the effect on itself on a success. On a successful saving throw, the creature is immune to the roar of all yetis for 1 day.
>
>***Deadly Leap.*** If the yeti jumps at least 20 ft. as part of its movement, it can then use this action to land on its feet in a space that contains one or more other creatures. Each of those creatures must succeed on a DC 18 Strength or Dexterity saving throw (target's choice) or be knocked prone and take 30 (4d10 + 6) bludgeoning damage.
<br>&nbsp;&nbsp;&nbsp; On a successful save, the creature takes only half of the damage, isn't knocked prone and is pushed 5 ft. out of the yeti space into an unoccupied space of the creature's choice. If no unoccupied space is within range, the creature instead falls prone in the yeti space.
>
>***Cold Breath (Recharge 5-6).*** The yeti exhales an icy blast in a 30-foot cone. Each creature in that area must make a DC 13 Constitution saving throw, taking 36 (6d10) cold damage on a failed save, or half as much damage on a successful one.
>
> ### Legendary Actions
>
>The yeti can take 3 legendary actions, choosing from the options below. Only one legendary action can be used at a time and only at the end of another creature’s turn. The yeti regains spent legendary actions at the start of its turn.
>
>***Claw Attack.*** The yeti makes one claw attack.
>
>***Leap Attack (Cost 2 actions).*** The yeti makes a deadly leap attack.

</div>

<div class="pageLetter">Y</div>
<div class='footnote'>YETIS </div>
<img src='https://www.gmbinder.com/images/ZQOYrMF.jpg' style='position:absolute; top:-100px; right:-350px; width:1100px' />
<img src='https://www.gmbinder.com/images/VdV67Oz.png' style='position:absolute; top:0px; right:0px; width:950px; transform:scaley(-1)' />
<img src="https://www.gmbinder.com/images/e5Dbuzd.png" class="inkblot" style="top:-120px;right: 390px;width:400px;transform:rotate(-40deg);">
<img src="https://www.gmbinder.com/images/QsGzjQf.png" style="position:absolute;top: 50px;left: 70px;transform: rotate(2deg);z-index:100;filter:drop-shadow(1px 1px 4px rgba(0,0,0,0.42));">

\pagebreakNum

<div class='wide'>

# Chapter 2: Miscellaneous Creatures

</div>


This chapter contains statistics for numerous miscellan&shy;eous animals, creatures, and critters. Several creatures in this chapter are magical in nature, some of them even on par so with creatures found in chapter 1, but we chose to bring them all together in this chapter. 

Azeroth is a fantastical world, and even some of its ordinary and everyday critters are larger than life without being monstrous. Massive scorpids, six-legged crocolisks, hawkstriders, and magical moths are all pretty typical sights on these mystical shores.


##### SRD Content Included

Some of the statblocks included in this chapter are taken from the Dungeons & Dragons SRD 5.1, following guidelines on copying and modifying SRD content. 

Some of them have been added as is, while others we've adjusted and rebalanced for Warcraft as a campaign setting. We did this because we wanted to have as many setting-appropriate creatures as possible, even ones already printed in the SRD, together in one place. 

> Keep this here for a bit but move it to the book intro later to clear some space.

___
> ## Ashwing Moth
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 10
> - **Hit Points** 1 (1d4 - 1)
> - **Speed** 5 ft., fly 25 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|3 (-4)|10 (+0)|8 (-1)|1 (-5)|6 (-2)|3 (-4)|
>___
> - **Senses** blindsight 30 ft., passive Perception 8
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> ***Illumination.*** The moth sheds bright light in a 5-foot radius and dim light for an additional 5 feet.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one target. *Hit:* 1 piercing damage.

An **ashwing moth** is a nocturnal creature, best known for its vibrant light. Assassins prize them for it, using it as a decoy or distraction, as well as a subtle light in dark places. 

The moth cannot survive for long in captivity, however. Those who wish to make regular use of its abilities must either carefully recreate its natural habitat -- as is often done by the Jinyu of Pandaria -- or only seek them out where they already are.

An ashwing moth kept in captivity sheds light for 1d8 days, after which the light fades as it goes dormant.

\columnbreak

___
> ## Bat
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 1 (1d4 - 1)
> - **Speed** 5 ft., fly 30ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|2 (-4)|15 (+2)|8 (-1)|2 (-4)|12 (+1)|4 (-3)|
>___
> - **Senses** blindsight 60ft., passive Perception 11
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> ***Echolocation.*** The bat can't use its blindsight while deafened.
>
> ***Keen Hearing.*** The bat has advantage on Wisdom (Perception) checks that rely on hearing.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +0 to hit, reach 5 ft., one creature. *Hit:* 1 piercing damage.

___
> ## Black Bear
>*Medium beast, unaligned*
> ___
> - **Armor Class** 11 (natural armor)
> - **Hit Points** 19 (3d8 + 6)
> - **Speed** 40 ft., climb 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|10 (+0)|14 (+2)|2 (-4)|12 (+1)|8 (-2)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
> ***Keen Smell.*** The bear has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Multiattack.*** The bear makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 7 (2d4 + 2) slashing damage.

<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>


\pagebreakNum

___
> ## Boar
>*Medium beast, unaligned*
> ___
> - **Armor Class** 11 (natural armor)
> - **Hit Points** 11 (2d8 + 2)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|11 (+0)|12 (+1)|2 (-4)|9 (-1)|5 (-3)|
>___
> - **Senses** passive Perception 9
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
> ***Charge.*** If the boar moves at least 20 feet straight toward a target and then hits it with a tusk attack on the same turn, the target takes an extra 3 (1d6) slashing damage. If the target is a creature, it must succeed on a DC 11 Strength saving throw or be knocked prone.
>
> ***Relentless (Recharges after a Short or Long Rest).*** If the boar takes 7 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ### Actions
> ***Tusk.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) slashing damage.

___
> ## Brown Bear
>*Large beast, unaligned*
> ___
> - **Armor Class** 11 (natural armor)
> - **Hit Points** 34 (4d10 + 12)
> - **Speed** 40 ft., climb 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|19 (+4)|10 (+0)|16 (+3)|2 (-4)|13 (+1)|7 (-2)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Keen Smell.*** The bear has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Multiattack.*** The bear makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (1d8 + 4) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 11 (2d6 + 4) slashing damage.


\columnbreak

___
> ## Carrion Bird
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 9 (2d6 + 2)
> - **Speed** 10 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|15 (+2)|13 (+1)|2 (-4)|14 (+2)|4 (-3)|
>___
> - **Skills** perception +4
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
> ***Keen Sight and Smell.*** The carrion bird has advantage on Wisdom (Perception) checks that rely on sight or smell.
>
> ***Pack Tactics.*** The carrion bird has advantage on an attack roll against a creature if at least one of the bird's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ### Actions
>
> ***Talons.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) slashing damage

A **carrion bird** is a large, carnivorous scavenger bird found across Azeroth. Their wings are broad and their heads often featherless. They stalk their prey from the skies, lurk&shy;ing from a distance, as they wait for it to fall -- whether from exhaustion, or from another hunter.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/QIZvRDl.jpg" style="position: absolute;bottom: -39px;right: -98px;width: 900px;">

<img src="https://i.imgur.com/MVDaLa2.png" style="position:absolute; top:-50px; right:0px; width:800px;" />

<img src="https://www.gmbinder.com/images/wJZvXi2.png" class="inkblot inkblot-green" style="top: -327px;right: -240px;width: 680px;transform: rotate(84deg);">


\pagebreakNum


___
> ## Coyote
>*Small beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 9 (2d6 + 2)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|14 (+2)|12 (+1)|3 (-4)|12 (+1)|6 (-2)|
>___
> - **Skills** Perception +3, Stealth +4
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
>
> ***Keen Hearing and Smell.*** The coyote has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Pack Tactics.*** The coyote advantage on an Attack roll against a creature if at least one of the coyotes allies is within 5 ft. of the creature and the ally isn't Incapacitated.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* +4 (1d4 + 2) piercing damage.

___
> ## Crab
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 11 (natural armor)
> - **Hit Points** 2 (1d4)
> - **Speed** 20 ft., swim 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|2 (-4)|11 (+0)|10 (+0)|1 (-5)|8 (-1)|2 (-4)|
>___
> - **Skills** Stealth +2
> - **Senses** blindsight 30 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ***Amphibious.*** The crab can breathe air and water.
>
> ### Actions
> ***Claw.*** *Melee Weapon Attack:* +0 to hit, reach 5 ft., one target. *Hit:* 1 bludgeoning damage.


\columnbreak

___
> ## Crocolisk
>*Large beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 19 (3d10 + 3)
> - **Speed** 20 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|10 (+0)|13 (+1)|2 (-4)|10 (+0)|5 (-3)|
>___
> - **Skills** Stealth +2
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
> ***Hold Breath.*** The crocolisk can hold its breath for 15 minutes.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* +7 (1d10 + 2) piercing damage, and the target is grappled (escape DC 12). Until this grapple ends, the target is restrained, and the crocodile can't bite another target.

A **crocolisk** is a massive, six-legged reptilian predator. It is an amphibious creature that can be found along most warm, humid shorelines across Azeroth -- or dwelling in its murky swamps, rivers, and marshes. 

Hunters prize the meat and thick, durable hide of the crocolisk. Some speculate the beast may be related to thediemetradon, as they share a number of characteristics. 


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://www.gmbinder.com/images/tiU4RnD.png" class="inkblot inkblot-green" style="top: 531px;left: 20px;width: 770px;transform: rotate(39deg);">
<img src="https://i.imgur.com/xgTWyy8.png" style="position:absolute;top: 640px;right: -18px;width: 760px;">

\pagebreakNum

___
> ## Darkhound
>*Medium fiend, chaotic evil*
> ___
> - **Armor Class** 12
> - **Hit Points** 11 (2d8 + 2)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|14 (+2)|12 (+1)|3 (-4)|12 (+1)|7 (-2)|
>___
> - **Skills** Perception +3
> - **Senses** darkvision 30 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
> ***Keen Hearing and Smell.*** The darkhound has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Otherworldly Perception.*** The darkhound can sense the presence of any creature within 30 feet of it that is invisible or on the Ethereal Plane. It can pinpoint such a creature that is moving.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage, plus 2 (1d4) poison damage.

A **darkhound** is a demonic dog found stalking the forests of the world, either by themselves or in small packs. Despite their dark origin, they are a fairly common presence where they dwell. To farmsteads and small communities, having a pack of darkhounds nearby is a trouble best dealt with quickly -- though the dark iron dwarves have found good use in them as patrol animals.


\columnbreak

___
> ## Deer
>*Medium beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 4 (1d8)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|11 (+0)|16 (+3)|11 (+0)|2 (-4)|14 (+2)|5 (-3)|
>___
> - **Senses** passive Perception 12
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ### Actions
>
> ***Bite.*** *Melee Weapon Attack:* +2 to hit, reach 5 ft., one target. *Hit:* 2 (1d4) piercing damage.

___
> ## Dire Wolf
>*Large beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 37 (5d10 + 10)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|15 (+2)|15 (+2)|3 (-4)|12 (+1)|7 (-2)|
>___
> - **Skills** Perception +3, Stealth +4
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1 (200 XP)
>___
> ***Keen Hearing and Smell.*** The wolf has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Pack Tactics.*** The wolf has advantage on an attack roll against a creature if at least one of the wolf's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ### Actions
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) piercing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.

A **dire wolf** has much in common with its smaller, more common counterpart; the two look alike, but dire wolves are nearly twice the size. Their massive jaws look like they could snap iron bars, and orcs have long favoured them over other mounts for their cunning and strength.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/BsqNNL3.png" style="position:absolute;bottom: -25px;left: -45px;width: 450px;">

\pagebreakNum


___
> ## Eagle
>*Small beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 3 (1d6)
> - **Speed** 10 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|6 (-2)|15 (+2)|10 (+0)|2 (-4)|14 (+2)|7 (-2)|
>___
> - **Skills** perception +4
> - **Senses** passive Perception 14
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> ***Keen Sight.*** The eagle has advantage on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
>
> ***Talons.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) slashing damage.

___
> ## Fox
>*Small beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 9 (2d6 + 2)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|10 (+0)|15 (+2)|12 (+1)|3 (-4)|13 (+1)|6 (-2)|
>___
> - **Skills** Perception +3, Stealth  +4
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
>
> ***Keen Hearing and Smell.*** The fox has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Nimble Escape.*** The fox can take the Disengage or Hide action as a bonus action on each of its turns.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.

\columnbreak

___
> ## Forest Spider
>*Small beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 7 (2d6)
> - **Speed** 20 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|14 (+2)|10 (+0)|2 (-4)|10 (+0)|4 (-3)|
>___
> - **Skills** Stealth +4
> - **Senses** darkvision 30 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
> ***Spider Climb.*** The spider can climb difficult surfaces, including upside down on ceilings, without needing to make an ability check.
>
> ***Web Sense.*** While in contact with a web, the spider knows the exact location of any other creature in contact with the same web.
>
> ***Web Walker.*** The spider ignores movement restrictions caused by webbing.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 4 (1d4+2) piercing damage, and the target must succeed on a DC 10 Constitution saving throw or take 2 (1d4) poison damage.



<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/zxp4HSp.png" class="inkblot inkblot-green" style="top: 361px;left: 20px;width: 820px;transform: rotate(39deg);">
<img src="https://i.imgur.com/DpcTgA2.png" style="position:absolute;bottom: 60px;right: 42px;width: 850px;">


\pagebreakNum


___
> ## Frenzyfish
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 1 (1d4 - 1)
> - **Speed** swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|2 (-4)|16 (+3)|9 (-1)|1 (-5)|7 (-2)|2 (-4)|
>___
> - **Senses** darkvision 60 ft.
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ***Blood Frenzy.*** The frenzyfish has advantage on melee attacks against any creature that doesn't have all its hit points.
>
> ***Water Breathing.*** The frenzyfish can breathe only underwater.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 1 piercing damage.

The **frenzyfish** are large, swarm-hunting predatory fish that can be far and wide across Azeroth, with different types well-adapted to different climates. Some prefer the warmer climates of southern Kalimdor and Eastern Kingdoms, while others thrive even in the frozen waters of Northrend.


\columnbreak

___
> ## Giant Bat
>*Large beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 22 (4d10)
> - **Speed** 10 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|16 (+3)|11 (+0)|2 (-4)|12 (+1)|6 (-2)|
>___
> - **Senses** blindsight 60ft., passive Perception 11
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
>
> ***Echolocation.*** The bat can't use its blindsight while deafened.
>
> ***Keen Hearing.*** The bat has advantage on Wisdom (Perception) checks that rely on hearing.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 5 (1d6 + 2) piercing damage.

___
> ## Giant Boar
>*Large beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 42 (5d10 + 15)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|10 (+0)|16 (+3)|2 (-4)|7 (-2)|5 (-3)|
>___
> - **Senses** passive Perception 8
> - **Languages** —
> - **Challenge** 2 (450 XP)
> ___
>
> ***Charge.*** If the boar moves at least 20 feet straight toward a target and then hits it with a tusk attack on the same turn, the target takes an extra 7 (2d6) slashing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ***Relentless (Recharges after a Short or Long Rest).*** If the boar takes 10 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ### Actions
> ***Tusk.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/R7wbd4k.png" class="inkblot inkblot-green" style="top: 411px;left: 80px;width: 650px;transform: rotate(100deg);">
<img src="https://i.imgur.com/QUUIyc6.png" style="position:absolute;bottom: 48px;left: 20px;width: 520px;">


\pagebreakNum

___
> ## Giant Crab
>*Medium beast, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 13 (3d8)
> - **Speed** 30 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|15 (+2)|11 (+0)|1 (-5)|9 (-1)|3 (-4)|
>___
> - **Skills** Stealth +4
> - **Senses** blindsight 30 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
>
> ***Amphibious.*** The crab can breathe air and water.
>
> ### Actions
> ***Claw.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) bludgeoning damage, and the target is grappled (escape DC 11). The crap has two claws, each of which can grapple only one target.

___
> ## Giant Eagle
>*Large beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 26 (4d10 + 4)
> - **Speed** 10 ft., fly 80 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|17 (+3)|13 (+1)|8 (-1)|14 (+2)|10 (+0)|
>___
> - **Skills** perception +4
> - **Senses** passive Perception 14
> - **Languages** understands at least one language but cannot speak
> - **Challenge** 1 (200 XP)
> ___
>
> ***Keen Sight.*** The eagle has advantage on Wisdom (Perception) checks that rely on sight.
>
> ### Actions
> ***Multiattack.*** The eagle makes two attacks: one with its beak and one with its talons.
>
> ***Beak.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) piercing damage.
>
> ***Talons.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) slashing damage.


\columnbreak

___
> ## Giant Moth
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 16 (3d8 + 3)
> - **Speed** 10 ft., fly 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|9 (-1)|14 (+2)|12 (+1)|3 (-4)|10 (+0)|4 (-3)|
>___
> - **Senses** blindsight 30 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
> ***Keen Smell.*** The moth has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage.
>
> ***Pulverulent Wings (1/day).*** A cloud of thick powder disperses out from the moth in a 15-foot radius. Each creature in that area must make a DC 12 Constitution saving throw, or be blinded until the end of the moth's next turn on a failed save.

___
> ## Giant Owl
>*Large beast, neutral*
> ___
> - **Armor Class** 12
> - **Hit Points** 19 (3d10 + 3)
> - **Speed** 5 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|15 (+2)|12 (+1)|8 (-1)|13 (+1)|10 (+0)|
>___
> - **Skills** Perception +5, Stealth +4
> - **Senses** darkvision 120 ft., passive Perception 15
> - **Languages** Giant Owl, understands one other language but can't speak it
> - **Challenge** 1/4 (50 XP)
> ___
>
> ***Flyby.*** The owl doesn't provoke opportunity attacks when it flies out of an enemy's reach.
>
> ***Keen Hearing and Sight.*** The owl has advantage on Wisdom (Perception) checks that rely on hearing or sight.
>
> ### Actions
> ***Talons.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 8 (2d6 + 1) slashing damage.


\pagebreakNum

___
> ## Giant Scorpid
>*Large beast, unaligned*
> ___
> - **Armor Class** 15 (natural armor)
> - **Hit Points** 52 (7d10 + 14)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|13 (+1)|15 (+2)|4 (-3)|9 (-1)|3 (-4)|
>___
> - **Senses** blindsight 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
>
> ### Actions
> ***Multiattack.*** The scorpid makes three attacks: two with its claws and one with its sting.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) bludgeoning damage, and the target is grappled (escape DC 12). The scorpion has two claws, each of which can grapple only one target.
>
> ***Sting.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 7 (1d10 + 2) piercing damage, and the target must make a DC 12 Constitution saving throw, taking 22 (4d10) poison damage on a failed save, or half as much on a successful one.

___
> ## Giant Shark
>*Huge beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 126 (11d12 + 55)
> - **Speed** 0 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|23 (+6)|11 (+0)|21 (+5)|1 (-5)|10 (+0)|5 (-3)|
>___
> - **Skills** Perception +3
> - **Senses** blindsight 60 ft., passive Perception 13
> - **Languages** –
> - **Challenge** 5 (1,800 XP)
> ___
>
> ***Blood Frenzy.*** The shark has advantage on melee attack rolls against any creature that doesn't have all its hit points.
>
> ***Water Breathing.*** The shark can breathe only underwater.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +9 to hit, reach 5 ft., one target. *Hit:* 22 (3d10 + 6) piercing damage.

\columnbreak


> I want a note here about Giant creatures and Azeroth here, if there is anything that could work. And a page tear with something suitably cool. Basically a half page tear fitting the last page and a half of statblocks.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/ssCX3kD.jpg" style="position: absolute;top: 0;right: -205px;width: 840px;">

<img src="https://i.imgur.com/7drSEMn.png" style="position:absolute;top: 0;right: 0px;width: 870px;">




\pagebreakNum

___
> ## Giant Spider
>*Large beast, unaligned*
> ___
> - **Armor Class** 14 (natural armor)
> - **Hit Points** 26 (4d10 + 4)
> - **Speed** 30 ft., climb 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|16 (+3)|12 (+1)|2 (-4)|11 (+0)|4 (-3)|
>___
> - **Skills** Stealth +7
> - **Senses** blindsight 10 ft., darkvision 60 ft., <br>passive Perception 10
> - **Languages** —
> - **Challenge** 1  (200 XP)
> ___
> ***Spider Climb.*** The spider can climb difficult surfaces, including upside down on ceilings, without needing to make an ability check.
>
> ***Web Sense.*** While in contact with a web, the spider knows the exact location of any other creature in contact with the same web.
>
> ***Web Walker.*** The spider ignores movement restrictions caused by webbing.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 7 (1d8 + 3) piercing damage, and the target must make a DC 11 Constitution saving throw, taking 3 (1d6) poison damage on a failed save, or half as much damage on a successful one. If the poison damage reduces the target to 0 hit points, the target is stable but poisoned for 1 hour, even after regaining hit points, and is paralyzed while poisoned in this way.
>
> ***Web (Recharge 5-6}.*** *Ranged Weapon Attack:* +5 to hit, range 30/60 ft., one creature. *Hit:* The target is then restrained by webbing. As an action, the restrained target can make a DC 12 Strength check, bursting the webbing on a success. The webbing can also be attacked and destroyed (AC 10; hp 5; vulnerability to fire damage; immunity to bludgeoning, poison, and psychic damage).


\columnbreak


> ##### Variant: Giant Deathweb Spider
> A deathweb spider has a challenge rating of 2 (450 XP). It has the same statistics as a giant spider except that it has Constitution 14, 37 (5d10 + 10) hit points, and replaces the giant spider's bite action option with the following actions. Additionally, the spider's web deals 9 (2d8) acid damage to a creature restrained by it at the beginning of the creatures turn.
>
> ***Infected Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one creature. *Hit:* 12 (2d8 + 3) piercing damage plus 3 (1d6) acid damage.
>
> ***Burning Acid (Recharge after a Short or Long rest).*** The spider spews forth a burning hot acid. Each creature in a 10-foot cone must make a DC 12 Dexterity saving throw, taking 13 (3d8) fire damage on a failed save, or half as much on a success.

___
> ## Giraffe
>*Huge beast, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 34 (4d12 + 8)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|12 (+1)|14 (+2)|2 (-4)|13 (+1)|7 (-2)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
>
> ***Keen Sight.*** The giraffe has advantage on Wisdom (Perception) checks that rely on sight.
>
> ***Charge.*** If the giraffe moves at least 20 ft. straight toward a target and then hits it with a hooves attack on the same turn, the target takes an extra 9 (2d8) bludgeoning damage. If the target is a creature, it must succeed on a DC 15 Strength saving throw or be knocked prone.
>
> ### Actions
> ***Hooves.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) bludgeoning damage.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/YmzkuLc.jpg" style="position: absolute;bottom: -60px;right: -10px;width: 900px;">

<img src="https://i.imgur.com/NO1EQoX.png" style="position:absolute;top: -20px;right:0px;width:800px;transform: scale(-1);">

\pagebreakNum


___
> ## Hawkstrider
>*Large beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 11 (2d10)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|15 (+2)|10 (+0)|3 (-4)|11 (+0)|7 (-2)|
>___
> - **Skills** Athletics +3, Acrobatics +4, Perception +2
> - **Senses** passive Perception 12
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
> ***Swift Stride.*** The hawkstrider can use a bonus action to take the Dash action.
>
> ### Actions
> ***Beak.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 3) piercing damage.
>
> ***Shriek (Recharge 6).*** The hawkstrider emits a horrific screech. Each creature within 20 feet of it that can hear it and that isn't a hawkstrider must succeed on a DC 13 Constitution saving throw or be incapaci&shy;tated until the end of the hawkstriders's next turn.

A **hawkstrider** is a large, flightless bird, indigenous to the forests of Quel'Thalas. Known for their bright, vibrant plumage and uncanny intelligence, these graceful creatures have long been a symbol of Silvermoon.


\columnbreak

___
> ## Hunter Shark
>*Large beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 45 (6d10 + 12)
> - **Speed** 0 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|18 (+4)|13 (+1)|15 (+2)|1 (-5)|10 (+0)|4 (-3)|
>___
> - **Skills** Perception +2
> - **Senses** blindsight 30 ft., passive Perception 12
> - **Languages** –
> - **Challenge** 2 (450 XP)
> ___
>
> ***Blood Frenzy.*** The shark has advantage on melee attack rolls against any creature that doesn't have all its hit points.
>
> ***Water Breathing.*** The shark can breathe only underwater.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +6 to hit, reach 5 ft., one target. *Hit:* 13 (2d8 + 4) piercing damage.

___
> ## Hyena
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 16 (3d8 + 3)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|14 (+2)|12 (+1)|2 (-4)|12 (+1)|5 (-3)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Pack Tactics.*** The hyena has advantage on an attack roll against a creature if at least one of the hyena's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ### Actions
> ***Multiattack***. The hyena makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 4 (1d4 + 2) piercing damage.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/Sjc9IFl.png" class="inkblot inkblot-green" style="bottom: -170px;left: -80px;width: 800px;transform: rotate(190deg);">
<img src="https://i.imgur.com/2Q5o3SA.png" style="position:absolute;bottom: -12px;left: 0px;width: 490px;">


\pagebreakNum

___
> ## Hyena Matriarch
>*Medium beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 27 (5d8 + 5)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|16 (+3)|13 (+1)|4 (-3)|12 (+1)|7 (-2)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
>
> ***Pack Tactics.*** The hyena has advantage on an attack roll against a creature if at least one of the hyena's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Rampage.*** When the hyena reduces a creature to 0 hit points with a melee attack on its turn, the hyena can take a bonus action to move up to half its speed and make a bite attack.
>
> ***Leadership.*** Once per turn, the hyena can let out a cry when a friendly hyena that it can see within 10 feet of it makes an attack roll. The hyena can add a d4 to its roll provided it can hear the cry. A creature can benefit from only one Leadership die at a time.
>
> ### Actions
> ***Multiattack***. The hyena makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 7 (2d4 + 2) piercing damage.

Hyenas are scavengers who thrive in the most barren reaches of Kalimdor and Zandalar &mdash; from Desolace and the Barrens, out across the dunes of Tanaris and Vol'dun. 

Azerothian hyenas keep keep together in large clans, with most following the call of their **matriarch**; the clan's strongest and most cunning female member, whose rallying cry can quickly rouse her kin to action.


\columnbreak

___
> ## Lion
>*Large beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 26 (4d10 + 4)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|15 (+2)|13 (+1)|3 (-4)|12 (+1)|8 (-1)|
>___
> - **Skills** Perception +3, Stealth +6
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
>
> ***Keen Smell.*** The lion has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pack Tactics.*** The lion has advantage on an attack roll against a creature if at least one of the lion's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Pounce.*** If the lion moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone. If the target is prone, the lion can make one bite attack against it as a bonus action.
>
> ***Running Leap.*** With a 10-foot running start, the lion can jump up to 25 feet.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) slashing damage.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://www.gmbinder.com/images/CRqcfac.png" class="inkblot inkblot-green" style="top: 600px;right: 20px;width: 740px;transform: rotate(-135deg);">
<img src="https://i.imgur.com/RRwI4sS.png" style="position:absolute; bottom:0; right:0px; width:540px;">

\pagebreakNum

___
> ## Lion Pridemane
>*Large beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 52 (7d10 + 14)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|17 (+3)|15 (+2)|14 (+2)|3 (-4)|13 (+1)|10 (+0)|
>___
> - **Skills** Perception +3, Stealth +6
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 3 (700 XP)
> ___
>
> ***Keen Smell.*** The lion has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pack Tactics.*** The lion has advantage on an attack roll against a creature if at least one of the lion's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Pounce.*** If the lion moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone. If the target is prone, the lion can make one bite attack against it as a bonus action.
>
> ***Running Leap.*** With a 10-foot running start, the lion can jump up to 25 feet.
>
> ### Actions
> ***Multiattack.*** The lion makes three attacks: one with its bite and two with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) slashing damage.
>
> ***Terrifying Roar.*** Each creature within 30 ft. of the lion that can hear it must succeed on a DC 13 Wisdom saving throw or be frightened for 1 minute. A frightened target can repeat the saving throw at the end of each of its turns, ending the frightened on itself on a success. If a target's saving throw is successful or the effect ends for it, the target is immune to the lion's Terrifying Roar for the next 24 hours.

Lions roam far and wide across central Kalimdor, stalking the tall grass in small packs -- their prides. They are not at all shy for what prey they hunt, and have at times been known to even stalk unwary travellers. 

Chief among them is the **pridemane**; the pride's leading male, who towers high above the rest with its imposing stature and massive mane.

\columnbreak

___
> ## Lizard
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 10
> - **Hit Points** 2 (1d4)
> - **Speed** 20 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|2 (-4)|11 (+0)|10 (+0)|1 (-5)|8 (-1)|3 (-4)|
>___
> - **Senses** darkvision 30 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +0 to hit, reach 5 ft., one target. *Hit:* 1 piercing damage.

___
> ## Mountain Lion
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 18 (4d8)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|15 (+2)|11 (+0)|3 (-4)|12 (+1)|7 (-1)|
>___
> - **Skills** Perception +3, Stealth +4
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Keen Smell.*** The lion has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Pounce.*** If the lion moves at least 20 feet straight toward a creature and then hits it with a claw attack on the same turn, that target must succeed on a DC 12 Strength saving throw or be knocked prone. If the target is prone, the lion can make one bite attack against it as a bonus action.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage.
>
> ***Claw.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 5 (1d6 + 2) slashing damage.

More commonplace across Azeroth than lions is the **mountain lion**, found both along the lush plains of Mulgore and up the grassy foothills of Hillsbrad.



<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

\pagebreakNum


___
> ## Moose
>*Large beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 30 (4d10 + 8)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|10 (+0)|15 (+2)|2 (-4)|10 (+0)|6 (-2)|
>___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
>
> ***Charge.*** If the moose moves at least 20 feet straight toward a target and then hits it with a ram on the same turn, the target takes an extra 7 (2d6) damage. If the target is a creature, the target must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ***Relentless (Recharges after a Short or Long Rest).*** If the moose takes 7 damage or less that would reduce it to 0 hit points, it is reduced to 1 hit point instead.
>
> ### Actions
> ***Ram.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 7 (1d8 + 3) bludgeoning damage.
>
> ***Hooves.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (2d4 + 3) bludgeoning damage.

Also known as elderhorn, the great **moose** of Azeroth are lumbering beasts recognized by the characteristic shape of their massive antlers. They are favored animals among the Highmountain tauren, and some herds make their home within druidic groves -- where they grow a particular kind of kinship with the grove's residing druids.

\columnbreak

___
> ## Octopus
>*Small beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 3 (1d6)
> - **Speed** 5 ft., swim 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|4 (-3)|15 (+2)|11 (+0)|3 (-4)|10 (+0)|4 (-3)|
>___
> - **Skills** Perception +2, Stealth +4
> - **Senses** darkvision 30 ft., passive Perception 12
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> 
> ***Hold Breath.*** While out of water, the octopus can hold its breath for 30 minutes.
>
> ***Underwater Camouflage.*** The octopus has advantage on Dexterity (Stealth) checks made while underwater.
> 
> ***Water Breathing.*** The octopus can breathe only underwater.
>
> ### Actions
> ***Tentacles.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. Hit: 1 bludgeoning damage, and the target is grappled (escape DC 10). Until this grapple ends, the octopus can't use its tentacles on another target.
> 
> ***Ink Cloud (Recharges after a Short or Long Rest).*** A 5-foot-radius cloud of ink extends all around the octopus if it is underwater. The area is heavily obscured for 1 minute, although a significant current can disperse the ink. After releasing the ink, the octopus can use the Dash action as a bonus action.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>


<img src="https://i.imgur.com/PMfzlNn.jpg" style="position:absolute;bottom: 0px;right: 0px;width: 910px;">
<img src="https://i.imgur.com/MVDaLa2.png" style="position:absolute;top: 0px;right:0px;width: 820px;transform: scaleX(-1);">
<img src="https://i.imgur.com/RUukMlL.png" style="position:absolute;bottom: 5px;right: 45px;width: 435px;">

\pagebreakNum


___
> ## Owl
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 1 (1d4 - 1)
> - **Speed** 5 ft., fly 60 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|3 (-4)|13 (+1)|8 (-1)|2 (-4)|12 (+1)|7 (-2)|
>___
> - **Skills** Perception +3, Stealth +3
> - **Senses** darkvision 120 ft., passive Perception 13
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ***Flyby.*** The owl doesn't provoke opportunity attacks when it flies out of an enemy's reach.
>
> ***Keen Hearing and Sight.*** The owl has advantage on Wisdom (Perception) checks that rely on hearing or sight.
>
> ### Actions
> ***Talons.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 1 slashing damage.


\columnbreak


___
> ## Polar Bear
>*Large beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 42 (5d10 + 15)
> - **Speed** 40 ft., climb 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|20 (+5)|10 (+0)|16 (+3)|2 (-4)|13 (+1)|7 (-2)|
>___
> - **Skills** Perception +3
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 2 (450 XP)
> ___
>
> ***Keen Smell.*** The bear has advantage on Wisdom (Perception) checks that rely on smell.
>
> ### Actions
> ***Multiattack.*** The bear makes two attacks: one with its bite and one with its claws.
>
> ***Bite.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 9 (1d8 + 5) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +7 to hit, reach 5 ft., one target. *Hit:* 12 (2d6 + 5) slashing damage.

___
> ## Reef Shark
>*Medium beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 22 (4d8 + 4)
> - **Speed** 0 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|13 (+1)|13 (+1)|1 (-5)|10 (+0)|4 (-3)|
>___
> - **Skills** Perception +2
> - **Senses** blindsight 30 ft., passive Perception 12
> - **Languages** –
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Pack Tactics.*** The shark has advantage on an attack roll against a creature if at least one of the shark's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ***Water Breathing.*** The shark can breathe only underwater.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/0hVRLNf.png" class="inkblot inkblot-green" style="bottom: -225px;left: -180px;width: 820px;transform: rotate(330deg) scaleX(-1);">
<img src="https://i.imgur.com/BecGt0i.png" style="position:absolute;bottom: -65px;left: 35px;width: 350px;">

\pagebreakNum


___
> ## Scorpid
>*Small beast, unaligned*
> ___
> - **Armor Class** 12 (natural armor)
> - **Hit Points** 13 (3d6 + 3)
> - **Speed** 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|8 (-1)|13 (+1)|12 (+1)|1 (-5)|8 (-1)|2 (-4)|
>___
> - **Senses** blindsight 60 ft., passive Perception 9
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
>
> ### Actions
> ***Sting.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) piercing damage, and the target must make a DC 9 Constitution saving throw, taking 4 (1d8) poison damage on a failed save, or half as much on a successful one.

A **scorpid** is a quick and vicious predator, commonly found in dry and arid parts of Azeroth -- from the Barrens to Tanaris, and from the Badlands to the Burning Steppes. 

They are kin to scorpions, though scorpids are far larger and far, far deadlier. it is said that the venom of an adult scorpid's stinger holds enough venom to kill beasts a hundred times its size.

___
> ## Sea Horse
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 1 (1d4-1)
> - **Speed** 0 ft., swim 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|1 (-5)|12 (+1)|8 (-1)|1 (-5)|10 (+0)|2 (-4)|
>___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ***Water Breathing.*** The sea horse can breathe only underwater.

\columnbreak

___
> ## Skywisp Moth
>*Small beast, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 3 (1d6)
> - **Speed** 10 ft., 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|5 (-3)|12 (+1)|10 (+0)|3 (-4)|11 (+0)|4 (-3)|
>___
> - **Senses** blindsight 30 ft., passive Perception
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
> ***Keen Smell.*** The moth has advantage on Wisdom (Perception) checks that rely on smell.
>
> ***Arcane Interference.*** When a spell is cast within a 10-foot radius of the moth, roll a d20. On a roll of 1, the spell is interrupted as if by the *counterspell* spell.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) piercing damage.
>
> ***Pulverulent Wings (1/day).*** A cloud of thick powder disperses out from the moth in a 5-foot radius. Each creature in that area must make on a DC 11 Constitution saving throw, or be blinded until the end of the moth's next turn on a failed save.

A **skywisp moth** is considered a docile, insignificant beast to most. Among arcane practicioners, however, they have a notorious reputation for their curiosity and their uncanny ability to interfere with spells cast in their vicinity.

Because of this, they are often a favoured companion for any hunters whose quarry is a dangerous spellcaster.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/a81VyUK.png" class="inkblot inkblot-green" style="bottom: -385px;left: -70px;width: 740px;transform: rotate(-150deg) scaleX(-1);">
<img src="https://i.imgur.com/kLKYzA0.png" style="position:absolute;bottom: -65px;right: -65px;width: 745px;">


\pagebreakNum

___
> ## Spider
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 12
> - **Hit Points** 1 (1d4-1)
> - **Speed** 20 ft., climb 20 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|2 (-4)|14 (+2)|8 (-1)|1 (-5)|10 (+0)|2 (-4)|
>___
> - **Skills** Stealth +4
> - **Senses** darkvision 30 ft., passive Perception 10
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
> ***Spider Climb.*** The spider can climb difficult surfaces, including upside down on ceilings, without needing to make an ability check.
>
> ***Web Sense.*** While in contact with a web, the spider knows the exact location of any other creature in contact with the same web.
>
> ***Web Walker.*** The spider ignores movement restrictions caused by webbing.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one creature. *Hit:* 1 piercing damage, and the target must succeed on a DC 9 Constitution saving throw or take 2 (1d4) poison damage.

___
> ## Stag
>*Large beast, unaligned*
> ___
> - **Armor Class** 10
> - **Hit Points** 13 (2d10 + 2)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|10 (+0)|12 (+1)|2 (-4)|10 (+0)|6 (-2)|
>___
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
>
> ***Charge.*** If the stag moves at least 20 feet straight toward a target and then hits it with a ram on the same turn, the target takes an extra 7 (2d6) damage. If the target is a creature, the target must succeed on a DC 13 Strength saving throw or be knocked prone.
>
> ### Actions
> ***Ram.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d6 + 3) bludgeoning damage.
>
> ***Hooves.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 8 (2d4 + 3) bludgeoning damage.


\columnbreak

___
> ## Swarm of Frenzyfish
>*Medium swarm, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 28 (8d8 - 8)
> - **Speed** swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|13 (+1)|16 (+3)|9 (-1)|1 (-5)|7 (-2)|2 (-4)|
>___
> - **Damage Resistances** bludgeoning, piercing, slashing
> - **Condition Immunities** charmed, frightened, grappled, paralyzed, petrified, prone, restrained, stunned
> - **Senses** darkvision 60 ft.
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
>
> ***Blood Frenzy.*** The quipper has advantage on melee attacks against any creature that doesn't have all its hit points.
>
> ***Swarm.*** The swarm can occupy another creature's space and vice versa, and the swarm can move through any opening large enough for a Tiny frenzyfish. The swarm can't regain hit points or gain temporary hit points.
>
> ***Water Breathing.*** The swarm can breathe only underwater.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 0 ft., one creature in the swarm's space. *Hit:* 14 (4d6) piercing damage, or 7 (2d6) piercing damage if the swarm has half of its hit points or fewer.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/pRTJEf1.jpg" style="position:absolute; right: -70px; bottom: 0px; width: 700px;">
<img src='https://i.imgur.com/VdV67Oz.png' style='position:absolute; right:0px; bottom:0px; width:850px' />

\pagebreakNum



___
> ## Tallstrider
>*Medium beast, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 9 (2d8)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|13 (+1)|10 (+0)|4 (-3)|10 (+0)|6 (-2)|
>___
> - **Skills** Athletics +3
> - **Senses** passive Perception 10
> - **Languages** —
> - **Challenge** 1/8 (25 XP)
> ___
>
> ### Actions
> ***Beak.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 3 (1d4 + 1) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +3 to hit, reach 5 ft., one target. *Hit:* 4 (1d6 + 1) slashing damage.

**Tallstriders** are large, flightless birds, native to the plains and savannahs of central Kalimdor. There is a very clear and stubborn pride to the tallstriders, making them near impossible to domesticate and useless as beasts of burden.

Some skilled hunters and beast-handlers have mastered the art of taming a tallstrider, however. For them, the birds' strength and speed make them excellent companions for any sudden skirmish.


\columnbreak

___
> ## Towering Tallstrider
>*Large beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 22 (4d10)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|14 (+2)|16 (+3)|10 (+0)|4 (-3)|11 (+0)|6 (-2)|
>___
> - **Skills** Athletics +4, Perception +2
> - **Senses** passive Perception 12
> - **Languages** —
> - **Challenge** 1 (200 XP)
> ___
> ***Trampling Charge.*** If the tallstrider moves at least 20 feet straight toward a creature and then hits it with a beak attack on the same turn, that target must succeed on a DC 12 Strength saving throw or be knocked prone. If the target is prone, the tallstrider can make another attack with its claws against it as a bonus action.
>
> ### Actions
> ***Beak.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 8 (1d12 + 2) piercing damage.
>
> ***Claws.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 9 (2d6 + 2) slashing damage.

___
> ## Turtle
>*Medium beast, unaligned*
> ___
> - **Armor Class** 16 (natural armor)
> - **Hit Points** 30 (4d8 + 12)
> - **Speed** 10 ft., swim 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|15 (+2)|10 (+0)|16 (+3)|4 (-3)|11 (+0)|6 (-2)|
>___
> - **Senses** darkvision 60 ft
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Amphibious.*** The turtle can breathe air and water.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 6 (1d8 + 2) piercing damage.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src="https://i.imgur.com/BrDcy46.png" class="inkblot inkblot-green" style="bottom: -295px;left: -130px;width: 850px;transform: rotate(-270deg);">
<img src="https://i.imgur.com/IrV9Ez8.png" style="position:absolute; left: 50px; bottom: -180px; width: 430px;">


\pagebreakNum


___
> ## Weasel
>*Tiny beast, unaligned*
> ___
> - **Armor Class** 13
> - **Hit Points** 1 (1d4-1)
> - **Speed** 30 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|3 (-4)|16 (+3)|8 (-1)|2 (-4)|12 (+1)|3 (-4)|
>___
> - *Skills** Perception +3, Stealth +5
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 0 (10 XP)
> ___
>
> ***Keen Hearing and Smell.*** The weasel has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 1 piercing damage.

___
> ## Wolf
>*Medium beast, unaligned*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 11 (2d8 + 2)
> - **Speed** 40 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|12 (+1)|15 (+2)|12 (+1)|3 (-4)|12 (+1)|6 (-2)|
>___
> - **Skills** Perception +3, Stealth +4
> - **Senses** passive Perception 13
> - **Languages** —
> - **Challenge** 1/4 (50 XP)
> ___
>
> ***Keen Hearing and Smell.*** The wolf has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ***Pack Tactics.*** The wolf has advantage on attack rolls against a creature if at least one of the wolf's allies is within 5 feet of the creature and the ally isn't incapacitated.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +4 to hit, reach 5 ft., one target. *Hit:* 7 (2d4 + 2) piercing damage. If the target is a creature, it must succeed on a DC 11 Strength saving throw or be knocked prone.


\columnbreak

___
> ## Worg
>*Large monstrosity, neutral evil*
> ___
> - **Armor Class** 13 (natural armor)
> - **Hit Points** 26 (4d10 + 4)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|13 (+1)|13 (+1)|7 (-2)|11 (+0)|8 (-1)|
>___
> - **Skills** Perception +4
> - **Senses** darkvision 60 ft., passive Perception 14
> - **Languages** Worg, understands one other language but can't speak it
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Keen Hearing and Smell.*** The worg has advantage on Wisdom (Perception) checks that rely on hearing or smell.
>
> ### Actions
> ***Bite.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d6 + 3) piercing damage. If the target is a creature, it must succeed on a DC 13 Strength saving throw or be knocked prone.


<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

\pagebreakNum


___
> ## Zhevra
>*Large beast, unaligned*
> ___
> - **Armor Class** 11
> - **Hit Points** 13 (2d10 + 2)
> - **Speed** 50 ft.
>___
>|STR|DEX|CON|INT|WIS|CHA|
>|:---:|:---:|:---:|:---:|:---:|:---:|
>|16 (+3)|12 (+1)|13 (+1)|2 (-4)|12 (+1)|7 (-2)|
>___
> - **Senses** passive Perception 11
> - **Languages** —
> - **Challenge** 1/2 (100 XP)
> ___
>
> ***Trampling Charge.*** If the zhevra moves at least 20 feet straight toward a creature and then hits it with a horn attack on the same turn, that target must succeed on a DC 13 Strength saving throw or be knocked prone. If the target is prone, the zhevra can make one attack with its hooves against it as a bonus action.
>
> ### Actions
> ***Hooves.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (2d4 + 3) piercing damage.
>
> ***Horn.*** *Melee Weapon Attack:* +5 to hit, reach 5 ft., one target. *Hit:* 10 (1d8 + 3) piercing damage.

A **zhevra** resembles a large, striped horse with a horn piercing through its forehead, similar to that of a unicorn. Though they might seem threatening, they are usually very passive beasts; remarkably easy to frighten. They move together in herds, keeping close for their own protection.

<div class='footnote'>APP. A: MISCELLANEOUS CREATURES </div>

<img src='https://www.gmbinder.com/images/CRqcfac.png' class='inkblot inkblot-green' style='top:550px; right:-220px; width:700px'>
<img src='https://www.gmbinder.com/images/4TyqQuB.png' style='position:absolute; top:600px; right:-75px; width:500px' />

\pagebreakNum

## Appendix A Art Credits

<div style='margin-top:-14px;'></div>

<br />**Dwarf Hunter with Bear** by [Miao Zi](https://www.reddit.com/r/Art/comments/5db5gv/dwarf_hunter_with_bear_by_miao_zi_2560_1600_2015/)
<br />**River Crocolisk** by [Daren Bader](https://hearthstone.fandom.com/wiki/River_Crocolisk)
<br />**Phase Hound** by [Lars Grant-West](https://wowpedia.fandom.com/wiki/Phase_Hound_(Blood_of_Gladiators))
<br />**Fox Render** from World of Warcraft
<br />**Frenzyfish Renders** from World of Warcraft
<br />**Wasteland Scorpid** by [Mauricio Herrera](https://hearthstone.fandom.com/wiki/Wasteland_Scorpid)
<br />**Tomb Spider** by [Turovec Konstantin](https://hearthstone.fandom.com/wiki/Tomb_Spider)
<br />**Swift Hawkstrider** by [Tyler Walpole](https://hearthstone.fandom.com/wiki/Battle_Hawkstrider)
<br />**Hyena Alpha** by [Peter Stapleton](https://hearthstone.fandom.com/wiki/Hyena_Alpha)
<br />**Elderhorn Render** from World of Warcraft
<br />**Highmountain Scenery** from World of Warcraft
<br />**Owl Render** from World of Warcraft
<br />**Ardenweald Moth** by [Natacha Nielsen](https://www.artstation.com/artwork/rAPxKE)
<br />**Brood Mother** by [Arthur Gimaldinov](https://www.artstation.com/artwork/2BNKa)


\pagebreakNum


<style>

/* BACK PAGE STYLES */

  /* Remove footer from back page, replace pX with last page number */
  .phb#p13:after { display:none; }

  .phb .back-cover-content {
    padding-left: 4px;
    padding-right: 16px;
  }
  .phb .back-cover-header p {
    line-height: 76px;
  }
  .phb .back-cover-right {
      padding-left: 40px;
  }
  .phb .back-cover-image {
    height: 1136px;
    left: -20px;
    top: -10px;
    width: 475px;
    background-size: 475px 1136px;
  }
  .phb .back-cover-diamond {
    display: block;
    position: initial;
    left: initial;
    top: initial;
    margin: auto;
    margin-bottom: 35px;
    box-sizing: border-box;
    background-repeat: no-repeat;
  }
 .phb .back-cover-logo-container {
    position: absolute;
    bottom: 30px;
    left: 64px;
    width: 314px;
 }
 .phb .back-cover-logo,
 .phb .back-cover-logo-link {
     position: initial;
     margin: auto;
     margin-bottom: 8px;
     left: initial;
     bottom: initial;
     right: initial;
     background-repeat: no-repeat;
 }
 
 </style>
 
 <img src='https://www.gmbinder.com/images/03TEaX0.jpg' style='position:absolute; top:0px; right:-300px; width:860px' />
 
 <div class='back-cover-image'></div>
 
 <div style='margin-top:20px;'></div>
 
 <div class='back-cover-header'>
 
 Warcraft
 
 5th Edition
 
 </div>
 
<div class='back-cover-text'>
 
  *WC5E Manual of Monsters v3*
 
  This document is part of the third major revision of our *Warcraft 5th Edition* project; a collection of player classes, races, backgrou&shy;nds, creature statblocks, and more to put a Warcraft spin on core Dungeons & Dragons material.
  
  We're a cozy little gang of people having fun writing this material in our spare time, and are always looking for people to join us, chat with us, and tell us what they think. If you'd like to do just that, this is where you can find us:
  
  [Our project on Github](https://github.com/WC5E/Warcraft-5e-Conversion/) <br />
  [Our community on Reddit](https://www.reddit.com/r/wc5e/) <br />
  [Our community on Discord](https://discord.com/invite/dKMJmmD)
  
</div>
 
<div class='back-cover-diamond' style='top: 679px;'></div>
 
<div style='margin-top:35px;'></div>
 
<div class='back-cover-close'>

  Big love from the team. ❤

   
</div>

<div class='back-cover-logo-container'>
 
  <div class='back-cover-logo'></div>
 
  <div class='back-cover-logo-link'>
 
  [WWW.GMBINDER.COM](https://www.gmbinder.com)
 
  </div>

</div>
 
 \columnbreak
 

<div class='back-cover-right'>

</div>