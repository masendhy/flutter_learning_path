- **Menggunakan Navigator.push pada InkWell**

* Buat file main.dart, main-page.dart dan detail_page.dart

- Modifikasi file main.dart, jangan lupa menggunakan return berupa context (misal : MaterialApp) -> arahkan home : menuju ke path yang akan dibuka pertama kali.
  > main.dart

```zsh
import 'package:flutter/material.dart';
import 'package:flutter_widget/pages/detail_page.dart';
import 'package:flutter_widget/pages/main-page.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  //const MyApp({super.key});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: MainPage(),
    );
  }
}
```

- Guanakan InkWell dengan onTap untuk menjalankan method Navigator.push.

> main-page.dart

```zsh
import 'package:flutter/material.dart';
import 'package:flutter_widget/pages/detail_page.dart';

class MainPage extends StatelessWidget {
  // const MainPage({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
          child: InkWell(
            onTap: () => Navigator.push(
                context, MaterialPageRoute(builder: (context) => DetailPage())),
            child: Image.asset('images/pexels-jessica.jpg'),
          ),
        ),
      ),
    );
  }
}
```

- pada file _main-page.dart_ diatas, dibuat sebuah image yng berada ditengah, apabila image tersebut di click akan masuk ke halaman detail_page.dart

* file detail_page.dart hanya berisi Text('Detail Page')
