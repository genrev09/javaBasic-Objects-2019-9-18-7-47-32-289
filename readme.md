# Overview

This repository is a part of the Java language training plan. Please read the following guidelines before start.

# Getting Start

## Basic Principals

Each repository contains a gradle java project with a number of unit tests. The initial state of all unit tests are *FAILED*. So the aim is to correct the failed test. Please follow the following steps to get the best experience:

* Read the test code and try to understand what it says.
* Trying to fix the test **WITHOUT RUNNING**. This is very important. Because once you run the test, you may find the failure message of the test telling you the expected result. That means you may lose the chance to figure it out by yourself. Note that you should **ONLY** be able to modify code within the **TODO AREA**. The code outside the **TODO AREA** is **NOT** changable.
* Run the test to examine if the fix is correct.
* Answer the following 4 questions after the test is passed.

The 4 questions are:

1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
1. Why the test failed at first?
1. Why you corrected the test that way?
1. Do you have further questions on this knowledge point?

## Example

Let's take a look at an example:

```java
@Test
void should_pass_by_value() {
  int value = 5;

  tryingToUpdateValue(value);

  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 0;
  // --end-->

  assertEquals(expected, value);
}
```

First, read the test. From the title and code we can know that the test what to examine the behavior when passing an argument. We are not sure what `tryingToUpdateValue` does, so we can jump into its implementation:

```java
private static void tryingToUpdateValue(int value) {
  value += 2;
}
```

Now we have got the full context of the test. The argument is passed by value so the integer will be copied when passing into `tryingToUpdateValue`. Thus the value from the caller site will not change.

Notice that the todo area is in the test method. So we can modify codes within the todo area to pass the test:

```java
  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 5;
  // --end-->
```

Please note that not all todo areas are located in test method. And some todo area may have further restrictions, for example:

```java
  // TODO: You should not write concrete number here. Please find a property or constant instead.
  // <!--start
  final int maximumSymbol = 0;
  final int minimumSymbol = 0;
  // --end-->
```

The hint indicates that we should not write concrete number here. So I should not write `3` or `0xffffffff`, but write symbol (e.g. `Integer.MAX_VALUE`).

## Running Test

You could run unit tests with the help of IntelliJ. But it is also possible to run unit test via command line: `./gradlew build`.

If you just want to build your code without running test. Please use `./gradlew build -x test
`

Exception Test:
1. should_customize_exception()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable on how to customize message for throw
  b) Why the test failed at first?
   - nothing was implemented in the constructor
  c) Why you corrected the test that way?
   - only parent class can be used for customizing message.
  d) Do you have further questions on this knowledge point?
  
2. should_customize_exception_continued()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable on how to customize message for throw with additional parameter exception
  b) Why the test failed at first?
   - nothing was implemented in the constructor
  c) Why you corrected the test that way?
   - only parent class can be used for customizing message with parameter exception.
  d) Do you have further questions on this knowledge point?

3. should_be_careful_of_the_order_of_finally_block()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about the use of finally block
  b) Why the test failed at first?
   - expected result contains maximum value of an integer
  c) Why you corrected the test that way?
   - it is the expected result.
  d) Do you have further questions on this knowledge point?
  
4. should_use_the_try_pattern()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about the use of try condition
  b) Why the test failed at first?
   - expected result is null
  c) Why you corrected the test that way?
   - it is the expected result.
  d) Do you have further questions on this knowledge point?
  
5. should_call_closing_even_if_exception_throws()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about the try catch.
  b) Why the test failed at first?
   - expected result contains nothing.
  c) Why you corrected the test that way?
   - expected result is of type array of strings.
  d) Do you have further questions on this knowledge point?
  
6. should_get_method_name_in_stack_frame()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with Stack Trace of throwable clause
  b) Why the test failed at first?
   - method throws unimplemented exception
  c) Why you corrected the test that way?
   - expected result is of type string.
  d) Do you have further questions on this knowledge point?

Inheritance Test:
1. should_be_derived_from_object_class()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To determine which is the parent class.
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - Object is the parent class.
  d) Do you have further questions on this knowledge point?
  
2. should_call_super_class_constructor()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To determine which is the parent class.
  b) Why the test failed at first?
   - expected result contains nothing.
  c) Why you corrected the test that way?
   - Expected result is array.
  d) Do you have further questions on this knowledge point?
  
3. should_call_super_class_constructor_continued()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To determine which constructor will be used.
  b) Why the test failed at first?
   - expected result contains nothing.
  c) Why you corrected the test that way?
   - Expected result is array.
  d) Do you have further questions on this knowledge point?
  
4. should_call_super_class_constructor_more()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To determine which constructor will be used.
  b) Why the test failed at first?
   - expected result contains nothing.
  c) Why you corrected the test that way?
   - Expected result is array.
  d) Do you have further questions on this knowledge point?
  
5. should_call_most_derived_methods()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about overriding methods.
  b) Why the test failed at first?
   - expected result contains nothing.
  c) Why you corrected the test that way?
   - Expected result is array.
  d) Do you have further questions on this knowledge point?
  
6. should_call_super_class_methods()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about super class and the overriding methods.
  b) Why the test failed at first?
   - expected result contains nothing.
  c) Why you corrected the test that way?
   - Expected result is array.
  d) Do you have further questions on this knowledge point?
  
7. should_use_caution_when_dealing_with_array_type()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about dealing with arrays.
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
8. should_not_make_you_confused()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about passing class with application of inheritance
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - Expected result is of type string.
  d) Do you have further questions on this knowledge point?
  
9. should_not_make_you_confused_2()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about using parent's method
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - Expected result is of type string.
  d) Do you have further questions on this knowledge point?
  
10. should_use_instance_of_to_determine_inheritance_relationship()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable about relationship when using inheritance
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
11. should_use_instance_of_only_in_inheritance_relationship()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable that "instance of" can only be used with inheritance.
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
12. should_write_perfect_equals_1()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable when comparing two objects
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
13. should_write_perfect_equals_2()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable when comparing two objects
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
14. should_write_perfect_equals_3()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable when comparing two objects
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
15. should_write_perfect_equals_4()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable when comparing two objects
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
16. should_write_perfect_equals_5()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable when comparing other types
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
17. should_write_perfect_equals_6()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable when comparing same class with different property values
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
  
18. should_write_perfect_equals_7()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable on how to use hashcode
  b) Why the test failed at first?
   - method throws not implemented.
  c) Why you corrected the test that way?
   - Expected result is of type integer.
  d) Do you have further questions on this knowledge point?
  
Object Test:
1. should_point_to_the_same_object()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable on referencing object
  b) Why the test failed at first?
   - expected result is null
  c) Why you corrected the test that way?
   - expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
   - none
   
2. should_point_to_different_object()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable on referencing object
  b) Why the test failed at first?
   - expected result is null
  c) Why you corrected the test that way?
   - expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
   - none
   
2. should_point_to_different_object()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be knowledgeable on comparing different object
  b) Why the test failed at first?
   - expected result is null
  c) Why you corrected the test that way?
   - expected result is of type boolean.
  d) Do you have further questions on this knowledge point?
   - none
   
3. should_initialized_to_default_value()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with object initialization
  b) Why the test failed at first?
   - expected result has value.
  c) Why you corrected the test that way?
   - expected result must be null or 0 since it was not initialized
  d) Do you have further questions on this knowledge point?
   - none
   
4. should_pass_by_value()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with pass by value
  b) Why the test failed at first?
   - expected result is 0.
  c) Why you corrected the test that way?
   - method did not return any integer, so amount is still the same
  d) Do you have further questions on this knowledge point?
   - none
   
5. should_pass_by_value_continued()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with pass by value
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type Object.
  d) Do you have further questions on this knowledge point?
   - none
   
6. should_modify_internal_state()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with properties of an object
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type String.
  d) Do you have further questions on this knowledge point?
   - none
   
7. should_choose_method_at_compile_time()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with methods that has same name but has different parameter
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type String.
  d) Do you have further questions on this knowledge point?
   - none
   
8. should_choose_the_most_specific_overload()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with overloading methods with two parameters
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type String.
  d) Do you have further questions on this knowledge point?
   - none
   
9. should_calling_another_constructor()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with constructors
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type String.
  d) Do you have further questions on this knowledge point?
   - none
   
10. should_get_initialization_ordering()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with initialization
  b) Why the test failed at first?
   - expected result is empty.
  c) Why you corrected the test that way?
   - expected result is of type array of strings.
  d) Do you have further questions on this knowledge point?
   - none
   
11. should_get_message_of_var_length_parameters()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with how foreach loop works
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type string.
  d) Do you have further questions on this knowledge point?
   - none
   
12. should_get_message_of_var_length_parameters_2()
  a) What is the knowledge point of the test? Where is the offical document to the knowledge point?
   - To be familiarized with how foreach loop works
  b) Why the test failed at first?
   - expected result is null.
  c) Why you corrected the test that way?
   - expected result is of type string.
  d) Do you have further questions on this knowledge point?
   - none