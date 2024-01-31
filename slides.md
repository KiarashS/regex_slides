---
theme: seriph
background: ./images/intro.png
class: text-center
lineNumbers: false
favicon: ./favicon.png
info: |+
  Ultimate Guide to Regular Expressions for scientist

  [www.kiarashs.ir](https://www.kiarashs.ir/)
author: Kiarash Soleimanzadeh
keywords: regular expressions,regex,scholar,academia,nlp,natural language processing,machine learning,deep learning
presenter: false
download: false
exportFilename: 'regex-slides'
export:
  format: pdf
  timeout: 30000
  dark: false
  withClicks: false
  withToc: false
aspectRatio: '16/9'
canvasWidth: 980
drawings:
  persist: false
transition: slide-left
title: Regular Expressions (Regex)
mdc: true
fonts:
  # for code blocks, inline code, etc.
  mono: 'Fira Code'
---

<h2 class="-mt-20">
Ultimate Guide to Regular Expressions
</h2>

Presentation slides for AI scientists

<div class="pt-70">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <!-- <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button> -->
  <a href="https://github.com/KiarashS" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# Intro

> A regular expression is a group of characters or symbols which is used to find a specific pattern in a text.

<v-click>
<p class="text-sm">Regex is short for <span class="highlight-gray">Regular Expression</span>. A regular expression is a pattern that is matched against a subject string from left to right. Regular expressions are used to replace text within a string, validate forms, extract a substring from a string based on a pattern match, and so much more.</p>
</v-click>

<v-click>
<p class="text-sm">Imagine you are writing an application and you want to set the rules for when a user chooses their username. We want to allow the username to contain letters, numbers, underscores and hyphens. We also want to limit the number of characters in the username so it does not look ugly. We can use the following regular expression to validate the username:</p>
</v-click>

<div class="flex justify-center items-center m-auto">
  <v-click><div class="flex-1"><img src="/images/regexp.png" alt="Regex" width="390px" /></div></v-click>
  <v-click><div class="flex-1 text-sm">This regular expression can accept the strings <span class="highlight-gray">john_doe</span>, <span class="highlight-gray">jo-hn_doe</span> and <span class="highlight-gray">john12_as</span>. It does not match <span class="highlight-gray">Jo</span> because that string contains an uppercase letter and also it is too short.</div></v-click>
</div>

---

# What is Regular Expressions?

<p>Regular Expressions are a string of characters that express a search pattern. Often abbreviated as <span class="highlight-gray">Regex</span> or <span class="highlight-gray">Regexp</span>. It is especially used to find or replace words in texts. In addition, we can test whether a text complies with the rules we set.</p>

<p>For example, let's say you have a list of filenames. And you only want to find files with the <span class="highlight-gray">pdf</span> extension. Following typing an expression <span class="highlight-gray">^\w+\.pdf$</span> will work. The meaning of the definitions in this expression will become clearer as the steps progress.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
readme.md<br>
<span class="highlight-green">document.pdf</span><br>
image.png<br>
music.mp4<br>
<span class="highlight-green">manual.pdf</span><br>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/^\w+\.pdf$/gm
```
</v-click>

---

# Basic Matchers

<p>The character or word we want to find is written directly. It is similar to a normal search process. For example, we want to find the word <span class="highlight-gray">curious</span> in the text.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
“I have no special talents. I am only passionately <span class="highlight-green">curious</span>.”
<br>
― Albert Einstein
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/curious/gm
```
</v-click>

---

<h1>Dot <span class="header-one-highlight">.</span>: Any Character</h1>

<p>The period <span class="highlight-gray">.</span> allows selecting any character, including special characters and spaces.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">a</span><span class="highlight-green">b</span><span class="highlight-green">c</span><span class="highlight-green">A</span><span class="highlight-green">B</span><span class="highlight-green">C</span><span class="highlight-green">1</span><span class="highlight-green">2</span><span class="highlight-green">3</span><span class="highlight-green">&nbsp;</span><span class="highlight-green">.</span><span class="highlight-green">:</span><span class="highlight-green">!</span><span class="highlight-green">?</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/./g
```
</v-click>

---

<h1>Character Sets <span class="header-one-highlight">[abc]</span></h1>

<p>If one of the characters in a word can be various characters, we write it in square brackets <span class="highlight-gray">[]</span> with all alternative characters. For example, to write an expression that can find all the words in the text, type the characters <span class="highlight-gray">a</span>, <span class="highlight-gray">e</span>, <span class="highlight-gray">i</span>, <span class="highlight-gray">o</span>, <span class="highlight-gray">u</span> adjacently within square brackets <span class="highlight-gray">[]</span>.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">bar</span> <span class="highlight-green">ber</span> <span class="highlight-green">bir</span> <span class="highlight-green">bor</span> <span class="highlight-green">bur</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/b[aeiou]r/g
```
</v-click>

---

<h1>Negated Character Sets <span class="header-one-highlight">[^abc]</span></h1>

<p>To find all words in the text below, except for <span class="highlight-gray">ber</span> and <span class="highlight-gray">bor</span>, type <span class="highlight-gray">e</span> and <span class="highlight-gray">o</span> side by side after the caret <span class="highlight-gray">^</span> character inside square brackets <span class="highlight-gray">[]</span>.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">bar</span> ber <span class="highlight-green">bir</span> bor <span class="highlight-green">bur</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/b[^eo]r/g
```
</v-click>

---

<h1>Letter Range <span class="header-one-highlight">[a-z]</span></h1>

<p>To find the letters in the specified range, the starting letter and the ending letter are written in square brackets <span class="highlight-gray">[]</span> with a dash between them <span class="highlight-gray">-</span>. It is case-sensitive. Type the expression that will select all lowercase letters between <span class="highlight-gray">e</span> and <span class="highlight-gray">o</span>, including themselves.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
abcd<span class="highlight-green">e</span><span class="highlight-green">f</span><span class="highlight-green">g</span><span class="highlight-green">h</span><span class="highlight-green">i</span><span class="highlight-green">j</span><span class="highlight-green">k</span><span class="highlight-green">l</span><span class="highlight-green">m</span><span class="highlight-green">n</span><span class="highlight-green">o</span>pqrstuvwxyz
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/[e-o]/g
```
</v-click>

---

<h1>Number Range <span class="header-one-highlight">[0-9]</span></h1>

<p>To find the numbers in the specified range, the starting number and the ending number are written in square brackets <span class="highlight-gray">[]</span> with a dash <span class="highlight-gray">-</span> between them. Write an expression that will select all numbers between <span class="highlight-gray">3</span> and <span class="highlight-gray">6</span>, including themselves.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
012<span class="highlight-green">3</span><span class="highlight-green">4</span><span class="highlight-green">5</span><span class="highlight-green">6</span>789
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/[3-6]/g
```
</v-click>

---

# Repetitions

<p>Some special characters are used to specify how many times a character will be repeated in the text. These special characters are the plus <span class="highlight-gray">+</span>, the asterisk <span class="highlight-gray">*</span>, and the question mark <span class="highlight-gray">?</span>.</p>

---

<h1>Asterisk  <span class="header-one-highlight">*</span></h1>

<p>We put an asterisk <span class="highlight-gray">*</span> after a character to indicate that the character may either not match at all or can match many times. For example, indicate that the letter <span class="highlight-gray">e</span> should never occur in the text, or it can occur once or more side by side.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">br</span><span class="highlight-green">ber</span><span class="highlight-green">beer</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/be*r/g
```
</v-click>

---

<h1>Plus Sign  <span class="header-one-highlight">+</span></h1>

<p>To indicate that a character can occur one or more times, we put a plus sign <span class="highlight-gray">+</span> after a character. For example, indicate that the letter <span class="highlight-gray">e</span> can occur one or more times in the text.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
br<span class="highlight-green">ber</span><span class="highlight-green">beer</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/be+r/g
```
</v-click>

---

<h1>Question Mark  <span class="header-one-highlight">?</span></h1>

<p>To indicate that a character is optional, we put a <span class="highlight-gray">?</span> question mark after a character. For example, indicate that the following letter <span class="highlight-gray">u</span> is optional.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">color</span>, <span class="highlight-green">colour</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/colou?r/g
```
</v-click>

---

# Curly Braces - 1

<p>To express a certain number of occurrences of a character, at the end we write curly braces <span class="highlight-gray">{n}</span> along with how many times we want it to occur. For example, indicate that the following letter <span class="highlight-gray">e</span> can occur only <span class="highlight-gray">2</span> times.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
ber<span class="highlight-green">beer</span>beeer beeeer
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/be{2}r/g
```
</v-click>

---

# Curly Braces - 2

<p>To express at least a certain number of occurrences of a character, immediately after the character we write at least how many times we want it to occur followed by a comma <span class="highlight-gray">,</span> and wrapped inside curly braces <span class="highlight-gray">{n,}</span>. For example, indicate that the following letter <span class="highlight-gray">e</span> can occur at least <span class="highlight-gray">3</span> times.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
ber beer<span class="highlight-green">beeer</span><span class="highlight-green">beeeer</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/be{3,}r/g
```
</v-click>

---

# Curly Braces - 3

<p>To express the occurrence of a character in a certain number range, we write curly braces <span class="highlight-gray">{x,y}</span> with the interval we want to go to the end. For example, indicate that the following letter <span class="highlight-gray">e</span> can only occur between <span class="highlight-gray">1</span> and <span class="highlight-gray">3</span>.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">ber</span><span class="highlight-green">beer</span><span class="highlight-green">beeer</span>beeeer
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/be{1,3}r/g
```
</v-click>