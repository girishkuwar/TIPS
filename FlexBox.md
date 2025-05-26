FlexBox

```css
.container {
  display :flex;    
}
```

Wrap Items In Container 

```css
.cotainer {
    display: flex;
    flex-wrap: wrap-reverse | wrap | nowrap;
}


output
000
0
```

Justify Content 

```css

.cotainer {
    justify-content: flex-start;    |000      |;
    justify-content: flex-end;      |      000|;
    justify-content: space-around;  |_0__0__0_|;
    justify-content: space-between; |0___0___0|;
    justify-content: space-evenly;  |_0__0__0_|;
}


output
|0000              |
|                  |
```