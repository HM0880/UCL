## Sorting

`sortrows(MATRIX,COLUMN)` Sorts the matrix by the designated COLUMN (given as a number-- 1 for the first column, 2 for the second column, etc.).  `sort(MATRIX)` sorts each column independently, which is often **not** what is desired!  [StackOverflow discussion](http://stackoverflow.com/questions/134712/how-can-i-sort-a-2-d-array-in-matlab-with-respect-to-one-column).


# [Formatting lines](http://www.mathworks.com/help/matlab/ref/linespec.html)

## Line types
'-' (solid), '--' (dashed), ':' (dotted), '-.' (dash-dot)

## Markers
+, o, *, ., x, s, d, ^, v, >, <, p, h

## Colors
r, g, b, c, m, y, k, w

## Example
Line types, markers, and colors can be combined by one single quote pair: e.g., `plot(x,y,'-.or')`


# [Text output on graph (EDIT)](http://www.mathworks.com/matlabcentral/newsreader/view_thread/296017)

text(-15,0.75*axesY,...
    {['circle {\itx} coord = ' num2str(circleX)],...
    ['circle {\ity} coord = ' num2str(circleY)],...
    ['circle ({\ity + s}) coord = ' num2str(circleY+finalshift)],...
    ['circle {\itR} = ' num2str(radius)],...
    ['truncation at ({\itx,y}) = (' num2str(-truncX) ',' num2str(truncY)...
        ') and (' num2str(truncX) ',' num2str(truncY) ')'],},'HorizontalAlignment','left')


# [Find (EDIT)](http://www.mathworks.com/help/matlab/matlab_prog/find-array-elements-that-meet-a-condition.html)

[row,col] = find(splineX == correction(n,1));

# Auto-dock all windows

`set(0,'DefaultFigureWindowStyle','docked')`


# No scientific formatting

`format long g`


## Get computer name/hostname - File Exchange - MATLAB Central 
http://www.mathworks.com/matlabcentral/fileexchange/16450-get-computer-name-hostname
Just this works fine. 
[~, name] = system(hostname');
