<h2 style="text-align: center;">Cheat Sheet Twine</h2>


In this cheat sheet you will find the code for the basic concepts we will be covering throughout the workshop. It is divided in sections, from the most basic (e.g. creating links) to the more advanced operations (e.g. macros or snippets of code to execute actions). The version of Twine we'll be using is called [Harlowe 3.5](https://twine2.neocities.org/), and you can access the Cookbook or manual using the link provided above. This cheat sheet extracts information directly from the Cookbook and contextualizes it for the workshop. 

## **Basic Level**

### **Creating links**

You need to write the following code: `[[Title of target page]]` or `[[Title you want the reader to see |Page's Title]]` ==> `[[Beginning]]` or `[[Passage 1|The beginning of our story]]`

### **Formating Text with Markdown and Harlowe**

#### **Headlines**

There are several levels. All of them use the `#` before the text we want to affect. 

`#Headline level 1`
`##Headline level 2`
`###Headline level 3`


#### **Alignment**

Left `(align:"<==")+(box:"X=")[Text you want to affect]`
Right `(align:"==>")+(box:"X=")[Text you want to affect]`
Centered `(align:"=><=")+(box:"X=")[Text you want to affect]`
Justified `(align:"<==>")+(box:"X=")[Text you want to affect]`


#### **Text size**

Use the following macro next to the text you wantto affect (called "changer"). Do not add spaces between the macro and the changer. `(text-size: a number)[changer]` ==> `(text-size: 10)[Hello World]`

## **Intermediate Level**

#### **Text style**

Use the macro `(text-style: "type of string")[Text you want to change]` ==> `(text-style: "underline")[Hello underlined world]`

Some strings that you can use are: "rumble", "bold", "underline", "strike", "ouline", etc. For a comprehensive list use the following [Cook book](https://twine2.neocities.org/#macro_text-style)

**To change font color**. The basic sintax you need is `(color: color name)[changer]` ==> `(color: red)[Germany]`

## **Itermediate High or Advanced Low Level**

#### **Macros**

Macros are pieces of code that help to make the game more dynamic and interactive. As a creator, you can use these pieces of code to a) create prompts where  players will enter information, b) timers that will add tension to the action, and other interactive features. Usually, macros work with the following syntax: 

`(command: "condition")[changer]` ==> `(text-size: 4)[Hello]` In this example, "Hello will be rendered at a size 4 which is around 24 or 30 pts. If you see, we started to use macros and hooks (a macro plus a changer) when we learned how to change text styles and colors. However, the concepts we'll learn below are a bit more complex. 

Some of the most popular marcos are: 

* Click macro
    * `(click: "Name of the clickable word")`. The word referenced in the "condition" (the clickable word) must be part of the narrative you are creating. The click macro must be linked (as a hook) to a condition that will appear when the player clicks the word affected by the click macro.
    `Eg. Javier turned the lights on ==> (click: "lights")` ==> This code will cause the word "lights" to be illuminated.Wehne we have the click, we can add the action that is going to appear when the player clicks on the word. 
    `Eg. Javier turded the lights on ==> (click: "lights")[With the lights on, Javier  discovered three big dogs]`
* Timer macro
    * `(set: "$variable" to "float")` ==> `(set: $counter to 10)`
    * Example used on the game:
        * `You have |amount>[$counter] seconds left!
(live: 1s)[(set: $counter to it -1) (if: $counter is 0)[(go-to: "Beginning")] (replace: ?amount)[$counter]]
`

* Conditional macro
    * `(if: “CONDITION”)[Action, text, image, etc. that will appear]
(else:)[Action, text, image, etc. that will appear]
`

* Prompt macro
    * `(set: $VARIABLE to (prompt: "VALUE YOU WANT TO SHOW AS TITLE OF BOX", "VALUE YOU WANT IN THE BOX"))`




#### **Embeding Web Technologies**

* **Adding image (to passage)**
    * `<img src = "YOUR URL" width = "300" height = "300">`

You can change the `src` to whatever image you can find on the web. You can also adjust the width and height. If you want to center the image, you need to add the HTML tag `<center><center>`

You need images from the internet. It means that the image needs to have a URL. If there is an image without URL or that you have on your machine, you can upload it to [Wix](https://www.wix.com/), a platform to create websites. Once you upload it there you can get a URL for your image. 

* **Adding a Youtube Video**
    * Go to the [YouTube](https://www.youtube.com/) video you want to copy
    * Go to the `"Share"` link
    * Select the option `< >`, which means that the platform provides the code to embed the video directly on your page.
    * Copy the code you'll find. It look like the following: 
        * `<iframe width= "560" height= "315" src="https://www.youtube.com/embed/k9wSW51sbuE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`


* **Adding audio**

At the passage level, you need to include the follwoing code: 
* `<sound src=”YOUR URL” autoplay>`. 

I recommend using the service [Sound Bible](https://soundbible.com/) so you can get diverse sounds and sound effects. 

**Note**: It’s better to add the audio command at the end of the page as it will play on a loop and won’t execute any other commands set after


  
#### **Adding a Background Image at a Global Level (it will affect your entire game/story)**

* Go to Story
* Click on the `“#Stylesheet”` link (button)
* Add the following code (CSS code): 
    
    `tw-story {background-image:url(“YOUR URL”); background-size:cover;}`


#### **Changing Background Image globally for a passage (using tags)**


* Click on the #Stylesheet button and add the following code: 

    `tw-story[tags~=”YOUR TAG NAME”] { background-image:url(“YOUR URL”); background-size:cover;}`

---
<font size="0.5">Afro-Latinx Digital Storytelling. A Twine Journey to Narrative Decolonization</font>
 

