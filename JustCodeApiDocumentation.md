- IComment
	- Returns standard comments
		- C# // and /* */ are returned
		- VB.NET ' and /* */
		- JavaScript // /* */

- IDocComment
	- Returns document comments ///
	- if you want to get a standard comment of //// you need to call IDocComment
	
- IStatement
	- Returns
		- IExpressionStatement 
			- "QuestionsFour();"
			- "cust = new Customer {CustomerID = 2, CustomerName = "Joes Supply", ContactEmail = "joe@supply.com"};"
		- IBlock
		- IVariableDeclaration "var len = _longName.Length;"
		- IReturnStatment "return _longName.Substring(len-1);"
		- IIFStatement
		- IForEachStatement
		
- IDeclaration
	- returns
		- IMethodDeclaration TestApplication.Program.Main(string[])
		- IFieldDeclaration  TestApplication.Program._longName
		- IAnonymousFieldDeclaration TestApplication.Program.(anonymous).OrderID
		- IConstructorDeclaration TestApplication.Program.Program()
		- IClassDeclaration TestApplication.Program
		- IPropertyDeclaration TestApplication.Customer.CustomerID

- IExpression
	- Returns
		- IExtendsClause
		- IMethodInvocation QuestionFour()
		- IStringLiteral "thisisacraxylongname"
		- IMemberAccess _longName    and _longName.Length
		- IVariableAccess  len
		- Iliteral  1
		- IBinaryExpression  len-1
		- IMemberAccess CustomerName
		- IAssignmentExpression   CustomerName = "Bills Bakery"
		- IobjectCreation new List<customer>()
		- IUnaryExpression !newList.Contains(f)   -- Looks to mean not something