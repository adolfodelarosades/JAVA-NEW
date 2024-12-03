# Beginning Java Objects: From Concepts to Code

By Jacquie Barker

![image](https://github.com/user-attachments/assets/6c448c5c-5019-4ce9-8095-ba2487dccd93)

* TIEMPO PARA COMPLETAR: 16h 39min
* NIVEL: Intermedio a avanzado
* HABILIDADES: Java
* PUBLICADO POR: Apretar
* FECHA DE PUBLICACIÓN: Abril de 2023
* LONGITUD DE IMPRESIÓN: 845 páginas

Como lenguaje de programación, la naturaleza orientada a objetos de Java es clave para crear código y aplicaciones potentes y reutilizables que sean fáciles de mantener y ampliar. Dicho esto, muchas personas aprenden la sintaxis de Java sin comprender realmente sus raíces orientadas a objetos, lo que las prepara para no aprovechar todo el poder de Java. ¡Este libro es la clave para aprender ambas cosas!

Esta nueva tercera edición de Beginning Java Objects: From Concepts to Code  analiza la sintaxis de Java, los principios de los objetos y cómo estructurar adecuadamente los requisitos de una aplicación en torno a una arquitectura de objetos. Es única en el sentido de que utiliza un único estudio de caso de un sistema de registro de estudiantes a lo largo del libro, llevando al lector desde los conceptos de objetos hasta el modelado de objetos y la creación de código real para una aplicación completa. Un nuevo capítulo cubre una discusión tecnológicamente neutral de los principios de creación de una arquitectura de tres niveles utilizando Java, introduciendo la noción de separación entre la capa de modelo, la capa de presentación y la capa de datos.

Los ejemplos de codificación que se utilizan en el libro son independientes de la versión de Java. Los principios básicos de la programación orientada a objetos que aprenderá en este libro son atemporales y son relevantes para todas las versiones del lenguaje Java, así como para muchos otros lenguajes orientados a objetos.  

El libro se puede utilizar para el autoaprendizaje individual o como libro de texto de nivel universitario.



#### Lo que aprenderás

Conozca los principios básicos de la orientación a objetos, desde la noción más simple de clases y objetos hasta el poder de la encapsulación, las clases abstractas y el polimorfismo.
Abordar los requisitos de una aplicación para estructurarla adecuadamente en torno a los objetos.
Convertir el modelo de objeto resultante en código Java, creando una capa de modelo funcional completa para el caso de estudio del Sistema de Registro de Estudiantes
Complete conceptualmente una capa de objeto agregando capas de presentación y datos 

#### Para quién es este libro

Desarrolladores de software que nunca han abordado Java como lenguaje de programación, así como aquellos que ya han utilizado Java pero quieren asegurarse de aprovechar al máximo la naturaleza orientada a objetos del lenguaje.

## Table of Contents

### Part I: The ABCs of Objects

#### Chapter 1:​ Abstraction and Modeling

* Simplification Through Abstraction
* Generalization Through Abstraction
* Organizing Abstractions into Classification Hierarchies
* Abstraction as the Basis for Software Development
* Reuse of Abstractions
* Inherent Challenges
* What Does It Take to Be a Successful Object Modeler?​
* Summary

#### Chapter 2:​ Some Java Basics
Java Is Architecture Neutral
Anatomy of a Simple Java Program
Comments
The Class Declaration
The main Method
Setting Up a Simple Java Development Environment
The Mechanics of Java
Compiling Java Source Code into Bytecode
Executing Bytecode
Primitive Types
Variables
Variable Naming Conventions
Variable Initialization
The String Type
Case Sensitivity
Java Expressions
Arithmetic Operators
Relational and Logical Operators
Evaluating Expressions and Operator Precedence
The Type of an Expression
Automatic Type Conversions and Explicit Casting
Loops and Other Flow Control Structures
if Statements
switch Statements
for Statements
while Statements
Jump Statements
Block-Structured Languages and the Scope of a Variable
Printing to the Console Window
print vs.​ println
Escape Sequences
Elements of Java Style
Proper Use of Indentation
Use Comments Wisely
Placement of Braces
Descriptive Variable Names
Summary

#### Chapter 3:​ Objects and Classes
Software at Its Simplest
Functional Decomposition
The Object-Oriented Approach
What Is an Object?​
State/​Data/​Attributes
Behavior/​Operations/​Methods
What Is a Class?​
A Note Regarding Naming Conventions
Declaring a Class, Java Style
Instantiation
Encapsulation
User-Defined Types and Reference Variables
Naming Conventions for Reference Variables
Instantiating Objects:​ A Closer Look
Garbage Collection
Objects As Attributes
A Compilation “Trick”:​ “Stubbing Out” Classes
Composition
The Advantages of References As Attributes
Three Distinguishing Features of an Object-Oriented Programming Language
Summary

#### Chapter 4:​ Object Interactions
Events Drive Object Collaboration
Declaring Methods
Method Headers
Method Naming Conventions
Passing Arguments to Methods
Method Return Types
An Analogy
Method Bodies
Features May Be Declared in Any Order
return Statements
Methods Implement Business Rules
Objects As the Context for Method Invocation
Java Expressions, Revisited
Capturing the Value Returned by a Method
Method Signatures
Choosing Descriptive Method Names
Method Overloading
Message Passing Between Objects
Delegation
Obtaining Handles on Objects
Objects As Clients and Suppliers
Information Hiding/​Accessibility
Public Accessibility
Private Accessibility
Publicizing Services
Method Headers, Revisited
Accessing the Features of a Class from Within Its Own Methods
Accessing Private Features from Client Code
Declaring Accessor Methods
Recommended “Get”/​“Set” Method Headers
IDE-Generated Get/​Set Methods
The “Persistence” of Attribute Values
Using Accessor Methods from Client Code
The Power of Encapsulation Plus Information Hiding
Preventing Unauthorized Access to Encapsulated Data
Helping Ensure Data Integrity
Limiting “Ripple Effects” When Private Features Change
Using Accessor Methods from Within a Class’s Own Methods
Exceptions to the Public/​Private Rule
Constructors
Default Constructors
Writing Our Own Explicit Constructors
Passing Arguments to Constructors
Replacing the Default Parameterless Constructor
More Elaborate Constructors
Overloading Constructors
An Important Caveat Regarding the Default Constructor
Using the “this” Keyword to Facilitate Constructor Reuse
Software at Its Simplest, Revisited
Summary

#### Chapter 5:​ Relationships Between Objects
Associations and Links
Multiplicity
Multiplicity and Links
Aggregation and Composition
Inheritance
Responding to Shifting Requirements with a New Abstraction
(Inappropriate) Approach #1:​ Modify the Student Class
(Inappropriate) Approach #2:​ “Clone” the Student Class to Create a GraduateStudent Class
The Proper Approach (#3):​ Taking Advantage of Inheritance
The “is a” Nature of Inheritance
The Benefits of Inheritance
Class Hierarchies
The Object Class
Is Inheritance Really a Relationship?​
Avoiding “Ripple Effects” in a Class Hierarchy
Rules for Deriving Classes:​ The “Do’s”
Overriding
Reusing Superclass Behaviors:​ The “super” Keyword
Rules for Deriving Classes:​ The “Don’ts”
Private Features and Inheritance
Inheritance and Constructors
A Few Words About Multiple Inheritance
Three Distinguishing Features of an OOPL, Revisited
Summary

#### Chapter 6:​ Collections of Objects
What Are Collections?​
Collections Are Defined by Classes and Must Be Instantiated
Collections Organize References to Other Objects
Collections Are Encapsulated
Three Generic Types of Collection
Ordered Lists
Dictionaries
Sets
Arrays As Simple Collections
Declaring and Instantiating Arrays
Accessing Individual Array Elements
Initializing Array Contents
Manipulating Arrays of Objects
A More Sophisticated Type of Collection:​ The ArrayList Class
Using the ArrayList Class:​ An Example
Import Directives and Packages
The Namespace of a Class
User-Defined Packages and the Default Package
Generics
ArrayList Features
Iterating Through ArrayLists
Copying the Contents of an ArrayList into an Array
The HashMap Collection Class
The TreeMap Class
The Same Object Can Be Simultaneously Referenced by Multiple Collections
Inventing Our Own Collection Types
Approach #1:​ Designing a New Collection Class from Scratch
Approach #2:​ Extending a Predefined Collection Class (MyIntCollection)
Approach #3:​ Encapsulating a Standard Collection (MyIntCollection2​)
Trade-Offs of Approach #2 vs.​ Approach #3
Collections As Method Return Types
Collections of Derived Types
Revisiting Our Student Class Design
The courseLoad Attribute of Student
The transcript Attribute of Student
The transcript Attribute, Take 2
Our Completed Student Data Structure
Summary

#### Chapter 7:​ Some Final Object Concepts
Polymorphism
Polymorphism Simplifies Code Maintenance
Three Distinguishing Features of an Object-Oriented Programming Language
The Benefits of User-Defined Types
The Benefits of Inheritance
The Benefits of Polymorphism
Abstract Classes
Implementing Abstract Methods
Abstract Classes and Instantiation
Declaring Reference Variables of Abstract Types
An Interesting Twist on Polymorphism
Interfaces
Implementing Interfaces
Another Form of the “Is A” Relationship
Interfaces and Casting
Implementing Multiple Interfaces
Interfaces and Casting, Revisited
Interfaces and Instantiation
Interfaces and Polymorphism
The Importance of Interfaces
Static Features
Static Variables
A Design Improvement:​ Burying Implementation Details
Static Methods
Restrictions on Static Methods
Utility Classes
The final Keyword
Custom Utility Classes
Summary

### Part II: Object Modeling 101

#### Chapter 8:​ The Object Modeling Process in a Nutshell
The “Big Picture” Goal of Object Modeling
Modeling Methodology =​ Process + Notation + Tool
My Recommended Object Modeling Process, in a Nutshell
Thoughts Regarding Object Modeling Software Tools
A Reminder
Summary

#### Chapter 9:​ Formalizing Requirements Through Use Cases
What Are Use Cases?​
Functional vs.​ Technical Requirements
Involving the Users
Actors
Identifying Actors and Determining Their Roles
Diagramming a System and Its Actors
Specifying Use Cases
Matching Up Use Cases with Actors
To Diagram or Not to Diagram?​
Summary

#### Chapter 10:​ Modeling the Static/​Data Aspects of the System
Identifying Appropriate Classes
Noun Phrase Analysis
Refining the Candidate Class List
Revisiting the Use Cases
Producing a Data Dictionary
Determining Associations Between Classes
Association Matrices
Identifying Attributes
UML Notation:​ Modeling the Static Aspects of an Abstraction
Classes, Attributes, and Operations
Relationships Between Classes
Reflecting Multiplicity
Object/​Instance Diagrams
Associations As Attributes
Information “Flows” Along an Association “Pipeline”
“Mixing and Matching” Relationship Notations
Association Classes
Our “Completed” Student Registration System Class Diagram
Metadata
Summary

#### Chapter 11:​ Modeling the Dynamic/​Behavioral Aspects of the System
How Behavior Affects State
Events
Scenarios
Scenario #1 for the “Register for a Course” Use Case
Scenario #2 for the “Register for a Course” Use Case
Sequence Diagrams
Determining Objects and External Actors for Scenario #1
Preparing the Sequence Diagram
Using Sequence Diagrams to Determine Methods
Communication Diagrams
Revised SRS Class Diagram
Summary

#### Chapter 12:​ Wrapping Up Our Modeling Efforts
Testing the Model
Revisiting Requirements
Reusing Models:​ A Word About Design Patterns
Summary
Part III: Translating an Object Blueprint into Java Code
Chapter 13:​ A Few More Java Details
Java-Specific Terminology
Java Archive (jar) Files
Creating Jar Files
Inspecting the Contents of a Jar File
Using the Bytecode Contained Within a Jar File
Extracting Contents from Jar Files
“Jarring” Entire Directory Hierarchies
Javadoc Comments
The Object Nature of Strings
Operations on Strings
Strings Are Immutable
The StringBuffer Class
The StringTokenizer Class
Instantiating Strings and the String Literal Pool
Testing the Equality of Strings
Message Chains
Object Self-Referencing with “this”
Java Exception Handling
The Mechanics of Exception Handling
Catching Exceptions
Interpreting Exception Stack Traces
The Exception Class Hierarchy
Catching the Generic Exception Type
Compiler Enforcement of Exception Handling
Taking Advantage of the Exception That We’ve Caught
Nesting of Try/​Catch Blocks
User-Defined Exception Types
Throwing Multiple Types of Exception
Enum(eration)s
Providing Input to Command-Line-Driven Programs
Accepting Command-Line Arguments:​ The args Array
Introducing Custom Command-Line Flags to Control a Program’s Behavior
Accepting Keyboard Input:​ The Scanner Class
Using Wrapper Classes for Input Conversion
Features of the Object Class
Determining the Class That an Object Belongs To
Testing the Equality of Objects
Overriding the equals Method
Overriding the toString Method
Static Initializers
Variable Initialization, Revisited
Variable Arguments (varargs)
Summary

#### Chapter 14:​ Transforming the Model into Java Code
Suggestions for Getting the Maximum Value from This Chapter
The SRS Class Diagram Revisited
The Person Class (Specifying Abstract Classes)
The Student Class (Reuse Through Inheritance, Extending Abstract Classes, Delegation)
The Professor Class (Bidirectionality​ of Relationships)
The Course Class (Reflexive Relationships, Unidirectional Relationships)
The Section Class (Representing Association Classes, Public Static Final Attributes, Enums)
Delegation Revisited
The ScheduleOfClasse​s Class
The TranscriptEntry Association Class (Static Methods)
The Transcript Class
The SRS Driver Program
Summary

#### Chapter 15:​ Building a Three-Tier User Driven Application
A Three-Tier Architecture
What Does the Controller Do?​
Building a Persistence/​Data Tier
Building a Web-Based Presentation Layer
Example Controller Logic
The Importance of Model–Data Layer–View Separation
Summary

Further Reading
Appendix A:​ Alternative Case Studies
Index
