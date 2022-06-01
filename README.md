# Pig game

### Pig game web application using HTML, CSS and JavaScript

Pig game is a simple dice game where players take turn in rolling a single dice as many times as possible and adding the number of the roll to a tally. If the dice rolls 1 the sum of the rolls is lost and the other player rolls the dice.

![pig-game-flowchart](https://user-images.githubusercontent.com/47001806/171420829-f05b25d6-115f-4d96-9ebe-2a29be49b1f9.png)


#### Some notes on deployment:

Buildpacks are basically a set of scripts depending on the programming language that is used in the project. The scripts of the buildpack are responsible for gathering the dependencies, which then outputs generated code, when pushing code to Heroku, the code is received by a compilter that transforms the repo into a slug and off to a dyno for execution.

All of this sounds good, but heroku doesn't provide a buildpack for HTML, CSS or JavaScript.

![image](https://user-images.githubusercontent.com/47001806/171442853-741a200b-f3a8-4011-a993-c1f68c605244.png)

A work around to this, is to tell Heroku to recognize the files of a static website as a PHP app.

For this:

1) In the root directory of the project, I added an empty file named `composer.json` that literally contains  `{}`
2) Then, in the same directory I added an `index.php` file with the following code: `<?php include_once("index.html"); ?>`

After this I pushed the project into Heroku the automatic deployment did its thing and everything ran smoothly!
