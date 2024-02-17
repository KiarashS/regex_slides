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
title: Regular Expressions
titleTemplate: '%s - Regex'
selectable: false
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
  <a href="https://github.com/KiarashS" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
title: 'Intro'
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
title: What is Regular Expressions?
---

<h1>What is Regular Expressions? <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Regular Expression</span></h1>

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
title: 'Basic Matchers'
---

<h1>Basic Matchers <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Basic Matchers</span></h1>

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
title: 'The Full Stop'
---

<h1>Dot <span class="header-one-highlight">.</span>: Any Character <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">The Full Stop</span></h1>

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
title: 'Character Sets'
---

<h1>Character Sets <span class="header-one-highlight">[abc]</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Character Sets</span></h1>

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
title: 'Negated Character Sets'
---

<h1>Negated Character Sets <span class="header-one-highlight">[^abc]</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Negated Character Sets</span></h1>

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
title: 'Character Sets: Alphanumeric Range'
---

<h1>Letter Range <span class="header-one-highlight">[a-z]</span> <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Character Sets: Alphanumeric Range</span></h1>

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
title: 'Character Sets: Digit Range'
---

<h1>Number Range <span class="header-one-highlight">[0-9]</span> <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Character Sets: Digit Range</span></h1>

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
title: 'Repetitions'
---

<h1>Repetitions <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions</span></h1>

<p>Some special characters are used to specify how many times a character will be repeated in the text. These special characters are the plus <span class="highlight-gray">+</span>, the asterisk <span class="highlight-gray">*</span>, and the question mark <span class="highlight-gray">?</span>.</p>

---
title: 'Repetitions: Asterisk'
---

<h1>Asterisk  <span class="header-one-highlight">*</span> <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions: Asterisk</span></h1>

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
title: 'Repetitions: The Plus'
---

<h1>Plus Sign  <span class="header-one-highlight">+</span> <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions: The Plus</span></h1>

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
title: 'Repetitions: The Question Mark'
---

<h1>Question Mark  <span class="header-one-highlight">?</span> <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions: The Question Mark</span></h1>

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
title: 'Repetitions: Curly Braces'
---

<h1>Curly Braces - 1 <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions: Curly Braces</span></h1>

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
title: 'Repetitions: Curly Braces'
---

<h1>Curly Braces - 2 <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions: Curly Braces</span></h1>

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
title: 'Repetitions: Curly Braces'
---

<h1>Curly Braces - 3 <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Repetitions: Curly Braces</span></h1>

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

---
title: 'Grouping'
---

<h1>Parentheses  <span class="header-one-highlight">()</span>: Grouping <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Grouping</span></h1>

<p>We can group an expression and use these groups to reference or enforce some rules. To group an expression, we enclose <span class="highlight-gray">()</span> in parentheses. For now just group <span class="highlight-gray">haa</span> below.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
ha-ha, <span class="highlight-green">haa</span>-<span class="highlight-green">haa</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/(haa)/g
```
</v-click>

---
title: 'Group Reference'
---

<h1>Referencing a Group <span class="float-right text-xs rounded-sm px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Group Reference</span></h1>

<p>The words <span class="highlight-gray">ha</span> and <span class="highlight-gray">haa</span> are grouped below. The first group is used by writing <span class="highlight-gray">\1</span> to avoid rewriting. Here 1 denotes the order of grouping. Type <span class="highlight-gray">\2</span> at the end of the expression to refer to the second group.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">ha-ha,haa-haa</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/(ha)-\1,(haa)-\2/g
```
</v-click>

---
title: 'Non-capturing Grouping'
---

<h1>Parentheses <span class="header-one-highlight">(?:)</span>: Non-capturing Grouping <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Non-capturing Grouping</span></h1>

<p>You can group an expression and ensure that it is not captured by references. For example, below are two groups. However, the first group reference we denote with <span class="highlight-gray">\1</span> actually indicates the second group, as the first is a non-capturing group.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">ha-ha,haa-haa</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/(?:ha)-ha,(haa)-\1/g
```
</v-click>

---
title: 'Alternation'
---

<h1>Pipe Character <span class="header-one-highlight">|</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Alternation</span></h1>

<p>It allows to specify that an expression can be in different expressions. Thus, all possible statements are written separated by the pipe sign <span class="highlight-gray">|</span>. This differs from charset <span class="highlight-gray">[abc]</span>, charsets operate at the character level. Alternatives are at the expression level. For example, the following expression would select both <span class="highlight-gray">cat</span> and <span class="highlight-gray">rat</span>. Add another pipe sign <span class="highlight-gray">|</span> to the end of the expression and type <span class="highlight-gray">dog</span> so that all words are selected.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">cat</span> <span class="highlight-green">rat</span> <span class="highlight-green">dog</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/(c|r)at|dog/g
```
</v-click>

---
title: 'Escape Character'
---

<h1>Escape Character <span class="header-one-highlight">\</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Escape Character</span></h1>

<p>There are special characters that we use when writing regex. <span class="highlight-gray">{ } [ ] / \ + * . $^ | ?</span> Before we can select these characters themselves, we need to use an escape character <span class="highlight-gray">\</span>. For example, to select the dot <span class="highlight-gray">.</span> and asterisk <span class="highlight-gray">*</span> characters in the text, let's add an escape character <span class="highlight-gray">\</span> before it.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
(<span class="highlight-green">*</span>) Asterisk<span class="highlight-green">.</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/(\*|\.)/g
```
</v-click>

---
title: 'Start of The String'
---

<h1>Caret Sign <span class="header-one-highlight">^</span>: Selecting by Line Start
 <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Start of The String</span></h1>

<p>We were using <span class="highlight-gray">[0-9]</span> to find numbers. To find only numbers at the beginning of a line, prefix this expression with the <span class="highlight-gray">^</span> sign.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
Basic Omellette Recipe
<br/><br/>
<span class="highlight-green">1</span>. 3 eggs, beaten<br/>
<span class="highlight-green">2</span>. 1 tsp sunflower oil<br/>
<span class="highlight-green">3</span>. 1 tsp butter
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/^[0-9]/g
```
</v-click>

---
title: 'End of The String'
---

<h1>Dollar Sign <span class="header-one-highlight">$</span>: Selecting by End of Line
 <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">End of The String</span></h1>

<p>Let's use the <span class="highlight-gray">$</span> sign after the <span class="highlight-gray">html</span> value to find the <span class="highlight-gray">html</span> texts only at the end of the line.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
https://domain.com/what-is-html.<span class="highlight-green">html</span><br/>
https://otherdomain.com/html-elements<br/>
https://website.com/html5-features.<span class="highlight-green">html</span><br/>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/html$/g
```
</v-click>

---
title: 'Alphanumeric'
---

<h1>Word Character <span class="header-one-highlight">\w</span><span class="text-2xl">: Letter, Number and Underscore</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Alphanumeric</span></h1>

<p>The expression <span class="highlight-gray">\w</span> is used to find letters, numbers and underscore characters. Let's use the expression <span class="highlight-gray">\w</span> to find word characters in the text.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">a</span><span class="highlight-green">b</span><span class="highlight-green">c</span><span class="highlight-green">A</span><span class="highlight-green">B</span><span class="highlight-green">C</span><span class="highlight-green">1</span><span class="highlight-green">2</span><span class="highlight-green">3</span><span class="highlight-green">_</span>.:!?
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/\w/g
```
</v-click>

---
title: 'Non-alphanumeric'
---

<h1>Except Word Character <span class="header-one-highlight">\W</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Non-alphanumeric</span></h1>

<p>The expression <span class="highlight-gray">\W</span> is used to find characters other than letters, numbers, and underscores.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
abcABC123<span class="highlight-green">&nbsp;</span>_<span class="highlight-green">.</span><span class="highlight-green">:</span><span class="highlight-green">!</span><span class="highlight-green">?</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/\W/g
```
</v-click>

---
title: 'Digits'
---

<h1>Number Character <span class="header-one-highlight">\d</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Digits</span></h1>

<p><span class="highlight-gray">\d</span> is used to find only number characters.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
abcABC<span class="highlight-green">1</span><span class="highlight-green">2</span><span class="highlight-green">3</span> .:!?
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/\d/g
```
</v-click>

---
title: 'Non-digits'
---

<h1>Except Number Character <span class="header-one-highlight">\D</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Non-digits</span></h1>

<p><span class="highlight-gray">\D</span> is used to find non-numeric characters.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">a</span><span class="highlight-green">b</span><span class="highlight-green">c</span><span class="highlight-green">A</span><span class="highlight-green">B</span><span class="highlight-green">C</span>123<span class="highlight-green">&nbsp;</span><span class="highlight-green">.</span><span class="highlight-green">:</span><span class="highlight-green">!</span><span class="highlight-green">?</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/\D/g
```
</v-click>

---
title: 'Whitespace Characters'
---

<h1>Space Character <span class="header-one-highlight">\s</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Whitespace Characters</span></h1>

<p><span class="highlight-gray">\s</span> is used to find only space characters.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
abcABC123<span class="highlight-green">&nbsp;</span>.:!?
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/\s/g
```
</v-click>

---
title: 'Non-whitespace Characters'
---

<h1>Except Space Character <span class="header-one-highlight">\S</span> <span class="float-right text-xs rounded-sm	px-1 border-double border-4 border-indigo-600 dark:border-indigo-200">Non-whitespace Characters</span></h1>

<p><span class="highlight-gray">\S</span> is used to find non-space characters.</p>

<v-click>
<div class="text-lg border-b-2 border-indigo-500 w-fit">Text</div>
<div class="text-sm mt-2 glass-card mb-5">
<span class="highlight-green">a</span><span class="highlight-green">b</span><span class="highlight-green">c</span><span class="highlight-green">A</span><span class="highlight-green">B</span><span class="highlight-green">C</span><span class="highlight-green">1</span><span class="highlight-green">2</span><span class="highlight-green">3</span><span class="mx-1">&nbsp;</span><span class="highlight-green">.</span><span class="highlight-green">:</span><span class="highlight-green">!</span><span class="highlight-green">?</span>
</div>
</v-click>

<v-click>
<div class="text-lg mb-2 border-b-2 border-indigo-500 w-fit">Regex</div>

```regex
/\S/g
```
</v-click>

