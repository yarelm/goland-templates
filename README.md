# goland-templates

### if err not nil return  
Checks that err is not nil and writes return statement with default return values, except last - error. It would be wrapped with fmt.Errorf (https://blog.golang.org/go1.13-errors)

Abbreviation: 
```
errr
```
Template text:
```go
if $ERR$ != nil {
 return $RETURN$fmt.Errorf("$TEXT$: %w",$ERR$)$END$
}
```
Applicable in Go: statement

| Name     | Expression                                               | Default value | Skip if defined |
|----------|----------------------------------------------------------|---------------|-----------------|
| $ERR$    | `errorVariable()`                                        | "err"         |                 |
| $RETURN$ | `regularExpression(defaultReturnValues, "([^,]*$)", "")` |               |                 |
| $TEXT$   | `errorVariable()`                                        |               |                 |

