# I don't know what any of this means...RIGHT NOW

when '-l' is run in home directory, the following is presented:

-l : The term '-l' is not recognized as the name of a cmdlet, function, script file, or 
operable program. Check the spelling of the name, or if a path was included, verify that 
the path is correct and try again.
At line:1 char:1
+ -l
+ ~~
    + CategoryInfo          : ObjectNotFound: (-l:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


when '-a' is run in home directory, the following is presented:

-a : The term '-a' is not recognized as the name of a cmdlet, function, script file, or 
operable program. Check the spelling of the name, or if a path was included, verify that 
the path is correct and try again.
At line:1 char:1
+ -a
+ ~~
    + CategoryInfo          : ObjectNotFound: (-a:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException


when 'ls -a' is run in home directory, the following is presented:

Get-ChildItem : Parameter cannot be processed because the parameter name 'a' is 
ambiguous. Possible matches include: -Attributes -Directory -File -Hidden -ReadOnly 
-System.
At line:1 char:4
+ ls -a
+    ~~
    + CategoryInfo          : InvalidArgument: (:) [Get-ChildItem], ParameterBindingExce 
   ption
    + FullyQualifiedErrorId : AmbiguousParameter,Microsoft.PowerShell.Commands.GetChildI 
   temCommand
