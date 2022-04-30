---
theme: default
highlighter: shiki
lineNumbers: false
info: Teach a Computer to Do Math
drawings:
  persist: false
layout: cover
title: Teach a Computer to Do Math
---

<!--
#e63946 #f1faee #a8dadc #457b9d #1d3557
-->

# Teach a Computer to Do Math

Yet another useless project by Joey Yu

---
layout: center
---

# But doesn't it already know how?

---

# Example

Additions in Python with different data types.

<div grid="~ cols-2 gap-4">
<div v-click>

**2 Integers**
___
Input:
```python
>>> 1 + 1 
```
Output:
```python
2
```
Checking the type:
```python
>>> type(1)
<class 'int'>   # 1 is an integer
```
</div>
<div v-click>

**2 Strings**
___
Input:
```python
>>> '1' + '1' 
```
Output:
```python
'11'    # We don't want this
```
Checking the type:
```python
>>> type('1')
<class 'str'>   # '1' is a string
```
</div>
</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# Making it more difficult

Let's also get rid of the concept of addition.

<div v-click>

- We will input the addition symbol as a string. + $\rightarrow$ '+'

</div>

<div v-click>

In summary, this is how normal people do addition:
```python
>>> expression = 1 + 1    # This is a normal math expression
>>> expression
2
```

</div>

<div v-click>

Now I made it more difficult for no reason:
```python
>>> expression = '1 + 1'    # This is a math expression as a string
>>> expression 
'1 + 1'   # This is not what we want :((
```
In string form, the computer has no idea what "numbers" are and what does "addition" mean.

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# Transforming the problem

Think outside of the box.


<div v-click>

<div grid="~ cols-2 gap-4">
<div>

```python
>>> expression = 1 + 1   
>>> expression
2
```
</div>
<div>

```python
>>> expression = '1 + 1'  
>>> expression 
'1 + 1'   # This is not what we want :((
```
</div>
</div>

By inputing everything as a string instead of a normal math expression, we are converting from

</div>

<div v-click>

<center><h2><b>A simple addition problem</b></h2></center>

</div>

<div v-click>

to

<center><h2><b>A machine translation problem</b></h2></center>

<br/>

</div>

<div v-click>

Think of it as **translating from a math expression to its answer**, just like how a translator may translate from English to French

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# How can we do it?

Let's explore our options for machine translation problems...

<div v-click>

1. **Rule-based** machine translation (RBMT)

- Basically mapping from **word to word**. 
- "We" $\rightarrow$ "Nous", "are" $\rightarrow$ "sommes", "graduating" $\rightarrow$ "diplômé(e/s/es)" 👨‍🎓 🎓 👩‍🎓

<br/>
</div>

<div v-click>

2. **Statistical** machine translation (SMT)

- Getting better, mapping from **sentence to sentence**. 
- "Hristo is bad at chess." $\rightarrow$ "Hristo est mauvais aux échecs." ♟️

<br/>
</div>

<div v-click>

3. **Neural** machine translation (NMT)

- The **neural network** learns from exiting translations and its own previous translations to keep improving its output.
- Requires a huge amount of data. 🤖

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# The solution

I'm a bit lazy so I would like to train a neural network to add numbers.

<div v-click>

Since we have turned it into a machine translation problem, we can use the **neural machine translation** (NMT) approach to solve our problem.

</div>

<div v-click>

More specifically, we will use the **Sequence to Sequence (seq2seq)** model, which is one of the cool applications of neural network, and is also the magic behind **Google Translate**, to solve our problem.

<div grid="~ cols-2 gap-4">

<div><img src="https://cscloud.itsjoeoui.com/LuQ8URjmFQ9oR8UzYWin/download" alt="Google Translate" width="500"/></div>

<div>
<br/>
<br/>
<br/>
<img src="https://cscloud.itsjoeoui.com/wpHYOt19o8f9UcwN6fna/download" alt="Google Translate" width="500"/></div>

</div>

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# Artificial Neural Network (ANN)

Starting from the basics.

<div v-click>

<center><img src="https://www.tibco.com/sites/tibco/files/media_entity/2021-05/neutral-network-diagram.svg" alt="ANN" width="600"/></center>

</div>

<div v-click>

ANN is not smart enough because it doesn't have "**momory**", but it is still able to do things like curve fitting.

</div>

<div v-click>

Image source: https://www.tibco.com/sites/tibco/files/media_entity/2021-05/neutral-network-diagram.svg

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# Recurrent Neural Network (RNN)

Getting smarter!

<div v-click>

RNN addresses the major shortcoming of ANN. It is now able to **retain information** from a previous state.

</div>

<div v-click>

For example, let's say we have a trained RNN that tries to predict the next word in a sentence.

</div>

<div v-click>

<center><h2><b>"The clouds are in the __?__"</b></h2></center>

</div>

<div v-click>

In this case, RNN can predict the next word because it is aware of the previous information => "**clouds**"

</div>

<div v-click>

<center><h2><b>"The clouds are in the sky"</b></h2></center>

</div>

<div v-click>

However, in the above example, the **distance** between the context and the place of prediction is small.

</div>

<div v-click>

What if we have: 

</div>

<div v-click>

<center><h2><b>"I grew up in France ... (omit 500 words) I speak fluent __?__"</b></h2></center>

</div>

<div v-click>

When the **distance** is long, RNN fails :((

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---

# Long Short-Term Memory Network (LSTM)

Even better!

<div v-click>

As its name suggests, it is capable for **long-term memory**. 

</div>

<br/>
<br/>

<div v-click>

<center><h2><b>"I grew up in France ... (omit 500 words) I speak fluent French"</b></h2></center>

</div>

<br/>
<br/>

<div v-click>

The **sequence to sequence** (seq2seq) model is one of the cool applications of LSTM.

</div>

<div v-click>

It is often used in language translation problems, which is **highly context dependent**.

</div>

<br/>
<br/>

<div v-click>

<center><h2><b>Let's translate some math expressions!</b></h2></center>

</div>

<style>
  .slidev-vclick-target {
    transition: opacity 500ms ease;
  }
  .slidev-vclick-hidden {
    opacity: 0;
    pointer-events: none;
  }
</style>

---
layout: center
---
# Demo

https://github.com/itsjoeoui/seq2seq-arithmetic

🙏 🙏 🙏  Let's pray that things are still working...

---
layout: center
---

# Don't be afraid! 🚀

---

# Thanks for listening!

<center><img src="https://www.dawsoncollege.qc.ca/science-fest/wp-content/uploads/sites/152/SF2015_banner.png" alt="ANN" width="600"/></center>

<center><img src="https://cscloud.itsjoeoui.com/ckD1RrAtmcnUwsCnM2Or/download" alt="ANN" width="600"/></center>

---

# Credit

- “A Ten-Minute Introduction to Sequence-To-Sequence Learning in Keras.” Keras.io, 2017, blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html. ‌
- Brownlee, Jason. “Learn to Add Numbers with an Encoder-Decoder LSTM Recurrent Neural Network.” Machine Learning Mastery, 18 May 2017, machinelearningmastery.com/learn-add-numbers-seq2seq-recurrent-neural-networks/.
- “Keras Documentation: Character-Level Recurrent Sequence-To-Sequence Model.” Keras.io, keras.io/examples/nlp/lstm_seq2seq/. ‌
- Olah, Christopher. “Understanding LSTM Networks -- Colah’s Blog.” Github.io, 2015, colah.github.io/posts/2015-08-Understanding-LSTMs/. ‌

Special thanks to my friend Junjie Yang at McGill University for his help! (github.com/JumjieYang)
