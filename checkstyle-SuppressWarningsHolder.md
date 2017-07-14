Pattern: Maintains a set of check suppressions from SuppressWarnings annotations.

Issue: -

## Description

Maintains a set of check suppressions from `@SuppressWarnings` annotations. It allows to prevent Checkstyle from reporting errors from parts of code that were annotated with `@SuppressWarnings` and using name of the check to be excluded. You can also define aliases for check names that need to be suppressed. 

## Examples

To prevent `FooCheck` errors from being reported write:
    
    
            @SuppressWarnings("foo") interface I { }
            @SuppressWarnings("foo") enum E { }
            @SuppressWarnings("foo") InputSuppressWarningsFilter() { }
            

  


Some real check examples:

This will prevent from invocation of the MemberNameCheck: 
    
    
             @SuppressWarnings({"membername"})
             private int J;
               

You can also use a `checkstyle` prefix to prevent compiler from processing this annotations. For example this will prevent ConstantNameCheck 
    
    
                @SuppressWarnings("checkstyle:constantname")
                private static final int m = 0;
              

The general rule is that the argument of the `@SuppressWarnings` will be matched against class name of the checker in lower case and without `Check` suffix if present

If `aliasList` property was provided you can use your own names e.g below code will work if there was provided a `ParameterNumberCheck=paramnum` in the `aliasList`
    
    
                @SuppressWarnings("paramnum")
                public void needsLotsOfParameters(@SuppressWarnings("unused") int a,
                  int b, int c, int d, int e, int f, int g, int h) {
                  ...
                }
              

It is possible to suppress all the checkstyle warnings with the argument `"all"`: 
    
    
                @SuppressWarnings("all")
                public void someFunctionWithInvalidStyle() {
                  //...
                }

## Further Reading

* [checkstyle - SuppressWarningsHolder](http://checkstyle.sourceforge.net/config_annotation.html#SuppressWarningsHolder)