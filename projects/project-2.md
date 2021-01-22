---
layout: project
type: project
image: images/anki.jpg
title: Epub Kanji Frequency Tool
permalink: projects/kanji
# All dates must be YYYY-MM-DD format!
date: 2020-08-01
labels:
  - Rust
  - Anki
summary: A small application for converting an Epub file into a list of kanji, sorted by frequency. 
---

<img class="ui medium right floated rounded image" src="../images/anki.jpg">

The Kanji frequency tool is a small application I wrote around the middle of 2020, in Rust.  

The intention of this tool is to import the .txt file outputted from the program into an [Anki](https://apps.ankiweb.net/) deck (an SRS flash card learning system) in order to complement learning while reading Japanese books.  

Takes in an epub book and prints the kanji to a file, sorted by highest frequency back.  

The kanji are compared to the [kanjidic](https://www.edrdg.org/wiki/index.php/KANJIDIC_Project) dictionary. The output format can be easily imported into Anki.  

Field 1 (front) is the kanji, 2 is meaning, 3 is on'yomi (represented in katakana), and field 4 is kun'yomi in hiragana.  

example: `cargo run example.epub output.txt`  

In my testing, some books could take over a minute.  
 
Source: <a href="https://github.com/keggit/epub-kanji-frequency/"><i class="large github icon"></i>keggit/epub-kanji-frequency</a>