# C-Sharp Style Guide

It is inspired by [Microsoft best practices](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions).


## Table of Contents
  1. [Naming](#Naming)
  1. [Whitespace](#whitespace)
      1. [Indentation](#indentation)
      2. [Linq-indentation](#linq-indentation)
      3. [Newlines](#newlines)
  2. [Line Length](#line-length)
  3. [Commenting](#commenting)
      1. [File/class-level comments](#fileclass-level-comments)
      2. [Function comments](#function-comments)
      3. [Block and inline comments](#block-and-inline-comments)
      4. [Punctuation, spelling, and grammar](#punctuation-spelling-and-grammar)
      5. [TODO comments](#todo-comments)
      6. [Commented-out code](#commented-out-code)
  4. [Methods](#methods)
  5. [Conditional Expressions](#conditional-expressions)
      1. [Conditional keywords](#conditional-keywords)
  8. [Classes](#classes)
  9. [Exceptions](#exceptions)
  10. [Collections](#collections)
  10. [Models](#models)
  11. [Strings](#strings)
  12. [Regular Expressions](#regular-expressions)
  15. [Be Consistent](#be-consistent)
  16. [Translation](#translation)

## Naming

We should allways try to follow the best practice naming of c# and the framework in use.

[C-Sharp caming convention](./Naming/readme.md)

## Whitespace

### Indentation

* <a name="default-indentation"></a>Use tabs with a
    4-space indent.<sup>[[link](#default-indentation)]</sup>
* <a name="linq-indentation"></a>
when using linq, allways add modifyers on new lines.<sup>[[link](#linq-indentation)]</sup>
```csharp
// bad
var newList = list.Select(x => x.Value).Where(x => !string.IsNullOrEmptyx)).ToArray()

// Good
var newList = list
                .Select(x => x.Value)
                .Where(x => !string.IsNullOrEmpty(x))
                .ToArray()
```


### Newlines

* <a name="newlines-braces"></a>Braces ind conditionals should always be on a new line.<sup>[[link](#newlines-braces)]</sup>

```csharp
// Bad
if (true) {
    // do stuff...
}

// Bad
if (true) // do stuff...

// Good
if (true)
{
    // do stuff...
}
```
* <a name="newlines-loops"></a>Braces in loops should always be on a new line.<sup>[[link](#newlines-loops)]</sup>

```csharp
// Bad
foreach (var item in items) {
    // do stuff...
}

// Bad
foreach (var item in items) // do stuff...

// Good
foreach (var item in items)
{
    // do stuff...
}

// Good
for (var index = 0; index < 10; index++)
{
    // do stuff...
}
```

* <a name="space-between-functions"></a>Allways space between functions.<sup>[[link](#space-between-functions)]</sup>

```csharp
// Bad
void FirstFunction () 
{
    // do stuff...
}
void SecondFunction () 
{
    // do stuff...
}

// Good
void FirstFunction () 
{
    // do stuff...
}

void SecondFunction () 
{
    // do stuff...
}
```

* <a name="space-after-local-variables"></a>Space after local variables.<sup>[[link](#space-after-local-variables)]</sup>

```csharp
// Bad
class MyClass 
{
    string FirstString { get; set; }
    string SecondString { get; set; }
    MyClass() 
    {
        // constructor
    }
}

// Good
class MyClass 
{
    string FirstString { get; set; }
    string SecondString { get; set; }

    MyClass() 
    {
        // constructor
    }
}
```

* <a name="no-tailing-spaces"></a>Functions and classes, should never end with spaces or newlines.<sup>[[link](#no-tailing-spaces)]</sup>

```csharp
// Bad
class MyClass 
{
    void MyFunction() 
    {
        // do work

    }

}

// Good
class MyClass 
{
    void MyFunction() 
    {
        // do work 
    }
}
```
## Line Length

* Keep each line of code to a readable length. Unless
  you have a reason to, keep lines to fewer than 100 characters.

## Commenting

> First and foremost, code easy readable code, with explicitly named variable names, explicitly named functions.
> 
> When having nice and readable code, comments should only be nessesarry in rare occations.
> 
> remember: while comments are very important, the best code is
> self-documenting. Giving sensible names to types and variables is much better than using obscure names that you must then explain through comments.
>
> When writing your comments, write for your audience: the next contributor who
> will need to understand your code. Be generous — the next one may be you!

### TODO comments

Use TODO comments for code that is temporary, a short-term solution, or
good-enough but not perfect.

TODOs should include the string TODO in all caps, followed by the name
of the person who can best provide context about the problem referenced by the TODO. A comment explaining what there is to do is required. 

The main purpose is to have a consistent TODO format that can be searched to find the person who can provide more details upon request.

A TODO is not a commitment that the person referenced will fix the problem. Thus when you create a TODO, it is almost always your name that is given.

Bad:
```csharp
// TODO: Improve me
return (-b + Math.Sqrt(b * b - 4 * a * c)) / (2 * a);
```

Good:
```csharp
// TODO: John Doe (2019-05-25): Simplify this, and improve readability
return (-b + Math.Sqrt(b * b - 4 * a * c)) / (2 * a);
```

#### Hacks
We prefer not using hacks, so we should rarely use the hack annotation. If a hack is present, add a #warning instead. So we are aware on each build.

bad:
```csharp
// HACK: quick fix
return (-b + Math.Sqrt(b * b - 4 * a * c)) / (2 * a);
```

good:
```sharp
#warning Durty quickfix, should be simplified
return (-b + Math.Sqrt(b * b - 4 * a * c)) / (2 * a);
```

#### StackOverflow or other sources
If code is copied or refrenced from the internet e.g. stackoverflow, remember to add the source of your solution as a comment.

bad:
```csharp
    void MyFunction() 
    {
        // do work 
    }
```

good:
```csharp
    // source: https://stackoverflow.com/somesolution
    void MyFunction() 
    {
        // do work 
    }
```
### Unfinished work / known errors

#### Warnings
Warnings are used when you know somthing is about to change or be deprecated. Warnings should be used when you know the code should change in the near future.

```sharp
#warning This is dirty code...
```

#### Errors
Errors should only be used in rare occasions. If you know the outcome of the code is highly error prone, wrong or just incomplete. throwing exceptions are preffered, if possible, but if project is not suppose be be buildable, the error can be used in rare occations. Ususally used if you leave the office with a half finished functions or classes.

```sharp
#error Fix this before everything explodes!
```
### Commented-out code

* <a name="commented-code"></a>Never leave commented-out code in our codebase.
    <sup>[[link](#commented-code)]</sup>

## Methods

### Method naming
Allways use informative naming when naming your functions.
Naming should be informative for the action.

```csharp
# Bad
bool Valid(string name)
{
    return true;
} 

# Good
bool IsNameValid(string name)
{
    return true;
} 
```

### Method calls
When a method has a lot of parameters, eksplicitly use the parameter name in your method call:

```csharp
bool IsUserAuthorized(User user, Company company, UserToken usertoken)
{
    // do work ...
}

# Bad
var isAuthorized = IsUserAuthorized(user, company, token);

# Good
var isAuthorized = IsUserAuthorized(user: user, company: company, usertoken: token);
```

### Conditionals operator
<a name="avoid-complex-Conditionals"></a>Avoid using complex conditionals.<sup>[[link](#avoid-complex-Conditionals)]</sup>

Conditionals should be easily readable.
```csharp
# bad
bool IsUserAuthorizedGuard(User user, string companyId)
{
    var auth = user?.CompanyId == companyId || (bool)user?.Roles?.Contains(companyId);
    return auth == true;
}

# good
public bool IsUserAuthorizedGuard(User user, string companyId)
{
    if (user == null)
    {
        return false;
    }

    if (user.CompanyId == companyId) 
    {
        return true;
    }
    
    if (user.Roles.Contains(companyId))
    {
        return true;
    }

    return false;
}
```

### Ternary operator

<a name="avoid-complex-ternary"></a>Avoid the ternary operator (`condition ? option1 : option2;`) except in cases where all expressions are extremely trivial.<sup>[[link](#avoid-complex-ternary)]</sup>

```csharp
# Bad
bool IsUserAuthorizedGuard(bool auth)
{
    return auth ? true : false;
}

# Good
public bool IsUserAuthorizedGuard(bool auth)
{
    if (auth == true)
    {
        return true;
    }

    return false;
}
```

<a name="no-nested-ternaries"></a>Never use more then one expression per branch in a ternary operator. This also means that ternary operators must never be nested. Prefer `if/else` constructs in these cases.<sup>[[link](#no-nested-ternaries)]</sup>

```csharp
// Bad
return some_condition ? (nested_condition ? nested_something : nested_something_else) : something_else;

// Better
if (some_condition) 
{
    return nested_condition ? nested_something : nested_something_else;
}
return something_else 
```

### Nested conditionals

* <a name="no-nested-conditionals"></a>
  Avoid the use of nested conditionals for flow of control.
  ([More on this][avoid-else-return-early].) <sup>[[link](#no-nested-conditionals)]</sup>

  Prefer a guard clause when you can assert invalid data. A guard clause is a conditional statement at the top of a function that returns as soon as it can.

  The general principles boil down to:
  * Return immediately once you know your function cannot do anything more.
  * Reduce nesting and indentation in the code by returning early. This makes the code easier to read and requires less mental bookkeeping on the part of the reader to keep track of `else` branches.
  * The core or most important flows should be the least indented.

```csharp
// bad
void Compute()
{
    var server = findServer;
    if (server)
    {
        var client = server.client;
        if (client)
        {
            var request = client.makeRequest;
            if (request)
            {
                ProcessRequest(request);
            }
        }
    }
}

# good
void Compute()
{
    var server = findServer;
    if (server == null)
    {
        return;
    }

    var client = server.client;
    if (client == null)
    {
        return;
    }

    var request = client.makeRequest;
    if (request == null)
    {
        return;
    }

    ProcessRequest(request);
}
```

## Syntax

* <a name="redundant-self"></a>Prefer `SomeMethod` over `base.SomeMethod` when calling a method on the current instance.<sup>[[link](#redundant-self)]</sup>

```csharp
// Bad
class A 
{
    protected virtual void Foo() 
    {
        Console.WriteLine("I'm A");
    }
}

class B : A {
    public void Bar() {
        base.Foo();
    }
}

// Good
class A 
{
    protected virtual void Foo() 
    {
        Console.WriteLine("I'm A");
    }
}

class B : A {
    public void Bar() {
        Foo();
    }
}
```

## Classes
Prefer using classes to encapsulate logic. 
* <a name="prefer-class-encapsulation"></a>Indent the `public`, `protected`, and
    `private` methods as much the method definitions they apply to. Leave one
    blank line above and below them.<sup>[[link](#access-modifiers)]</sup>

```csharp

// less preffered
void MyFunction() 
{
    DoMyStuff(baseModel);
}

void DoMyStuff(BaseModel baseModel)
{
    // Do stuff
}

// Good
void MyFunction() 
{
    new SomeClass(baseModel).Execute();
}

public class SomeClass
{
    readonly BaseModel _baseModel;

    public SomeClass(BaseModel baseModel)
    {
        _baseModel = baseModel;
    }

    public void Execute()
    {
        // Do stuff
    }
}
```
## Guards
Encapsulate guards. 
<a name="guard-encapsulation"></a>Encapsulation of guards is preffered. Throw a suitable error, with a suitable errormessage if guard fails.<sup>[[link](#guard-encapsulation)]</sup>

```csharp

// Bad
void DoMyStuff() 
{
    var allowed = CanIDoMyStuff(myModel);
    if (!allowed)
    {
        // handle
    }
}

public bool CanIDoMyStuff(MyModel myModel)
{
    // Do stuff
}

// Good
void MyFunction() 
{
    new CanIDoMyStuff(baseModel).Execute();
    // Do my stuff
    // If the i failed my guard, the guard should have thrown an exception.
}

public class CanIDoMyStuff
{
    readonly BaseModel _baseModel;

    public CanIDoMyStuff(BaseModel baseModel)
    {
        _baseModel = baseModel;
    }

    public void Execute()
    {
        if (notAllowd)
        {
            throw new UnauthorizedAccessException("Not allowed"); 
        }
    }
}
```

## Exceptions

* <a name="exception-flow-control"></a>Prefer not to control your flow though exception. And allways use your exception in a try/catch.
    <sup>[[link](#exception-flow-control)]</sup>

```csharp
// Bad
try
{
    DoOneThing();
}
catch (Exception exception)
{
    DoAnotherThing();
}

// Good
try
{
    DoOneThing();
}
catch (Exception exception)
{
    Log.Error(exception);
    throw exception;
}
```

* <a name="dont-rescue-exception"></a>Avoid rescuing the `Exception`. We throw exceptions to stop the action. Allways throw exception with an intention to stop further execution.
    <sup>[[link](#dont-rescue-exception)]</sup>

```csharp
// Bad
try
{
    // do somthing i would expect to fail.
}
catch
{
    // catch and carry on.
}

// Good
try
{
    // do somthing i wouldnt except could fail.
}
catch (Exception exception)
{
    // use your exception for logging/reporting and stop the execution flow.
    Log.Error(exception);
    throw exception;
}
```

* <a name="redundant-exception"></a>Don't specify `RuntimeError` explicitly in the two argument version of raise. Prefer error sub-classes for clarity and explicit error creation.<sup>[[link](#redundant-exception)]</sup>

```csharp
// Bad
void MyErrorFunction() 
{
    throw;
}

// Bad, but better
void MyErrorFunction() 
{
    throw "my error";
}

// Good
void MyErrorFunction() 
{
    throw new UserDefinedException("my error");
}

// Good
void MyErrorFunction() 
{
    throw new NotAuthorizedExeception("my error");
}
```

## Collections

* <a name="list-over-array"></a>Prefer `list` over
    `array`.<sup>[[link](#list-over-array)]</sup>
```csharp
# Bad
string[] ArrayOfStrings = new string[]{ "sting1", "string2" };

# Good
List<string> ListOfStrings = new List<string>{ "sting1", "string2" };

```
When using lists in a model, allways instansiate the list in the constructor:
```csharp
// Bad
class MyModel 
{
    public List<string> ListOfStrings;
}

// Good
class MyModel 
{
    public List<string> ListOfStrings;

    public MyModel() 
    {
       ListOfStrings = new List<string>();
    }
}
```

## Strings

* <a name="string-interpolation"></a>Prefer string interpolation instead of string concatenation:<sup>[[link](#string-interpolation)]</sup>

```csharp
// Bad
var emailWithName = user.Name + ' <' + user.Email + '>';

// Better
var emailWithName = string.Format("{0} <{1}>", user.Name, user.Email);

// Good
var emailWithName = $"{user.Name} <{user.Email}>";
```

## Be Consistent

> If you're editing code, take a few minutes to look at the code around you and determine its style. If they use spaces around all their arithmetic operators, you should too. If their comments have little boxes of hash marks around them, make your comments have little boxes of hash marks around them too.
>
> The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you're saying rather than on how you're saying it. We present global style rules here so people know the vocabulary, but local style is also important.
> 
> If the code you add to a file looks drastically different from the existing code around it, it throws readers out of their rhythm when they go to read it. - Avoid this.