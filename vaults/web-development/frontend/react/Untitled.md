## Styled-Components - Pros

1.  Total styling isolation; prevents potential bugs when working in teams, when one team member can never override a style of another. _(unless multiple places share the same styled component)_
2.  Remove the need to manually handle class names as they get auto-generated _(name-picking components is somewhat easier IMHO than class names)_
3.  I've found it easier to work with _CSS_ within the _JSX_ file itself _(Opposing my judgment for many years before)_
    
4.  Easily use javascript variables within styles _(eliminate the need for 2-sets of theme variable)_
    

## Styled-Components - Cons

1.  Each style component is yet another wrapper function, and many styled-components means more functions, which means less efficient since all that code needs to be "compiled" and so on.
2.  **Biggest drawback**: changes to styles require bundle re-compilation and the app's state might reset.

> The cons can be only viewed as such on some scenarios but not necessarily all.


