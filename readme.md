#Brink

##About
A simple functional programming language written to experiment with simple parsing, compiling, and analysis.

##General
###Characteristics
-Entirely functional language
-Recursive (no iterative loops)
-Functional "Trees"
  - 
###Types
-Functions
-Integer
-Char
-Bool
-Array
  -Leads to functional "trees"

##Syntax
###Concrete
_def_ ::= (_variable-name_ = _exp_)
        (_function-name_ = _exp_)
        (_function-name_ (_formals_) = _exp)

_exp_ ::= _literal_
        _variable-name_
        (if _exp exp exp_)
        (if _exp_
            _exp_
            _exp_)

_formals_ ::= _{variable-name}_

_value_ ::= literal | _function_

_literal_ ::= _integer_ | true | false | _string_ | [_value_]

_function_ ::= _def_

_primitive_ ::= + | - | < | > | = 

_integer_ ::= _sequence of digits, possibly prefixed with a minus sign_

_*-name_ ::= _sequence of characters, not starting with an integer and not containing (,), ;, or whitespace_

###Abstract
datatype value = NULL     of NIL
               | BOOL     of bool
               | INT      of int
               | ARRAY    of value * value
               | FUNCTION of name * value

datatype def = VAL    of name * exp
             | EXP    of exp

datatype exp = LITERAL    of value
             | VAR        of name
             | IFX        of exp * exp * exp
