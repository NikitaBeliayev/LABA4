# Документация к лабораторной номер 4 #
### Возможности ###
1. Демонстрация четырех алгоритмов растеризации: 
   - Алгоритм ЦДА
   - Пошаговый алгоритм
   - Алгоритм Брезенхема
   - Алгоритм Брезенхема (окружность)
2. Построение прямых, полученных данными алгоритмами.

***

Для вышеперечисленных функций используются методы:
1. void DBAAlghoritm(int x1, int x2, int y1, int y2);
2. void BresenhamAlghoritm(int x1, int x2, int y1, int y2);
3. void BresenhamCircleAlghoritm(int xc, int yc, int r);
4. void StepByStepAlghoritm(int x1, int x2, int y1, int y2);

Исходный код функции алгоритма ЦДА:
~~~ 
    ui->plot->clearGraphs();
    int length = std::max(std::abs(x2 - x1), std::abs(y2 - y1));
    QVector<double> xs, ys;
    double dx = (x2 - x1) / length;
    double dy = (y2 - y1) / length;
    double x = x1 + 0.5 * std::signbit(dx);
    double y = y1 + 0.5 * std::signbit(dy);
    xs.append(x);
    ys.append(y);
    for (int i = 1; i < length; i++){
        x += dx;
        y += dy;
        xs.append(x);
        ys.append(y);
    }
    ui->plot->addGraph();
    ui->plot->graph(0)->setData(xs, ys);
    ui->plot->graph(0)->setPen(QColor(50, 50, 50, 255));
    ui->plot->graph(0)->setScatterStyle(QCPScatterStyle(QCPScatterStyle::ssCircle, 4));

~~~

***

Вся разметка и дизайн формируется в конструкторе класса MainWindow

