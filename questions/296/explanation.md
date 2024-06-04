You are actually allowed to specify fewer initializers than a struct/class has members, as long as that struct/class is an aggregate.

§[dcl.init.aggr]¶8:
> When an aggregate is initialized by an initializer list (...), the elements of the initializer list are taken as initializers for the elements of the aggregate. The explicitly initialized elements of the aggregate are determined as follows:
— If the initializer list is a brace-enclosed designated-initializer-list, (...).
— If the initializer list is a brace-enclosed initializer-list, the explicitly initialized elements of the aggregate are the first n elements of the aggregate, where n is the number of elements in the initializer list.
— Otherwise, the initializer list must be {}, and there are no explicitly initialized elements.

In this case, the second bullet point applies, and the program is actually well formed. You may not even get a warning about this, for instance both gcc and clang requires `-Wextra` to warn about it.
