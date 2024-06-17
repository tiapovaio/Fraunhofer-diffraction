# Дифракция Фраунгофера

Моделирование дифракции Фраунгофера от прямоугольных объектов, задаваемых
двумерным амплитудным распределением. Задача показать распределение интенсивности
в плоскости, удаленной от объекта на расстояние L при заданной длине волны излучения λ.

> Зададим амплитудное распределение $A\left(x,\ y\right)$ для прямоугольника с шириной w и высотой h, центрированного в начале координат:

$$
A\left(x,\ y\right)=
\begin{cases}
A_0, & \text{если } |x|≤\frac{w}{2} \text{ и } |y|≤\frac{h}{2} \\
0, & \text{иначе}
\end{cases}
$$


Здесь $A_0$ — это постоянная амплитуда волны внутри прямоугольника. Вне прямоугольника амплитуда равна нулю. Это уравнение предполагает, что волна имеет одинаковую амплитуду во всех точках внутри прямоугольника и полностью отсутствует вне его.

> Вычислим комплексную амплитуду $U\left(P\right)$ в точке наблюдения, используя приведённую формулу. 

Дифракционная картина в плоскости наблюдения связана с амплитудным распределением в плоскости объекта через преобразование Фурье. Для двумерного амплитудного распределения $A\left(x,\ y\right)$ комплексная амплитуда волны в плоскости наблюдения $U\left(P\right)$ выражается как:

$$
U(P) = \frac{e^{ikL}}{i\lambda L} \iint A(x,y) e^{-i\frac{2\pi}{\lambda}(x\sin\theta_x + y\sin\theta_y)} \,dx\,dy
$$

, где 
$k=\frac{2\pi}{\lambda}$  — волновое число, 
$\lambda\$ — длина волны, 
$\theta_x$  и $\theta_y$ — углы дифракции.

> Определим интенсивность I(P) в точке наблюдения.

$$I\left(P\right)=\ \left|U\left(P\right)\right|^2$$

В численном моделировании преобразование Фурье выполняется с использованием быстрого преобразования Фурье (БПФ). Для этого амплитудное распределение $A\left(x,\ y\right)\$ дискретизируется и представляется в виде матрицы значений.

Быстрое преобразование Фурье применяется к дискретизированному амплитудному распределению для получения комплексной амплитуды в плоскости наблюдения:

$$U_{\text{дискрет}}(P) = \text{БПФ} \\{ A_{\text{дискрет}}(x,y) \\}$$

Интенсивность для дискретных значений вычисляется как квадрат модуля результата БПФ:

$$I_{\text{дискрет}} (P)=|U_{\text{дискрет}} (P)|^2$$

