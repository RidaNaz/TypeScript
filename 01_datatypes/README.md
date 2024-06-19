# Primitive Types
Primitive data types are the most basic data types in TypeScript. They are immutable, meaning their value cannot be changed once created.

**Null:** Represents the intentional absence of any object value.
Example: let emptyValue: null = null;

**Undefined:** Indicates a variable that has been declared but not yet assigned a value.
Example: let notAssigned: undefined;

**BigInt:** Used for integers larger than the safe integer limit for the number type.
Example: let bigIntNumber: bigint = 12345678901234567890n;

**Symbol:** Represents a unique, immutable identifier.
Example: let uniqueId: symbol = Symbol('id');

# Non-primitive Types
Non-primitive types are more complex types and are derived from the primitive types. The main non-primitive types in TypeScript are:
* objects
* arrays
* tuple
* function
* enum 
* interface
* class

## Differences Between Primitive and Non-Primitive Types
1. **Mutability**
Primitive types are immutable.
Non-primitive types are mutable.

2. **Reference vs Value**
Primitive types are accessed by value.
Non-primitive types are accessed by reference.

3. **Memory Allocation**
Primitive types are stored directly in the memory location associated with the variable.
Non-primitive types are stored as references pointing to the memory location where the object is stored.