Kuba Walusiak, Juliusz Kościołek, 26.03.2022

# Labolatorium 2
Wstęp do GSL i GNUPLOT. Interpolacja.


## 
Temat laboratorium
1.     Treść zadań

2.     Podejście do rozwiązania zadań, argumentacja, fragmenty algorytmu, kodu ilustrujące rozwiązanie

3.     Wykresy, tabele, wyniki liczbowe

4.     Wnioski



5.     Bibliografia


### Zad 1.

Narysować na jednym wykresie krzywe otrzymane różnymi metodami interpolacji (w przykładzie ustawione jest `gsl_interp_polynomial`). `gsl_interp_polynomial`, 

Użyte polecenie:
```
gnuplot> plot "wartosci.txt", "inter-cspline.txt" with lines, "inter-linear.txt" with lines, "inter-polynomial.txt" with lines
```

![](interpolations.png)


## Zad 2

### Polecenie

Przy pomocy gnuplot prosze narysowac dane zgromadzone w pliku dane1.dat. Aby wykres byl czytelny, jedna z osi musi miec skale logarytmiczna. Prosze ustalic, ktora to os i narysowac wykres.

### Wykres

Polecenie użyte do narysowania wykresu:

```
gnuplot> set logscale x
gnuplot> plot "dane1.dat" with lines
```

![](neutron-stars.png)

### Zad 3
Prosze narysowac wykres funkcji dwywymiarowej, ktorej punkty znajduja sie w pliku dane2.dat. Prosze przegladnac plik i sprobowac znalezc w nim maksimum. Potem prosze zlokalizowac maksimum wizualnie na wykresie. Prosze na wykresie zaznaczyc maksimum strzałką.

```
gnuplot> set xlabel "x"
gnuplot> show xlabel
gnuplot> set ylabel "y"
gnuplot> show ylabel
gnuplot> set zlabel "z"
gnuplot> show zlabel
gnuplot> splot "dane2.dat"
```

x=4, y=3

![](2d.png)
![](x-axis.png)
![](y-axis.png)

```
set title "Wykres testowy";
set key left top;
set key box lt rgb "black" lw 1;
set ylabel "Amplituda";
show ylabel;
set xrange [-3:3];
set yrange [-4:5];
plot "fun1.txt" using 1:(($3+$2)/2):2:3 with yerrorbars lt rgb "red" title "Dane z pliku fun1.txt", sin(x**5) lt rgb "green" title "funkcja2: sinus(x^5)", 2*cos(x*sin(x)) lt rgb "blue" title "funkcja1: 2*cos(x*sin(x))" with boxes, 3*sin(x) lt rgb "red" title "funkcja3: 3*sin(x)"
```

![](replicated.png)