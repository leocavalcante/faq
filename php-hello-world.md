# PHP's "Hello, World!"

# en
I guess PHP is the most straightforward language to output a "Hello, World!" on the screen, it is just exacly `Hello, World!`, no `echo`, no `print`, not even quotes (`"`) are necessary.

That is because **what ever is outside PHP tags is an output.**

Some of you might think it is HTML then, well, not exactly and I know why you folks can be confused about this; it is because usually PHP is used on the web as some kind of HTML pre-processor, then you might think that every output on PHP is some HTML, but that is not quite right.
**Output is output like any other, just a piece of text, the PHP interpreter doesn't know and doesn't care what type of format you are outputting,** for it it is just some text, that is why you can implement APIs that outputs some JSON or XML "instead". What your text might represent is NOT defined in the PHP interpreter when it is outputting something, that is why is wrong to say it is HTML, **it is just some regular text, exactly like doing echo.**
