# description: 
 Only reinterpret_cast can be used to convert a pointer to an object to a pointer to an unrelated object type.  The dynamic cast would fail at run-time, however on most compilers it will also fail to compile because there are no virtual functions in the class of the pointer being casted.

```C++ runnable
struct Foo
{
};
 
struct Bar
{
};


int main()
{
    Foo* f = new Foo;

    Bar* b1 = f;
    Bar* b2 = static_cast<Bar*>(f);
    Bar* b3 = dynamic_cast<Bar*>(f);
    Bar* b4 = reinterpret_cast<Bar*>(f);
    Bar* b5 = const_cast<Bar*>(f);
 
    return 0;
}
```
