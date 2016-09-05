# matlab-iteration
5th september 2016
function iteration method(xin,yin,Tol)
x0=xin;
y0=yin;
itr=0;
error=1;
while error>Tol
    itr=itr+1;
    [f0,fx0,fy0]=f(x0,y0);
    [g0,gx0,gy0]=g(x0,y0);
D=[fx0 gx0 0 0;fy0 gy0 0 0;0 0 fx0 gx0;0 0 fy0 gy0];
B=[-1;0;0;-1];
if det(D)==0
    disp('change x0,y0');
else
    A=inv(D)*b;
end
x1=x0+A(1)*f0+A(2)*g0;
y2=y0+A(3)*f0+A(4)*g0;
val1=[x0;y0];
val2=[x1;y1];
error=norm(val1-val2,inf);
x0=x1;
y0=y1;
end
fprintf('itr=%d',itr);
fprintf('x1=%f;y1=%f',x1,y1);

    
