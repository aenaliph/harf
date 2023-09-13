---
layout: post
title: "Hacks for Urdu"
bibliography: /_bibliography/file_skeleton.json
reference-section-title: References
---

This document is meant to record technology related issues faced when working with Urdu data. Our primary work environments are MacOS and Ubuntu (remote) based. We intend to document solutions and workarounds discovered. 

## Urdu Display and Rendering on Terminal, Vim, Nano in MacOS and Ubuntu

We take some sample text (reproduced below) from [Siasat Urdu](https://urdu.siasat.com/news/مراقش-زلزلہ-مہلوکین-کی-تعداد-2ہزار-سے-م-1491628/) and create a sample file `urdu.sample.txt`

::: {dir="rtl"}
مراقش : زلزلہ مہلوکین کی تعداد 2ہزار سے متجاوز، 3روزہ سوگ کا اعلان رباط : مراقش میں جمعہ کی شب آئے شدید زلزلے کے نتیجے میں اموات کی تعداد دو ہزار سے تجاوز کر گئی ہے۔ حکام نے ہلاکتوں میں اضافے کا خدشہ ظاہر کیا ہے۔امریکی خبر رساں ادارے اے پی کے مطابق وزارت داخلہ نے کہا ہے کہ کم از کم دو ہزاور اور 12 افراد ہلاک اور دو ہزار 59 زخمی ہوئے ہیں جبکہ 14 سو سے زیادہ افراد کی حالت تشویشناک ہے۔
:::

### MacOS 
On MacoS the  _zsh_ based _shell_ is able to display Urdu correctly from the terminal. See example below for the cat command: 

![urdu_terminal_mac.png]({{ site.baseurl }}/assets/images/urdu_terminal_mac.png)

The file opens correctly in _vim_ as well. 

![urdu_vim_mac.png](/{{ site.baseurl }}/assets/urdu_vim_mac.png)

You can use `:set nu` to display line numbers as usual. 

![urdu_setnu_mac.png](/{{ site.baseurl }}/assets/urdu_setnu_mac.png)

You can use `:syntax on` followed by `:set syntax=whitespace` to highlight whitespaces. This helps when debugging for space issues in Urdu. 

![urdu_space_mac.png](/{{ site.baseurl }}/assets/urdu_space_mac.png)

---

### Ubuntu

We assume that we `ssh` into a remote Ubuntu machine for this from a MacOS terminal. The bash based shell seems to work fine when displaying output of the file. 

![urdu_terminal_ubuntu.png](/{{ site.baseurl }}/assets/urdu_terminal_ubuntu.png)

But _vim_ seems to have rendering issues now. Notice some of the characters are not joined properly. What changed? We still have the same Terminal emulator. 

![urdu_vim_ubuntu.png](/{{ site.baseurl }}/assets/urdu_vim_ubuntu.png)

Until a fix is found use _nano_ instead. Like so to display with line numbers `nano -l urdu-test.txt` 

![urdu_nano_ubuntu.png](/{{ site.baseurl }}/assets/urdu_nano_ubuntu.png)

To display whitespace in nano, use `M-P` to toggle where `M-` refers to a meta key -- on Macos keyboards understood to be the `esc` key. For Linux keyboards this is usually the `Alt` key. 

![urdu_space_nano_ubuntu.png](/{{ site.baseurl }}/assets/urdu_space_nano_ubuntu.png)

---


