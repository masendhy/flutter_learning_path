- **Membuat lebar image sama dengan lebar layarnya :**

  ```zsh
   width:MediaQuery.of(context).size.width
  ```

* **Navigator.pop(context) : digunakan untuk membuat fungsi button back ke halaman sebelumnya**

* **Memberikan border radius pada container bagian atas**

```zsh
  decoration:BoxDecoration(borderRadius:BorderRadius.vertical(
  top:Radius.circular(20),
  ))
```

- **Memberikan border radius pada image :**

```zsh
   ClipRRect(
   borderRadius: BorderRadius.circular(8.0),
   child: Image.network(
   subject['images']['large'],
   height: 150.0,
   width: 100.0,
   ),
   )
```

- **Memberikan border radius pada Container :**

```zsh
 decoration: BoxDecoration(
 borderRadius: BorderRadius.circular(10),
```

- **Memberikan color pada ElevatedButton :**

```zsh
   child: ElevatedButton(
   child: Text('Pesan Sekarang'),
   onPressed: () {},
   style: ElevatedButton.styleFrom(backgroundColor: redColor,)
```

- **Memberikan border radius pada ElevatedButton :**

```zsh
   shape: RoundedRectangleBorder(
   borderRadius: BorderRadius.circular(10),
```

- **Membuat route kembali ke halaman tertentu**

```zsh
   onPressed: () {
   Navigator.pushAndRemoveUntil(
   context,
   MaterialPageRoute(builder: (context) => HomePage()),
   (route) => false);
   },
```

- **Membuat background image**

```zsh
 body: Stack(
 children: [

 Container(
 width: double.infinity,
 height: double.infinity,
 decoration: BoxDecoration(
 image: DecorationImage(image: AssetImage('assets/plane.jpg'))),
 )
 ],
 ),

```

- **Membuat perpindahan dari splash_page ke get_started_page secara otomatis**

```zsh
 @override
 void initState() {
 // TODO: implement setState
 Timer(Duration(seconds: 3), () {
 Navigator.push(
 context, MaterialPageRoute(builder: (context) => GetStarted()));
 });
 super.initState();
 }

atau dapat juga dengan menggunakan _pushNamed_

1.  Pada main.dart buat routes untuk menggantikan home nya

 routes: {
 '/': (context) => SplashPage(),
 '/get-started': (context) => GetStarted(),
 },

```

2.  Ubah code _Navigator_ nya menjadi :

```zsh
    > @override
    > void initState() {
    > // TODO: implement setState
    > Timer(Duration(seconds: 3), () {
    >
    >      Navigator.pushNamed(context, '/get-started');
    >
    > });
    > super.initState();
    > }
```

- **Membuat form Input**

```zsh
TextFormField(
  // memberikan warna pada cursor :
              cursorColor: blackColor,
  // memberikan placeholder text
              decoration: InputDecoration(
                  hintText: 'your full name',
  // memberikan animasi warna saat entry form :
                  border: OutlineInputBorder(
                      borderRadius: BorderRadius.circular(defaultRadius)),
  // membuat text yang entry menjadi tidak terlihat(biasanya untuk pengamanan saat meng entry password)
                  obscureText: true,
  // memberikan borderRadius pada form input
                  focusedBorder: OutlineInputBorder(
                      borderRadius: BorderRadius.circular(defaultRadius),
                      borderSide: BorderSide(color: blackColor))),
            )
```

- **Memberikan garis bawah pada text :**

```zsh
child: Text(
          'Term and Conditions',
          style: greyTextStyle.copyWith(
              fontSize: 16, decoration: TextDecoration.underline),
        ),
```

- **Memberikan boxSHadow pada container**

```zsh
return Container(
        width: 300,
        height: 211,
        padding: EdgeInsets.all(defaultMargin),
        decoration: BoxDecoration(
            borderRadius: BorderRadius.circular(defaultRadius),
            boxShadow: [
              BoxShadow(
                color: blackColor.withOpacity(0.5),
                spreadRadius: 5,
                blurRadius: 7,
                offset: Offset(0, 3), // changes position of shadow
              ),
            ],
            color: blackColor),
      );
```

- **Menggunakan _Expanded_ untuk memberikan jarak dengan cara mengisi ruang yang kosong, serta menggunakan _overflow_ untuk memberikan tanda ... untuk mengatasi field yang terlalu panjang**

```zsh
Expanded(
                    child: Column(
                      crossAxisAlignment: CrossAxisAlignment.start,
                      children: [
                        Text('Name',
                            style: whiteTextStyle.copyWith(
                                fontSize: 15,
                                fontWeight: FontWeight.w100,
                                overflow: TextOverflow.ellipsis)),
                        Text(
                          'John Due',
                          style: whiteTextStyle.copyWith(
                              fontSize: 20, fontWeight: FontWeight.bold),
                        )
                      ],
                    ),
                  ),
```

- **Membuat default button**

1. Buat halaman untuk default button nya :

```zsh
import 'package:flutter/material.dart';
import 'package:piknik/shared/theme.dart';

class CustomButton extends StatelessWidget {

  // Buat variable dan constructor nya
  final Widget? iconUrl;

  const CustomButton({this.iconUrl});

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.spaceBetween,
      children: [
        SizedBox(),
        Container(width: 24, height: 24, child: iconUrl),
        Container(
          margin: EdgeInsets.only(left: 10),
          width: 30,
          height: 2,
          decoration: BoxDecoration(
              color: blackColor,
              borderRadius: BorderRadius.circular(defaultRadius)),
        ),
      ],
    );
  }
}

```

2. Panggil _iconUrl_ nya dan modifikasi, gunakan di halaman yang membutuhkan customButton nya

```zsh
CustomButton(
              iconUrl: Align(
                  child: Icon(
                Icons.settings,
                size: 33,
                color: greyColor,
              )),
            )
```

- \*\*Membuat button active dan non active dengan isSelected

1. Buat variable dan constructor pada halaman buttonCustom

```zsh
final Widget? iconUrl;
  final bool isSelected;

  const CustomButton({this.iconUrl, this.isSelected = false});
```

2. Gunakan ternary operator untuk menjalankan isSelected

```zsh
decoration: BoxDecoration(
              color: isSelected ? blackColor : Colors.transparent,
              borderRadius: BorderRadius.circular(defaultRadius)),
```

- **Menggunakan image dan merubah bentuknya menjadi lingkaran**

```zsh
Container(
              width: 75,
              height: 150,
              decoration: BoxDecoration(
                  shape: BoxShape.circle,
                  image:
                      DecorationImage(image: AssetImage('assets/profile.jpg'))),
            )
```

- **Expanded** digunakan untuk memberikan jarak yang sama pada column,unutk menghindari overflow.

* **overflow** untuk menyelesaikan permasalahan _overflow_ gunakan

```zsh
overfflow : TextOverFlow.ellipsis
```

sehingga akan menampilkan sebaian text dan menambahkan ... sebagai tanda tex panjang.

- **Memberikan icon button pada appBar**

```zsh
actions: [
              IconButton(
                  onPressed: () {},
                  icon: const Icon(
                    Icons.home,
                    color: Colors.black,
                  ))
            ],
```

- **Menggunakan _fit:BoxFit.cover_ untuk membuat border radius pada image agar porposional**

```zsh
Container(
          width: 70,
          height: 70,
          decoration: BoxDecoration(
              borderRadius: BorderRadius.circular(defaultRadius),
              image: DecorationImage(
                  fit: BoxFit.cover, image: AssetImage('assets/ntt.jpg'))),
        ),
```
