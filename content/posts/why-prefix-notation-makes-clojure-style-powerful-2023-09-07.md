+++
date = '2023-09-07T11:41:33+02:00'
draft = false
title = 'Why Prefix Notation Makes Clojure Style Powerful 2023 09 07'
+++

I have been working as a software engineer for almost 15 years from now, and I have experience with different kinds of programming languages, from procedural to object-oriented, and since 2019 with functional like Lisp-style as Clojure. I have no preferences for the languages, to be honest, I always say that each one serves one purpose. That said when we talk about solving math problems, well, the languages that adopt the Prefix/Polish notation are far more simple and powerful than others, and I'll briefly show you why.

Zoom image will be displayed

First, let's step back a little bit and review the math basis. Overall, mathematics often hailed as the universal language, is a field where precision and clarity are paramount. In the quest for efficient problem-solving and communication, mathematicians have developed various notations. One such powerful notation system is Polish notation, also known as prefix notation. Polish notation revolutionizes the way mathematical expressions are written and calculated. The Polish notation was developed by **Jan Łukasiewicz** in 1931 when he figured out that is much more logical than the classical infix notation. I'm not going through the history and reasons why OK? For that, I recommend a read of the book [Enter: Reverse Polish Notation Made Easy](https://www.amazon.com/Enter-Reverse-Polish-notation-made/dp/0961217421). A fun fact about this book is it was made to help the owners of **Series 10 HP calculators** 😅, but chapters 1 and 2 are focused on the Polish notation itself, which I recommend.

That said, here’s some key takeaways on why Polish notation is so powerful:

1.  **Simplicity and Clarity**: Polish notation simplifies mathematical expressions by removing the ambiguity found in traditional infix notation. In the standard notation, parentheses are often required to indicate the order of operations. However, Polish notation eliminates this need, making expressions more straightforward. For example, the expression _**“3 + 5 × 2”**_ would be written as **“+ 3 × 5 2”** in Polish notation, making it clear that addition should be performed first, followed by multiplication.
    
2.  **No Ambiguity**: In infix notation, complex expressions can lead to confusion regarding the order of operations. Polish notation eliminates this ambiguity entirely. Each operator is placed before its operands, leaving no room for misinterpretation. This clarity is particularly useful when working with intricate mathematical problems.
    
3.  **Efficient Calculation**: Polish notation lends itself to efficient and systematic calculations. Using a stack-based approach, calculations in Polish notation can be performed without the need for parentheses or complex rules. When evaluating a Polish expression, you simply traverse the expression from left to right, and operations are performed as soon as the required number of operands is available. This efficiency is valuable in computer programming and symbolic mathematics.
    
4.  **Versatility**: Polish notation is versatile and can represent a wide range of mathematical operations and functions. It accommodates unary and binary operators, making it suitable for various mathematical contexts, including algebra, calculus, and logic. Its flexibility contributes to its power as a mathematical notation.
    
5.  **Reduced Error**: And gosh, I love this one. Due to its clarity and lack of ambiguity, Polish notation reduces the chances of making calculation errors. When using traditional infix notation, misplaced parentheses or incorrect order of operations can lead to mistakes. Polish notation minimizes these risks, making it a reliable choice for mathematical calculations.
    
6.  **Perfect for programming languages**: In software and symbolic mathematics, Polish notation is highly compatible with algorithms and automated processes. Its structured format allows for straightforward parsing and evaluation by machines, making it an essential tool for software development and computer-based mathematics.
    

That said, let's image a snippet of code that needs to get all Credit Card purchases on a defined month, with polish notation, you just need to add a sum symbol after a list of values, something like that:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   (+ (filter monthly-bases credit-card-purches))   `

In a language that uses in-fix notation, you should probably do a kind of loop to do the same, also doing this weird and dangerous variable value, like that:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   for(let i = 0; i < creditCardPurchases.length; i++){    billAmount += creditCardPurchases[i].value; };   `

And even if you try to avoid loops, like using reduce, will look simple while our code does not have too many features, like that:

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   var billAmount = creditCardPurchases.reduce(function(a,b){    return a+b;}, 0);   `

Now, try to do a simple review of the code that you ever made and think how many times you need to do a loop kind to deal with this approach of using infix notation only. Well, that's it, that way of doing calculus is too simple and powerful.

**Conclusion**: Polish notation, with its simplicity, clarity, and efficiency, stands as a powerful tool in the realm of mathematics. Its ability to eliminate ambiguity, reduce errors, and enhance automation makes it a valuable notation system for mathematicians, engineers, computer scientists, and anyone who deals with mathematical expressions. As we continue to explore the frontiers of mathematics and computation, Polish notation remains a steadfast ally in our pursuit of precision and efficiency.

When you’re coding in clojure, you don’t need operator overloading, you might want to define plus on your own datatype. In Java, you basically can’t touch the plus. In Python, you might have a better chance, but you’d still have to “extend standard plus semantics”. In Clojure, you can just provide your own math namespace and do (your.math/\* y z). You could justimport your own plus and avoid the default provided one. Some languages allow you to create your own operators. Haskell is one of them. But in Haskell, you have to keep the infix table in mind. Each infix operator has its precedence (higher precedence is “collected together first”) and fixity (whether a + b + c = (a + b) + c (infix) or a + b + c = a + (b + c) (infixr)).

You basically don’t need to remember the infix operator associativity table. No extra fuzz, just use functions with good names. Deliver bugless math software, and have fun.