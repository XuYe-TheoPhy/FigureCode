# FigureCode
MMA code on common figure plotting

### Uniform Figure style


 Plot[{x0, x1, \\[Delta]x}, {t, 0, tend}, Frame -> True, 
 AxesOrigin -> {0, 0}, PlotRange -> {-1.2, 2.4}, 
 PlotStyle -> {Black, Red, Green}, 
 FrameLabel -> {Style["t", 18, Bold, Black, Italic], 
   Style["x", 18, Bold, Black, Italic]}, 
 PlotLegends -> 
  Placed[LineLegend[{"x_1(t)","x_2(t)","x_3(t)"}, 
    LegendFunction -> Frame], {0.75, 0.8}],
 FrameStyle -> Directive[Black,Thickness[0.003]], 
 LabelStyle -> Directive[ Black, Bold, FontSize -> 13], 
 AspectRatio -> 2/3, ImageSize -> Medium]

 ### add horizon line in plot

 Plot[Cos[t], {t, 0, 10}, GridLines -> {None, {-1, -0.5, 0, 0.5, 1}}, 
 GridLinesStyle -> Directive[Dashed, Gray]]

### add the Legend in figure (contorl the position and frame of legend)

Plot[{Sin[x], Cos[x]}, {x, 0, 2 \[Pi]}, PlotStyle -> {Blue, Red}, 
 PlotLegends -> 
  Placed[LineLegend["Expressions", LegendFunction -> "Frame", 
    LegendLayout -> "Column"], {{0.7, 1}, {0.5, 1}}]]

### change the tick for y axis

Plot[Sin[x], {x, 0, 2 Pi}, PlotRange -> {-\[Pi], \[Pi]}, 
 Ticks -> {Automatic, {{0, "0"}, {Pi/4, "\[Pi]/4"}, {Pi/2, 
     "\[Pi]/2"}, {3 Pi/4, "3\[Pi]/4"}, {Pi, "\[Pi]"}}}]
