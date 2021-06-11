Microsoft Standards Documentation
https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/?redirectedfrom=MSDN
Naming conventions are particularly helpful

StyleCop and Resharper are tools that can enforce coding standards

properties - noun or noun phrase
methods - verbs
boolean - affirmative phrase

Convey meaning with your code

To avoid cognitive dissidence, meaning of code should be truthful to what the code does. The code shouldn't do more or less than what it says it does.

Everything in software requires
Time, Practice, Thinking(Introspection, bringing your code into the light)

Visual Studio Shortcuts
prop tab tab for a property
ctor tab tab for a constructor
Ctrl shift b to build
Ctrl . for help

All data and no behavior is usually a sign of bad design

Adding class libraries is a great to abstract away and contain concepts.

3 A's of testing
arrange(the data)
act(on the data)
assert(the data is a particular state)

OOP
Encapsulation
	The level of abstraction
	(glance test - at a glance can you see what the code is doing) 
Inheritance
Polymorphism

Responsibilities and Roles
	Knowing
	Deciding
	Doing

YAGNI - You Ain't Gonna Need It
KISS - Keep It Simple, Stupid

Template Pattern - Abstract class with concrete inherited classes

Encapsulation is good
Polymorphism is convenient
Inheritance causes more problems than it solves

Inheritance Critique
Pro: Code Reuse
Con: Binds two classes tightly together. A derived class needs to know details about the base class. This creates


If you don't like the API you see, go off and write the API you want to see in notepad or on a piece of paper.

Code should be written so that it takes the least amount of cognitive load to know what it is doing without having information that is repetitive or unnecessary.

[Scott Allen's 10 Rules] (https://app.pluralsight.com/library/courses/csharp-fundamentals-2/table-of-contents)
1.  Keep classes small - roles, responsibilities
2.  Keep methods short - 1 to 10 lines of code is good. ~20 might be okay. Up to 30 might be worrying. Anything over 60 needs to be refactored. If the method doesn't fit on screen it is harder to understand. Break up strategy to deciding things and doing things
3.  Try to avoid comments - Comments are meaningless. Rewrite the code to have more meaning instead of relying on comments, more intention revealing. API documentation comments are okay.
4.  Try to avoid multiple exits - Makes the flow confusing. Only one return statement at the bottom of the method. Single entry and single exit point. 
5.  Encapsulate complex expressions - it reveals the expressions meaning. Leans more to instant recognition. Look for a singular relationship in the expressions, what do they all have in common and can we encapsulate that?
6.  Warnings are errors - Keeps entropy away. Clean up the warnings. Warnings level to 4 and warnings as errors. In Visual Studio: Project Properties/Build/ Warning level to 4 and Treat Warnings as Error to All
7.  Avoid too many parameters - it causes confusion and is a sign that a class should be used instead. 4 parameters is too much. 4 may signify that the parameters have a relationship.
8.  Avoid Boolean Parameters that are flags to a function - it looks bad and doesn't tell you what it's doing. Requires more thought than what is necessary. Don't allow the client to see it. Okay for private methods that aid the public facing API.
9.  Use Exceptions for errors - use only for errors and not control flow, do not use status codes or returning booleans for errors
10. Avoid #regions - regions are used to hide ugly code and classes that have exploded in size and responsibility

Symmetry is good

Builder Pattern
public class CatBuilder {
	public static CatBuilder DefaultCat() {
		return new CatBuilder();
	}
	public CatBuilder() {
		_cat = new Cat();
		_cat.Name = "Rosie";
		_cat.Age = 1;
	}
	public Cat Build() {
		return _cat;
	}
	public CatBuilder WithOrangeFur() {
		_cat.Fur(Color.Orange);
		return this;
	}
	private Object _cat;
}

Example: var Rosie = CatBuilder.DefaultCat().WithOrangeFur().Build();





