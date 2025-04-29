# infr11199---coursework-assignment-1-solved
**TO GET THIS SOLUTION VISIT:** [INFR11199 – Coursework Assignment 1 Solved](https://www.ankitcodinghub.com/product/infr11199-coursework-assignment-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;116128&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;INFR11199 - Coursework Assignment 1 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
1 Goals and Important Points

In this assignment, you will implement the minimization procedure for conjunctive queries and a lightweight database engine for evaluating queries called Minibase.

The goals of this assignment are threefold:

1. to understand the minimization procedure for conjunctive queries,

2. to teach you how to translate conjunctive queries into relational algebra query plans,

3. to learn the iterator model for relational operator evaluation and implement the most common operators (e.g., selection, projection, join, aggregation).

The assignment consists of three tasks:

Task 1 (30%): Implementation of the minimization procedure for conjunctive queries.

Task 2 (40%): Implementation of the iterator model and common RA operators.

Task 3 (20%): Optimisation of constructed query plans.

You should consider the set semantics for each task, meaning that every relation consists of distinct tuples and the input and output of each operator contain no duplicates.

You will start from a skeleton project consisting of two main classes:

• CQMinimizer, which should contain your code for Task 1

• Minibase, which should contain your code for Tasks 2 &amp; 3.

Both classes define the expected command line interface. You are free to modify these classes but must preserve their command line interface as it is essential for marking.

The skeleton project also comes with a parser for our query language, so you do not have to write your own (unless you want to). The main classes show how to parse query strings into Java objects.

The rest of this document describes in detail how to complete the assignment. Take time to read it carefully. Note that some topics will be covered later in the course. Start working as early as possible. This is not a project that should be left to the last minute.

2 Setting Up Local Development Environment

You are free to use any text editor or IDE to complete the project. We will use Maven to compile your project. We recommend setting up a local development environment by installing Java 8 or later and using an IDE such as IntelliJ or Eclipse. To import the project into IntelliJ or Eclipse, make sure that you import as a Maven project (select the pom.xml file when importing).

3 Task 1: CQ Minimization

In Task 1, you will implement the minimization algorithm for conjunctive queries discussed in class. You will build a program that reads a query from the specified input file, minimizes the query, and writes a minimized query in the specified output file.

3.1 Query Language

Task 1 considers the language of conjunctive queries as presented in class, with queries expressed using the rule-based form:

Q(v) :- R1(t1),…,Rm(tm)

head body

Examples of valid conjunctive queries are:

Q(x) :- R(x,’This is a test string’)

Q(x,z) :- R(4,z),S(x,y),T(12,’x’)

Q() :- R(y,z),R(z,x)

DBSTUDENTNAME(name) :- STUDENT(id,name),ENROLLED(id,’ADBS’) Examples of invalid conjunctive queries in our language are:

Q(y) :- R(x,’test’) – y does not appear in body

Q() :- – empty body

Q(x,3) :- R(4,z),S(x,y) – constant in head

Q(y) :- R(y),S() – empty relational atom in body

You can assume that only valid, correctly-typed conjunctive query will be provided as input. For instance, Q(x) :- R(x,4),R(y,’4’) is wrongly-typed as the second attribute of R does not have a unique type. Similarly, Q(x) :- R(x,y),R(x,y,z) is also wrongly-typed as the arity of R is not unique. Such queries will never appear as input.

For simplicity, you can assume that every relational atom appearing in the body or the head has no repeated variables. For instance, the atom R(x,x) is invalid according to this restriction, while R(x,xx) and R(3,3) are valid; the query Q(x,x) :- R(x) is also invalid. But the same variable can appear in different relational atoms in the body.

You do not need to perform any type or naming checks on the input query.

3.2 Query Parser

The provided code contains a parser for our query language. The parser was generated using ANTLR (https://www.antlr.org/) based on the grammar defined in parser/Minibase.g4. Have a look at the grammar to understand the structure of the language constructs. The base directory contains Java classes matching these constructs.

You are free to modify and extend these classes.

The grammar also allows comparison atoms such as x &gt; 3 and x != y to appear in the body and SUM aggregation to appear in the head. We will consider comparison atoms and aggregation in Tasks 2 &amp; 3. For Task 1, we will assume that the body consists of relational atoms only and that the head consists of (non-repeated) variables only.

The parser/generated directory contains the parser classes generated by ANTLR. Do not modify these generated classes directly. The class from parser/QueryParser.java uses the visitor pattern to construct a Query object from ANTLR objects.

To get you started, we provide a simple method in CQMinimizer.java that uses the parser to read a query from a file, print it out, and access fields of the Query object.

3.3 Input and Output

We provide a few sample conjunctive queries. The data/minimization directory contains input and expected output as subdirectories. The input directory contains files with example conjunctive queries. There is one query per file. The expected output directory contains the expected output files for the given sample queries. For example, the query in expected output/query1.txt is the minimized version of the query in input/query1.txt.

CQMinimizer.java provides the command-line interface that expects two arguments: the path to an input file and the path to an output file. You are free to modify the provided code and include additional classes and packages, but you must preserve the existing command-line interface. You can run the CQMinimizer class from your IDE and provide the required arguments.

3.4 Compile and Run

We will compile your code from the command line as follows:

mvn clean compile assembly:single

This command will produce target/minibase-1.0.0-jar-with-dependencies.jar.

We will run CQMinimizer as follows:

$ java -cp target/minibase-1.0.0-jar-with-dependencies.jar ed.inf.adbs.minibase.CQMinimizer

Usage: CQMinimizer input_file output_file

CQMinimizer requires passing two mandatory arguments.

$ java -cp target/minibase-1.0.0-jar-with-dependencies.jar ed.inf.adbs.minibase.CQMinimizer

data/minimization/input/query1.txt data/minimization/output/query1.txt

Entire query: Q() :- R(x, ’z’), S(4, z, w)

Head: Q()

Body: [R(x, ’z’), S(4, z, w)]

The provided sample code parses the query from the input file into a Java object and prints different parts of the query. Your code should print the minimized query into the specified output file. You can assume that the output directory already exists.

After running your code, we will check whether the query in the output file is equivalent to ours up to variable renaming; e.g., Q(x) :- R(x) would be equivalent to Q(y) :- R(y).

We will test your code on a set of conjunctive queries, including the sample queries.

4 Task 2: Query Evaluation

In Task 2, you will implement a simple interpreter for conjunctive queries. You will build a program that takes in a database (a set of files with data) and an input file containing one query. The program will process and evaluate the query on the database and write the query result in the specified output file. The evaluation should be based on the set semantics, meaning no tuple duplicates should appear in the input and the output.

4.1 Query Language

For Tasks 2 &amp; 3, we extend the query language from Task 1 to allow comparison atoms in the body of a query. A comparison atom has the form:

term1 op term2

where term1 and term2 are constants or variables, and op ∈{=,!=,&lt;,&lt;=,&gt;,&gt;=}. For instance, x = y, x &lt; 4, ’ADBS’ &gt;= z, 3 &gt; 12 are valid comparison atoms. String comparison should be performed lexicographically.

Comparison atoms in the body of a query represent a conjunction of predicates that filter the query result, similarly to a conjunction of predicates in the WHERE clause in SQL.

For instance, the query

Q(name) :- STUDENT(id,name,age), age = 23, name !=’Jones’ returns the names of all students who are 23 years old and whose name is not ’Jones’. The equivalent SQL query is (remember that this assignment assumes the set semantics):

SELECT DISTINCT name FROM STUDENT WHERE age = 23 AND name != ’Jones’

You can assume that both terms in a comparison atom are always of the same type. Furthermore, every variable appearing in a comparison atom must also appear in at least one relational atom. No need to perform such checks.

We also extend the query language with the SUM aggregate; more details are in

Section 4.5.5.

We make a few simplifying assumptions as below. When we say a query is valid, we mean it is a permitted input to your interpreter which you should be able to handle. When we talk about a base relation, we mean a real relation that exists in the database.

• The head atom contains at least one term. For instance, Q() :- R(x,y) is a valid Boolean conjunctive query but will not be considered in Tasks 2 &amp; 3.

4.2 Data and Output Formats

We have provided you some sample data and some sample queries. Take a look at the data/evaluation directory. It has db, input, and expected output as subdirectories.

• The input directory has files with example queries. There is one query per file.

• The db directory contains schema.txt specifying the schema for your database as well as the files subdirectory, where the data itself is stored. The names schema.txt and files are hard-coded and must exist in a valid database directory. Your program should support an arbitrary schema defined in schema.txt, not just the schema of the sample data.

The schema.txt file contains one line per relation (table) in the database. Every line contains several strings separated by spaces. The first string on each line is the relation name and all the remaining ones are attribute (column) types, in the order in which they appear in the relation. The possible names for attribute types are int and string.

The data subdirectory contains one file per database relation, and the name of the file is the same as the name of the database relation with the added .csv extension. Every file contains zero or more tuples without duplicates; a tuple is a line in the file with field (attribute) values separated by commas. The type of each value is defined in the schema file. You do not have to handle null values, but you do need to handle empty relations.

• The expected output directory contains the expected output files for the queries we provided. For example, query1.csv contains the expected output for the query in query1.txt. The format for the output is the same as the format for the data.

4.3 Compile and Run

We will compile and run your code from the command line as in Task 1:

$ mvn clean compile assembly:single

$ java -cp target/minibase-1.0.0-jar-with-dependencies.jar ed.inf.adbs.minibase.Minibase

data/evaluation/db data/evaluation/input/query1.txt data/evaluation/output/query1.csv

Entire query: Q(x, y, z) :- R(x, y, z)

Head: Q(x, y, z)

Body: [R(x, y, z)]

The Minibase class requires passing three mandatory arguments: the path to a database directory, the path to an input file, and the path to an output file. Your code should handle these arguments appropriately (i.e., do not hardcode any paths).

After we run your code, we will compare your output files with ours. The order of tuples in the output file does not matter for this assignment. As you can imagine, it is very important for you to respect the expected input and output format.

Note: We will test your code on a DICE machine with Ubuntu Linux. Remember that Linux/MacOS environments use ’/’ as path separator. The database directory will be provided with no final ’/’ symbol, as above. If you use Windows, make sure that when you form file paths, you use File.separator instead of ’’ as path separator.

4.4 Operators and the Iterator Model

A key abstraction in this project will be the iterator model for relational operators. You will implement several operators:

• selection, projection, (tuple nested loop) join, and group-by aggregation.

• a scan operator which is the leaf operator for any query plan. This is really a physical operator rather than something you would add to the relational algebra, but for now we will put it in the same category as the above.

Every operator must implement the methods getNextTuple() and reset() (put these in your abstract Operator class). The idea is that once you create a relational operator, you can call getNextTuple() repeatedly to get the next tuple of the operator’s output. This is sometimes called “pulling tuples” from the operator. If the operator still has some available output, it will return the next tuple, otherwise it should return null.

For each of the above operators, you will implement both getNextTuple() and reset(). Remember that if your operator has a child operator, the getNextTuple() of your operator can – and probably will – call getNextTuple() on the child operator and do something useful with the output it receives from the child.

A big advantage of the iterator model, and one of the reasons it is popular, is that it supports pipelined evaluation of multi-operator plans, i.e., evaluation without materialising (writing to disk) intermediate results.

The bulk of this task involves implementing each of the above operators, as well as writing code to translate a given query (i.e., a line of text) to a query plan (i.e., a suitable tree of operators). Once you have the query plan, you can actually compute the answer to the query by repeatedly calling getNextTuple() on the root operator and putting the tuples somewhere as they come out.

We suggest you add a dump() method to your abstract Operator class. This method repeatedly calls getNextTuple() until the next tuple is null (no more output) and writes each tuple to a suitable PrintStream. That way you can dump() the results of any operator – including the root of your query plan – to your favourite PrintStream, whether it leads to a file or whether it is System.out (for testing).

4.5 Implementation Instructions

We recommend that you implement and test one feature at a time. Our instructions below are given in suggested implementation order.

We also recommend (but do not require) you set up a test infrastructure early on. You should do two kinds of testing – unit tests for individual components and end-to-end tests where you run your interpreter on queries and look at the output files produced to see if they match a set of expected output files. As you add more features, rerun all your tests to check that you didn’t introduce bugs that affect earlier functionality.

After you implement and test each feature, make a copy of your code and save it so if you mess up later you still have a version that works (and that you can submit for partial credit if all else fails!).

4.5.1 Implement Scan

Your first goal is to support queries that are full relation scans, e.g., Q(x,y,z) :- R(x,y,z).

To achieve this, you will need to implement your first operator – the scan operator.

Implement a ScanOperator that extends your Operator abstract class. Every instance of ScanOperator knows which base relation it is scanning. Upon initialisation, it opens a file scan on the appropriate data file; when getNextTuple() is called, it reads the next line from the file and returns the next tuple. You probably want to have a Tuple class to handle the tuples as objects.

Once you have written ScanOperator, test it thoroughly to be sure getNextTuple() and reset() both work as expected. Then, hook up your ScanOperator to your interpreter. Assuming that all your queries are of the form Q(x,y,…) :- RELATION(x,y,…), write code that grabs RELATION from the body and constructs a ScanOperator for it.

In summary the top-level structure of your code at this point should be:

• parse the query from the input file

• construct a ScanOperator for the relation in the body of the query

• call dump() on your ScanOperator to send the results somewhere helpful, like a file or your console.

4.5.2 Implement Selection

The next order of business is single-relation selection. That is, you are aiming to support queries like Q(x,y,z) :- R(x,y,z),y &gt; 3.

This means you need to implement a second Operator, which is a SelectOperator.

Your query plan will now have two operators – the SelectOperator as the root and the

ScanOperator as its child. During evaluation, the SelectOperator’s getNextTuple() method will grab the next tuple from its child (i.e., from the scan), check if that tuple passes the selection condition, and if so output it. If the tuple does not pass the selection condition, the selection operator will continue pulling tuples from the scan until either it finds one that passes or it receives null (i.e., the scan runs out of output).

The tricky part will be implementing the logic to check if a tuple passes the selection condition. The selection condition is a list (conjunction) of ComparisonAtoms from the body of your query. The SelectOperator needs to know that selection condition.

Your code needs some way to resolve variable references; i.e., if our input tuple is (1,9,’adbs’) coming from the atom R(x,y,z), your code needs a way to determine that x is 1, y is 9, etc. So, it also needs to take in some schema information and allow mapping from variable references like x to their value.

Once you have written your class for evaluating selection conditions, unit-test it thoroughly. Start with simple expressions that have no variable references, like the conjunction of 1 &lt; 2 and 3 = 17. Then test it with variable references until you are 100% sure it works. Once your expression evaluation logic is solid, you can plug it into the getNextTuple() method of your SelectOperator.

Queries with constants in relational atoms are also valid, e.g., Q(x,y) :- R(x,y,4) is valid and equivalent to Q(x,y) :- R(x,y,z),z = 4. Support the latter form with explicit comparisons first and then do the former form, which also requires projection.

4.5.3 Implement Projection

For implementing projection, you need a third Operator that is a ProjectOperator. Recall that projection must return only distinct tuples. When getNextTuple() is called, it grabs the next tuple from its child, extracts only the desired values into a new tuple, and returns that tuple if it has not been reported before; otherwise, the operator fetches the next tuple from its child. Note that the child could be either a SelectOperator or a ScanOperator, depending on whether your query has a selection condition.

Note that the variable order in the head atom does not have to match the attribute order in the relation. The queries Q(x,y) :- R(x,y) and Q(y,x) :- R(x,y) are both valid and produce different output results.

By this point you should have code that takes in a query and produces a query plan containing:

• an optional projection operator, having as a child

• an optional selection operator, having as a child

• a non-optional scan operator.

Thus, your query plan could have one, two or three operators. Make sure you are supporting all possibilities; try queries with/without a projection/selection. If the query does not project away any variables and does not reorder variables in the head, then do not create a projection operator, and if the query has no selection predicate, do not create a selection operator.

You are now producing relatively complex query plans; however, things are about to get much more exciting and messy as we add joins. This is a good time to pull out the logic for constructing the query plan into its own class, if you have not done so already. Thus, you should have a top-level interpreter class that reads the statement from the query file. You should also have a second class that knows how to construct a query plan for a Query object, and returns the query plan back to the interpreter so the interpreter can dump() the results of the query plan somewhere.

4.5.4 Implement Join

Next up, the star of the show: joins.

You need a JoinOperator that has both a left and right child Operator. It also has a selection predicate that captures the join condition. This selection predicate could be a single comparison such as x = y, a conjunction of comparisons, or it could be null if the join is a cross product.

Implement the simple (tuple) nested loop join algorithm: the join should scan the left (outer) child once, and for each tuple in the outer child, it should scan the inner child completely (finally a use for the reset() method!). Once the operator has obtained a tuple from the outer and a tuple from the inner, it glues them together. If there is a non-null join condition, the tuple is only returned if it matches the join condition (so you will be reusing your class for evaluating a selection condition from Section 4.5.2). If the join is a cross product, all pairs of tuples are returned.

Once you have implemented and unit-tested your JoinOperator, you need to figure out how to translate a query to a plan that includes joins.

For this project, we require that you construct a left-deep join tree that follows the order in the body of the query. That is, a query whose body includes relational atoms R(x,y),S(y,z),T(x,y) produces a plan with the structure shown below:

R” S”

Q(x) :- R(x,y),S(z,u),x = y,z = 1,y &gt; u

contains a selection condition on R, a selection condition on S, and a join condition on both R and S together. Obviously, it is most efficient to evaluate the selections as early as possible and to evaluate y &gt; u during computation of the join, rather than computing a cross product and having a selection later.

You should also be aware of implicit equi-join conditions arising when the same variable appears in more relational atoms, e.g., Q(x) :- R(x,y),S(y,z) encodes the equality condition between the second variable of R and the first variable of S. An equivalent query would be Q(x) :- R(x,y),S(yy,z),y = yy.

For example, if we have

Q(b) :- R(1,b),S(b,c),T(d,c,e),d &lt; 5,e != 0

the above approach would give the following query plan (in the figure below, R. i refers to the i-th attribute of R):

You don’t have to follow exactly this strategy for Task 2.

4.5.5 Implement Group-By Aggregation

The aggregate query

Q(SUM(x)) :- R(x,y)

returns one integer value representing the sum of x-values in R. An equivalent SQL query would be SELECT SUM(R.x) FROM R. The output file for this query should contain one integer number. Similarly, Q(SUM(1)) :- R(x,y) computes the number of tuples in R.

The group-by aggregate query

Q(x,SUM(z ∗ z)) :- R(x,y),S(y,z)

returns distinct x-values, each paired with the sum of squared z-values computed from the body for the given x-value. An equivalent SQL query would be SELECT R.x, SUM(S.z *

S.z) FROM R JOIN S ON R.y = S.y GROUP BY R.x. There could be multiple (distinct) group-by variables in the head but at most one SUM aggregate function or none at all. Group-by variables can appear in the SUM function, e.g., the query Q(x,SUM(x)) is valid.

You can assume that all variables in the SUM function will be of integer type.

You will implement one group-by aggregation operator, SumOperator, which reads all of the output from its child, extracts relevant values into tuples, organizes tuples into groups, and for each group computes an aggregate value. The SUM operator needs to see all of its input before producing any output (i.e., it is a blocking operator).

5 Task 3: Query Optimisation

The final task is to enrich Minibase with query optimisation. The goal of query optimisation is to transform query plans such that their operators process as few tuples as possible, thus reducing processing time and avoiding large intermediate results; yet such optimised query plans must still produce correct query results. To achieve this goal, you must keep the same join order but you are allowed to transform query plans, for example, swap operators or introduce new instances of the non-join operators discussed above. You should not implement any new relational algebra operator.

Properly optimised query plans should avoid processing large intermediate results whenever possible, thus allowing such plans to be executed under restricted memory budgets and time limits. We will evaluate the effectiveness of your optimisation rules by running a set of queries on large databases. Failing to properly optimise input queries will most likely lead to wrong results, out-of-memory exceptions, or timeouts.

Task 3 is not about improving the performance of individual relational algebra operators but about coming up with optimisation rules for the class of group-by aggregate queries described in Section 4. Some optimisation rules will be covered in lectures but some will require a bit of thinking on your side.

6 Grading

We strongly suggest that you follow the architecture we described for Task 2. However, we will not penalize you for making different architectural decisions, with a few exceptions:

• You must have relational Operators that implement getNextTuple() and reset() methods as outlined above. This is the standard relational algebra evaluation model and you need to learn it. Do not hard-wire combinations of operators, e.g., projection should not assume selection as its child.

• You must construct a tree of Operators and then evaluate it by repeatedly calling getNextTuple() on the root operator.

• As explained in Section 4.5.4, you must build a left-deep join tree that follows the ordering of the relations in the body. Also, you must have a strategy to identify join conditions and evaluate them as part of the join rather than doing a selection after a cross product.

Disregarding any of the above three requirements will result in severe point deductions.

Next we give the grading breakdown.

6.1 Code Style and Comments (10 points)

Follow standard guidelines for writing clean and understandable code; e.g., use standard naming conventions for classes and methods, break up large monolithic blocks of code into smaller logical pieces, avoid code duplication if possible – the “rule of three” says if your code is copied more than twice, then it probably needs to be abstracted out.

You must provide comments for every method you implement. At minimum, the comment must include one sentence about the purpose of the method, and @params/@return annotations for every argument/return value respectively. In addition, every class must have a comment describing the class and the logic of any algorithm used in the class.

If you follow the above rules and write reasonably clean code that follows our overall architecture, you are likely to get the full 10 points for code style.

6.2 Test Queries (90 points)

We will run your code with our own queries and database. We will award you 2 points for every query that returns the correct output. The queries we provide with the assignment count for 24 out of the 90 points. You can expect that we will add additional relations to the database; of course the schema of these relations will be mentioned in schema.txt and the data files will be found in the files directory. We will test with basic queries as well as with complex queries that include any/all of the features you are to implement.

If you cannot implement one or more parts, that is fine, although obviously you won’t get full points. In that case, you must clearly tell us in the README what you have not been able to implement.

7 Submission Instructions

Double-check that your code compiles and runs as described in this document. If your code fails to compile or crashes during execution, we will invest a reasonable effort to fix the problem; this can cause (severe) point deduction.

You must keep CQMinimizer and Minibase as the top-level main classes of your code.

Submit just one project directory for all three tasks.

Create a README file in the root of the project directory containing the following:

• For Task 2, an explanation of your logic for extracting join conditions from the body of a query. If this logic is fully explained in comments in your code, your README does not need to repeat that; however, it must mention exactly where in the code/comments the description is, so the grader can find it easily.

• For Task 3, an explanation of your optimisation rules, reasons why they are correct, and how they can reduce the size of intermediate results during query evaluation.

• Any other information you want the grader to know, such as known bugs.

Create a .zip archive containing a README file and your entire project directory so that we can compile and run your code on the command line. Do not include any .class files nor large .csv files. Disable all debugging statements before submitting your code.

Upload the zip archive to Learn: Assessment (the left panel) → Assignment Submission → Coursework: Minibase.

Make sure you start early! Good luck!

End of Coursework Assignment
