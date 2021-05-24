# c语言中存储多种数据类型的结构体

单击右方的[在线代码段Url网址](http://www.pythontutor.com/c.html#code=%23include%20%3Cstdio.h%3E%0A%23include%20%3Cstring.h%3E%0A%20%0Astruct%20Books%20%7B%0A%20%20%20char%20%20title%5B50%5D%3B%0A%20%20%20char%20%20author%5B50%5D%3B%0A%20%20%20char%20%20subject%5B100%5D%3B%0A%20%20%20int%20%20%20book_id%3B%0A%7D%3B%0A%20%0Aint%20main%28%20%29%20%7B%0A%0A%20%20%20struct%20Books%20Book1%3B%20%20%20%20%20%20%20%20/*%20Declare%20Book1%20of%20type%20Book%20*/%0A%20%20%20struct%20Books%20Book2%3B%20%20%20%20%20%20%20%20/*%20Declare%20Book2%20of%20type%20Book%20*/%0A%20%0A%20%20%20/*%20book%201%20specification%20*/%0A%20%20%20strcpy%28%20Book1.title,%20%22C%20Programming%22%29%3B%0A%20%20%20strcpy%28%20Book1.author,%20%22Nuha%20Ali%22%29%3B%20%0A%20%20%20strcpy%28%20Book1.subject,%20%22C%20Programming%20Tutorial%22%29%3B%0A%20%20%20Book1.book_id%20%3D%206495407%3B%0A%0A%20%20%20/*%20book%202%20specification%20*/%0A%20%20%20strcpy%28%20Book2.title,%20%22Telecom%20Billing%22%29%3B%0A%20%20%20strcpy%28%20Book2.author,%20%22Zara%20Ali%22%29%3B%0A%20%20%20strcpy%28%20Book2.subject,%20%22Telecom%20Billing%20Tutorial%22%29%3B%0A%20%20%20Book2.book_id%20%3D%206495700%3B%0A%20%0A%20%20%20/*%20print%20Book1%20info%20*/%0A%20%20%20printf%28%20%22Book%201%20title%20%3A%20%25s%5Cn%22,%20Book1.title%29%3B%0A%20%20%20printf%28%20%22Book%201%20author%20%3A%20%25s%5Cn%22,%20Book1.author%29%3B%0A%20%20%20printf%28%20%22Book%201%20subject%20%3A%20%25s%5Cn%22,%20Book1.subject%29%3B%0A%20%20%20printf%28%20%22Book%201%20book_id%20%3A%20%25d%5Cn%22,%20Book1.book_id%29%3B%0A%0A%20%20%20/*%20print%20Book2%20info%20*/%0A%20%20%20printf%28%20%22Book%202%20title%20%3A%20%25s%5Cn%22,%20Book2.title%29%3B%0A%20%20%20printf%28%20%22Book%202%20author%20%3A%20%25s%5Cn%22,%20Book2.author%29%3B%0A%20%20%20printf%28%20%22Book%202%20subject%20%3A%20%25s%5Cn%22,%20Book2.subject%29%3B%0A%20%20%20printf%28%20%22Book%202%20book_id%20%3A%20%25d%5Cn%22,%20Book2.book_id%29%3B%0A%0A%20%20%20return%200%3B%0A%7D&curInstr=19&mode=display&origin=opt-frontend.js&py=c_gcc9.3.0&rawInputLstJSON=%5B%5D)，浏览器里会打开一个新的页面，里面有下面的代码段。

```c
#include <stdio.h>
#include <string.h>
 
struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main( ) {

   struct Books Book1;        /* Declare Book1 of type Book */
   struct Books Book2;        /* Declare Book2 of type Book */
 
   /* book 1 specification */
   strcpy( Book1.title, "C Programming");
   strcpy( Book1.author, "Nuha Ali"); 
   strcpy( Book1.subject, "C Programming Tutorial");
   Book1.book_id = 6495407;

   /* book 2 specification */
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Zara Ali");
   strcpy( Book2.subject, "Telecom Billing Tutorial");
   Book2.book_id = 6495700;
 
   /* print Book1 info */
   printf( "Book 1 title : %s\n", Book1.title);
   printf( "Book 1 author : %s\n", Book1.author);
   printf( "Book 1 subject : %s\n", Book1.subject);
   printf( "Book 1 book_id : %d\n", Book1.book_id);

   /* print Book2 info */
   printf( "Book 2 title : %s\n", Book2.title);
   printf( "Book 2 author : %s\n", Book2.author);
   printf( "Book 2 subject : %s\n", Book2.subject);
   printf( "Book 2 book_id : %d\n", Book2.book_id);

   return 0;
}
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/c.html#code=%23include%20%3Cstdio.h%3E%0A%23include%20%3Cstring.h%3E%0A%20%0Astruct%20Books%20%7B%0A%20%20%20char%20%20title%5B50%5D%3B%0A%20%20%20char%20%20author%5B50%5D%3B%0A%20%20%20char%20%20subject%5B100%5D%3B%0A%20%20%20int%20%20%20book_id%3B%0A%7D%3B%0A%0A/*%20function%20declaration%20*/%0Avoid%20printBook%28%20struct%20Books%20book%20%29%3B%0A%0Aint%20main%28%20%29%20%7B%0A%0A%20%20%20struct%20Books%20Book1%3B%20%20%20%20%20%20%20%20/*%20Declare%20Book1%20of%20type%20Book%20*/%0A%20%20%20struct%20Books%20Book2%3B%20%20%20%20%20%20%20%20/*%20Declare%20Book2%20of%20type%20Book%20*/%0A%20%0A%20%20%20/*%20book%201%20specification%20*/%0A%20%20%20strcpy%28%20Book1.title,%20%22C%20Programming%22%29%3B%0A%20%20%20strcpy%28%20Book1.author,%20%22Nuha%20Ali%22%29%3B%20%0A%20%20%20strcpy%28%20Book1.subject,%20%22C%20Programming%20Tutorial%22%29%3B%0A%20%20%20Book1.book_id%20%3D%206495407%3B%0A%0A%20%20%20/*%20book%202%20specification%20*/%0A%20%20%20strcpy%28%20Book2.title,%20%22Telecom%20Billing%22%29%3B%0A%20%20%20strcpy%28%20Book2.author,%20%22Zara%20Ali%22%29%3B%0A%20%20%20strcpy%28%20Book2.subject,%20%22Telecom%20Billing%20Tutorial%22%29%3B%0A%20%20%20Book2.book_id%20%3D%206495700%3B%0A%20%0A%20%20%20/*%20print%20Book1%20info%20*/%0A%20%20%20printBook%28%20Book1%20%29%3B%0A%0A%20%20%20/*%20Print%20Book2%20info%20*/%0A%20%20%20printBook%28%20Book2%20%29%3B%0A%0A%20%20%20return%200%3B%0A%7D%0A%0Avoid%20printBook%28%20struct%20Books%20book%20%29%20%7B%0A%0A%20%20%20printf%28%20%22Book%20title%20%3A%20%25s%5Cn%22,%20book.title%29%3B%0A%20%20%20printf%28%20%22Book%20author%20%3A%20%25s%5Cn%22,%20book.author%29%3B%0A%20%20%20printf%28%20%22Book%20subject%20%3A%20%25s%5Cn%22,%20book.subject%29%3B%0A%20%20%20printf%28%20%22Book%20book_id%20%3A%20%25d%5Cn%22,%20book.book_id%29%3B%0A%7D&mode=edit&origin=opt-frontend.js&py=c_gcc9.3.0&rawInputLstJSON=%5B%5D)，浏览器里会打开一个新的页面，里面有下面的代码段。

```c
#include <stdio.h>
#include <string.h>
 
struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};

/* function declaration */
void printBook( struct Books book );

int main( ) {

   struct Books Book1;        /* Declare Book1 of type Book */
   struct Books Book2;        /* Declare Book2 of type Book */
 
   /* book 1 specification */
   strcpy( Book1.title, "C Programming");
   strcpy( Book1.author, "Nuha Ali"); 
   strcpy( Book1.subject, "C Programming Tutorial");
   Book1.book_id = 6495407;

   /* book 2 specification */
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Zara Ali");
   strcpy( Book2.subject, "Telecom Billing Tutorial");
   Book2.book_id = 6495700;
 
   /* print Book1 info */
   printBook( Book1 );

   /* Print Book2 info */
   printBook( Book2 );

   return 0;
}

void printBook( struct Books book ) {

   printf( "Book title : %s\n", book.title);
   printf( "Book author : %s\n", book.author);
   printf( "Book subject : %s\n", book.subject);
   printf( "Book book_id : %d\n", book.book_id);
}
```

## 参考文献及资料

1. [**C - Structures**](https://www.tutorialspoint.com/cprogramming/c_structures.htm)



