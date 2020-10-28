# practice for html and css

practice for basic of html and css coding

# Day1

# Day2
> align-self: 단 하나의 개체에 align-self: center, flex-end 등을 줄 수 있다.
> order: HTML을 변경할 필요 없이, css를 통해서 개체의 순서를 변경할 수 있다. (default: 0) - not useful
> flex-wrap: flex-box는 child의 width/height가 변하더라도, 같은 main-axis에 정렬하도록 조정한다. 이를 방지하는 것이 wrapping (wrap / nowrap)
> reverse: flex-direction: row-reverse (row elements의 order가 reversed) / flex-wrap: wrap-reverse
> flex-shrink: 2; - flex로 인해 찌그러질 때, 2배 더 많이 찌그러짐
> flex-grow: 2; - 여분의 공간이 있으면, 더 크게 됨 (다른 특성을 해치지 않는 선에서)
> flex-basis: element에게 처음 크기를 주는 것. main-axis를 나타낸다. (before changed) flex-grow, flex-shrink에 의해 변하게 된다.

#Day3
> display: grid
> grid-template-columns: 20px 55px 89px 100px => 4개의 child의 width가 이 크기를 따라서 격자로 배열됨
> ㅁ ㅁ ㅁ
> ㅁ ㅁ ㅁ
> ㅁ ㅁ ㅁ => grid 만드는 법?
> display: grid;
> grid-template-columns: 250px 250px 250px
> column-gap: 10px                 == 
> row-gap: 10px => 이렇게 하면 된다 == gap: 10px 로 하면 한꺼번에 ~
> grid-template-rows: child의 height가 ..

> repeat
> grid-template-columns: 200px 200px 200px 200px => grid-template-columns: repeat(4, 200px) 로 해결

> grid-template-areas:
>   "header header header header"
>   "content content content nav"
>   "content content . nav"
>   "footer footer footer footer" => 이렇게 하고, .aaa { grid-area: header }로 하면, header에 .aaa의 style이 적용되는듯? 굳굳
>   '.' 으로 적은 부분은 빈 칸으로 남는다
>   example-link:  

> grid-template-areas를 대체하는 것
> .header {
>  background-color: aaa;
>  grid-column-start: 1;
>  grid-column-end: 2; 하면, 1~2 column 사이에 그려짐. row도 마찬가지로 격자 무늬를 만들 수 있다 }