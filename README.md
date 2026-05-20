# FigureCode
MMA code on common figure plotting

## Figure style for Plot

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

 ## 2D ParametricPlot Style

 ParametricPlot[{{r1 Cos[\[Phi]1], r1 Sin[\[Phi]1]}, {r0 Cos[\[Phi]0], 
   r0 Sin[\[Phi]0]}}, {t, 0, 50}, PlotRange -> All, 
 PlotStyle -> {Red, Black}, 
 FrameLabel -> {Style["x", 18, Bold, Black, Italic], 
   Style["y", 18, Bold, Black, Italic]}, 
 FrameStyle -> Directive[Black(*,Thickness[0.003]*)], Frame -> True, 
 AxesOrigin -> {0, 0}, 
 LabelStyle -> Directive[ Black, Bold, FontSize -> 13], 
 AspectRatio -> 1, ImageSize -> Medium, 
 PlotLegends -> 
  Placed[LineLegend[{"r1", "r2"}, LegendFunction -> Frame], {0.65, 0.65}]]

 ### add horizon line in plot

 Plot[Cos[t], {t, 0, 10}, GridLines -> {None, {-1, -0.5, 0, 0.5, 1}}, 
 GridLinesStyle -> Directive[Dashed, Gray]]

### add the Legend in figure (contorl the position and frame of legend)

Plot[{Sin[x], Cos[x]}, {x, 0, 2 \[Pi]}, PlotStyle -> {Blue, Red}, 
 PlotLegends -> 
  Placed[LineLegend["Expressions", LegendFunction -> "Frame", 
    LegendLayout -> "Column"], {{0.7, 1}, {0.5, 1}}]]

### change the tick for y axis

## first plot the two figure, then add the legend

p1 = ParametricPlot[{Cos[t], Sin[t]}, {t, 0, 2 Pi}, PlotStyle -> Red, 
   PlotRange -> {{-1.4, 1.4}, {-1.4, 1.4}}, Frame -> True];
p2 = ParametricPlot[{1.2 Cos[t], 1.2 Sin[t]}, {t, 0, 2 Pi}, 
   PlotStyle -> Blue];

Legended[Show[p1, p2], 
 Placed[LineLegend[{Red, Blue}, {"orbit 1", "orbit 2"}, 
   LegendFunction -> Framed], {0.5, 0.5}]]

Plot[Sin[x], {x, 0, 2 Pi}, PlotRange -> {-\[Pi], \[Pi]}, 
 Ticks -> {Automatic, {{0, "0"}, {Pi/4, "\[Pi]/4"}, {Pi/2, 
     "\[Pi]/2"}, {3 Pi/4, "3\[Pi]/4"}, {Pi, "\[Pi]"}}}]
