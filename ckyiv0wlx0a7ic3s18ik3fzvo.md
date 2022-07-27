## How do you know if a method is available to an object?

Hey guys, how have you been?
Hope you are healthy and happy.

### Intro
Today, let's see how to check if a method is available to an object.
Again, the goal of this article is to check if a specific method is available to an object.

### Introduction to the solutions
In Ruby,  there are often a bunch of different ways to get the same results. Sometimes, the chosen method or solution is just a matter of preference.

This is not common in other programming languages, that's why some newcomers might feel uncomfortable.

This article offers 2 possible approaches.


### 2 approaches
Basically, there are 2 approaches (methods):
- class.methods
- respond_to? 

#### The first approach - The `class.methods` method
*Syntax: parameter.class.methods*
**Parameter**: The value that it is going to be checked
Method: class.methods
Return: It returns all the methods available to the class

First things first, the `class` method alone allows us to see the class of the value. Let's see some examples:
```
irb(main):001:0> "alexandre-calaca".class
=> String
irb(main):002:0> 2014.class
=> Integer
 ```

Let's check one example with an integer object using the `.class.methods` approach:
```
irb(main):001:0> 2.class.methods
=> [:sqrt, :allocate, :superclass, :<=>, :<=, :>=, :==, :===, :autoload?, :autoload, :included_modules, :include?, :name, :ancestors, :attr, :attr_reader, :attr_writer, :attr_accessor, :instance_methods, :public_instance_methods, :protected_instance_methods, :private_instance_methods, :constants, :const_get, :const_set, :const_defined?, :class_variables, :remove_class_variable, :class_variable_get, :class_variable_set, :class_variable_defined?, :public_constant, :freeze, :inspect, :deprecate_constant, :private_constant, :const_missing, :singleton_class?, :prepend, :class_exec, :module_eval, :class_eval, :include, :<, :>, :remove_method, :undef_method, :alias_method, :protected_method_defined?, :module_exec, :method_defined?, :public_method_defined?, :to_s, :public_class_method, :public_instance_method, :define_method, :private_method_defined?, :private_class_method, :instance_method, :instance_variable_set, :instance_variable_defined?, :remove_instance_variable, :instance_of?, :kind_of?, :is_a?, :tap, :instance_variable_get, :instance_variables, :method, :public_method, :singleton_method, :define_singleton_method, :public_send, :extend, :to_enum, :enum_for, :pp, :=~, :!~, :eql?, :respond_to?, :object_id, :send, :display, :nil?, :hash, :class, :singleton_class, :clone, :dup, :itself, :yield_self, :taint, :tainted?, :untrust, :untaint, :trust, :untrusted?, :methods, :frozen?, :protected_methods, :singleton_methods, :public_methods, :private_methods, :!, :equal?, :instance_eval, :instance_exec, :!=, :__send__, :__id__]
irb(main):002:0> ```

Let's check one example with a string object:
```
irb(main):002:0> "alexandre".class.methods
=> [:try_convert, :new, :allocate, :superclass, :<=>, :<=, :>=, :==, :===, :autoload?, :autoload, :included_modules, :include?, :name, :ancestors, :attr, :attr_reader, :attr_writer, :attr_accessor, :instance_methods, :public_instance_methods, :protected_instance_methods, :private_instance_methods, :constants, :const_get, :const_set, :const_defined?, :class_variables, :remove_class_variable, :class_variable_get, :class_variable_set, :class_variable_defined?, :public_constant, :freeze, :inspect, :deprecate_constant, :private_constant, :const_missing, :singleton_class?, :prepend, :class_exec, :module_eval, :class_eval, :include, :<, :>, :remove_method, :undef_method, :alias_method, :protected_method_defined?, :module_exec, :method_defined?, :public_method_defined?, :to_s, :public_class_method, :public_instance_method, :define_method, :private_method_defined?, :private_class_method, :instance_method, :instance_variable_set, :instance_variable_defined?, :remove_instance_variable, :instance_of?, :kind_of?, :is_a?, :tap, :instance_variable_get, :instance_variables, :method, :public_method, :singleton_method, :define_singleton_method, :public_send, :extend, :to_enum, :enum_for, :pp, :=~, :!~, :eql?, :respond_to?, :object_id, :send, :display, :nil?, :hash, :class, :singleton_class, :clone, :dup, :itself, :yield_self, :taint, :tainted?, :untrust, :untaint, :trust, :untrusted?, :methods, :frozen?, :protected_methods, :singleton_methods, :public_methods, :private_methods, :!, :equal?, :instance_eval, :instance_exec, :!=, :__send__, :__id__]
```
##### Pros and cons of the first approach
As you can see, it's possible to see all the available methods to that specific object, it allows you to have a wide view of all the available methods, however, you might feel kinda stuck due to so many methods.

#### The second approach - The `respond_to?` method
*Syntax: parameter.respond_to? ("method")*
Parameter: The value that it is going to be checked
Method: The method's name
Return: It returns a boolean value (true or false)

The `respond_to?` method allows us to identify if a certain object is able to take certain method and return true or false.


Let's check some examples with a true return:
``` 
irb(main):003:0> array = [1, 3, 5, 0]
irb(main):005:0> array.respond_to? ("push")
=> true
irb(main):006:0> (2.4).class
=> Float
irb(main):007:0> (2.4).respond_to? ("round")
=> true
``` 
Let's check some examples with a boolean return:
```
irb(main):008:0> "alexandre-calaca".class
=> String
irb(main):009:0> "alexandre-calaca".respond_to? ("sqrt")
=> false
irb(main):010:0> 2.class
=> Integer
irb(main):011:0> 2.respond_to? ("substring")
=> false
```

##### Pros and cons of the second approach
As you can see, it's really quick to check if the method is available to the object. The only downside is that it is only possible to check one method at at time.

### Summing up
Together, the `respond_to?` and `class.methods` approaches let us know if a method is available to an object, which is something so important when we are developing or debugging.

### Conclusion
In this article, it was possible to learn and practice how to know if a method is available to an object.

Hope it was useful.

That's for today. Let me know if you have any questions.

By the way, you help me a lot if you like and/or share this article. 


