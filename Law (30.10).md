Find the derivative of: $f(x)=(2x-3)^4(x_{2}+2+1)^5$
Solution:
$Let$ $g(x)=x^{4}$
	$h(x)=x^5$
	$a(x)=2x-3$
	$b(x)=x^2+x+1$
We have $f(x)=g \circ a \times h\circ b$
Applying product rule:
$f'(x)=g'\circ a \times h\circ b+g\circ a \times h' \circ b$
Applying the chain rule:
- $\frac{d}{dx}g(a(x))=g'(a(x)).a'(x)=4(2x-3)^3.2=8(2x-3)^3$
- $\frac{d}{dx}h(b(x))=h'(b(x)).b'(x)=5(x^2+x+1)^4.(2x+1)$
$\implies f'(x)=8(2x-3)^3(x^2+x+1)^5+5(2x+1)(x^2+x+1)^4(2x-3)^4$
