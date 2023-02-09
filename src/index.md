---
title: The Four Programming Elements
layout: base.njk
templateEngineOverride: njk,md
---

# The Four Elements of Programming

Welcome to The Four Elements of Programming micro-course! Learning to program was one of the best things to happen to me. I am extremely grateful that I have managed to make a good living in the industry but that is not even a top five reason why I love being a programmer. 

First and foremost, it has given me the tools to be a better thinker. Without reservation, the mental discipline I have acquired has benefitted me in every other area of my life. It is like growing up playing shortstop in baseball and then finding out that this skill set makes you an unstoppable quarterback in football. 

In a close second, I have made a lot of friends through programming. Creative people are just more interesting! Programmers are no exception to the rule. 


And thirdly, I have had the opportunity to build stuff that has made a huge difference in the lives of the people using those applications. We are seeing software solve some of the biggest problems in the world today in really powerful ways. 

I created this micro-course as a personal invitation into the world of programming. If you are even remotely curious about programming, it would be a huge honor for you to give me the chance to make the case for you to stick around. This is by no means an exhaustive tour of programming but through a series of basic exercises, we are going to back into something really important. I am not going to spoil the surprise!

## Complex vs Complicated
---

Do you know the difference between **complex** and **complicated**? This distinction profoundly changes the way that we see the world and more importantly, how we approach new and unknown experiences. **Complexity** is hard to control and predict. **Complicated** things are not simple but ultimately knowable. 

What crosses your mind when you think of the word *"programming?"*

The most common response is a variation of *"programming is hard!"*, and only very smart people can do it. This is an understandable outcome, and we are not surprised how many people arrive at this conclusion. Without realizing it, we can classify programming as **complex** which comes with a steep mental and emotional tax. How committed can someone be to a journey that deep down they believe they will never arrive at their destination? 

The goal of this micro-course is to gently guide you on a journey to show you that programming is not **complex** but can be **complicated** and we can solve **complicated** with the right mental tools. 

Programming is not *"hard"* because that is just the nature of programming. Programming is *"hard"* because reality is *"hard"*. Programming, like music and art, depends on our ability to observe what is happening around us and process it. Music is more about hearing than it is about playing. Art is more about seeing than drawing or painting. Likewise, programming revolves around our ability to think and not so much our ability to code. 

We do not become better programmers by learning new and novel ways to create more code. Likewise, learning the latest trendy framework will not necessarily make you a better programmer if it does not change how you think about the world. 

Welcome! We will work through a series of exercises that reduces programming to its first principles to establish a mental model to better understand the world around us. These exercises may seem absurdly simple initially, but please stick around and see this to its conclusion. 

In the spirit of Karate Kid, it will seem like all we are doing is painting fences and waxing cars at first, but inevitably, we will realize that we have been learning a much more valuable set of skills all along. 


Programming is **complicated** but ultimately knowable. 

## The Premise

After programming for many years, I realized that I was doing the same basic things over and over again. Specifically, I was only ever doing **four basic things**. This revelation was stunning to me! But, equally surprising is that I realized that I had understood these concepts since I was a small child. This insight was a major inflection point in my personal worldview. 

**We do not need to acquire new information as much as we need to have a deeper understanding of what we already know.**

We will introduce and elaborate on these four elements in the following sections, but I wanted to give you a preview of where we are going. 
## The Exercises

The format for this course will consist of a series of small exercises that we will do entirely in [StackBlitz](https://stackblitz.com/). [StackBlitz](https://stackblitz.com/) is an online code editor which makes it an excellent choice because it allows us to start immediately without anything getting in the way. To start, navigate to [StackBlitz](https://stackblitz.com/) and click on the [TypeScript Blank Project](https://stackblitz.com/#:~:text=TypeScript,Blank%20project) button. 

![screenshot](/assets/screenshots/stackblitz.png)

You should see an editor like the screenshot below, and this is where we will write all of our code.  

![screenshot](/assets/screenshots/stackblitz-editor.png)

## Helpful Hint

All our code will be in TypeScript which creates some challenges in terms of visualizing the output of our work. We are going to solve this by updating the last line of our code to the following snippet:

```javascript
appDiv.innerHTML = `<h1><pre>${JSON.stringify(
  SOMETHING_HERE,
  null,
  2
)}</pre></h1>`;
```

This will allow us to see the output of our code in the browser in big, bold letters. As we progress through the exercises, we will replace **SOMETHING_HERE** with whatever we want to output to the browser.