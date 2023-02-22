# Object Relationships

## Learning Goals

- Introduce different types of object relationships
- Introduce Unified Modeling Language (UML)

## Introduction

Objects are often related to other objects.  There are
several types of relationships.  

- *Association* represents a general relationship between two objects,
  where neither object is considered a part or member of the
  other.
- *Aggregation* represents a whole-part or parent-child relationship
  between objects.  Aggregation represents a *weak* existence relationship,
  where the child object can exist independently of the parent.
- *Composition* also represents a whole-part or parent-child relationship.
  However, the child object can not exist independently of the whole/part.
  Composition represents a *strong* existence relationship. Deletion of
  the parent would result in the child deletion as well.

## Unified Modeling Language (UML)

**Unified Modeling Language (UML)** is a standardized modeling language to visually
represent software artifacts.    We can create UML diagrams to depict class structure
and class relationships.  We draw a class as shown below.  The fields and methods may
be omitted.  Relationships between classes are drawn using different types of edges.

![uml class](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/uml_class.png)

## Association


*Association* is used to model a general relationship between objects.
Neither object is considered a part or member of the other.
An association is drawn using an edge between classes.  The edge may have
have an arrow to indicate direction.  The arrow is often left off if the association
is bi-directional.  

![general association](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/general_association.png)

An example association is the relationship between `Student` and `Instructor`. 

![instructor student](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/instructor_student_assoc.png)

We can also indicate cardinality of the association.  Students
take many classes from instructors, instructors teach many students.

- `0..1` represents an optional association
- `0..*` represents 0 or more object associations
- `1..*` represents 1 or more object associations

![instructor student cardinality](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/instructor_student_cardinality.png)

As another example, a student has one advisor, while an `Advisor` advises many
students.

![student advisor](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/student_advisor_assoc.png)


## Aggregation

*Aggregation* represents a whole-part or parent-child relationship
between objects. Aggregation denotes a "has-a" relationship
(a car has tires, a department has employees,
a course has students).  Aggregation represents a "weak" existence relationship,
where the child/part object can exist independently of the parent/whole.
A tire can exist without a car. If a department
is deleted, we could just move the employees to another department rather
than deleting all the employees.  A student may take a class, but their
existence is not tied to a particular class.

We use a diamond symbol on the parent side of the aggregation relationship.

![aggregation](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/aggregation.png)

![department employee](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/department_employee.png)
 
## Composition

*Composition* also represents a whole-part or parent-child relationship.
However, the child object can not exist independently of the whole/part.
Composition represents a "strong" existence relationship. Deletion of
the parent would result in the child deletion as well.
Some examples:


We use a filled diamond symbol on the parent side of the composition relationship.

![composition](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/composition.png)

An example is the relationship between a company and a department.
Deleting the company object would mean all departments cease to exist as well.

![company department](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/company_department.png)


## Self-Association

A *self-association* is a relationship between a class and itself.  For example,
an employee may share an office with other employees.  The UML class diagram
below shows 

![self association](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/self_association.png)

## Implementing an Association

A relationship is usually implemented as an instance variable in one or both classes,
depending on whether the relationship is uni-directional or bi-directional.

The relationship cardinality determines whether the association is implemented
as a single value field or a collection such as an array or list.

## Conclusion

We can model different types of relationships using a UML class diagram.

- Composition (whole/part + strong existence dependency): A company has departments.  A department's existence is tied to the company's existence.
- Aggregation (whole/part + weak existence dependency): A department has employees. An employee's existence is not tied to the department's existence.
- Association (not whole/part) - An employee may be associated with other employees who share the same office.


![company class diagram](https://curriculum-content.s3.amazonaws.com/6676/java-multipleclasses/company_department_employees.png)

There are many tools available for creating UML diagrams, including
the free tool [draw.io](https://drawio-app.com/uml-class-diagrams-in-draw-io/)
used to produce the examples in this lesson.


## Resources

- [UML](https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-uml/)   
- [draw.io](https://drawio-app.com/uml-class-diagrams-in-draw-io/)
