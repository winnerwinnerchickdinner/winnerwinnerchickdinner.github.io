### 设置grid

Chrome://flags

experimental web platform features

重启浏览器



Opera://flags

experimental web platform features



(Firefox)layout.css.grid.enabled



* display

* grid-template-columns

* grid-template-rows

* grid-template-areas

* grid-column-gap

* grid-row-gap

* grid-gap

* justify-items

* align-items

* justify-content

* align-content

* grid-auto-columns

* grid-auto-rows

* grid-auro-flow

* grid

Grid Items 的全部属性:

- grid-column-start

- grid-column-end
- grid-row-start
- grid-row-end
- grid-column
- grid-row
- grid-area
- justify-self
- align-self

1.display:gird|inline-grid(行内网格)|subgrid(继承父的行、列大小)
2.grid-template-columns:40px 50px auto 40px;

grid-template-rows:25% 100px auto;

grid-template-columns:[first]40px [line2 second]50px [three]auto [col4-start]40px[end];

grid-template-columns:rep	eat(3, 20px[col-start]) 5%;

grid-template-columns:1fr 50px 1fr 1fr;

grid:grid-template-rows/grid-template-columns(先rows后columns)

```
.container {
  grid-template:
    [row1-start] "header header header" 25px [row1-end]
    [row2-start] "footer footer footer" 25px [row2-end]
    / auto 50px auto;
}
```

以上等价于：

```
.container {
  grid-template-rows: [row1-start] 25px [row1-end row2-start] 25px [row2-end];
  grid-template-columns: auto 50px auto;
  grid-template-areas: 
    "header header header" 
    "footer footer footer";
}
```

3.grid-template-areas:"header header header  header"

"main main . sidebar"

"footer footer footer footer"

.item-1 { 

grid-area:header;

//grid-column:1/5;

//grid-row:1/2;

}

4.grid-column/row-gap:10px;

grid-gap:10px 15px;

grid-gap:10px;

5.justify-items:start（区域水平左对齐）|end|center|stretch（填满默认）;

align-items:start（区域垂直左对齐）|end|center|stretch;







//整个grid容器的位置：

6.justify-content:start（主轴上轨道左对齐）|end|center|stretch|space-around|space-between|space-evenly（around的空白均匀版）

align-content:start（主轴上轨道左对齐）|end|center|stretch|space-around|space-between|space-evenly（around的空白均匀版）



7.自动填充的隐式轨道默认0px;

grid-auto-columns/rows:60px;

8.grid-auto-flow:row(自动流默认为水平左右左右)|column(自动流垂直上下上下)|row/column? dense（按先后顺序排列//告诉自动布局算法，如果后面出现较小的 grid item，则尝试在网格中填充空洞

）;

```
.container {
  grid: column 1fr / auto;
}
.container {
  grid-auto-flow: column;
  grid-auto-rows: 1fr;
  grid-auto-columns: auto;
}
```

9.grid-column/row-start:数字|线名;

grid-colunm/row-end:数字|线名|span 数字/线名(跨越/跨越到的意思);

grid-colunm:start / end;

如果没有声明 grid-column-end / grid-row-end，默认情况下，该网格项将跨越1个轨道。

重叠用z-index设置层级

10.grid-area:名字| start / start / end / end;

11.justify-self:start |end|center|stretch;(单个网格水平对齐方式)

align-self:start |end|center|stretch;(单个网格垂直对齐方式)







