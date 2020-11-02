# Principles of refactoring

Refactoring - is a process of changing structure of the source code without changing its behaviour to make code base more clear and to increase ability to open/modify and maintain it.

Creation of new functionality without refactoring leads to increasing code base size that leads to structure degradation.

Refactoring helps developer to better understand code base. Also it makes code base more readable.

Refactoring helps to find bugs and write programs faster.

**The 3 copy-paste rule**
Developer must start refactoring when he have at least 3 code duplications. *(If I remember correctly, Mark Seeman said that 3 clones might be not enough.)*

Refactoring is useless:
- for short-term project;
- when code base so bad, that it'd better to re-write everything from scratch.