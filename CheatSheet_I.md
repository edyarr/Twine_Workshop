<h2 style="text-align: center;">Cheat Sheet Twine</h2>


In this cheat sheet you will find the code for teh basci concepts and actions we will be developing throughout the workshop. It is divided in sections, from the most basic to the inclussion of macros which are snippets of code. 

## **Basic**

### **Creating links**

You need to write the following code: `[[Title of target page]]` or `[[Title you want the reader to see |Page's Title]]`

### **Formating Text with Markdown and Harlowe (the Twine's sub-language)**

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

Use the following macro next to the text you wantto affect `(text-size: a number)`

#### **Text style**

Use the macro `(text-style: "type of string")`

Some strings that you can use are: "rumble", "bold", "underline", "strike", "ouline", etc. For a comprehensive list use the following [Cook book](https://twine2.neocities.org/#macro_text-style)

**To change font color**. The basic sintax you need is `(color: color name)[changer]` ==> `(color: red)[Germany]`

#### **Macros**

Macros are pieces of code that help the game to be more dynamic and interactive. You can use these pieces of code to ask players to enter information that could be used later, to create timers, and other interactive features. Usually, macros work with the following syntax: 

`(command: "condition")[changer]` ==> `(text-size: 4)[Hello]` In this example, "Hello will be rendered at a size 4 which is around 24 or 30 pts. 

Some of the ksot popular marcos are: 

* Click macro
    * `(click: "Name of the clickable word")`
* Counter macro
    * `(set: "$variable" to "float")` ==> `(set: $counter to 10)`
    * Example used on the game:
        * `You have |amount>[$counter] seconds left!
(live: 1s)[ (set: $counter to it -1) (if: $counter is 0)[(go-to: "Beginning")] (replace: ?amount)[$counter]]
`

* Conditional macro
    * `(if: “CONDITION”)[Action, text, image, etc. that will appear]
(else:)[Action, text, image, etc. that will appear]
`

* Prompt macro
    * `(set: $VARIABLE to (prompt: "VALUE YOU WANT TO SHOW AS TITLE OF BOX", "VALUE YOU WANT IN THE BOX"))`




#### E**mbeding Web Technologies**

* **Adding image (to passage)**
    * `<img src = "YOUR URL" height = "300" width = "300">`

You can change the `src` to whatever image you can find on the web. You can also adjust the height and width. If you want to center you need to add the tag `<center><center>`

You need images from teh internet. Tham means the image needs to have a URL. If there is an image without URL or that you have on your machine, you can upload it to [Wix](https://www.wix.com/), a platform to create websites.

* **Adding a Youtube Video**
    * Go to the [YouTube](https://www.youtube.com/) video you want to copy
    * Go to the “Share” link
    * Select the option `< >`, which means that the platform provides the code to embed the video directly in your page.
    * Copy the code you'll find. It look like the following: 
        * `<iframe width= "560" height= "315" src="https://www.youtube.com/embed/k9wSW51sbuE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`


* **Adding audio**

At the passage level you need to include the follwoing code: 
`<sound src=”YOUR URL” autoplay>`. I recommend using the service [Sound Bible](https://soundbible.com/) so you can get diverse sounds and sound effects. 

**Note**: It’s better to add audio command at the end of the page as it will be still playing and won’t execute any other commands set after


  
#### **Adding Background Image at a Global Level**

* Go to Story
* Click on the “#Stylesheet” link (button)
* Add the following code (CSS code): 
    `tw-story {background-image:url(“YOUR URL”); background-size:cover;}`


#### **Changing Background Image globally for a passage (using tags)**


* Click on the #Stylesheet button and add the following code: `tw-story[tags~=”YOUR TAG NAME”] { background-image:url(“YOUR URL”); background-size:cover;}`

---
<font size="0.5">Afro-Latinx Digital Storytelling. A Twine Journey to Narrative Decolonization</font>
 

