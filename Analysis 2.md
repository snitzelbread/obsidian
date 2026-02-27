# Taylorpolynom

$$
p_n(x) = f(x) \approx \sum_{k=0}^{n} \frac{f^{(k)}(x_0)}{k!}(x-x_0)^k
$$
for $n$ approaching infinity, the $\approx$ becomes $=$.

### Rechenfehler

Kann nicht exakt angegeben werden können, aber kann ein Gefühl geben

$$
Rechenfehler = |f(x) - p_n(x)| \approx |p_{n+1}(x) - p_n(x)|
$$
$$
'' = \frac{f^{n+1}(x_0)}{(n+1)!}|x-x_0|^{n+1}
$$
Jetzt wackelt man da iwie an dem $x_0$ und das wird zum $?$ welches zwischen $x$ und $x_0$ liegt.
$$
Rechenfehler = \frac{|f^{(n+1)}(?)|}{(n+1)!}|x-x_0|^{n+1}
$$
NOCH MEHR

$$
Rechenfehler = \frac{max(?\in [a, b] |f^{(n+1)}(?)|}{(n+1)!}(\frac{b-a}{2})^{n+1} \leq \frac{m}{(n+1)!} (\frac{b-a}{2})^{n+1} < max.\ Erlaubte\ Fehler
$$
$$
Wähle\ m > max(?\in [a, b])\ |f^{(n+1)}(?)|
$$

