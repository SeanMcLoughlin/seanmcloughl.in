---
title: "VLaDOS Dev Blog: Intro (Also Titled: Do More Research Before Committing to a Project Like This)"
date: 2020-12-27T14:45:50-08:00
draft: false
---

## EDIT (12/30/2020)

VLaDOS is now defunct and its (empty) repository was removed. It had a very short life after I learned about already-existing tools to do meet its goals, such as [LLHD](https://github.com/fabianschuiki/llhd) (and, to an extent, [Verilator](https://www.veripool.org/wiki/verilator)). It makes far more sense to contribute to this project than to start something from scratch. I researched tools like this earlier this year and couldn't find *anything*, but I guess LLHD released their paper earlier this year and I missed it.

Thanks to everyone who responded on Twitter with great feedback on this subject. I'm really glad there are a lot of people who work with HDLs who want to make the tool ecosystem better.

## Original Article

Today, I've finally begun work on the SystemVerilog compiler and simulator, [VLaDOS](https://github.com/SeanMcLoughlin/VLaDOS). This project has been a long time coming, and I've had to learn a lot to even get to the point of being able to start writing it. This is probably the most ambitious project I have ever taken up, and is my first *major* open-source project. Because of that, I'm going to do development blogs for each alpha release of the tool that has major features -- starting with this one.

## What is VLaDOS?

VLaDOS aims to be a free and open-source SystemVerilog compiler and simulator. The project has a few goals:

1. Obviously, **compile code that adheres to the SystemVerilog LRM into a simulator executable.**
2. As much as is reasonable and possible, **act as a drop-in replacement for most other EDA vendor compilers and simulators.** Semiconductor companies should have minimal pain switching to this tool -- otherwise they may never do so.
3. **Remain free and open-source** to allow anyone to simulate SystemVerilog anywhere.

## What's with the name "VLaDOS?"

VLaDOS is an acronym for *(System)Verilog Language: a Definitively Open Simulator*. It is also a play-on-words of [GLaDOS](https://en.wikipedia.org/wiki/GLaDOS), the AI antagonist of the popular *Portal* video game series.

## Why are you working on this?

I've discussed this in length in my ["Modern" Hardware Design](https://seanmcloughl.in/posts/modern-hardware-design/) post, but the gist of the issue is that EDA vendors generally provide sub-par tools at extreme prices per license. Not only are these licenses are a non-trivial development cost for semiconductor companies, but any individual who isn't able to pay for a license has no way of simulating SystemVerilog code on their local machine.

In this case, the only feasible option is to use [EDAPlayground](https://www.edaplayground.com/), but there are obvious downsides to this, namely that it requires an account, and that you have to run the code in a web browser.

I like software development, I work in the semiconductor industry, and I see this as a major pain point for the industry at large. Given the circumstances, I almost feel like I have an obligation to work on things such as this.

## Why Rust?

Basically all the reasons that anyone would choose Rust over C++ for an application like this. It's more modern. It has attractive features. Its  not tied to linking with other C++ code (aside from LLVM, which there are Rust bindings for). I can think of several more reasons off the top of my head, but you get the idea.

Maybe a few months down the line I'll realize that Rust was a terrible choice and I'll revert to using C++, but I highly doubt it.

## This sounds great! How can I help?

Compilers are huge undertakings, and I know that I won't be able to complete this project by myself. If you know Rust and want to work on an interesting domain-specific language that was used to code your CPU/GPU, feel free to chat on the project's [Gitter community](https://gitter.im/vlados-compiler). Eventually, descriptive [issues](https://github.com/SeanMcLoughlin/VLaDOS/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) will be filed, and you should look there instead.

If you're not able to contribute via code, a financial contribution would mean a lot. You can [sponsor me on GitHub](https://github.com/SeanMcLoughlin), or you can [buy me a coffee](https://www.buymeacoffee.com/smcloughlin).
