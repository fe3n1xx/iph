## IPH Language

# Syntax
Iph code must be ran in this order: <br>
- Include (#i) - Add headers(.h.iph)/extensions(.e.iph) to your code <br>
- Definitions (#d) - Initially define variables - All variables are fixed types <br>
- Run (run()iph) - Add runtime arguments <br>
- Functions/Types (#f) - Define functions and types <br>
- Code (#c) - The code that runs <br>
<br>
To skip a specific part, use #skip <br>
e.g. You have code that doesn't use custom functions or types:
```
#skip f
```
<br>
All code within a part has to be indented within the #start and #end calls
```
#start d
    /*Create number variable called num1*/
    #d num1 ##
#end d
```
<br>

# Types
There are 4 built types in iph:
```
"Hello" - String - Contains text
#213# - Integer - Contains integers
/3.14159/ - Float - Contains decimal numbers
</home/nm> - FilePath - Contains filepaths
<<True>> - Boolean - Contains True/False Statements
```
You can translate between these by using each of these functions:
```
str(#12#); - Change to String
int("4"); - Change to Integer
flt(#71#); - Change to Float
fp("/home/nm"); - Change to FilePath
bool("True"); - Change to Boolean
```
To create custom types use #ct in the #f part:
```
#start f
    #ct (start: $, end: $) {
        name | "",
        age | ##
    }
#end f
```
Which you can then reference by doing something like this:
```
#start c
    pre_defined_variable_1 = $"Jeffery", #58#$;
    pre_defined_variable_2 = pre_defined_variable_1.name;
    out(pre_defined_variable_2);
    /*Outputs Jeffery*/
    /*Add 1 to age*/
    pre_defined_variable_1.age = cl(pre_defined_variable_1.age + 1);
    out(pre_defined_variable_1.age)
    /*Outputs 59*/
#end c
```