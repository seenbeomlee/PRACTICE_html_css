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

# Day3
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

## Day4
>  grid-column 1 / -1 => 1 column ~ lost column
> grid-column 1 / 4 => 1 ~ 4 column
> grid-column: span 4 => 1 ~ 4 column (span -1 doesn't work)
> grid-column: 2 / span 2 => 2에서 시작 ~ 2칸 => 2 ~ 4 column

>  lineNaming
> [moomoo-line] 100px [second-line] 100px ... [fifth-line];
> grid-column moomoo-line / fourth line === 1 / 4 => just naming for column

# fraction
> fr == fraction == 사용 가능한 넓이
> column-template-columns: 4fr 1fr 1fr 1fr ==> if body width 700 => 400 100 100 100 으로 변환 (px은 display에 flex하지 않음)
> repeat(4, 1fr) 처럼 사용 가능하다

# grid-template
> "header header header header" 1fr
> "content content content nav " 2fr
> "footer footer footer footer" 1fr / 1fr 1fr 1fr 1fr

# justify-items (default: stretch) => grid의 item에 일괄적으로 적용
> start => not strech (grid는 만들어지지만, item은 맞춰서 늘어나지 않음) , center, end

# align-items (default: stretch) => grid의 item에 일괄적으로 적용
> same as justify

# place-items
> place-items : stretch / center (align / justify) 로 shortcut

## Day5

# align-self && justify-self
> place-self: end center === justify-self: end; align-self: center;

# grid-auto-rows
> grid-auto-rows: 100px => grid에 item이 몇 개가 들어가던, row의 크기를 100px로 만들어준다. repeat(4, 100px) 이라고 하면 4개만 100px로 정의.

# grid-auto-flow (default: row)
> grid-auto-flow: column; => grid item이 넘칠 때, row로 생성할지, column으로 생성할 지 결정한다. (axis를 결정하는 역할을 수행함)
> column => vertical => gallery를 만들 때 사용될 수 있다(사진이 가로로 쭉- 나열되도록 grid가 설정됨)
> row => horizontal

# grid-auto-columns
> same as grid-auto-rows

# minmax
> grid-template-column: repeat(10, 1fr); => 'fr' 단위가 너무 작게/크게 안되었으면 좋겠다.
> grid-template-column: repeat(10, minmax(100px, 1fr)); => 100px ~ 1fr 크기로 grid-item의 size 조절

# auto-fit / auto-fill ***
> grid-template-column: repeat(auto-fill, minmax(100px, 1fr)); => create column as many as possible (남는 공간에 비어있는 grid-item을 만듬)
>grid-template-column: repeat(auto-fit, minmax(100px, 1fr)); => 현재 element를 stretch해서 size를 fit 시킨다

# min-content / max-content ***
> grid-template-columns: max-content min-content => max-content를 하면, box안에 span을 넣었을 때, '한 즐' 안에 span을 모두 담을 수 있을 만큼 box size를 auto-fit / min-content는 box '전체' 안에 span을 넣을 수 있을 만큼 작게 auto-fit
> min-content
> max-content

## Day6

# CSS preprocessors
> They are programs that transform special CSS to normal CSS.

# browsers doesn't understand SCSS
> we can use variables without SCSS
> $name-of-variable:value => this is the format to create variable on SCSS
> &:hover {} => write a nested :hover on SCSS

# mixins & extends
> mixins and extends => we both use them to re-use styles
> Mixins can have logic and args, but extends cannot
> we can give arguments to mixins
> we can put if/else in mixins
> @mixin btn{} => create a mixin called 'btn'
> %btn{} => create an extend called 'btn

