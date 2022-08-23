## lex与yacc的介绍
编译器和解释器的设计工具，也可以用于其他应用；这些应用的特征是它们的输入都具有一定模式，输入是有结构的。
一些使用lex和yacc开发的应用：`eqn`和`pic`分别是数学公式和复杂图片的排版预处理器; pcc和gcc编译器; SQL语言语法检查器；
这两个工具都有很多版本，比如AT&T lex and yacc, Berkeley yacc, flex, GNU bison, MKS lex and yacc;

词法分析(lexical analysis)是将输入划分为一些单元(units, 或者称为tokens)的阶段，对于C程序而言就是一些变量名称，常量，字符串，运算符，标点等。向lex给定一些可能的token的描述(lex specification)，然后lex产生一个C例程(routine, 称为lexical analyzer/lexer/scanner)。token的描述采用正则表达式，lex将这些表达式转换为lexer可以很快扫描输入的格式，和尝试匹配的表达式数量无关。

语法分析(grammar analysis)是根据一组精确描述的语法建立token之间关系的阶段，yacc根据语法规产生一个C例程(parser，可以解析语法)，会对输入的一系列tokens自动进行语法规则匹配，如果未匹配到任意语法则产生语法错误。

一些简单程序可能只用到lex而不会用到yacc。

## Parsing SQL


