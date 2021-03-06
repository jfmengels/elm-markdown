# GFM - Tabs

## [Example 2](https://spec.commonmark.org/0.29/#example-2)

This markdown:

````````````markdown
  	foo	baz		bim

````````````

Should give output:

````````````html
<pre><code>foo baz bim</code></pre>
````````````

But instead was:

````````````html
<p>foo baz bim</p>
````````````
## [Example 4](https://spec.commonmark.org/0.29/#example-4)

This markdown:

````````````markdown
  - foo

	bar

````````````

Should give output:

````````````html
<ul><li><p>foo</p><p>bar</p></li></ul>
````````````

But instead was:

````````````html
<p>- foo</p><pre><code>bar</code></pre>
````````````
## [Example 5](https://spec.commonmark.org/0.29/#example-5)

This markdown:

````````````markdown
- foo

		bar

````````````

Should give output:

````````````html
<ul><li><p>foo</p><pre><code>bar</code></pre></li></ul>
````````````

But instead was:

````````````html
<ul><li>foo</li></ul><pre><code>bar</code></pre>
````````````
## [Example 7](https://spec.commonmark.org/0.29/#example-7)

This markdown:

````````````markdown
-		foo

````````````

Should give output:

````````````html
<ul><li><pre><code>foo</code></pre></li></ul>
````````````

But instead was:

````````````html
<p>- foo</p>
````````````
## [Example 9](https://spec.commonmark.org/0.29/#example-9)

This markdown:

````````````markdown
 - foo
   - bar
	 - baz

````````````

Should give output:

````````````html
<ul><li>foo<ul><li>bar<ul><li>baz</li></ul></li></ul></li></ul>
````````````

But instead was:

````````````html
<p>- foo - bar - baz</p>
````````````
## [Example 11](https://spec.commonmark.org/0.29/#example-11)

This markdown:

````````````markdown
*	*	*	

````````````

Should give output:

````````````html
<hr>
````````````

But instead was:

````````````html
<p>* * *</p>
````````````
