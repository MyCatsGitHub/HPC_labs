https://colab.research.google.com/drive/1ZqXr3pPbuY3i9RzlOiS1ZsD5UIromGW7?usp=sharing

На gpu параллельные вычисления выполняются для каждого пикселя на изображении (одна нить - один пиксель). В самом алгоритме обработки изображения проверяем что координата потока в сетке не выходит за границы изображения,
далее выполняем расчет значений по формуле

| Размерность изображения  | Время обработки на cpu | Время обработки на gpu | Ускорение                 |
| ------------------------ | ---------------------- | -----------------------| --------------------------|
| 240*320                  |           11.7        | 0.0078                  | 1487                      |
| 630*930                  |  84.42                | 0.034                   | 2458                      |
| 3840*2160                |  Больше 20 минут       | 0.31                   | стремится к бесконечности |

Также пробовал обработать 4к изображение на cpu, после 20 минут ожидания результата решил дальше не ждать. Примеры изображение до/после обработки приведены ниже.


Изображение до обработки
![without blur](https://github.com/MyCatsGitHub/HPC_labs/blob/main/Bilateral%20filtering/sharikov%20no%20blur.png?raw=true)

Изображение после обработки
![with blur](https://github.com/MyCatsGitHub/HPC_labs/blob/main/Bilateral%20filtering/sharikov%20blur.png?raw=true)
