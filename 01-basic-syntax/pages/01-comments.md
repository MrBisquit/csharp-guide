# Basic Syntax: Comments

[Go back](../README.md)
&bullet;
/ [A complete beginners guide to C#](/README.md)
/ [Basic Syntax](../README.md)
/ Comments /

## Summary
This page tells you how to use them, with examples.

## Table Of Contents

1. [ ] [Comments](#comments)
2. [ ] [Where and how to use them](#where-and-how-to-use-them)
    - [ ] [Single-line comments](#single-line-comments)
    - [ ] [Multi-line (block) comments](#multi-line-block-comments)
    - [ ] [XMLDoc comments](#xmldoc-comments)

### Comments

In C#, there are a few different ways to use comments, including
what are called "code hints," which are also referred as different
names in their various different languages. In C#, they are called
"XMLDocs"[<sup>[1]</sup>](#ref-1).

The other types of comments, single-line, and multi-line (block) comments.

### Where and how to use them

When commenting in your code, it is a good idea to leave various comments
about how things work. However, excessive commenting can be quite annoying
when reading code.

Sometimes, when you are programming, you will get annoyed at the fact that
something is done in a dumb way, or for a number of other reasons.
In these cases, a lot of people write comments with profanity in, you'll
even see in the source code from some versions of Windows that the
developers were getting annoyed at their own compiler, so left a lot of
comments, mainly saying things like "doing x to shut MSVC up".

Using profanity in comments is fairly normal, but sometimes quite frowned
upon, so it's a good idea to be careful where you are using it.

Comments can also be used to temporarily remove some chunk of a file from
being compiled. This is good for debugging, but if you are using version
control, like git[<sup>[2]</sup>](#ref-2), you can just remove the chunks
from the code entirely, since the changes will be saved, and you can always
get it back later.

#### Single-line comments

These comments span a single line, and are good for little comments.
The syntax for a single line comments is two forward slashes (`//`) at the
beginning of the comment.

These single-line comments can either be used on their own line, or on the
end of a line. Some examples:
```cs
// I am a single line comment
int life = 42; // Meaning of line
```

#### Multi-line (block) comments

Multi-line comments span multiple lines, and can also be used inline.
The syntax for multi-line comments is slightly different, as you
must use the prefix, and suffix asterisk forward slash combination.

For the prefix (meaning at the start), you must use a forward slash
followed by an asterisk (`/*`).
For the suffix (meaning at the end), you must use an asterisk followed
by a forward slash (`*/`).
A simple example of this is just `/* ... */`.

Some examples:
```cs
string johny = /* five */ "is alive!"; // As an inline comment
/*
    This is a multi-line comment.
    
    public static void Main(string[] args) {
        Console.WriteLine("Hello World!");
    }
*/
```

#### XMLDoc comments

XMLDoc comments are used mainly for giving the IDE (Integrated Development
Environment) information about the method, class, variable, etc...
This is especially useful when developing a library, as XMLDoc comments are
included in things such as NuGet Packages (the package manager typically
used with C# .NET), or just linked libraries in general.

XMLDocs use the same syntax as, you guessed it... XML! Most IDEs will add
the basic structure of the XMLDocs if you type three forward slashes (`///`)
above a variable, class, method, etc...

For example, in Visual studio, if you type three forward slashes above
```cs
public int Add(int a, int b) {
    return a + b;
}
```
It will add the following:
```cs
/// <summary>
/// 
/// </summary>
/// <param name="a"></param>
/// <param name="b"></param>
/// <returns></returns>
public int Add(int a, int b) {
    return a + b;
}
```
Whenever you hover over where you have used the method `Add`, your IDE
(assuming that it supports XMLDocs), will show you the above information.

---

- <a id="ref-1"><sup>[1]</sup></a>: https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/xmldoc/
- <a id="ref-2"><sup>[2]</sup></a>: https://git-scm.com/