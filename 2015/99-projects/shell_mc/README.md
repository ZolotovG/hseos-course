# Работа с библиотекой NCURSES
## Установка библиотеки NCURSES
```
sudo apt-get install libncurses5-dev
```
Компилиция
```
   #include <ncurses.h>
   ....
   gcc <program file> -lncurses
```

## Фукнции ввода

1. getch() - Функция возвращает введенный символ
2. scanw() - Форматированный ввод
3. getstr() - Функция возвращает введнную строку

## Фукнции вывода

1. addch() - Печать символа с учетом атрибутов
2. printw()- Печать строки в stdscr. Аналогично printf()
3. addstr() - Печать строки

Пример 1.
```
#include <ncurses.h>

int main()
{	
	initscr();			/* Инициализация использования библиотеки NCURSES  */
	printw("Hello World");	/* Вывод на печать в буфер активного окна stdscr Hello World		  */
	refresh();			/* Вывод на печать в окно stdscr */
	getch();			/* Ожидание ввода символа */
	endwin();			/* Завершения использования библиотеки 	NCURSES */
	

	return 0;
}
```

Пример 2.
```

#include <ncurses.h>			/* ncurses.h включает stdio.h */  
#include <string.h> 
 
int main()
{
 char mesg[]="Enter a string: ";		
 char str[80];
 int row,col;				/* переменные для хранения строк и столбцов */
 initscr();				/* инициализация */
 getmaxyx(stdscr,row,col);		/* получение количества строки и столбцов */
 mvprintw(row/2,(col-strlen(mesg))/2,"%s",mesg); /* печать сообщения на середине экрана */
 getstr(str);
 mvprintw(LINES - 2, 0, "You Entered: %s", str);
 getch();
 endwin();

 return 0;
}
```

 
## Ссылки

	1. ftp://ftp.gnu.org/gnu/ncurses/ 
	2. https://www.gnu.org/software/ncurses/
	3. http://invisible-island.net/ncurses/ncurses-intro.html#introduction
	4. http://www.tldp.org/HOWTO/NCURSES-Programming-HOWTO/
	5. http://www.c-for-dummies.com/ncurses/
