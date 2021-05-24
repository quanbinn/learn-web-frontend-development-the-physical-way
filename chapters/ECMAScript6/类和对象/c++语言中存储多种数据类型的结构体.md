# c++语言中存储多种数据类型的结构体

单击右方的[在线代码段Url网址](http://www.pythontutor.com/cpp.html#code=%23include%20%3Ciostream%3E%0A%23include%20%3Ccstring%3E%0A%20%0Ausing%20namespace%20std%3B%0A%20%0Astruct%20Books%20%7B%0A%20%20%20char%20%20title%5B50%5D%3B%0A%20%20%20char%20%20author%5B50%5D%3B%0A%20%20%20char%20%20subject%5B100%5D%3B%0A%20%20%20int%20%20%20book_id%3B%0A%7D%3B%0A%20%0Aint%20main%28%29%20%7B%0A%20%20%20struct%20Books%20Book1%3B%20%20%20%20%20%20%20%20//%20Declare%20Book1%20of%20type%20Book%0A%20%20%20struct%20Books%20Book2%3B%20%20%20%20%20%20%20%20//%20Declare%20Book2%20of%20type%20Book%0A%20%0A%20%20%20//%20book%201%20specification%0A%20%20%20strcpy%28%20Book1.title,%20%22Learn%20C%2B%2B%20Programming%22%29%3B%0A%20%20%20strcpy%28%20Book1.author,%20%22Chand%20Miyan%22%29%3B%20%0A%20%20%20strcpy%28%20Book1.subject,%20%22C%2B%2B%20Programming%22%29%3B%0A%20%20%20Book1.book_id%20%3D%206495407%3B%0A%0A%20%20%20//%20book%202%20specification%0A%20%20%20strcpy%28%20Book2.title,%20%22Telecom%20Billing%22%29%3B%0A%20%20%20strcpy%28%20Book2.author,%20%22Yakit%20Singha%22%29%3B%0A%20%20%20strcpy%28%20Book2.subject,%20%22Telecom%22%29%3B%0A%20%20%20Book2.book_id%20%3D%206495700%3B%0A%20%0A%20%20%20//%20Print%20Book1%20info%0A%20%20%20cout%20%3C%3C%20%22Book%201%20title%20%3A%20%22%20%3C%3C%20Book1.title%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%201%20author%20%3A%20%22%20%3C%3C%20Book1.author%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%201%20subject%20%3A%20%22%20%3C%3C%20Book1.subject%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%201%20id%20%3A%20%22%20%3C%3C%20Book1.book_id%20%3C%3Cendl%3B%0A%0A%20%20%20//%20Print%20Book2%20info%0A%20%20%20cout%20%3C%3C%20%22Book%202%20title%20%3A%20%22%20%3C%3C%20Book2.title%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%202%20author%20%3A%20%22%20%3C%3C%20Book2.author%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%202%20subject%20%3A%20%22%20%3C%3C%20Book2.subject%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%202%20id%20%3A%20%22%20%3C%3C%20Book2.book_id%20%3C%3Cendl%3B%0A%0A%20%20%20return%200%3B%0A%7D&mode=edit&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D)，浏览器里会打开一个新的页面，里面有下面的代码段。

```c++
#include <iostream>
#include <cstring>
 
using namespace std;
 
struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main() {
   struct Books Book1;        // Declare Book1 of type Book
   struct Books Book2;        // Declare Book2 of type Book
 
   // book 1 specification
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // book 2 specification
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // Print Book1 info
   cout << "Book 1 title : " << Book1.title <<endl;
   cout << "Book 1 author : " << Book1.author <<endl;
   cout << "Book 1 subject : " << Book1.subject <<endl;
   cout << "Book 1 id : " << Book1.book_id <<endl;

   // Print Book2 info
   cout << "Book 2 title : " << Book2.title <<endl;
   cout << "Book 2 author : " << Book2.author <<endl;
   cout << "Book 2 subject : " << Book2.subject <<endl;
   cout << "Book 2 id : " << Book2.book_id <<endl;

   return 0;
}
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/cpp.html#code=%23include%20%3Ciostream%3E%0A%23include%20%3Ccstring%3E%0A%20%0Ausing%20namespace%20std%3B%0Avoid%20printBook%28%20struct%20Books%20book%20%29%3B%0A%0Astruct%20Books%20%7B%0A%20%20%20char%20%20title%5B50%5D%3B%0A%20%20%20char%20%20author%5B50%5D%3B%0A%20%20%20char%20%20subject%5B100%5D%3B%0A%20%20%20int%20%20%20book_id%3B%0A%7D%3B%0A%20%0Aint%20main%28%29%20%7B%0A%20%20%20struct%20Books%20Book1%3B%20%20%20%20%20%20%20%20//%20Declare%20Book1%20of%20type%20Book%0A%20%20%20struct%20Books%20Book2%3B%20%20%20%20%20%20%20%20//%20Declare%20Book2%20of%20type%20Book%0A%20%0A%20%20%20//%20book%201%20specification%0A%20%20%20strcpy%28%20Book1.title,%20%22Learn%20C%2B%2B%20Programming%22%29%3B%0A%20%20%20strcpy%28%20Book1.author,%20%22Chand%20Miyan%22%29%3B%20%0A%20%20%20strcpy%28%20Book1.subject,%20%22C%2B%2B%20Programming%22%29%3B%0A%20%20%20Book1.book_id%20%3D%206495407%3B%0A%0A%20%20%20//%20book%202%20specification%0A%20%20%20strcpy%28%20Book2.title,%20%22Telecom%20Billing%22%29%3B%0A%20%20%20strcpy%28%20Book2.author,%20%22Yakit%20Singha%22%29%3B%0A%20%20%20strcpy%28%20Book2.subject,%20%22Telecom%22%29%3B%0A%20%20%20Book2.book_id%20%3D%206495700%3B%0A%20%0A%20%20%20//%20Print%20Book1%20info%0A%20%20%20printBook%28%20Book1%20%29%3B%0A%0A%20%20%20//%20Print%20Book2%20info%0A%20%20%20printBook%28%20Book2%20%29%3B%0A%0A%20%20%20return%200%3B%0A%7D%0Avoid%20printBook%28%20struct%20Books%20book%20%29%20%7B%0A%20%20%20cout%20%3C%3C%20%22Book%20title%20%3A%20%22%20%3C%3C%20book.title%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%20author%20%3A%20%22%20%3C%3C%20book.author%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%20subject%20%3A%20%22%20%3C%3C%20book.subject%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%20id%20%3A%20%22%20%3C%3C%20book.book_id%20%3C%3Cendl%3B%0A%7D&mode=edit&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D)，浏览器里会打开一个新的页面，里面有下面的代码段。

```c++
#include <iostream>
#include <cstring>
 
using namespace std;
void printBook( struct Books book );

struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
 
int main() {
   struct Books Book1;        // Declare Book1 of type Book
   struct Books Book2;        // Declare Book2 of type Book
 
   // book 1 specification
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // book 2 specification
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // Print Book1 info
   printBook( Book1 );

   // Print Book2 info
   printBook( Book2 );

   return 0;
}
void printBook( struct Books book ) {
   cout << "Book title : " << book.title <<endl;
   cout << "Book author : " << book.author <<endl;
   cout << "Book subject : " << book.subject <<endl;
   cout << "Book id : " << book.book_id <<endl;
}
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/cpp.html#code=%23include%20%3Ciostream%3E%0A%23include%20%3Ccstring%3E%0A%20%0Ausing%20namespace%20std%3B%0Avoid%20printBook%28%20struct%20Books%20*book%20%29%3B%0A%0Astruct%20Books%20%7B%0A%20%20%20char%20%20title%5B50%5D%3B%0A%20%20%20char%20%20author%5B50%5D%3B%0A%20%20%20char%20%20subject%5B100%5D%3B%0A%20%20%20int%20%20%20book_id%3B%0A%7D%3B%0Aint%20main%28%29%20%7B%0A%20%20%20struct%20Books%20Book1%3B%20%20%20%20%20%20%20%20//%20Declare%20Book1%20of%20type%20Book%0A%20%20%20struct%20Books%20Book2%3B%20%20%20%20%20%20%20%20//%20Declare%20Book2%20of%20type%20Book%0A%20%0A%20%20%20//%20Book%201%20specification%0A%20%20%20strcpy%28%20Book1.title,%20%22Learn%20C%2B%2B%20Programming%22%29%3B%0A%20%20%20strcpy%28%20Book1.author,%20%22Chand%20Miyan%22%29%3B%20%0A%20%20%20strcpy%28%20Book1.subject,%20%22C%2B%2B%20Programming%22%29%3B%0A%20%20%20Book1.book_id%20%3D%206495407%3B%0A%0A%20%20%20//%20Book%202%20specification%0A%20%20%20strcpy%28%20Book2.title,%20%22Telecom%20Billing%22%29%3B%0A%20%20%20strcpy%28%20Book2.author,%20%22Yakit%20Singha%22%29%3B%0A%20%20%20strcpy%28%20Book2.subject,%20%22Telecom%22%29%3B%0A%20%20%20Book2.book_id%20%3D%206495700%3B%0A%20%0A%20%20%20//%20Print%20Book1%20info,%20passing%20address%20of%20structure%0A%20%20%20printBook%28%20%26Book1%20%29%3B%0A%0A%20%20%20//%20Print%20Book1%20info,%20passing%20address%20of%20structure%0A%20%20%20printBook%28%20%26Book2%20%29%3B%0A%0A%20%20%20return%200%3B%0A%7D%0A%0A//%20This%20function%20accept%20pointer%20to%20structure%20as%20parameter.%0Avoid%20printBook%28%20struct%20Books%20*book%20%29%20%7B%0A%20%20%20cout%20%3C%3C%20%22Book%20title%20%3A%20%22%20%3C%3C%20book-%3Etitle%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%20author%20%3A%20%22%20%3C%3C%20book-%3Eauthor%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%20subject%20%3A%20%22%20%3C%3C%20book-%3Esubject%20%3C%3Cendl%3B%0A%20%20%20cout%20%3C%3C%20%22Book%20id%20%3A%20%22%20%3C%3C%20book-%3Ebook_id%20%3C%3Cendl%3B%0A%7D&mode=edit&origin=opt-frontend.js&py=cpp_g%2B%2B9.3.0&rawInputLstJSON=%5B%5D)，浏览器里会打开一个新的页面，里面有下面的代码段。

```c++
#include <iostream>
#include <cstring>
 
using namespace std;
void printBook( struct Books *book );

struct Books {
   char  title[50];
   char  author[50];
   char  subject[100];
   int   book_id;
};
int main() {
   struct Books Book1;        // Declare Book1 of type Book
   struct Books Book2;        // Declare Book2 of type Book
 
   // Book 1 specification
   strcpy( Book1.title, "Learn C++ Programming");
   strcpy( Book1.author, "Chand Miyan"); 
   strcpy( Book1.subject, "C++ Programming");
   Book1.book_id = 6495407;

   // Book 2 specification
   strcpy( Book2.title, "Telecom Billing");
   strcpy( Book2.author, "Yakit Singha");
   strcpy( Book2.subject, "Telecom");
   Book2.book_id = 6495700;
 
   // Print Book1 info, passing address of structure
   printBook( &Book1 );

   // Print Book1 info, passing address of structure
   printBook( &Book2 );

   return 0;
}

// This function accept pointer to structure as parameter.
void printBook( struct Books *book ) {
   cout << "Book title : " << book->title <<endl;
   cout << "Book author : " << book->author <<endl;
   cout << "Book subject : " << book->subject <<endl;
   cout << "Book id : " << book->book_id <<endl;
}
```

## 参考文献及资料

1. [**C++ Data Structures**](https://www.tutorialspoint.com/cplusplus/cpp_data_structures.htm)



