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
>>> '1' + '1'   # We don't want this
```
Output:
```python
'11'
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

In summary, this is how normal people does addition:
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

# Transforming the problem with

Think outside of the box.


<div v-click>

By inputing everything as a string instead of a normal math expression, we are converting from

</div>

<div v-click>

<center><h2>A simple addition problem</h2></center>

</div>

<div v-click>

to

</div>

<div v-click>

<center><h2>A machine translation problem</h2></center>

<br/>

</div>

<div v-click>

Basically translating from a math expression to its answer, just like how a translator may translate from English to French

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

I am a bit lazy so I would like to solve it using a neural network.

<div v-click>

Since we have turned it into a machine translation problem, we can use the **Sequence to Sequence (seq2seq)** model, which is the magic behind **Google Translate**, to solve our problem.

<br/>
<br/>
<br/>

<center><img src="https://cscloud.itsjoeoui.com/wpHYOt19o8f9UcwN6fna/download" alt="Google Translate" width="500"/></center>

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

Placeholder

---

# Recurrent Neural Network (RNN)

Placeholder

---

# Long Short-Term Memory Network (LSTM)

Placeholder

---

# One More Thing

https://www.youtube.com/watch?v=xyrgkui0uCA

<Youtube id="xyrgkui0uCA" :width='640' :height='360'/>
