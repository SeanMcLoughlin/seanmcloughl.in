---
title: "\"Modern\" Hardware Design"
date: 2020-09-14T15:49:26-08:00
tags: ["rust", "systemverilog"]
---

### While software development tools are better than ever, hardware development tools are still stuck in the 90’s. How can this be fixed?

I am a pre-silicon validation engineer. What that means is that I write software to test, analyze, and stress hardware designs to ensure that they adhere to their architectural specifications. Aside from a Linux environment, The common tools that I use for my job are:

* SystemVerilog: An IEEE-standard language designed for defining hardware at the Register Transfer Level (RTL), as well as the test benches to test that hardware.
* UVM (Universal Verification Methodology): An open-source library that standardizes how hardware validators should write test benches for hardware designs.
* DVT Eclipse: A plugin for the (previously) popular IDE Eclipse that works with SystemVerilog. It supports syntax highlighting, custom build scripts, etc.
* Synopsys VCS: A SystemVerilog compiler, simulator, and synthesizer. Proprietary. A license costs a boat-load of money.
* Various other tools to help me debug and track the progress of the testing of the design, such as waveform viewers, coverage viewers, etc. These tools all come from external vendors such as Synopsys, Cadence, and Mentor, all of them cost quite a bit, and none are open-source.

If you’re coming from a pure software background and you haven’t heard of any of these tools, that’s perfectly fine.

The issue is that many new graduates coming into the semiconductor industry, such as myself a few years ago, haven’t heard of many of these tools at all. At my college, our Computer Architecture course allowed us to use Synopsys VCS to compile our SystemVerilog code, but we did not use any other tools. For the most part, we were stuck with using Vim/Emacs to do our coding, and while we were still able to design an out-of-order processor properly, the experience with these tools was unenjoyable due to their poor and complex documentation, as well as a lack of coding automation that an IDE would provide for us.

Contrast this with a mobile app development class that was also available at my university, where all the students would use Xcode with all the IDE features you’d expect, a live app simulator, dozens of well-documented libraries from Apple, and either Swift or Objective-C as the language. While not perfect, the tools for that job allow the developer to work much more efficiently and happily.

So why is it that the tools for hardware design are so much worse than software design?

The most obvious reason is that software designers far outnumber hardware designers, and so the tools for hardware design are either going to be featureless in comparison, or completely nonexistent. We could just stop there, but I don’t think that it explains the whole story.

I believe that a larger contributor to this issue is that designing hardware isn’t as widely available as designing software. I mean two things by this:

1. Most people don’t have access to a nanofab or an FPGA lying around where they can design a new piece of hardware and see it working the same day. In contrast, anyone who knows HTML/CSS and JavaScript can create a nice, functional website in a few hours.
2. Even if I had an FPGA or access to a nanofab, I couldn’t work on hardware design because the software tools I need for development are too expensive.

A big part of any engineer’s job is to make his or her job as easy as possible. Tools that are a pleasure to use contribute greatly to the ease of one’s work. I’m not going to make hardware design a more desirable career path, and I’m not going to be able to give all aspiring developers an FPGA. However, anyone, including myself, can remake these proprietary tools as FOSS alternatives. So is making free and open-source software to rival proprietary design tools the best route to take?

Consider g++. One of the biggest reasons g++ is the go-to C and C++ compiler is, not only does it work (and it works well!), but it’s free and easy to access anywhere. Both Microsoft and Intel, among others, have their own proprietary C++ compilers, but [g++ is arguably the best choice out of all of them.](https://en.wikipedia.org/wiki/List_of_compilers#C++_compilers) While g++ might be better in terms of performance, a major contributor to it’s success is that, unlike its competitors, it’s free. Anyone who learns C++ is going to compile their code with g++. I work at Intel, and even I use g++ to compile the C++ code that I sometimes write. It’s an absolute wonderful tool that I’ve never had any trouble with (except when I’m angry that my code doesn’t compile).

This describes many of the types of tools that are used in the software world: free, open-source, community-driven pieces of software that drive the industry forward. NodeJS, Git, the entirety of Linux, Apache, everything Mozilla has ever made, and more, are all great examples of this. What if the semiconductor industry took notes from these practices and created a cross-company initiative to create FOSS tools to benefit the industry?

Unfortunately, it is all too common in the semiconductor industry to develop tools internally, or pay a pretty penny from EDA (Electronic Design Automation) vendors like Synopsys, Cadence, and Mentor in order to license tool usage[[1]](#[1]). You will never see Intel, AMD, NVIDIA, Qualcomm, etc. ever release an EDA tool that the rest of the industry gets to use, but if you ever work at one of those companies, you’ll know just how many people they hire to develop tools that are for internal usage only (hint: it’s a lot).

[NVIDIA’s recent deal to purchase ARM](https://www.cnbc.com/2020/09/14/nvidia-to-buy-arm-holdings-from-softbank-for-40-billion.html) is another great example of the semiconductor giants trying to top one another by getting a stronghold on an industry tool such as ARM’s ISA.

I yearn to live in a world where the semiconductor industry takes a modern approach to their tool design and usage by learning from the successes of the software industry, but we’re never going to get there if there isn’t a FOSS-initiative started between these companies. While I would love to be in a small team that creates these FOSS tools to help everyone, it’s simply not realistic for me to work a full-time job and create open-source software that major industries use.

This change needs to start internally in these companies. However, with all of the forks happening in the industry now, such as Apple creating their own (silicon for Macs)[https://en.wikipedia.org/wiki/Apple-designed_processors], Microsoft creating [silicon for Azure](https://azure.microsoft.com/en-us/blog/silicon-development-on-microsoft-azure/), and Facebook making [custom silicon for training neural networks](https://www.extremetech.com/computing/285980-facebook-is-working-on-its-own-custom-ai-silicon), I wonder if it’s even still possible.
Footnotes

#### Footnotes 

<a id="[1]"></a>[1] One of the tools I mentioned previously that I find to be an exception to this problem is UVM, since it is open-source, industry-standard, and quite well-documented. Given the climate of the semiconductor industry towards FOSS tools, it’s a miracle that a library such as UVM even exists in its current form.

_This story was originally published on [Medium.](https://medium.com/swlh/modern-hardware-design-941ac64682ef) In the future, blog posts will be first posted here, and then cross-posted to Medium, as opposed to the other way around._
