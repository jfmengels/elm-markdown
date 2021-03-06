# Original - links_reference_style

## Example undefined

This markdown:

````````````markdown
Foo [bar] [1].

Foo [bar][1].

Foo [bar]
[1].

[1]: /url/  "Title"


With [embedded [brackets]] [b].


Indented [once][].

Indented [twice][].

Indented [thrice][].

Indented [four][] times.

 [once]: /url

  [twice]: /url

   [thrice]: /url

    [four]: /url


[b]: /url/

* * *

[this] [this] should work

So should [this][this].

And [this] [].

And [this][].

And [this].

But not [that] [].

Nor [that][].

Nor [that].

[Something in brackets like [this][] should work]

[Same with [this].]

In this case, [this](/somethingelse/) points to something else.

Backslashing should suppress \[this] and [this\].

[this]: foo


* * *

Here's one where the [link
breaks] across lines.

Here's another where the [link 
breaks] across lines, but with a line-ending space.


[link breaks]: /url/

````````````

Should give output:

````````````html
<p>Foo<a href="/url/" title="Title">bar</a>.</p><p>Foo<a href="/url/" title="Title">bar</a>.</p><p>Foo<a href="/url/" title="Title">bar</a>.</p><p>With<a href="/url/">embedded [brackets]</a>.</p><p>Indented<a href="/url">once</a>.</p><p>Indented<a href="/url">twice</a>.</p><p>Indented<a href="/url">thrice</a>.</p><p>Indented [four][] times.</p><pre><code>[four]: /url</code></pre><hr><p><a href="foo">this</a>should work</p><p>So should<a href="foo">this</a>.</p><p>And<a href="foo">this</a>.</p><p>And<a href="foo">this</a>.</p><p>And<a href="foo">this</a>.</p><p>But not [that] [].</p><p>Nor [that][].</p><p>Nor [that].</p><p>[Something in brackets like<a href="foo">this</a>should work]</p><p>[Same with<a href="foo">this</a>.]</p><p>In this case,<a href="/somethingelse/">this</a>points to something else.</p><p>Backslashing should suppress [this] and [this].</p><hr><p>Here&#39;s one where the<a href="/url/">link breaks</a>across lines.</p><p>Here&#39;s another where the<a href="/url/">link breaks</a>across lines, but with a line-ending space.</p>
````````````

But instead was:

````````````html
<p>Foo [bar]<a href="/url/" title="Title">1</a>.</p><p>Foo<a href="/url/" title="Title">bar</a>.</p><p>Foo [bar]<a href="/url/" title="Title">1</a>.</p><p>With [embedded [brackets]]<a href="/url/">b</a>.</p><p>Indented [once][].</p><p>Indented [twice][].</p><p>Indented [thrice][].</p><p>Indented [four][] times.</p><p>[once]: /url</p><p>[twice]: /url</p><p>[thrice]: /url</p><pre><code>[four]: /url</code></pre><hr><p><a href="foo">this</a><a href="foo">this</a>should work</p><p>So should<a href="foo">this</a>.</p><p>And<a href="foo">this</a>[].</p><p>And<a href="foo">this</a>.</p><p>And<a href="foo">this</a>.</p><p>But not [that] [].</p><p>Nor [that][].</p><p>Nor [that].</p><p>[Something in brackets like<a href="foo">this</a>should work]</p><p>[Same with<a href="foo">this</a>.]</p><p>In this case,<a href="/somethingelse/">this</a>points to something else.</p><p>Backslashing should suppress [this] and [this].</p><hr><p>Here&#39;s one where the [link breaks] across lines.</p><p>Here&#39;s another where the [link breaks] across lines, but with a line-ending space.</p>
````````````
