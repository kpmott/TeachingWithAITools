# Example prompts for a ~second lecture in introductory finance

Adapt the following prompts to your preferred lecture. 

## Step 1: Slides
The prompts I use are usually quite informal. 

```
Can you write a beamer using @Mott_Beamer.sty that covers the following finance content? 
- reminder of previously covered time value of money (and opportunity cost)
- bond pricing from first principles
- stock pricing (dividend discount model) with link to accounting material
- definition of financial security 
- general result that price of security = present value of cash flows 
- preview that 'hey where do these discount rates come from' and we need to first understand risk. next two lectures will unpack this! 

Students have already seen basic time value of money (including annuity / perpetuity formulas) and are reasonably comfortable with formulas and basic math. they also some some accounting. but their general business/finance intuition is not so strong. Please use packages e.g. tikz to draw nice timelines for cash flow diagrams to drill the intuition of timing and present/future value. 
```

This should get the outline of the lecture in place. Please modify it for your preferred lecture. Then, tweak! Ask the AI to adjust pacing, ordering, and other structural components first. Then move on to slide-by-slide improvements. 

## Step 2: Notes
Again, informal prompting is pretty good. Also note the content in [CLAUDE.md](CLAUDE.md) which is *global* to the scope of the class. 

Tip: if you have existing work in previous lectures, I always start here:
```
Please go back to @[previous lecture slides] and @[previous lecture notes] to learn the mapping between them. Read both in full. Notice how the notes flow much more nicely, containing lots of connecting language, smooth writing, and really work to fill in the gaps from the slides. 
```
This sets the context for the AI to be reminded of the style you like. 
```
Please use @Mott_Handout.sty to write high-quality, textbook-level, beautifully formatted notes based on the lecture slides. There should be no new content in the notes, and the examples should be the same as in the slides. The goal is to have smooth, clean narratives to explain the material and tie everything together. 

Start by mimicking everything in the slides exactly into the notes, focusing on using paragraph formats instaad of the bullets which dominate the slides. 
```
At this point, the structure should be in place. Now proceed through the document and clean up as necessary. 

## Step 3: Additional Resources
At this point, depending on your course structure, you're free to work through additional resources that may be useful. My engineering classes have 2-hours-weekly tutorial sessions, so I always create an abridged version of the slide deck touching on the biggest themes. 

You can also try your hand at practice problem creation, though I do still mostly rely on this as a manual process due to the limited nature of the questions produced by AI (this may change...).